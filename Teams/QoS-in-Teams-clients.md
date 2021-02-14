---
title: Microsoft Teams 클라이언트에서 QoS(서비스 품질) 구현
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: QoS(서비스 품질)를 사용하여 Microsoft Teams 데스크톱 클라이언트에 대한 네트워크 트래픽을 최적화하는 방법을 배워야 합니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: bc352303cf63ea966927aece0aef36854a0ace1b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526405"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a><span data-ttu-id="de997-103">Microsoft Teams 클라이언트에서 QoS(서비스 품질) 구현</span><span class="sxs-lookup"><span data-stu-id="de997-103">Implement Quality of Service (QoS) in Microsoft Teams clients</span></span>

<span data-ttu-id="de997-104">그룹 정책 내에서 QoS(정책 기반 서비스 품질)를 사용하여 Teams 클라이언트에서 미리 정의한 DSCP 값에 대한 원본 포트 범위를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de997-104">You can use policy-based Quality of Service (QoS) within Group Policy to set the source port range for the predefined DSCP value in the Teams client.</span></span> <span data-ttu-id="de997-105">다음 표에 지정된 포트 범위는 각 워크로드에 대한 정책을 만들기 위한 시작점입니다.</span><span class="sxs-lookup"><span data-stu-id="de997-105">The port ranges specified in the following table are a starting point to create a policy for each workload.</span></span>

<span data-ttu-id="de997-106">*표 1. 권장되는 초기 포트 범위*</span><span class="sxs-lookup"><span data-stu-id="de997-106">*Table 1. Recommended initial port ranges*</span></span>

|<span data-ttu-id="de997-107">미디어 트래픽 유형</span><span class="sxs-lookup"><span data-stu-id="de997-107">Media traffic type</span></span>| <span data-ttu-id="de997-108">클라이언트 원본 포트 범위 </span><span class="sxs-lookup"><span data-stu-id="de997-108">Client source port range</span></span> |<span data-ttu-id="de997-109">프로토콜</span><span class="sxs-lookup"><span data-stu-id="de997-109">Protocol</span></span>|<span data-ttu-id="de997-110">DSCP 값</span><span class="sxs-lookup"><span data-stu-id="de997-110">DSCP value</span></span>|<span data-ttu-id="de997-111">DSCP 클래스</span><span class="sxs-lookup"><span data-stu-id="de997-111">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="de997-112">오디오</span><span class="sxs-lookup"><span data-stu-id="de997-112">Audio</span></span>| <span data-ttu-id="de997-113">50,000~50,019</span><span class="sxs-lookup"><span data-stu-id="de997-113">50,000–50,019</span></span>|<span data-ttu-id="de997-114">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="de997-114">TCP/UDP</span></span>|<span data-ttu-id="de997-115">46</span><span class="sxs-lookup"><span data-stu-id="de997-115">46</span></span>|<span data-ttu-id="de997-116">Expedited Forwarding(EF)</span><span class="sxs-lookup"><span data-stu-id="de997-116">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="de997-117">비디오</span><span class="sxs-lookup"><span data-stu-id="de997-117">Video</span></span>| <span data-ttu-id="de997-118">50,020~50,039</span><span class="sxs-lookup"><span data-stu-id="de997-118">50,020–50,039</span></span>|<span data-ttu-id="de997-119">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="de997-119">TCP/UDP</span></span>|<span data-ttu-id="de997-120">34</span><span class="sxs-lookup"><span data-stu-id="de997-120">34</span></span>|<span data-ttu-id="de997-121">Assured Forwarding(AF41)</span><span class="sxs-lookup"><span data-stu-id="de997-121">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="de997-122">응용 프로그램/화면 공유</span><span class="sxs-lookup"><span data-stu-id="de997-122">Application/Screen Sharing</span></span>| <span data-ttu-id="de997-123">50,040~50,059</span><span class="sxs-lookup"><span data-stu-id="de997-123">50,040–50,059</span></span>|<span data-ttu-id="de997-124">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="de997-124">TCP/UDP</span></span>|<span data-ttu-id="de997-125">18</span><span class="sxs-lookup"><span data-stu-id="de997-125">18</span></span>|<span data-ttu-id="de997-126">Assured Forwarding(AF21)</span><span class="sxs-lookup"><span data-stu-id="de997-126">Assured Forwarding (AF21)</span></span>|
| | | | | |

