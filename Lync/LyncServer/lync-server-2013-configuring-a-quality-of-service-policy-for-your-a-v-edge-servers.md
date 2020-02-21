---
title: A/V에 지 서버에 대 한 서비스 품질 정책 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30fece45c4b13bd9cd2c9243dd21cdac1d779733
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="13366-102">Lync Server 2013에서 A/V에 지 서버에 대 한 서비스 품질 정책 구성</span><span class="sxs-lookup"><span data-stu-id="13366-102">Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13366-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="13366-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="13366-p101">회의, 응용 프로그램 및 중재 서버용 QoS 정책을 만드는 것 외에도 A/V 에지 서버의 내부용으로 오디오 및 비디오 정책 역시 만들어야 합니다. 그러나 에지 서버에서 사용되는 정책은 회의, 응용 프로그램 및 중재 서버에서 사용되는 정책과는 다릅니다. 회의, 응용 프로그램 및 중재 서버의 경우에는 원본 포트 범위를 지정했지만, 에지 서버에서는 대상 포트 범위를 지정해야 합니다. 따라서 단순히 회의, 응용 프로그램 및 중재 서버 QoS 정책을 에지 서버에 적용할 수는 없으며 이러한 정책은 작동하지 않습니다. 대신 새 정책을 만들어 에지 서버에만 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-p101">In addition to creating QoS policies for your Conferencing, Application, and Mediation servers, you must also create both audio and video policies for the internal side of your A/V Edge servers. However, the policies used on your Edge servers are different from the policies used on your Conferencing, Application, and Mediation servers. For the Conferencing, Application, and Mediation servers you specified a source port range; with Edge servers, you need to specify a destination port range. Because of that you cannot simply apply the Conferencing, Application, and Mediation server QoS policies to your Edge servers: these policies simply won't work. Instead, you must create new policies and apply those policies to your Edge servers only.</span></span>

<span data-ttu-id="13366-p102">다음 절차에서는 에지 서버에서 서비스 품질을 관리하는 데 사용할 수 있는 Active Directory 그룹 정책 개체를 만드는 프로세스를 설명합니다. 물론 에지 서버가 Active Directory 계정을 포함하지 않는 독립 실행형 서버일 수도 있습니다. 이 경우에는 Active Directory 그룹 정책 대신 로컬 그룹 정책을 사용하면 되며, 두 경우의 차이점은 이러한 로컬 정책의 경우 로컬 그룹 정책 편집기를 사용하여 만들어야 하며 각 에지 서버에서 동일한 정책 집합을 개별적으로 만들어야 한다는 것뿐입니다. 에지 서버에서 로컬 그룹 정책 편집기를 시작하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-p102">The following procedure describes the process for creating Active Directory Group Policy objects that can be used to manage Quality of Service on Edge Servers. Of course, it's possible that your Edge servers are stand-alone servers that do not have Active Directory accounts. If that's the case, you can use local Group Policy instead of Active Directory Group Policy: the only difference is that you must create these local policies using the Local Group Policy Editor, and must individually create the same set of policies on each Edge Server. To start the Local Group Policy Editor on an Edge server do the following:</span></span>

1.  <span data-ttu-id="13366-113">**시작**을 클릭한 다음 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-113">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="13366-114">**실행** 대화 상자에 **gpedit.msc**를 입력한 다음 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="13366-114">In the **Run** dialog box, type **gpedit.msc** and then press ENTER.</span></span>

<span data-ttu-id="13366-p103">Active Directory 기반 정책을 만드는 경우에는 그룹 정책 관리가 설치된 컴퓨터에 로그온해야 합니다. 이 경우 **시작**을 클릭하고 **관리 도구**를 가리킨 다음 **그룹 정책 관리**를 클릭하여 그룹 정책 관리를 열고 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-p103">If you are creating Active Directory-based policies, then you should log on to a computer where Group Policy Management has been installed. In that case, open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following steps:</span></span>

