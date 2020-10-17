---
title: 'Lync Server 2013: 회의, 응용 프로그램 및 중재 서버에 대 한 서비스 품질 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your Conferencing, Application, and Mediation servers
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205076(v=OCS.15)
ms:contentKeyID: 48184769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ca1e1e243fe6957fdc5233b248c358d82817516
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508875"
---
# <a name="configuring-a-quality-of-service-policy-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="8d1bf-102">Lync Server 2013에서 회의, 응용 프로그램 및 중재 서버에 대 한 서비스 품질 정책 구성</span><span class="sxs-lookup"><span data-stu-id="8d1bf-102">Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d1bf-103">_**마지막으로 수정 된 항목:** 2014-06-23_</span><span class="sxs-lookup"><span data-stu-id="8d1bf-103">_**Topic Last Modified:** 2014-06-23_</span></span>

<span data-ttu-id="8d1bf-p101">포트 범위를 구성하면 지정된 유형의 모든 트래픽(예: 모든 오디오 트래픽)이 동일한 포트 집합을 통과하도록 보장하여 QoS(서비스 품질)를 쉽게 사용할 수 있습니다. 이렇게 하면 시스템에서 특정 패킷을 쉽게 식별하고 표시할 수 있습니다. 포트 49152가 오디오 트래픽을 위해 예약된 경우 포트 49152를 통과하는 모든 패킷에 이 패킷이 오디오 패킷임을 나타내는 DSCP 코드를 표시할 수 있습니다. 이렇게 하면 라우터가 패킷을 오디오 패킷으로 식별하고 표시되지 않은 패킷(예: 서버 간 파일 복사에 사용되는 패킷)보다 높은 우선 순위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-p101">Configuring port ranges facilitates the use of Quality of Service by ensuring that all traffic of a specified type (for example, all audio traffic) travels through the same set of ports. This makes it easy for the system to identify and mark a given packet: if port 49152 is reserved for audio traffic, then any packet traveling through port 49152 can be marked with a DSCP code that indicates that this is an audio packet. In turn, this enables routers to identify the packet as an audio packet, and give it higher priority than unmarked packets (such as packets used to copy a file from one server to another).</span></span>

<span data-ttu-id="8d1bf-107">하지만 단순히 포트 집합을 특정 트래픽 유형으로 제한하는 것만으로는 패킷이 적절한 DSCP 코드로 표시된 포트를 통과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-107">However, simply restricting a set of ports to a specific type of traffic does not result in packets traveling through those ports being marked with the appropriate DSCP code.</span></span> <span data-ttu-id="8d1bf-108">포트 범위를 정의하는 것 외에도 각 포트 범위와 연결할 DSCP 코드를 지정하는 QoS(서비스 품질) 정책을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-108">In addition to defining port ranges you must also create Quality of Service policies that specify the DSCP code to be associated with each port range.</span></span> <span data-ttu-id="8d1bf-109">Microsoft Lync Server 2013의 경우 일반적으로 오디오 용 1과 비디오용으로 각각 하나씩 두 개의 정책을 만드는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-109">For Microsoft Lync Server 2013 that typically means creating two policies: one for audio and one for video.</span></span>

<span data-ttu-id="8d1bf-110">QoS(서비스 품질) 정책은 그룹 정책을 사용해서 가장 쉽게 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-110">Quality of Service policies are most-easily created, and managed, by using Group Policy.</span></span> <span data-ttu-id="8d1bf-111">로컬 보안 정책을 사용해서도 이와 동일한 정책을 만들 수 있지만 이렇게 하려면 모든 컴퓨터에서 동일한 절차를 반복해서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-111">(These same policies can also be created by using local security policies.</span></span> <span data-ttu-id="8d1bf-112">그러나이 경우 각 컴퓨터에서 동일한 절차를 반복 해야 합니다. 초기 QoS 정책 집합 (오디오 및 비디오용)은 회의 서버, 응용 프로그램 서버 및/또는 중재 서버 서비스를 실행 하는 Lync Server 컴퓨터에만 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-112">However, that requires you to repeat the same procedure on each and every computer.) Your initial set of QoS policies (one for audio and one for video) should be applied only to Lync Server computers running the Conferencing server, Application server, and/or Mediation server services.</span></span> <span data-ttu-id="8d1bf-113">또는 다른 단계에 따라 지정된 컴퓨터로 새 정책의 대상을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-113">If all of these computers are located in the same Active Directory OU then you can simply assign the new Group Policy object (GPO) to that OU.</span></span> <span data-ttu-id="8d1bf-114">예를 들어 보안 그룹에 적절한 컴퓨터를 배치한 후 그룹 정책 보안 필터링을 사용해서 GPO를 해당 보안 그룹에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-114">Alternatively, you can take other steps to target the new policy to the specified computers; for example, you can place the appropriate computers in a security group, then use Group Policy security filtering to apply the GPO just to that security group.</span></span>

<span data-ttu-id="8d1bf-115">오디오 관리를 위해 QoS(서비스 품질) 정책을 만들려면 그룹 정책 관리가 설치된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-115">In order to create a Quality of Service policy for managing audio, log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="8d1bf-116">**시작**을 클릭 하 고 **관리 도구**를 가리킨 다음 **그룹 정책 관리**를 클릭 하 여 그룹 정책 관리를 열고 다음 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-116">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**) and then complete the following procedure:</span></span>