<span data-ttu-id="de997-127">가능한 경우 그룹 정책 개체 내에서 정책 기반 QoS 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="de997-127">Wherever possible, configure policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="de997-128">다음 단계는 비즈니스용  [Skype Server에서](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)클라이언트에 대한 포트 범위 및 서비스 품질 정책 구성과 매우 유사하며, 이 정책에는 필요하지 않을 수 있는 몇 가지 추가 세부 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de997-128">The following steps are very similar to  [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), which has some additional details that may not be necessary.</span></span>

<span data-ttu-id="de997-129">도메인에 가입된 Windows 10 컴퓨터에 대한 QoS 오디오 정책을 만들하려면 먼저 그룹 정책 관리가 설치된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="de997-129">To create a QoS audio policy for domain-joined Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="de997-130">그룹 정책 관리를 열고(시작을 클릭하고 관리 도구를 클릭한 다음 그룹 정책 관리를 클릭) 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="de997-130">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="de997-131">그룹 정책 관리에서 새 정책을 만들어야 하는 컨테이너를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="de997-131">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="de997-132">예를 들어 모든 클라이언트 컴퓨터가 클라이언트라는 OU에 있는 경우 클라이언트 OU에 새 정책을 만들어야 합니다. </span><span class="sxs-lookup"><span data-stu-id="de997-132">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Clients OU.</span></span>

1. <span data-ttu-id="de997-133">적절한 컨테이너를 마우스 오른쪽 단추로 클릭한 다음 이 도메인에서 GPO 만들기를 **클릭하고 여기에 연결합니다.**</span><span class="sxs-lookup"><span data-stu-id="de997-133">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

1. <span data-ttu-id="de997-134">새 **GPO** 대화 상자의 이름 상자에 새 그룹  정책 개체의 이름을 입력한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="de997-134">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

1. <span data-ttu-id="de997-135">새로 만든 정책을 마우스 오른쪽 단추로 클릭한 다음 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="de997-135">Right-click the newly created policy, and then click **Edit**.</span></span>

1. <span data-ttu-id="de997-136">그룹 정책 관리 편집기에서 **컴퓨터** 구성을 확장하고 **Windows 설정을** 확장하고 정책 기반 **QoS를** 마우스 오른쪽 단추로 클릭한 다음 새 정책 **만들기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="de997-136">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

1. <span data-ttu-id="de997-137">정책 기반 **QoS** 대화 상자의 열기 페이지에서 이름 상자에 새 정책의 이름을 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="de997-137">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="de997-138">**DSCP 값 지정을** 선택하고 값을 **46으로 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="de997-138">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="de997-139">아웃바운드 **스로틀** 속도 지정을 선택하지 않은 그대로 두고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="de997-139">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

1. <span data-ttu-id="de997-140">다음 페이지에서 이  실행 가능한 이름이 있는 애플리케이션만 \*\*\*\* 선택하고 이름Teams.exe다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="de997-140">On the next page, select **Only applications with this executable name** and enter the name **Teams.exe**, and then click **Next**.</span></span> <span data-ttu-id="de997-141">이 설정은 Teams 클라이언트에서 일치하는 트래픽의 우선 순위를 지정하는 정책에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="de997-141">This setting instructs the policy to only prioritize matching traffic from the Teams client.</span></span>

1. <span data-ttu-id="de997-142">세 번째 페이지에서 원본 **IP** 주소와 대상 **IP** 주소가 모두 선택되어 있는지 확인한 후 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="de997-142">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="de997-143">이러한 두 설정은 패킷을 전송하는 컴퓨터(IP 주소)와 패킷을 받을 컴퓨터(IP 주소)에 관계 없이 패킷을 관리하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="de997-143">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

1. <span data-ttu-id="de997-144">4페이지에서 이 **QoS** 정책이 드롭다운 목록에 적용되는 프로토콜 선택에서 **TCP 및 UDP를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="de997-144">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="de997-145">TCP(Transmission Control Protocol) 및 UDP(User Datagram Protocol)는 가장 일반적으로 사용되는 두 가지 네트워킹 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="de997-145">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

