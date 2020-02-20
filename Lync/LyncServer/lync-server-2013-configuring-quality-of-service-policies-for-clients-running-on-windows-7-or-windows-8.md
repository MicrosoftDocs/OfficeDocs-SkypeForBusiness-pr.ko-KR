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
ms.openlocfilehash: 1fdb331a8d0e6a369f67726c755d76ab1d3bec58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a><span data-ttu-id="1d77a-102">Windows 7 또는 Windows 8에서 실행 되는 클라이언트에 대해 Lync Server 2013에서 서비스 품질 정책 구성</span><span class="sxs-lookup"><span data-stu-id="1d77a-102">Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d77a-103">_**마지막으로 수정 된 항목:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="1d77a-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="1d77a-104">Lync 클라이언트에서 사용할 포트 범위를 지정 하는 것 외에도 클라이언트 컴퓨터에 적용 되는 별도의 서비스 정책 품질을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-104">In addition to specifying port ranges for use by your Lync clients you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="1d77a-105">회의, 응용 프로그램 및 중재 서버에 대해 만들어지는 서비스 정책의 품질 정책은 클라이언트 컴퓨터에 적용 되지 않아야 합니다. 이 정보는 Lync 2013 클라이언트를 실행 하는 컴퓨터와 Windows 7 또는 Windows 8 중 하나에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-105">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Lync 2013 client and either Windows 7 or Windows 8.</span></span>

