---
title: A/V Edge 서버의 서비스 품질 정책 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58f5bfabfe794ed274d28074aaf162bc715a6ed3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="13576-102">Lync Server 2013에서 A/V Edge 서버의 서비스 품질 정책 구성</span><span class="sxs-lookup"><span data-stu-id="13576-102">Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13576-103">_**마지막으로 수정한 주제:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="13576-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="13576-104">회의, 응용 프로그램 및 조정 서버용 QoS 정책을 만드는 것 외에도 A/V Edge 서버의 내부 쪽에 대 한 오디오 및 비디오 정책도 모두 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-104">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers.</span></span> <span data-ttu-id="13576-105">그러나 Edge 서버에서 사용 되는 정책은 회의, 응용 프로그램 및 중재 서버에서 사용 되는 정책과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="13576-105">However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="13576-106">원본 포트 범위를 지정한 회의, 응용 프로그램 및 중재 서버의 경우 Edge 서버를 사용 하는 경우 대상 포트 범위를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-106">For the Conferencing, Application, and Mediation servers you specified a source port range; with Edge servers, you need to specify a destination port range.</span></span> <span data-ttu-id="13576-107">Edge 서버에는 단순히 회의, 응용 프로그램 및 조정 서버 QoS 정책을 적용할 수 없기 때문에 이러한 정책은 단순히 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13576-107">Because of that you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work.</span></span> <span data-ttu-id="13576-108">대신 새 정책을 만들고 해당 정책을 Edge 서버에만 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-108">Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="13576-109">다음 절차에서는 Edge 서버의 서비스 품질을 관리 하는 데 사용할 수 있는 Active Directory 그룹 정책 개체를 만드는 프로세스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-109">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers.</span></span> <span data-ttu-id="13576-110">물론, Edge 서버는 Active Directory 계정이 없는 독립 실행형 서버 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13576-110">Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts.</span></span> <span data-ttu-id="13576-111">그러한 경우 Active Directory 그룹 정책 대신 로컬 그룹 정책을 사용할 수 있습니다. 유일한 차이점은 로컬 그룹 정책 편집기를 사용 하 여 이러한 로컬 정책을 만들고 각 Edge 서버에서 동일한 정책 집합을 개별적으로 만들어야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="13576-111">If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server.</span></span> <span data-ttu-id="13576-112">Edge 서버에서 로컬 그룹 정책 편집기를 시작 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-112">To start the Local Group Policy Editor on an Edge server do the following:</span></span>

1.  <span data-ttu-id="13576-113">**시작** 을 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-113">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="13576-114">**실행** 대화 상자에서 **gpedit.msc** 를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="13576-114">In the **Run** dialog box, type **gpedit.msc** and then press ENTER.</span></span>

<span data-ttu-id="13576-115">Active Directory 기반 정책을 만드는 경우 그룹 정책 관리가 설치 된 컴퓨터에 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-115">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="13576-116">이 경우 그룹 정책 관리 ( **시작**을 클릭 하 고 **관리 도구**를 가리킨 다음 **그룹 정책 관리**클릭)를 열고 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-116">In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following steps:</span></span>

1.  <span data-ttu-id="13576-117">그룹 정책 관리에서 새 정책을 만들 컨테이너를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="13576-117">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="13576-118">예를 들어 lync server 컴퓨터가 모두 Lync Server 라는 OU에 있는 경우에는 Lync Server OU에서 새 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-118">For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="13576-119">적절 한 컨테이너를 마우스 오른쪽 단추로 클릭 한 다음 **이 도메인에서 GPO 만들기를 클릭 하 고 여기에 연결**합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="13576-120">**새 GPO** 대화 상자의 **이름** 상자에 새 그룹 정책 개체의 이름 (예: **Lync Server 오디오**)을 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="13576-121">새로 만든 정책을 마우스 오른쪽 단추로 클릭 한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-121">Right-click the newly-created policy and then click **Edit**.</span></span>

