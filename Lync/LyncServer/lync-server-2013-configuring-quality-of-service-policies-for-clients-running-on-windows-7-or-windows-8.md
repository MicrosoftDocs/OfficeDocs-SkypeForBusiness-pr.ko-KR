---
title: 'Lync Server 2013: Windows 7 또는 Windows 8에서 실행 되는 클라이언트에 대 한 서비스 품질 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc06f5079fc6876c85324af67bd22be12f85a3c9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a><span data-ttu-id="5468e-102">Windows 7 또는 Windows 8에서 실행 되는 클라이언트에 대 한 Lync Server 2013의 서비스 품질 정책 구성</span><span class="sxs-lookup"><span data-stu-id="5468e-102">Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5468e-103">_**마지막으로 수정한 주제:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="5468e-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="5468e-104">Lync 클라이언트에서 사용할 포트 범위를 지정 하는 것 외에도 클라이언트 컴퓨터에 적용 되는 별도의 서비스 품질 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-104">In addition to specifying port ranges for use by your Lync clients you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="5468e-105">(회의, 응용 프로그램 및 중재 서버에 대해 생성 되는 서비스 품질 정책은 클라이언트 컴퓨터에 적용 되어서는 안 됩니다.) 이 정보는 Lync 2013 클라이언트와 Windows 7 또는 Windows 8 중 하나를 실행 하는 컴퓨터에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-105">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Lync 2013 client and either Windows 7 or Windows 8.</span></span>

<span data-ttu-id="5468e-106">다음 예에서는이 포트 범위 집합을 사용 하 여 오디오 정책 및 비디오 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-106">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5468e-107">클라이언트 트래픽 형식</span><span class="sxs-lookup"><span data-stu-id="5468e-107">Client Traffic Type</span></span></th>
<th><span data-ttu-id="5468e-108">포트 시작</span><span class="sxs-lookup"><span data-stu-id="5468e-108">Port Start</span></span></th>
<th><span data-ttu-id="5468e-109">포트 범위</span><span class="sxs-lookup"><span data-stu-id="5468e-109">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5468e-110">오디오</span><span class="sxs-lookup"><span data-stu-id="5468e-110">Audio</span></span></p></td>
<td><p><span data-ttu-id="5468e-111">50020</span><span class="sxs-lookup"><span data-stu-id="5468e-111">50020</span></span></p></td>
<td><p><span data-ttu-id="5468e-112">명</span><span class="sxs-lookup"><span data-stu-id="5468e-112">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5468e-113">비디오만</span><span class="sxs-lookup"><span data-stu-id="5468e-113">Video</span></span></p></td>
<td><p><span data-ttu-id="5468e-114">58000</span><span class="sxs-lookup"><span data-stu-id="5468e-114">58000</span></span></p></td>
<td><p><span data-ttu-id="5468e-115">명</span><span class="sxs-lookup"><span data-stu-id="5468e-115">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5468e-116">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="5468e-116">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="5468e-117">42000</span><span class="sxs-lookup"><span data-stu-id="5468e-117">42000</span></span></p></td>
<td><p><span data-ttu-id="5468e-118">명</span><span class="sxs-lookup"><span data-stu-id="5468e-118">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5468e-119">파일 전송</span><span class="sxs-lookup"><span data-stu-id="5468e-119">File transfer</span></span></p></td>
<td><p><span data-ttu-id="5468e-120">42020</span><span class="sxs-lookup"><span data-stu-id="5468e-120">42020</span></span></p></td>
<td><p><span data-ttu-id="5468e-121">명</span><span class="sxs-lookup"><span data-stu-id="5468e-121">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5468e-122">Windows 7 또는 Windows 8 컴퓨터용 서비스 품질 오디오 정책을 만들려면 먼저 그룹 정책 관리가 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-122">To create a Quality of Service audio policy for Windows 7 or Windows 8 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="5468e-123">그룹 정책 관리를 열고 ( **시작**을 클릭 하 고 **관리 도구**를 가리킨 다음 **그룹 정책 관리**클릭) 다음 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-123">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="5468e-124">그룹 정책 관리에서 새 정책을 만들 컨테이너를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-124">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="5468e-125">예를 들어 모든 클라이언트 컴퓨터가 클라이언트 라는 OU에 있는 경우 클라이언트 OU에서 새 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-125">For example, if all your client computers are located in an OU named Clients then the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="5468e-126">적절 한 컨테이너를 마우스 오른쪽 단추로 클릭 한 다음 **이 도메인에서 GPO 만들기를 클릭 하 고 여기에 연결**합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-126">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="5468e-127">**새 GPO** 대화 상자의 **이름** 상자에 새 그룹 정책 개체의 이름 (예: **Lync 오디오**)을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-127">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="5468e-128">새로 만든 정책을 마우스 오른쪽 단추로 클릭 한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-128">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="5468e-129">그룹 정책 관리 편집기에서 **컴퓨터 구성**, **정책**, **Windows 설정을**차례로 확장 하 고 **정책 기반 QoS**를 마우스 오른쪽 단추로 클릭 한 다음 **새 정책 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-129">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="5468e-130">**정책 기반 QoS** 대화 상자의 열기 페이지에 있는 **이름** 상자에 새 정책의 이름 (예: **Lync 오디오**)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-130">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Audio**) in the **Name** box.</span></span> <span data-ttu-id="5468e-131">**DSCP 값 지정** 을 선택 하 고 값을 **46**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-131">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="5468e-132">**아웃 바운드 스로틀 속도 지정** 을 선택 하지 않은 상태로 두고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-132">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="5468e-133">다음 페이지에서 **이 실행 파일 이름의 응용** 프로그램만 선택 하 고 **Lync**의 이름을 입력 한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-133">On the next page, select **Only applications with this executable name** and enter the name **Lync.exe**, and then click **Next**.</span></span> <span data-ttu-id="5468e-134">이 설정은 Lync 클라이언트에서 일치 하는 트래픽에만 우선 순위를 지정 하도록 정책에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-134">This setting instructs the policy to only prioritize matching traffic from the Lync client.</span></span>