1.  <span data-ttu-id="13366-p104">그룹 정책 관리에서 새 정책을 만들 컨테이너를 찾습니다. 예를 들어 모든 Lync Server 컴퓨터가 Lync Server라는 OU에 있는 경우에는 새 정책을 Lync Server OU에서 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-p104">In Group Policy Management, locate the container where the new policy should be created. For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="13366-119">적절한 컨테이너를 마우스 오른쪽 단추로 클릭하고 **이 도메인에서 GPO를 만들어 여기에 연결**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="13366-120">**새 GPO** 대화 상자의 **이름** 상자에 새 그룹 정책 개체의 이름을 **Lync Server 오디오**와 같이 입력하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server Audio**) and then click **OK**.</span></span>

4.  <span data-ttu-id="13366-121">새로 만든 정책을 마우스 오른쪽 단추로 클릭하고 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-121">Right-click the newly-created policy and then click **Edit**.</span></span>

<span data-ttu-id="13366-122">여기서부터는 Active Directory 정책을 만들든 로컬 정책을 만들든 관계없이 프로세스가 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-122">From here the process is identical regardless of whether you are creating an Active Directory policy or a local policy:</span></span>

1.  <span data-ttu-id="13366-123">그룹 정책 관리 편집기 또는 로컬 그룹 정책 편집기에서 **컴퓨터 구성**, **정책**, **Windows 설정**을 차례로 확장하고 **정책 기반 QoS**를 마우스 오른쪽 단추로 클릭한 후에 **새 정책 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-123">In the Group Policy Management Editor or the Local Group Policy Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

2.  <span data-ttu-id="13366-p105">**정책 기반 QoS** 대화 상자의 시작 페이지에서 새 정책의 이름(예: **Lync Server 오디오**)을 **이름** 상자에 입력합니다. **DSCP 값 지정**을 선택하고 값을 **46**으로 설정합니다. **아웃바운드 스로틀 속도 지정**은 선택되지 않은 상태로 두고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-p105">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server Audio**) in the **Name** box. Select **Specify DSCP Value** and set the value to **46**. Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

3.  <span data-ttu-id="13366-p106">다음 페이지에서 **모든 응용 프로그램**이 선택되어 있는지 확인하고 **다음**을 클릭합니다. 이 설정은 특정 응용 프로그램이 만든 패킷만이 아니라 DSCP 표시가 46인 모든 패킷을 찾도록 네트워크에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-p106">On the next page, make sure that **All applications** is selected and then click **Next**. This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

4.  <span data-ttu-id="13366-p107">세 번째 페이지에서는 **모든 원본 IP 주소** 및 **모든 대상 IP 주소**가 둘 다 선택되어 있는지 확인하고 **다음**을 클릭합니다 이 두 설정은 패킷을 보낸 컴퓨터(IP 주소) 및 받는 컴퓨터(IP 주소)에 관계없이 패킷이 관리되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-p107">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

5.  <span data-ttu-id="13366-131">4페이지에서는 **이 QoS 정책이 적용되는 프로토콜 선택** 드롭다운 목록에서 **TCP 및 UDP**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-131">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="13366-132">TCP (전송 제어 프로토콜) 및 UDP (사용자 데이터 그램 프로토콜)는 Lync Server 및 해당 클라이언트 응용 프로그램에서 가장 일반적으로 사용 하는 두 가지 네트워킹 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="13366-132">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

6.  <span data-ttu-id="13366-p109">**대상 포트 번호 지정** 제목 아래에서 **이 대상 포트 또는 범위부터**를 선택합니다. 그 옆의 텍스트 상자에는 오디오 전송용으로 예약된 포트 범위를 입력합니다. 예를 들어 오디오 트래픽용으로 포트 49152~57500을 예약한 경우 **49152:57500** 형식으로 포트 범위를 입력합니다. 그런 다음 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-p109">Under the heading **Specify the destination port number**, select **From this destination port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 49152 through ports 57500 for audio traffic then enter the port range using this format: **49152:57500**. Click **Finish**.</span></span>