<span data-ttu-id="13576-122">여기서 프로세스는 Active Directory 정책 또는 로컬 정책 중 어느 것을 만들고 있는지에 관계 없이 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-122">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="13576-123">그룹 정책 관리 편집기 또는 로컬 그룹 정책 편집기에서 **컴퓨터 구성**, **정책**, **Windows 설정을**차례로 확장 하 고 **정책 기반 QoS**를 마우스 오른쪽 단추로 클릭 한 다음 **새 정책 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-123">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="13576-124">**정책 기반 QoS** 대화 상자의 열기 페이지에 있는 **이름** 상자에 새 정책의 이름 (예: **Lync Server 오디오**)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-124">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server Audio**) in the **Name** box.</span></span> <span data-ttu-id="13576-125">**DSCP 값 지정** 을 선택 하 고 값을 **46**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-125">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="13576-126">**아웃 바운드 스로틀 속도 지정** 을 선택 하지 않은 상태로 두고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-126">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="13576-127">다음 페이지에서 **모든 응용 프로그램이** 선택 되어 있는지 확인 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-127">On the next page, make sure that **All applications** is selected and then click **Next**.</span></span> <span data-ttu-id="13576-128">이 설정은 특정 응용 프로그램에서 만든 패킷 뿐 아니라 DSCP 46 표시가 있는 모든 패킷을 검색 하도록 네트워크에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-128">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="13576-129">세 번째 페이지에서 **원본 ip 주소** 와 **대상 ip 주소가** 모두 선택 되어 있는지 확인 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-129">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**.</span></span> <span data-ttu-id="13576-130">이러한 두 가지 설정은 해당 패킷과 전송 되는 컴퓨터 (ip 주소) 및 해당 패킷을 받을 컴퓨터 (IP 주소)에 관계 없이 패킷이 관리 됨을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-130">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="13576-131">4 페이지에서 **이 QoS 정책이 적용 되는 프로토콜 선택** 드롭다운 목록에서 **TCP 및 UDP** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-131">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="13576-132">TCP (전송 제어 프로토콜) 및 UDP (사용자 데이터 그램 프로토콜)는 Lync Server 및 해당 클라이언트 응용 프로그램에서 가장 일반적으로 사용 하는 두 가지 네트워킹 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="13576-132">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

6.  <span data-ttu-id="13576-133">**대상 포트 번호를 지정 하는**제목 아래에서 **대상 포트 또는 범위에서**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-133">Under the heading **Specify the destination port number**, select **From this destination port or range**.</span></span> <span data-ttu-id="13576-134">해당 텍스트 상자에 오디오 전송용으로 예약 된 포트 범위를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-134">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="13576-135">예를 들어 포트 49152를 오디오 트래픽에 대 한 포트 57500에서 예약한 경우 다음 형식을 사용 하 여 포트 범위를 입력 합니다: **49152:57500**.</span><span class="sxs-lookup"><span data-stu-id="13576-135">For example, if you reserved ports 49152 through ports 57500 for audio traffic then enter the port range using this format: **49152:57500**.</span></span> <span data-ttu-id="13576-136">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-136">Click **Finish**.</span></span>