8.  <span data-ttu-id="5468e-135">세 번째 페이지에서 **원본 ip 주소** 와 **대상 ip 주소가** 모두 선택 되어 있는지 확인 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-135">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**.</span></span> <span data-ttu-id="5468e-136">이러한 두 가지 설정은 해당 패킷과 전송 되는 컴퓨터 (ip 주소) 및 해당 패킷을 받을 컴퓨터 (IP 주소)에 관계 없이 패킷이 관리 됨을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-136">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="5468e-137">4 페이지에서 **이 QoS 정책이 적용 되는 프로토콜 선택** 드롭다운 목록에서 **TCP 및 UDP** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-137">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="5468e-138">TCP (전송 제어 프로토콜) 및 UDP (사용자 데이터 그램 프로토콜)는 Lync Server 및 해당 클라이언트 응용 프로그램에서 가장 일반적으로 사용 하는 두 가지 네트워킹 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-138">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="5468e-139">**원본 포트 번호를 지정 하는**제목 아래에서 **이 원본 포트 또는 범위를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-139">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="5468e-140">해당 텍스트 상자에 오디오 전송용으로 예약 된 포트 범위를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-140">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="5468e-141">예를 들어 오디오 트래픽에 포트 50039을 통해 포트 50020를 예약한 경우이 형식을 사용 하 여 포트 범위를 입력 합니다 ( **50020:50039**).</span><span class="sxs-lookup"><span data-stu-id="5468e-141">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="5468e-142">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-142">Click **Finish**.</span></span>

