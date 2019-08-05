---
title: Microsoft 팀 클라이언트에서 서비스 품질 구현
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Microsoft 팀 클라이언트에 대 한 서비스 품질 (QoS)을 구현 합니다.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 101deb10cf3d86dbc97116cad269556683d03be4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "36180444"
---
# <a name="set-qos-on-windows-clients"></a><span data-ttu-id="2f974-103">Windows 클라이언트에서 QoS 설정</span><span class="sxs-lookup"><span data-stu-id="2f974-103">Set QoS on Windows clients</span></span>

<span data-ttu-id="2f974-104">그룹 정책 내에서 정책 기반 QoS를 사용 하 여 팀 클라이언트에서 미리 정의 된 DSCP 값에 대 한 원본 포트 범위를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-104">You can use policy-based QoS within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="2f974-105">다음 표에 지정 된 포트 범위는 각 작업 부하에 대 한 정책을 만들기 위한 출발점입니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="2f974-106">_권장 되는 초기 포트 범위_</span><span class="sxs-lookup"><span data-stu-id="2f974-106">_Recommended initial port ranges_</span></span>

<span data-ttu-id="2f974-107">미디어 트래픽 형식</span><span class="sxs-lookup"><span data-stu-id="2f974-107">Media traffic type</span></span>| <span data-ttu-id="2f974-108">클라이언트 원본 포트 범위</span><span class="sxs-lookup"><span data-stu-id="2f974-108">Client source port range</span></span> |<span data-ttu-id="2f974-109">프로토콜별</span><span class="sxs-lookup"><span data-stu-id="2f974-109">Protocol</span></span>|<span data-ttu-id="2f974-110">DSCP 값</span><span class="sxs-lookup"><span data-stu-id="2f974-110">DSCP value</span></span>|<span data-ttu-id="2f974-111">DSCP 클래스</span><span class="sxs-lookup"><span data-stu-id="2f974-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="2f974-112">오디오</span><span class="sxs-lookup"><span data-stu-id="2f974-112">Audio</span></span>| <span data-ttu-id="2f974-113">50000 – 50019</span><span class="sxs-lookup"><span data-stu-id="2f974-113">50,000–50,019</span></span>|<span data-ttu-id="2f974-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="2f974-114">TCP/UDP</span></span>|<span data-ttu-id="2f974-115">46</span><span class="sxs-lookup"><span data-stu-id="2f974-115">46</span></span>|<span data-ttu-id="2f974-116">전달 발송 (EF)</span><span class="sxs-lookup"><span data-stu-id="2f974-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="2f974-117">비디오만</span><span class="sxs-lookup"><span data-stu-id="2f974-117">Video</span></span>| <span data-ttu-id="2f974-118">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="2f974-118">50,020–50,039</span></span>|<span data-ttu-id="2f974-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="2f974-119">TCP/UDP</span></span>|<span data-ttu-id="2f974-120">34</span><span class="sxs-lookup"><span data-stu-id="2f974-120">34</span></span>|<span data-ttu-id="2f974-121">전달 보장 (AF41)</span><span class="sxs-lookup"><span data-stu-id="2f974-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="2f974-122">응용 프로그램/화면 공유</span><span class="sxs-lookup"><span data-stu-id="2f974-122">Application/Screen Sharing</span></span>| <span data-ttu-id="2f974-123">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="2f974-123">50,040–50,059</span></span>|<span data-ttu-id="2f974-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="2f974-124">TCP/UDP</span></span>|<span data-ttu-id="2f974-125">awg</span><span class="sxs-lookup"><span data-stu-id="2f974-125">18</span></span>|<span data-ttu-id="2f974-126">전달 보장 (AF21)</span><span class="sxs-lookup"><span data-stu-id="2f974-126">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="2f974-127">가능 하면 그룹 정책 개체 내에서 정책 기반 QoS 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="2f974-128">다음 단계는 [비즈니스용 Skype Server에서 클라이언트에 대 한 포트 범위와 서비스 품질 정책을 구성](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)하는 것과 매우 유사 하며, 필요 하지 않을 수도 있는 추가 세부 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="2f974-129">도메인에 가입한 Windows 10 컴퓨터에 대해 QoS 오디오 정책을 만들려면 먼저 그룹 정책 관리가 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="2f974-130">그룹 정책 관리 (시작을 클릭 하 고 관리 도구를 가리킨 다음 그룹 정책 관리 클릭)를 열고 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="2f974-131">그룹 정책 관리에서 새 정책을 만들 컨테이너를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="2f974-132">예를 들어 모든 클라이언트 컴퓨터가 **클라이언트**라는 OU에 있는 경우 클라이언트 ou에서 새 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Client OU.</span></span>