1. <span data-ttu-id="de997-146">제목에서 원본 포트 번호를 **지정하고** 이 원본 포트 또는 **범위에서 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="de997-146">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="de997-147">함께 제공되는 텍스트 상자에 오디오 전송을 위해 예약된 포트 범위를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="de997-147">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="de997-148">예를 들어 오디오 트래픽에 대해 포트 50000~포트 50019를 예약한 경우 **50000:50019** 형식을 사용하여 포트 범위를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="de997-148">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="de997-149">**마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="de997-149">Click **Finish**.</span></span>

1. <span data-ttu-id="de997-150">5-10단계를 반복하여 비디오 및 응용 프로그램/데스크톱 공유에 대한 정책을 만들고 6단계와 10단계에서 적절한 값을 대신합니다.</span><span class="sxs-lookup"><span data-stu-id="de997-150">Repeat steps 5-10 to create policies for Video and Application/Desktop Sharing, substituting the appropriate values in steps 6 and 10.</span></span>

<span data-ttu-id="de997-151">만든 새 정책은 클라이언트 컴퓨터에서 그룹 정책을 새로 고칠 때까지 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="de997-151">The new policies you've created won't take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="de997-152">그룹 정책은 주기적으로 자체적으로 새로 고쳐지지만 다음 단계를 수행하여 즉시 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de997-152">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by following these steps:</span></span>

1. <span data-ttu-id="de997-153">그룹 정책을 새로 고치고자 하는 각 컴퓨터에서 관리자 권한으로 명령 프롬프트를 *여습니다(관리자 권한으로 실행).*</span><span class="sxs-lookup"><span data-stu-id="de997-153">On each computer for which you want to refresh Group Policy, open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="de997-154">명령 프롬프트에서</span><span class="sxs-lookup"><span data-stu-id="de997-154">At the command prompt, enter</span></span>

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="de997-155">그룹 정책 개체에서 DSCP 표시 확인</span><span class="sxs-lookup"><span data-stu-id="de997-155">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="de997-156">그룹 정책 개체의 값이 설정되어 있는지 확인한 후 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="de997-156">To verify that the values from the Group Policy object have been set, perform the following steps:</span></span>

1. <span data-ttu-id="de997-157">관리자 권한으로 명령 프롬프트 *열기(관리자 권한으로 실행).*</span><span class="sxs-lookup"><span data-stu-id="de997-157">Open a Command Prompt as administrator (*Run as administrator*).</span></span>

1. <span data-ttu-id="de997-158">명령 프롬프트에서</span><span class="sxs-lookup"><span data-stu-id="de997-158">At the command prompt, enter</span></span>

   ```console
   gpresult /R > gp.txt
   ```

   <span data-ttu-id="de997-159">이렇게 하면 적용된 GPOS에 대한 보고서가 생성되고 이 보고서가 *gp.txt.*</span><span class="sxs-lookup"><span data-stu-id="de997-159">This will generate a report of applied GPOs and send it to a text file named *gp.txt*.</span></span>

   <span data-ttu-id="de997-160">gp.htm읽기 쉽게 HTML 보고서를 사용하려면 *다음* 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="de997-160">For a more readable HTML report named *gp.html*, enter the following command:</span></span>

   ```console
   gpresult /H gp.html
   ```

1. <span data-ttu-id="de997-161">생성된 파일에서 적용된 그룹  정책 개체 제목을 찾아서 앞에서 만든 그룹 정책 개체의 이름이 적용된 정책 목록에 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de997-161">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span>