1.  <span data-ttu-id="8d1bf-p105">그룹 정책 관리에서 새 정책을 만들 컨테이너를 찾습니다. 예를 들어 모든 Lync Server 컴퓨터가 Lync Server라는 OU에 있는 경우에는 새 정책을 Lync Server OU에서 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-p105">In Group Policy Management, locate the container where the new policy should be created. For example, if all your Lync Server computers are located in an OU named Lync Server then the new policy should be created in the Lync Server OU.</span></span>

2.  <span data-ttu-id="8d1bf-119">적절한 컨테이너를 마우스 오른쪽 단추로 클릭하고 **이 도메인에서 GPO를 만들어 여기에 연결**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-119">Right-click the appropriate container and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="8d1bf-120">**새 GPO** 대화 상자에서 **이름** 상자에 새 그룹 정책 개체의 이름 (예: **Lync Server QoS**)을 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-120">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box (for example, **Lync Server QoS**) and then click **OK**.</span></span>

4.  <span data-ttu-id="8d1bf-121">새로 만든 정책을 마우스 오른쪽 단추로 클릭한 다음 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-121">Right-click the newly-created policy and then click **Edit**.</span></span>

5.  <span data-ttu-id="8d1bf-122">그룹 정책 관리 편집기에서 **컴퓨터 구성**, **정책**, **Windows 설정**을 확장하고 **정책 기반 QoS**를 확장하고 **새 정책 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-122">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Policies**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="8d1bf-123">**정책 기반 QoS** 대화 상자의 열기 페이지에서 **이름** 상자에 새 정책 이름 (예: **Lync Server QoS**)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-123">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy (e.g., **Lync Server QoS**) in the **Name** box.</span></span> <span data-ttu-id="8d1bf-124">**DSCP 값 지정**을 선택하고 값을 **46**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-124">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="8d1bf-125">**아웃바운드 스로틀 속도 지정**을 선택하지 않은 상태로 두고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-125">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="8d1bf-p107">다음 페이지에서 **모든 응용 프로그램**이 선택되었는지 확인한 후 **다음**을 클릭합니다. 이렇게 하면 모든 응용 프로그램이 지정된 DSCP 코드로 지정된 포트 범위의 패킷과 일치하도록 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-p107">On the next page, make sure that **All applications** is selected and then click **Next**. This simply ensures that all applications will match packets from the specified port range with the specified DSCP code.</span></span>

8.  <span data-ttu-id="8d1bf-p108">세 번째 페이지에서는 **모든 원본 IP 주소 및 모든 대상 IP 주소**가 모두 선택되었는지 확인한 후 **다음**을 클릭합니다. 이러한 두 설정은 해당 패킷을 전송하는 컴퓨터(IP 주소) 및 패킷을 수신하는 컴퓨터(IP 주소)에 관계없이 패킷이 관리되도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-p108">On the third page, make sure that both **Any source IP address and Any destination IP address** are selected and then click **Next**. These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="8d1bf-130">4페이지에서는 **이 QoS 정책이 적용되는 프로토콜 선택** 드롭다운 목록에서 **TCP 및 UDP**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-130">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="8d1bf-131">TCP (전송 제어 프로토콜) 및 UDP (사용자 데이터 그램 프로토콜)는 Lync Server 및 해당 클라이언트 응용 프로그램에서 가장 일반적으로 사용 하는 두 가지 네트워킹 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-131">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Lync Server and its client applications.</span></span>