2. <span data-ttu-id="2f974-133">적절 한 컨테이너를 마우스 오른쪽 단추로 클릭 한 다음 **이 도메인에서 GPO 만들기를 클릭 하 고 여기에 연결**합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3. <span data-ttu-id="2f974-134">**새 GPO** 대화 상자의 **이름** 상자에 새 그룹 정책 개체의 이름을 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4. <span data-ttu-id="2f974-135">새로 만든 정책을 마우스 오른쪽 단추로 클릭 한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-135">Right-click the newly created policy, and then click **Edit**.</span></span>

5. <span data-ttu-id="2f974-136">그룹 정책 관리 편집기에서 **컴퓨터 구성**, **Windows 설정을**차례로 확장 하 고 **정책 기반 QoS**를 마우스 오른쪽 단추로 클릭 한 다음 **새 정책 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6. <span data-ttu-id="2f974-137">**정책 기반 QoS** 대화 상자의 열기 페이지에 있는 **이름** 상자에 새 정책의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="2f974-138">**DSCP 값 지정** 을 선택 하 고 값을 **46**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="2f974-139">**아웃 바운드 스로틀 속도 지정** 을 선택 하지 않은 상태로 두고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="2f974-140">다음 페이지에서 **이 실행 파일 이름의 응용** 프로그램만 선택 하 고 **다음**을 클릭 하 \*\*\*\* 여 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="2f974-141">이 설정은 팀 클라이언트에서 일치 하는 트래픽에만 우선 순위를 지정 하도록 정책에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

8. <span data-ttu-id="2f974-142">세 번째 페이지에서 **원본 ip 주소** 와 **대상 ip 주소가** 모두 선택 되어 있는지 확인 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="2f974-143">이러한 두 가지 설정은 패킷을 보낸 컴퓨터 (IP 주소)와 패킷을 받을 컴퓨터 (IP 주소)에 관계 없이 패킷이 관리 됨을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

9. <span data-ttu-id="2f974-144">4 페이지에서 **이 QoS 정책이 적용 되는 프로토콜 선택** 드롭다운 목록에서 **TCP 및 UDP** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="2f974-145">TCP (전송 제어 프로토콜) 및 UDP (사용자 데이터 그램 프로토콜)는 가장 일반적으로 사용 되는 두 가지 네트워킹 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

10. <span data-ttu-id="2f974-146">**원본 포트 번호를 지정 하는**제목 아래에서 **이 원본 포트 또는 범위를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="2f974-147">해당 텍스트 상자에 오디오 전송용으로 예약 된 포트 범위를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="2f974-148">예를 들어 오디오 트래픽용 포트 50019를 통해 포트 5만를 예약한 경우이 형식을 사용 하 여 포트 범위를 입력 합니다 ( **50000:50019**).</span><span class="sxs-lookup"><span data-stu-id="2f974-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="2f974-149">**마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-149">Click **Finish**.</span></span>

11. <span data-ttu-id="2f974-150">6 ~ 10 단계의 적절 한 값으로 대체 하 여 비디오 및 응용 프로그램/데스크톱 공유에 대 한 정책을 만들려면 5-10 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="2f974-151">만든 새 정책은 클라이언트 컴퓨터에서 그룹 정책이 새로 고쳐질 때까지 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-151">The new policies you’ve created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="2f974-152">그룹 정책은 주기적으로 자체적으로 새로 고쳐지고, 다음 단계에 따라 즉시 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="2f974-153">그룹 정책을 새로 고칠 각 컴퓨터에서 명령 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-153">On each computer for which you want to refresh Group Policy, open a command console.</span></span> <span data-ttu-id="2f974-154">명령 콘솔이 관리자로 실행 되도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-154">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="2f974-155">명령 프롬프트에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-155">At the command prompt, enter</span></span>

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="2f974-156">그룹 정책 개체에서 DSCP 표시 확인</span><span class="sxs-lookup"><span data-stu-id="2f974-156">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="2f974-157">그룹 정책 개체의 값이 설정 되어 있는지 확인 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-157">To verify that the values from the Group Policy object have been set, perform the following steps.</span></span>