1. <span data-ttu-id="de997-162">레지스트리 편집기를 열고</span><span class="sxs-lookup"><span data-stu-id="de997-162">Open the Registry Editor, and go to</span></span>

   <span data-ttu-id="de997-163">HKEY \_ LOCAL MACHINE 소프트웨어 정책 Microsoft Windows \_ \\ \\ \\ \\ \\ QoS</span><span class="sxs-lookup"><span data-stu-id="de997-163">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\QoS</span></span>

   <span data-ttu-id="de997-164">표 2에 나열된 레지스트리 항목의 값을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de997-164">Verify the values for the registry entries listed in Table 2.</span></span>

   <span data-ttu-id="de997-165">*표 2. QoS에 대한 Windows 레지스트리 항목에 대한 값*</span><span class="sxs-lookup"><span data-stu-id="de997-165">*Table 2. Values for Windows registry entries for QoS*</span></span>

   |          <span data-ttu-id="de997-166">이름</span><span class="sxs-lookup"><span data-stu-id="de997-166">Name</span></span>          |  <span data-ttu-id="de997-167">유형</span><span class="sxs-lookup"><span data-stu-id="de997-167">Type</span></span>  |    <span data-ttu-id="de997-168">데이터</span><span class="sxs-lookup"><span data-stu-id="de997-168">Data</span></span>     |
   |         :---:          | :---:  |    :---:    |
   |    <span data-ttu-id="de997-169">애플리케이션 이름</span><span class="sxs-lookup"><span data-stu-id="de997-169">Application Name</span></span>    | <span data-ttu-id="de997-170">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="de997-170">REG_SZ</span></span> |  <span data-ttu-id="de997-171">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="de997-171">Teams.exe</span></span>  |
   |       <span data-ttu-id="de997-172">DSCP 값</span><span class="sxs-lookup"><span data-stu-id="de997-172">DSCP Value</span></span>       | <span data-ttu-id="de997-173">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="de997-173">REG_SZ</span></span> |     <span data-ttu-id="de997-174">46</span><span class="sxs-lookup"><span data-stu-id="de997-174">46</span></span>      |
   |        <span data-ttu-id="de997-175">로컬 IP</span><span class="sxs-lookup"><span data-stu-id="de997-175">Local IP</span></span>        | <span data-ttu-id="de997-176">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="de997-176">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="de997-177">로컬 IP Prefix 길이</span><span class="sxs-lookup"><span data-stu-id="de997-177">Local IP Prefix Length</span></span> | <span data-ttu-id="de997-178">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="de997-178">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="de997-179">로컬 포트</span><span class="sxs-lookup"><span data-stu-id="de997-179">Local Port</span></span>       | <span data-ttu-id="de997-180">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="de997-180">REG_SZ</span></span> | <span data-ttu-id="de997-181">50000-50019</span><span class="sxs-lookup"><span data-stu-id="de997-181">50000-50019</span></span> |
   |        <span data-ttu-id="de997-182">프로토콜</span><span class="sxs-lookup"><span data-stu-id="de997-182">Protocol</span></span>        | <span data-ttu-id="de997-183">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="de997-183">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="de997-184">원격 IP</span><span class="sxs-lookup"><span data-stu-id="de997-184">Remote IP</span></span>        | <span data-ttu-id="de997-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="de997-185">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="de997-186">원격 IP Prefix</span><span class="sxs-lookup"><span data-stu-id="de997-186">Remote IP Prefix</span></span>    | <span data-ttu-id="de997-187">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="de997-187">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="de997-188">원격 포트</span><span class="sxs-lookup"><span data-stu-id="de997-188">Remote Port</span></span>       | <span data-ttu-id="de997-189">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="de997-189">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="de997-190">스로틀 속도</span><span class="sxs-lookup"><span data-stu-id="de997-190">Throttle Rate</span></span>      | <span data-ttu-id="de997-191">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="de997-191">REG_SZ</span></span> |     <span data-ttu-id="de997-192">-1</span><span class="sxs-lookup"><span data-stu-id="de997-192">-1</span></span>      |
   | | | |

1. <span data-ttu-id="de997-193">사용 하는 클라이언트에 대한 애플리케이션 이름 항목의 값이 올바른지 확인하고 DSCP 값 및 로컬 포트 항목 모두 그룹 정책 개체의 설정을 반영하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="de997-193">Verify that the value for the Application Name entry is correct for the client you're using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>


## <a name="related-topics"></a><span data-ttu-id="de997-194">관련 항목</span><span class="sxs-lookup"><span data-stu-id="de997-194">Related topics</span></span>

[<span data-ttu-id="de997-195">Teams에서 QoS(서비스 품질) 구현</span><span class="sxs-lookup"><span data-stu-id="de997-195">Implement Quality of Service (QoS) in Teams</span></span>](QoS-in-Teams.md)