10. <span data-ttu-id="8d1bf-p110">**원본 포트 번호 지정** 제목 아래에서 **이 원본 포트 또는 범위부터**를 선택합니다. 포함된 텍스트 상자에는 오디오 전송에 예약된 포트 범위를 입력합니다. 예를 들어 오디오 트래픽에 대해 포트 49152 ~ 57500을 예약한 경우 **49152:57500** 형식으로 포트 범위를 입력합니다. **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-p110">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 49152 through ports 57500 for audio traffic enter the port range using this format: **49152:57500**. Click **Finish**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d1bf-p111">DSCP 값 46은 다소 추상적입니다. DSCP 46은 오디오 패킷에 자주 사용되지만 오디오 통신에 DSCP 46을 사용할 필요는 없습니다. 이미 QoS를 구현했고 오디오에 다른 DSCP 코드를 사용 중인 경우(예: DSCP 40) 해당 코드를 사용하도록(예: 오디오에 40 사용) QoS(서비스 품질) 정책을 구성해야 합니다. 이제 막 QoS(서비스 품질)를 구현하는 경우에는 46이 오디오 패킷을 표시하는 데 일반적으로 사용되므로 오디오에 대해 DSCP 46을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-p111">The DSCP value of 46 is somewhat arbitrary: although DSCP 46 is often used for marking audio packets, you do not have to use DSCP 46 for audio communications. If you have already implemented QoS and you are using a different DSCP code for audio (for example, DSCP 40) then you should configure your Quality of Service policy to use that same code (i.e., 40 for audio). If you are just now implementing Quality of Service, then it is recommended that you use DSCP 46 for audio, simply because that value is commonly used to mark audio packets.</span></span>



</div>

<span data-ttu-id="8d1bf-p112">오디오 트래픽에 대한 QoS 정책을 만든 후에는 비디오 트래픽에 대한 두 번째 정책을 만들어야 합니다(선택적으로 응용 프로그램 공유 트래픽 관리를 위한 세 번째 정책도 만들 수 있음). 비디오에 대한 정책을 만들려면 오디오 정책을 만들 때 수행한 것과 동일한 절차를 따르고 다음과 같은 값을 바꿔서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-p112">After you have created the QoS policy for audio traffic you should then create a second policy for video traffic (and, optionally, a third policy for managing application sharing traffic). To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="8d1bf-141">다른(그리고 고유한) 정책 이름을 사용합니다(예: **Lync Server Video**).</span><span class="sxs-lookup"><span data-stu-id="8d1bf-141">Use a different (and unique) policy name (for example, **Lync Server Video**).</span></span>

  - <span data-ttu-id="8d1bf-p113">DSCP 값을 46 대신 **34**로 설정합니다. DSCP 값으로 반드시 34를 사용해야 하는 것은 아닙니다. 비디오에 대해 오디오에 사용한 것과 다른 DSCP 값을 사용하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-p113">Set the DSCP value to **34** instead of 46. (Note that you do not have to use a DSCP value of 34. The only requirement is that you use a different DSCP value for video than you used for audio.)</span></span>

  - <span data-ttu-id="8d1bf-p114">비디오 트래픽에 대해 이전에 구성한 포트 범위를 사용합니다. 예를 들어 비디오에 대해 포트 57501 ~ 65535를 예약한 경우 **57501:65535**와 같이 포트 범위를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-p114">Use the previously-configured port range for video traffic. For example, if you have reserved ports 57501 through 65535 for video, then set the port range to this: **57501:65535**.</span></span>

<span data-ttu-id="8d1bf-147">응용 프로그램 공유 트래픽을 관리하기 위한 정책을 만들 경우 세 번째 정책을 만들고 다음과 같은 항목을 바꿔서 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-147">If you decide to create a policy for managing application sharing traffic you must create a third policy, making the following substitutions:</span></span>

  - <span data-ttu-id="8d1bf-148">위의 두 정책과는 다른 고유한 정책 이름(예: **Lync Server 응용 프로그램 공유**)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-148">Use a different (and unique) policy name (for example, **Lync Server Application Sharing**).</span></span>

  - <span data-ttu-id="8d1bf-p115">DSCP 값을 46이 아닌 **24**로 설정합니다. DSCP 값 24를 반드시 사용할 필요는 없습니다. 오디오나 비디오에 사용한 것과는 다른 DSCP 값을 응용 프로그램 공유에 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-p115">Set the DSCP value to **24** instead of 46. (Again, you do not have to use a DSCP value of 24. The only requirement is that you use a different DSCP value for application sharing than you used for audio or for video.)</span></span>

  - <span data-ttu-id="8d1bf-p116">비디오 트래픽용으로 이전에 구성한 포트 범위를 사용합니다. 예를 들어 응용 프로그램 공유용으로 포트 40803~49151를 예약한 경우 포트 범위를 **40803:49151**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-p116">Use the previously-configured port range for video traffic. For example, if you have reserved ports 40803 through 49151 for application sharing, then set the port range to this: **40803:49151**.</span></span>