1. <span data-ttu-id="2f974-158">명령 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-158">Open a command console.</span></span> <span data-ttu-id="2f974-159">명령 콘솔이 관리자로 실행 되도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-159">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="2f974-160">명령 프롬프트에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-160">At the command prompt, enter:</span></span>

   ``` powershell
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="2f974-161">그러면 보고서가 생성 되 고 gp .txt 라는 텍스트 파일로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-161">This will generate a report and send it to a text file named gp.txt.</span></span> <span data-ttu-id="2f974-162">또는 다음 명령을 입력 하 여 보다 읽기 쉬운 HTML 보고서 (예: gp)에 동일한 데이터를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-162">Alternatively, you can enter the following command to produce the same data in a more readable HTML report named gp.html:</span></span>

   ``` powershell
   gpresult /H >gp.html
   ```

   <span data-ttu-id="2f974-163">![Gpresult 명령을 실행 하는 콘솔 창 스크린샷] (media/Qos-in-Teams-Image3.png "Gpresult 명령을 실행 하는 콘솔 창 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="2f974-163">![Screenshot of the console window running the gpresult command.](media/Qos-in-Teams-Image3.png "Screenshot of the console window running the gpresult command.")</span></span>

3. <span data-ttu-id="2f974-164">생성 된 파일에서 **적용 된 그룹 정책 개체** 의 머리글을 찾아 이전에 만든 그룹 정책 개체의 이름이 적용 된 정책 목록에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-164">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

4. <span data-ttu-id="2f974-165">레지스트리 편집기를 열고 다음으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-165">Open the Registry Editor, and go to:</span></span>

   <span data-ttu-id="2f974-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS</span><span class="sxs-lookup"><span data-stu-id="2f974-166">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS</span></span>\

   <span data-ttu-id="2f974-167">표 4에 나열 된 레지스트리 항목의 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-167">Verify the values for the registry entries listed in Table 4.</span></span>

   <span data-ttu-id="2f974-168">_표 4 QoS에 대 한 Windows 레지스트리 항목의 값_</span><span class="sxs-lookup"><span data-stu-id="2f974-168">_Table 4. Values for Windows registry entries for QoS_</span></span>

   |          <span data-ttu-id="2f974-169">이름</span><span class="sxs-lookup"><span data-stu-id="2f974-169">Name</span></span>          |  <span data-ttu-id="2f974-170">유형</span><span class="sxs-lookup"><span data-stu-id="2f974-170">Type</span></span>  |    <span data-ttu-id="2f974-171">데이터</span><span class="sxs-lookup"><span data-stu-id="2f974-171">Data</span></span>     |
   |         :---:          |:---:   |    :---:    |
   |    <span data-ttu-id="2f974-172">응용 프로그램 이름</span><span class="sxs-lookup"><span data-stu-id="2f974-172">Application Name</span></span>    | <span data-ttu-id="2f974-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="2f974-173">REG_SZ</span></span> |  <span data-ttu-id="2f974-174">팀. exe</span><span class="sxs-lookup"><span data-stu-id="2f974-174">Teams.exe</span></span>  |
   |       <span data-ttu-id="2f974-175">DSCP 값</span><span class="sxs-lookup"><span data-stu-id="2f974-175">DSCP Value</span></span>       | <span data-ttu-id="2f974-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="2f974-176">REG_SZ</span></span> |     <span data-ttu-id="2f974-177">46</span><span class="sxs-lookup"><span data-stu-id="2f974-177">46</span></span>      |
   |        <span data-ttu-id="2f974-178">로컬 IP</span><span class="sxs-lookup"><span data-stu-id="2f974-178">Local IP</span></span>        | <span data-ttu-id="2f974-179">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="2f974-179">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="2f974-180">로컬 IP 접두사 길이</span><span class="sxs-lookup"><span data-stu-id="2f974-180">Local IP Prefix Length</span></span> | <span data-ttu-id="2f974-181">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="2f974-181">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="2f974-182">로컬 포트</span><span class="sxs-lookup"><span data-stu-id="2f974-182">Local Port</span></span>       | <span data-ttu-id="2f974-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="2f974-183">REG_SZ</span></span> | <span data-ttu-id="2f974-184">50000-50019</span><span class="sxs-lookup"><span data-stu-id="2f974-184">50000-50019</span></span> |
   |        <span data-ttu-id="2f974-185">프로토콜별</span><span class="sxs-lookup"><span data-stu-id="2f974-185">Protocol</span></span>        | <span data-ttu-id="2f974-186">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="2f974-186">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="2f974-187">원격 IP</span><span class="sxs-lookup"><span data-stu-id="2f974-187">Remote IP</span></span>        | <span data-ttu-id="2f974-188">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="2f974-188">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="2f974-189">원격 IP 접두사</span><span class="sxs-lookup"><span data-stu-id="2f974-189">Remote IP Prefix</span></span>    | <span data-ttu-id="2f974-190">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="2f974-190">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="2f974-191">원격 포트</span><span class="sxs-lookup"><span data-stu-id="2f974-191">Remote Port</span></span>       | <span data-ttu-id="2f974-192">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="2f974-192">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="2f974-193">스로틀 속도</span><span class="sxs-lookup"><span data-stu-id="2f974-193">Throttle Rate</span></span>      | <span data-ttu-id="2f974-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="2f974-194">REG_SZ</span></span> |     <span data-ttu-id="2f974-195">-1</span><span class="sxs-lookup"><span data-stu-id="2f974-195">-1</span></span>      |

5. <span data-ttu-id="2f974-196">사용 중인 클라이언트에 대 한 응용 프로그램 이름 항목의 값이 올바른지 확인 하 고 DSCP 값과 로컬 포트 항목에 그룹 정책 개체의 설정이 반영 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f974-196">Verify that the value for the Application Name entry is correct for the client you’re using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>