<span data-ttu-id="1d77a-106">다음 예에서는이 포트 범위 집합을 사용 하 여 오디오 정책과 비디오 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-106">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d77a-107">클라이언트 트래픽 유형</span><span class="sxs-lookup"><span data-stu-id="1d77a-107">Client Traffic Type</span></span></th>
<th><span data-ttu-id="1d77a-108">포트 시작</span><span class="sxs-lookup"><span data-stu-id="1d77a-108">Port Start</span></span></th>
<th><span data-ttu-id="1d77a-109">포트 범위</span><span class="sxs-lookup"><span data-stu-id="1d77a-109">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d77a-110">오디오만</span><span class="sxs-lookup"><span data-stu-id="1d77a-110">Audio</span></span></p></td>
<td><p><span data-ttu-id="1d77a-111">50020</span><span class="sxs-lookup"><span data-stu-id="1d77a-111">50020</span></span></p></td>
<td><p><span data-ttu-id="1d77a-112">20cm(8</span><span class="sxs-lookup"><span data-stu-id="1d77a-112">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d77a-113">비디오</span><span class="sxs-lookup"><span data-stu-id="1d77a-113">Video</span></span></p></td>
<td><p><span data-ttu-id="1d77a-114">58000</span><span class="sxs-lookup"><span data-stu-id="1d77a-114">58000</span></span></p></td>
<td><p><span data-ttu-id="1d77a-115">20cm(8</span><span class="sxs-lookup"><span data-stu-id="1d77a-115">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d77a-116">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="1d77a-116">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="1d77a-117">42000</span><span class="sxs-lookup"><span data-stu-id="1d77a-117">42000</span></span></p></td>
<td><p><span data-ttu-id="1d77a-118">20cm(8</span><span class="sxs-lookup"><span data-stu-id="1d77a-118">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d77a-119">파일 전송</span><span class="sxs-lookup"><span data-stu-id="1d77a-119">File transfer</span></span></p></td>
<td><p><span data-ttu-id="1d77a-120">42020</span><span class="sxs-lookup"><span data-stu-id="1d77a-120">42020</span></span></p></td>
<td><p><span data-ttu-id="1d77a-121">20cm(8</span><span class="sxs-lookup"><span data-stu-id="1d77a-121">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1d77a-122">Windows 7 또는 Windows 8 컴퓨터에 대 한 서비스 품질 오디오 정책을 만들려면 먼저 그룹 정책 관리가 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-122">To create a Quality of Service audio policy for Windows 7 or Windows 8 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="1d77a-123">**시작**을 클릭 하 고 **관리 도구**를 가리킨 다음 **그룹 정책 관리**를 클릭 하 여 그룹 정책 관리를 열고 다음 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-123">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="1d77a-124">그룹 정책 관리에서 새 정책을 만들 컨테이너를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-124">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="1d77a-125">예를 들어 모든 클라이언트 컴퓨터가 Clients 라는 OU에 있는 경우 클라이언트 OU에 새 정책이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-125">For example, if all your client computers are located in an OU named Clients then the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="1d77a-126">적절한 컨테이너를 마우스 오른쪽 단추로 클릭하고 **이 도메인에서 GPO를 만들어 여기에 연결**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-126">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="1d77a-127">**새 GPO** 대화 상자에서 **이름** 상자에 새 그룹 정책 개체의 이름 (예: **Lync Audio**)을 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-127">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="1d77a-128">새로 만든 정책을 마우스 오른쪽 단추로 클릭한 다음 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-128">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="1d77a-129">그룹 정책 관리 편집기에서 **컴퓨터 구성**, **정책**, **Windows 설정**을 확장하고 **정책 기반 QoS**를 확장하고 **새 정책 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-129">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="1d77a-130">**정책 기반 QoS** 대화 상자의 열기 페이지에서 **이름** 상자에 새 정책 이름 (예: **Lync Audio**)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-130">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Audio**) in the **Name** box.</span></span> <span data-ttu-id="1d77a-131">**DSCP 값 지정**을 선택하고 값을 **46**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-131">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="1d77a-132">**아웃바운드 스로틀 속도 지정**은 선택되지 않은 상태로 두고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-132">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="1d77a-133">다음 페이지에서 **이 실행 파일 이름의 응용 프로그램만** 선택 하 **고 이름을 입력**한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-133">On the next page, select **Only applications with this executable name** and enter the name **Lync.exe**, and then click **Next**.</span></span> <span data-ttu-id="1d77a-134">이 설정은 Lync 클라이언트에서 일치 하는 트래픽의 우선 순위를 지정 하는 것만 정책에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-134">This setting instructs the policy to only prioritize matching traffic from the Lync client.</span></span>

8.  <span data-ttu-id="1d77a-p106">세 번째 페이지에서는 **모든 원본 IP 주소** 및 **모든 대상 IP 주소**가 둘 다 선택되어 있는지 확인하고 **다음**을 클릭합니다 이 두 설정은 패킷을 보낸 컴퓨터(IP 주소) 및 받는 컴퓨터(IP 주소)에 관계없이 패킷이 관리되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-p106">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="1d77a-137">4페이지에서는 **이 QoS 정책이 적용되는 프로토콜 선택** 드롭다운 목록에서 **TCP 및 UDP**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-137">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="1d77a-138">TCP (전송 제어 프로토콜) 및 UDP (사용자 데이터 그램 프로토콜)는 Lync Server 및 해당 클라이언트 응용 프로그램에서 가장 일반적으로 사용 하는 두 가지 네트워킹 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-138">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="1d77a-139">**원본 포트 번호 지정** 제목 아래에서 **이 원본 포트 또는 범위부터**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-139">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="1d77a-140">포함된 텍스트 상자에는 오디오 전송에 예약된 포트 범위를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-140">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="1d77a-141">예를 들어 포트 50020을 사용 하 여 오디오 트래픽에 대해 포트 50039을 예약한 경우이 형식으로 포트 범위를 입력 합니다 **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="1d77a-141">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="1d77a-142">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-142">Click **Finish**.</span></span>

<span data-ttu-id="1d77a-143">오디오에 대 한 QoS 정책을 만든 후에는 비디오에 대 한 두 번째 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-143">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="1d77a-144">비디오용 정책을 만들려면 오디오 정책을 만들 때 수행한 것과 기본적으로는 같은 절차를 따르되 다음 항목을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-144">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="1d77a-145">다른 고유한 정책 이름 (예: **Lync Video**)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-145">Use a different (and unique) policy name (for example, **Lync Video**).</span></span>

  - <span data-ttu-id="1d77a-146">DSCP 값을 46이 아닌 **34**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-146">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="1d77a-147">이전에 설명 했 듯이, DSCP 값 34를 사용 하지 않아도 되는 경우에는 오디오에 사용 되는 것과 다른 DSCP 값을 할당 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-147">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="1d77a-148">비디오 트래픽용으로 이전에 구성한 포트 범위를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-148">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="1d77a-149">예를 들어 비디오용으로 58019 58000를 예약한 포트를 설치한 경우 포트 범위를 this: **58000:58019**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-149">For example, if you have reserved ports 58000 through 58019 for video, then set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="1d77a-150">응용 프로그램 공유 트래픽을 관리 하기 위한 정책을 만들려는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-150">If you decide to create a policy for managing application sharing traffic make these substitutions:</span></span>

  - <span data-ttu-id="1d77a-151">위의 두 정책과는 다른 고유한 정책 이름(예: **Lync Server 응용 프로그램 공유**)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-151">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="1d77a-152">DSCP 값을 46이 아닌 **24**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-152">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="1d77a-153">다시 말해서,이 값은 24 일 필요는 없으며 오디오 및 비디오에 사용 되는 DSCP 값과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-153">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="1d77a-154">비디오 트래픽용으로 이전에 구성한 포트 범위를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-154">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="1d77a-155">예를 들어 응용 프로그램 공유를 위해 42000에서 42019 포트를 예약한 경우 포트 범위를 this: **42000:42019**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-155">For example, if you have reserved ports 42000 through 42019 for application sharing, then set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="1d77a-156">파일 전송 정책의 경우:</span><span class="sxs-lookup"><span data-stu-id="1d77a-156">For a file transfer policy:</span></span>

  - <span data-ttu-id="1d77a-157">다른 고유한 정책 이름 (예: **Lync Server 파일 전송**)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-157">Use a different (and unique) policy name (for example, **Lync Server File Transfers**).</span></span>

  - <span data-ttu-id="1d77a-158">DSCP 값을 **14**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-158">Set the DSCP value to **14**.</span></span> <span data-ttu-id="1d77a-159">다시 말하지만이 값은 14 일 필요는 없으며 단순히 고유한 DSCP 코드 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-159">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="1d77a-160">이전에 구성한 응용 프로그램 포트 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-160">Use the previously-configured port range for application.</span></span> <span data-ttu-id="1d77a-161">예를 들어 응용 프로그램 공유를 위해 42020에서 42039 포트를 예약한 경우 포트 범위를 this: **42020:42039**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-161">For example, if you have reserved ports 42020 through 42039 for application sharing, then set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="1d77a-162">새로 만든 정책은 클라이언트 컴퓨터에서 그룹 정책을 새로 고칠 때까지 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-162">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="1d77a-163">그룹 정책은 일정한 간격에 따라 자체적으로 새로 고쳐지기는 하지만, 그룹 정책을 새로 고쳐야 하는 각 컴퓨터에서 다음 명령을 실행하면 그룹 정책을 강제로 즉시 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-163">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="1d77a-164">이 명령은 관리자 자격 증명으로 실행 되는 모든 명령 창에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-164">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="1d77a-165">관리자 자격 증명을 사용한 명령 창을 실행하려면 **시작**을 클릭하고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭한 후 **관리자 권한으로 실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-165">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="1d77a-166">이러한 정책은 클라이언트 컴퓨터에 대 한 대상으로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-166">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="1d77a-167">Lync Server를 실행 하는 서버에는 적용 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-167">They should not be applied to servers running Lync Server.</span></span>

<span data-ttu-id="1d77a-168">네트워크 패킷이 적절한 DSCP 값으로 표시되도록 하려면 다음 절차를 완료하여 각 컴퓨터에서 새 레지스트리 항목도 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-168">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="1d77a-169">**시작**을 클릭한 다음 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-169">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="1d77a-170">**실행** 대화 상자에 **regedit**를 입력한 다음 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-170">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="1d77a-171">레지스트리 편집기에서 **\_HKEY\_로컬 컴퓨터**를 확장 하 고 **시스템**, **CurrentControlSet**, **서비스**를 차례로 확장 한 다음 **Tcpip**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-171">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="1d77a-p119">**Tcpip**를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 다음 **키**를 클릭합니다. 새 레지스트리 키를 만든 후 **QoS**를 입력하고 Enter 키를 눌러 키 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-p119">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="1d77a-p120">**QoS**를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 다음 **문자열 값**을 클릭합니다. 새 레지스트리 값을 만든 후 **NLA 사용 안 함**을 입력하고 Enter 키를 눌러 값 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-p120">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="1d77a-176">**NLA 사용 안 함**을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-176">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="1d77a-177">**문자열 편집** 대화 상자의 **값 데이터** 상자에 **1**을 입력한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-177">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="1d77a-178">레지스트리 편집기를 닫고 컴퓨터를 다시 부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-178">Close the Registry Editor and then reboot your computer.</span></span>

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="1d77a-179">여러 네트워크 어댑터가 장착 된 컴퓨터에서 서비스 품질 구성</span><span class="sxs-lookup"><span data-stu-id="1d77a-179">Configuring Quality of Service on Computers with Multiple Network Adapters</span></span>

<span data-ttu-id="1d77a-180">컴퓨터에 여러 네트워크 어댑터가 있는 경우 DSCP 값이 구성 된 값이 아닌 0x00으로 표시 되는 문제가 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-180">If you have a computer that has multiple network adapters you might occasionally run into issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="1d77a-181">이 문제는 일반적으로 하나 이상의 네트워크 어댑터에서 Active Directory 도메인에 액세스할 수 없는 컴퓨터에서 발생 합니다 (예: 이러한 어댑터가 개인 네트워크에 사용 되는 경우).</span><span class="sxs-lookup"><span data-stu-id="1d77a-181">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="1d77a-182">이와 같은 경우, DSCP 값은 도메인에 액세스할 수 있는 어댑터에 태그를 지정 하지만 도메인에 액세스할 수 없는 어댑터에 대해서는 태그를 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-182">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="1d77a-183">도메인에 대 한 액세스 권한이 없는 어댑터를 포함 하 여 컴퓨터에 있는 모든 네트워크 어댑터의 DSCP 값에 태그를 설정 하려면 레지스트리에 값을 추가 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-183">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, then you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="1d77a-184">이 작업은 다음 절차에 따라 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-184">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="1d77a-185">**시작**을 클릭한 다음 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-185">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="1d77a-186">**실행** 대화 상자에 **regedit**를 입력한 다음 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-186">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="1d77a-187">레지스트리 편집기에서 **\_HKEY\_로컬 컴퓨터**를 확장 하 고 **시스템**, **CurrentControlSet**, **서비스**를 차례로 확장 한 다음 **Tcpip**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-187">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="1d77a-188">**QoS** 라는 이름의 레지스트리 키가 표시 되지 않으면 **Tcpip**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **키**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-188">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="1d77a-189">새 키를 만든 후 **QoS** 를 입력 하 고 enter 키를 눌러 키의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-189">After the new key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="1d77a-p125">**QoS**를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 다음 **문자열 값**을 클릭합니다. 새 레지스트리 값을 만든 후 **NLA 사용 안 함**을 입력하고 Enter 키를 눌러 값 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-p125">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="1d77a-192">**NLA 사용 안 함**을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-192">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="1d77a-193">**문자열 편집** 대화 상자의 **값 데이터** 상자에 **1**을 입력한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-193">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

<span data-ttu-id="1d77a-194">새 레지스트리 값을 만들고 구성한 후에는 변경 내용을 적용 하기 위해 컴퓨터를 다시 부팅 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d77a-194">After creating and configuring the new registry value you will need to reboot your computer in order for the changes to take effect.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