<span data-ttu-id="5468e-143">오디오에 대 한 QoS 정책을 만든 후에는 비디오에 대 한 두 번째 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-143">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="5468e-144">비디오에 대 한 정책을 만들려면 오디오 정책을 만들 때 팔 로우 하는 기본 절차를 따르고 다음과 같이 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-144">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="5468e-145">다른 고유 정책 이름 (예: **Lync 비디오**)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-145">Use a different (and unique) policy name (for example, **Lync Video**).</span></span>

  - <span data-ttu-id="5468e-146">DSCP 값을 46 대신 **34** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-146">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="5468e-147">(앞에서 설명한 것 처럼, DSCP 값 34을 사용할 필요가 없으며, 오디오에 사용 되는 것과 다른 DSCP 값을 할당 하기만 하면 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="5468e-147">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="5468e-148">비디오 트래픽에 이전에 구성한 포트 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-148">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="5468e-149">예를 들어 비디오에 대해 58019 58000를 예약한 포트를 사용 하는 경우 포트 범위를 다음으로 설정: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="5468e-149">For example, if you have reserved ports 58000 through 58019 for video, then set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="5468e-150">응용 프로그램 공유 트래픽을 관리 하기 위한 정책을 만들려는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-150">If you decide to create a policy for managing application sharing traffic make these substitutions:</span></span>

  - <span data-ttu-id="5468e-151">다른 고유 정책 이름 (예: **Lync Server 응용 프로그램 공유**)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-151">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="5468e-152">46 대신 DSCP 값을 **24** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-152">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="5468e-153">(이 값은 24 일 필요는 없으며, 오디오 및 비디오에 사용 되는 DSCP 값과 달라 야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="5468e-153">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="5468e-154">비디오 트래픽에 이전에 구성한 포트 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-154">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="5468e-155">예를 들어 응용 프로그램 공유에 대해 포트 42000 ~ 42019을 (를) 예약한 경우 포트 범위를 this: **42000:42019**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-155">For example, if you have reserved ports 42000 through 42019 for application sharing, then set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="5468e-156">파일 전송 정책:</span><span class="sxs-lookup"><span data-stu-id="5468e-156">For a file transfer policy:</span></span>

  - <span data-ttu-id="5468e-157">다른 (고유) 정책 이름 (예: **Lync Server 파일 전송**)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-157">Use a different (and unique) policy name (for example, **Lync Server File Transfers**).</span></span>

  - <span data-ttu-id="5468e-158">DSCP 값을 **14**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-158">Set the DSCP value to **14**.</span></span> <span data-ttu-id="5468e-159">(이 값은 14 일 필요는 없으며 단순히 고유한 DSCP 코드 여야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="5468e-159">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="5468e-160">이전에 구성 된 응용 프로그램의 포트 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-160">Use the previously-configured port range for application.</span></span> <span data-ttu-id="5468e-161">예를 들어 응용 프로그램 공유에 대해 포트 42020 ~ 42039을 (를) 예약한 경우 포트 범위를 this: **42020:42039**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-161">For example, if you have reserved ports 42020 through 42039 for application sharing, then set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="5468e-162">만든 새 정책은 클라이언트 컴퓨터에서 그룹 정책을 새로 고칠 때까지 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-162">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="5468e-163">그룹 정책은 주기적으로 자체적으로 새로 고쳐지고 그룹 정책을 새로 고쳐야 하는 각 컴퓨터에서 다음 명령을 실행 하 여 즉시 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-163">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="5468e-164">이 명령은 관리자 자격 증명으로 실행 되는 모든 명령 창에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-164">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="5468e-165">명령 창을 관리자 자격 증명으로 실행 하려면 **시작**을 클릭 하 고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-165">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="5468e-166">이러한 정책은 클라이언트 컴퓨터를 대상으로 해야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="5468e-166">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="5468e-167">Lync Server를 실행 하는 서버에는 적용 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-167">They should not be applied to servers running Lync Server.</span></span>

<span data-ttu-id="5468e-168">네트워크 패킷이 적절 한 DSCP 값으로 표시 되도록 하려면 다음 절차를 완료 하 여 각 컴퓨터에 새 레지스트리 항목을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-168">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="5468e-169">**시작** 을 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-169">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="5468e-170">**실행** 대화 상자에서 **regedit** 를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-170">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="5468e-171">레지스트리 편집기에서 **\_HKEY\_LOCAL MACHINE**을 확장 하 고 **시스템**, **CurrentControlSet**를 차례로 확장 한 다음 **서비스**를 확장 한 다음 **Tcpip**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-171">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="5468e-172">**Tcpip**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **키**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-172">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="5468e-173">새 레지스트리 키가 만들어지면 **QoS** 를 입력 한 다음 enter 키를 눌러 키의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-173">After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="5468e-174">**QoS**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **문자열 값**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-174">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="5468e-175">새 레지스트리 값을 만든 후에는 **NLA를 사용 하지 않음을** 입력 하 고 enter 키를 눌러 값의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-175">After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="5468e-176">**NLA를 사용 하지 않음을**두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-176">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="5468e-177">**문자열 편집** 대화 상자의 **값 데이터** 상자에 **1** 을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-177">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="5468e-178">레지스트리 편집기를 닫은 다음 컴퓨터를 다시 부팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-178">Close the Registry Editor and then reboot your computer.</span></span>

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="5468e-179">여러 네트워크 어댑터가 있는 컴퓨터에서 서비스 품질 구성</span><span class="sxs-lookup"><span data-stu-id="5468e-179">Configuring Quality of Service on Computers with Multiple Network Adapters</span></span>

<span data-ttu-id="5468e-180">여러 네트워크 어댑터가 있는 컴퓨터를 사용 하는 경우 DSCP 값이 구성 된 값이 아닌 0x00으로 표시 되는 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-180">If you have a computer that has multiple network adapters you might occasionally run into issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="5468e-181">이 문제는 일반적으로 하나 이상의 네트워크 어댑터가 Active Directory 도메인에 액세스할 수 없는 컴퓨터에서 발생 합니다 (예: 해당 어댑터가 개인 네트워크에 사용 되는 경우).</span><span class="sxs-lookup"><span data-stu-id="5468e-181">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="5468e-182">이와 같은 경우 DSCP 값에는 도메인에 액세스할 수 있는 어댑터에 대 한 태그가 지정 되지만 도메인에 액세스할 수 없는 어댑터에는 태그가 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-182">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="5468e-183">도메인에 대 한 액세스 권한이 없는 어댑터를 포함 하 여 컴퓨터에 있는 모든 네트워크 어댑터의 DSCP 값에 태그를 지정 하려면 레지스트리에 값을 추가 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-183">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, then you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="5468e-184">다음 절차를 완료 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-184">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="5468e-185">**시작** 을 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-185">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="5468e-186">**실행** 대화 상자에서 **regedit** 를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-186">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="5468e-187">레지스트리 편집기에서 **\_HKEY\_LOCAL MACHINE**을 확장 하 고 **시스템**, **CurrentControlSet**를 차례로 확장 한 다음 **서비스**를 확장 한 다음 **Tcpip**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-187">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="5468e-188">**QoS** 라는 레지스트리 키가 표시 되지 않으면 **Tcpip**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **키**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-188">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="5468e-189">새 키가 만들어지면 **QoS** 를 입력 한 다음 enter 키를 눌러 키의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-189">After the new key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="5468e-190">**QoS**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **문자열 값**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-190">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="5468e-191">새 레지스트리 값을 만든 후에는 **NLA를 사용 하지 않음을** 입력 하 고 enter 키를 눌러 값의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-191">After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="5468e-192">**NLA를 사용 하지 않음을**두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-192">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="5468e-193">**문자열 편집** 대화 상자의 **값 데이터** 상자에 **1** 을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-193">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

<span data-ttu-id="5468e-194">새 레지스트리 값을 만들고 구성한 후 변경 내용이 적용 되려면 컴퓨터를 다시 부팅 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5468e-194">After creating and configuring the new registry value you will need to reboot your computer in order for the changes to take effect.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