<span data-ttu-id="8d1bf-154">새로 만든 정책은 Lync Server 컴퓨터에서 그룹 정책을 새로 고칠 때까지 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-154">The new policies you have created will not take effect until Group Policy has been refreshed on your Lync Server computers.</span></span> <span data-ttu-id="8d1bf-155">그룹 정책은 일정한 간격에 따라 자체적으로 새로 고쳐지기는 하지만, 그룹 정책을 새로 고쳐야 하는 각 컴퓨터에서 다음 명령을 실행하면 그룹 정책을 강제로 즉시 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-155">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="8d1bf-156">이 명령은 Lync Server 관리 셸 내에서 또는 관리자 자격 증명으로 실행 되는 명령 창에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-156">This command can be run from within the Lync Server Management Shell or from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="8d1bf-157">관리자 자격 증명을 사용한 명령 창을 실행하려면 **시작**을 클릭하고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭한 후 **관리자 권한으로 실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-157">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="8d1bf-158">새 QoS 정책이 적용되었는지 확인하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-158">To verify that the new QoS policies have been applied, do the following:</span></span>

1.  <span data-ttu-id="8d1bf-159">Lync Server 컴퓨터에서 **시작**을 클릭한 후 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-159">On a Lync Server computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="8d1bf-160">**실행** 대화 상자에 **regedit**를 입력한 다음 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-160">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="8d1bf-161">레지스트리 편집기에서 **컴퓨터**를 확장 하 고 **, HKEY \_ 로컬 \_ 컴퓨터**, **소프트웨어**, **정책**, **Microsoft**, **Windows**를 차례로 확장 한 다음 **QoS**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-161">In Registry Editor, expand **Computer**, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Policies**, expand **Microsoft**, expand **Windows**, and then click **QoS**.</span></span> <span data-ttu-id="8d1bf-162">**QoS** 아래에 바로 전에 만든 각 QoS 정책에 대한 레지스트리 키가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-162">Under **QoS** you should see registry keys for each of the QoS policies you just created.</span></span> <span data-ttu-id="8d1bf-163">예를 들어 두 개의 새 정책 (이름이 Lync Server Audio QoS와 다른 명명 된 Lync Server 비디오 QoS)을 만든 경우 Lync Server 오디오 QoS 및 Lync Server 비디오 QoS에 대 한 레지스트리 항목이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-163">For example, if you created two new policies (one named Lync Server Audio QoS and the other named Lync Server Video QoS) you should registry entries for Lync Server Audio QoS and Lync Server Video QoS.</span></span>

<span data-ttu-id="8d1bf-164">네트워크 패킷이 적절한 DSCP 값으로 표시되도록 하려면 다음 절차를 완료하여 각 컴퓨터에서 새 레지스트리 항목도 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-164">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="8d1bf-165">**시작**을 클릭한 다음 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-165">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="8d1bf-166">**실행** 대화 상자에 **regedit**를 입력한 다음 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-166">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="8d1bf-167">레지스트리 편집기에서 **HKEY \_ 로컬 \_ 컴퓨터**를 확장 하 고 **시스템**, **CurrentControlSet**, **서비스**를 차례로 확장 한 다음 **Tcpip**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-167">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="8d1bf-p120">**Tcpip**를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 다음 **키**를 클릭합니다. 새 레지스트리 키를 만든 후 **QoS**를 입력하고 Enter 키를 눌러 키 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-p120">Right-click **Tcpip**, point to **New**, and then click **Key**. After the new registry key is created, type **QoS** and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="8d1bf-p121">**QoS**를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 다음 **문자열 값**을 클릭합니다. 새 레지스트리 값을 만든 후 **NLA 사용 안 함**을 입력하고 Enter 키를 눌러 값 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-p121">Right-click **QoS**, point to **New**, and then click **String Value**. After the new registry value is created, type **Do not use NLA** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="8d1bf-172">**NLA 사용 안 함**을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-172">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="8d1bf-173">**문자열 편집** 대화 상자의 **값 데이터** 상자에 **1**을 입력한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-173">In the **Edit String** dialog box, type **1** in the **Value data** box and then click **OK**.</span></span>

7.  <span data-ttu-id="8d1bf-174">레지스트리 편집기를 닫고 컴퓨터를 다시 부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="8d1bf-174">Close the Registry Editor and then reboot your computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