<span data-ttu-id="13576-137">오디오 트래픽에 대 한 QoS 정책을 만든 후에는 비디오 트래픽에 대 한 두 번째 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-137">After you have created the QoS policy for audio traffic you should create a second policy for video traffic.</span></span> <span data-ttu-id="13576-138">비디오에 대 한 정책을 만들려면 오디오 정책을 만들 때 팔 로우 하는 기본 절차를 따르고 다음과 같이 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-138">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="13576-139">다른 고유 정책 이름 (예: **Lync Server 비디오**)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-139">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="13576-140">DSCP 값을 46 대신 **34** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-140">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="13576-141">(DSCP 값 34를 사용 하지 않아도 된다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="13576-141">(Note that you do not have to use a DSCP value of 34.</span></span> <span data-ttu-id="13576-142">유일한 요구 사항은 오디오에 사용 하는 것 보다 비디오에 다른 DSCP 값을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="13576-142">The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="13576-143">비디오 트래픽에 이전에 구성한 포트 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-143">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="13576-144">예를 들어 비디오에 대해 65535 57501를 예약한 포트를 사용 하는 경우 포트 범위를 다음으로 설정: **57501:65535**.</span><span class="sxs-lookup"><span data-stu-id="13576-144">For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**.</span></span> <span data-ttu-id="13576-145">이는 대상 포트 범위로 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-145">Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="13576-146">응용 프로그램 공유 트래픽을 관리 하기 위한 정책을 만들려는 경우 세 번째 정책을 만들어 다음과 같이 대체 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-146">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="13576-147">다른 고유 정책 이름 (예: **Lync Server 응용 프로그램 공유**)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-147">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="13576-148">46 대신 DSCP 값을 **24** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-148">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="13576-149">(다시 한번, DSCP 값 24를 사용할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13576-149">(Again, you do not have to use a DSCP value of 24.</span></span> <span data-ttu-id="13576-150">유일한 요구 사항은 오디오 또는 비디오에 사용 하는 것과는 다른 DSCP 값을 응용 프로그램 공유에 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="13576-150">The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="13576-151">비디오 트래픽에 이전에 구성한 포트 범위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-151">Use the previously-configured port range for video traffic.</span></span> <span data-ttu-id="13576-152">예를 들어 응용 프로그램 공유에 대해 포트 40803 ~ 49151을 (를) 예약한 경우 포트 범위를 this: **40803:49151**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-152">For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="13576-153">사용자가 만든 새 정책은 Edge 서버에서 그룹 정책이 새로 고쳐질 때까지 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13576-153">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers.</span></span> <span data-ttu-id="13576-154">그룹 정책은 주기적으로 자체적으로 새로 고쳐지고 그룹 정책을 새로 고쳐야 하는 각 컴퓨터에서 다음 명령을 실행 하 여 즉시 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13576-154">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="13576-155">이 명령은 Lync Server 내에서 또는 관리자 자격 증명으로 실행 되는 명령 창에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13576-155">This command can be run from within the Lync Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="13576-156">명령 창을 관리자 자격 증명으로 실행 하려면 **시작**을 클릭 하 고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-156">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="13576-157">Gpudate을 실행 한 후에도 Edge 서버를 다시 시작 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13576-157">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="13576-158">네트워크 패킷이 적절 한 DSCP 값으로 표시 되도록 하려면 다음 절차를 완료 하 여 각 컴퓨터에 새 레지스트리 항목을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-158">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="13576-159">**시작** 을 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-159">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="13576-160">**실행** 대화 상자에서 **regedit** 를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="13576-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="13576-161">레지스트리 편집기에서 **\_HKEY\_LOCAL MACHINE**을 확장 하 고 **시스템**, **CurrentControlSet**를 차례로 확장 한 다음 **서비스**를 확장 한 다음 **Tcpip**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-161">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="13576-162">**Tcpip**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **키**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-162">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="13576-163">새 레지스트리 키가 만들어지면 **QoS** 를 입력 한 다음 enter 키를 눌러 키의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="13576-163">After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="13576-164">**QoS**를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **문자열 값**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-164">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="13576-165">새 레지스트리 값을 만든 후에는 **NLA를 사용 하지 않음을** 입력 하 고 enter 키를 눌러 값의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="13576-165">After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="13576-166">**NLA 사용 안 함**을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-166">Double-click **Do no use NLA**.</span></span> <span data-ttu-id="13576-167">**문자열 편집** 대화 상자의 **값 데이터** 상자에 **1** 을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-167">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="13576-168">레지스트리 편집기를 닫은 다음 컴퓨터를 다시 부팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="13576-168">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