<span data-ttu-id="13366-p110">오디오 트래픽용 QoS 정책을 만든 후에는 비디오 트래픽용으로 두 번째 정책을 만들어야 합니다. 비디오용 정책을 만들려면 오디오 정책을 만들 때 수행한 것과 기본적으로는 같은 절차를 따르되 다음 항목을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-p110">After you have created the QoS policy for audio traffic you should create a second policy for video traffic. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="13366-139">오디오 정책과는 다른 고유한 정책 이름(예: **Lync Server 비디오**)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-139">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="13366-p111">DSCP 값을 46이 아닌 **34**로 설정합니다. DSCP 값 34를 반드시 사용할 필요는 없습니다. 오디오에 사용한 것과는 다른 DSCP 값을 비디오에 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13366-p111">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="13366-p112">비디오 트래픽용으로 이전에 구성한 포트 범위를 사용합니다. 예를 들어 비디오용으로 포트 57501~65535를 예약한 경우 포트 범위를 **57501:65535**로 설정합니다. 이 범위 역시 대상 포트 범위로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-p112">Use the previously-configured port range for video traffic. For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**. Again, this should be configured as the destination port range.</span></span>

<span data-ttu-id="13366-146">응용 프로그램 공유 트래픽을 관리하기 위한 정책을 만들려는 경우에는 다음 항목을 대체하여 세 번째 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-146">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="13366-147">위의 두 정책과는 다른 고유한 정책 이름(예: **Lync Server 응용 프로그램 공유**)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-147">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="13366-p113">DSCP 값을 46이 아닌 **24**로 설정합니다. DSCP 값 24를 반드시 사용할 필요는 없습니다. 오디오나 비디오에 사용한 것과는 다른 DSCP 값을 응용 프로그램 공유에 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13366-p113">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="13366-p114">비디오 트래픽용으로 이전에 구성한 포트 범위를 사용합니다. 예를 들어 응용 프로그램 공유용으로 포트 40803~49151를 예약한 경우 포트 범위를 **40803:49151**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-p114">Use the previously-configured port range for video traffic. For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="13366-p115">새 정책은 에지 서버에서 그룹 정책을 새로 고쳐야 적용됩니다. 그룹 정책은 일정한 간격에 따라 자체적으로 새로 고쳐지기는 하지만, 그룹 정책을 새로 고쳐야 하는 각 컴퓨터에서 다음 명령을 실행하면 그룹 정책을 강제로 즉시 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13366-p115">The new policies you have created will not take effect until Group Policy has been refreshed on your Edge servers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="13366-155">이 명령은 Lync Server 또는 관리자 자격 증명으로 실행 되는 명령 창에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13366-155">This command can be run from within the Lync Server or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="13366-156">관리자 자격 증명을 사용한 명령 창을 실행하려면 **시작**을 클릭하고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭한 후 **관리자 권한으로 실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-156">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span> <span data-ttu-id="13366-157">Gpudate를 실행 한 후에도에 지 서버를 다시 시작 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13366-157">Note that you might need to restart the Edge server even after running Gpudate.exe.</span></span>

<span data-ttu-id="13366-158">네트워크 패킷이 적절한 DSCP 값으로 표시되도록 하려면 다음 절차를 완료하여 각 컴퓨터에서 새 레지스트리 항목도 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-158">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="13366-159">**시작**을 클릭하고 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-159">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="13366-160">**실행** 대화 상자에 **regedit**를 입력한 다음 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="13366-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="13366-161">레지스트리 편집기에서 **\_HKEY\_로컬 컴퓨터**를 확장 하 고 **시스템**, **CurrentControlSet**, **서비스**를 차례로 확장 한 다음 **Tcpip**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-161">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="13366-p117">**Tcpip**를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 다음 **키**를 클릭합니다. 새 레지스트리 키를 만든 후 **QoS**를 입력하고 Enter 키를 눌러 키 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="13366-p117">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="13366-p118">**QoS**를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 다음 **문자열 값**을 클릭합니다. 새 레지스트리 값을 만든 후 **NLA 사용 안 함**을 입력하고 Enter 키를 눌러 값 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="13366-p118">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="13366-p119">**NLA 사용 안 함**을 두 번 클릭합니다. **문자열 편집** 대화 상자의 **값 데이터** 상자에 **1**을 입력한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-p119">Double-click **Do no use NLA**. In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="13366-168">레지스트리 편집기를 닫고 컴퓨터를 다시 부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="13366-168">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

