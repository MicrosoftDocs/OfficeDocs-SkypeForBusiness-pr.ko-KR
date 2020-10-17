---
title: Lync Server 2013 Enterprise Voice
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39179f1db1c547081e059d9b3ee275c924621cab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533175"
---
# <a name="enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="ac403-102">Lync Server 2013의 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="ac403-102">Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac403-103">_**마지막으로 수정 된 항목:** 2015-04-08_</span><span class="sxs-lookup"><span data-stu-id="ac403-103">_**Topic Last Modified:** 2015-04-08_</span></span>

<span data-ttu-id="ac403-104">Enterprise Voice를 사용 하는 경우 Lync Server에서는 기존 PBX (private branch exchange) 시스템을 향상 시키거나 교체 하기 위한 VoIP (독립 실행형 Voice over Internet Protocol)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-104">With Enterprise Voice, Lync Server delivers a stand-alone Voice over Internet Protocol (VoIP) offering to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="ac403-105">Enterprise Voice 사용자는 조직의 VoIP 네트워크 또는 PBX에서 동료에 게 전화를 걸 수 있으며 조직 외부의 일반 전화 번호로 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-105">Enterprise Voice users can call colleagues on your organization’s VoIP network or PBX, and they can call traditional phone numbers outside your organization.</span></span> <span data-ttu-id="ac403-106">Enterprise Voice solution에는 answer, forward, transfer, 보류, divert, 릴리스 및 대기 및 향상 된 9-1-1 (E9-1-1) 통화와 같은 일반적인 통화 기능이 포함 되어 있습니다 (E9-1,-1은 미국 에서만 사용 가능). 또한 Enterprise Voice에서는 다양 한 범위의 현재 및 오래 된 IP 및 USB 장치를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-106">The Enterprise Voice solution includes common calling features such as answer, forward, transfer, hold, divert, release and park, and Enhanced 9-1-1 (E9-1-1) calling (E9-1-1 is available only in the United States.) Enterprise Voice also supports a broad range of current and older IP and USB devices.</span></span>

<div>

## <a name="placing-and-receiving-calls"></a><span data-ttu-id="ac403-107">전화 걸기 및 받기</span><span class="sxs-lookup"><span data-stu-id="ac403-107">Placing and Receiving Calls</span></span>

<span data-ttu-id="ac403-108">Lync를 사용 하면 사용자가 키보드에 이름 또는 전화 번호를 입력 하거나 화면에 표시 되는 다이얼 패드를 사용 하 여 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-108">Using Lync, users can place calls by typing a name or phone number on their keyboard, or using a dial pad displayed on their screen.</span></span> <span data-ttu-id="ac403-109">사용자는 또한 대화 상대 목록에서 직접 통화를 시작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-109">Users can also initiate calls directly from their Contacts list.</span></span> <span data-ttu-id="ac403-110">Microsoft 파트너가 제공 하는 독립 실행형 IP 전화 장치인 Lync Phone Edition 장치를 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-110">You can also deploy Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

<span data-ttu-id="ac403-111">사용자는 Lync Server에 등록 된 여러 전화 장치를 사용할 수 있으며,이를 쉽게 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-111">Users can have multiple phone devices registered with Lync Server, and can switch between them easily.</span></span>

<span data-ttu-id="ac403-112">사용자는 IP 전화 장치의 사용자 지정 가능한 벨 소리와 PC의 메신저와 유사한 알림을 통해 모든 장치에 걸려오는 전화에 대한 알림을 동시에 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-112">Users are alerted to incoming calls on all their devices simultaneously, with customizable ringtones on IP phone devices and a notification similar to an instant message on their PC.</span></span>

<span data-ttu-id="ac403-113">사용자는 또한 일반 전화기, PC 및 휴대폰에 연결되는 단일 전화 번호를 설정하여 어디에 있든지 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-113">Users can also set a single telephone number that connects to their desk phone, PC and mobile phone, so they can be reached no matter where they are.</span></span>

</div>

<div>

## <a name="basic-call-features"></a><span data-ttu-id="ac403-114">기본 통화 기능</span><span class="sxs-lookup"><span data-stu-id="ac403-114">Basic Call Features</span></span>

<span data-ttu-id="ac403-p103">사용자는 통화 중일 때 또 다른 수신 전화에 응답하거나 발신 통화를 시작할 수 있으며 기존의 활성 통화는 자동으로 대기합니다. 직접 또는 첫 번째 사용자가 개인적으로 두 번째 사용자에게 말한 후 다른 사용자에게 통화를 전송할 수 있습니다. 사용자는 또한 다른 장치에 통화를 전송할 수도 있습니다. 예를 들어 사무실을 나오면서 활성 통화를 휴대폰으로 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-p103">While on a call, a user can answer additional incoming calls or initiate outgoing calls, and the existing active call is automatically put on hold. Calls can be transferred from one user to another, either directly or after the first user speaks privately with the second user. Users can also transfer calls to another device; for example, they could transfer an active call to their mobile phone as they walk out the door of their office.</span></span>

</div>

<div>

## <a name="richer-communications"></a><span data-ttu-id="ac403-118">더욱 풍부한 커뮤니케이션</span><span class="sxs-lookup"><span data-stu-id="ac403-118">Richer Communications</span></span>

<span data-ttu-id="ac403-119">Lync를 사용 하 여 다른 사용자와 대화할 때 사용자는 통화에 텍스트, 비디오 또는 데스크톱 공유를 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-119">When talking to another user with Lync, users can easily add text, video, or desktop sharing to the call.</span></span> <span data-ttu-id="ac403-120">[방해 금지] 기능은 Lync의 현재 상태 설정에 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-120">The Do-Not-Disturb feature is integrated with the presence settings in Lync.</span></span>

<span data-ttu-id="ac403-121">Exchange UM (통합 메시징)을 사용 하 여 Lync 및 Lync Server와 microsoft Exchange Server 2013 및 Microsoft Outlook 2013을 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-121">With Exchange Unified Messaging (UM), Lync and Lync Server integrate with Microsoft Exchange Server 2013 and Microsoft Outlook 2013.</span></span> <span data-ttu-id="ac403-122">사용자는 Lync 창 및 전자 메일에 모두 새 음성 메일이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-122">Users can see if they have new voice mail both in their Lync window and in email.</span></span> <span data-ttu-id="ac403-123">전자 메일의 경우 전자 메일 메시지에서 음성 메일 오디오를 클릭하여 재생하거나 음성 메일 메시지의 대화 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-123">While in email they can click to play the voice mail audio in an email message, or view a transcript of the voice mail message.</span></span>

</div>

<div>

## <a name="advanced-calling-features"></a><span data-ttu-id="ac403-124">고급 통화 기능</span><span class="sxs-lookup"><span data-stu-id="ac403-124">Advanced Calling Features</span></span>

<span data-ttu-id="ac403-125">Enterprise Voice에는 Lync call 위임, 팀 호출, 그룹 통화 픽업 및 응답 그룹과 같은 몇 가지 고급 통화 기능도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-125">Enterprise Voice includes several advanced calling features as well, such as Lync call delegation, team calling, Group Call Pickup, and Response Groups.</span></span>

<span data-ttu-id="ac403-126">Lync 호출 위임을 사용 하면 사용자가 **도구** \> **옵션** \> **착신 전환 설정**으로 이동 하 여 하나 이상의 도우미에 대 한 통화 처리를 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-126">Lync call delegation enables users to delegate call handling to one or more assistants, by going to **Tools** \> **Options** \> **Call Forwarding Settings**.</span></span> <span data-ttu-id="ac403-127">대리인은 사용자를 대신해서 통화 차단, 전화 걸기 및 회의 시작을 포함한 여러 통화 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-127">The delegate can perform multiple calling tasks on behalf of the user, including screening calls, placing calls, and initiating conferences.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ac403-128">이와 유사한 다른 명명 된 기능인 Lync 일정 위임도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-128">You may be looking for another similarly named feature, Lync calendar delegation.</span></span> <span data-ttu-id="ac403-129">Enterprise Voice 기능이 필요 하지 않으며 사용자가 Outlook에서 온라인 Lync 모임을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-129">It doesn't require the Enterprise Voice feature and does allow users to schedule online Lync meetings from Outlook.</span></span> <span data-ttu-id="ac403-130">여기에서 해당 정보를 찾고 있다면 Exchange 위임 동기화를 사용 하도록 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">설정</A> 하는 방법에 대 한 정보를 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-130">If you've come here looking for that info, we recommend checking out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> for information on enabling Exchange delegate sync.</span></span>



</div>

<span data-ttu-id="ac403-131">팀 호출 기능을 사용 하면 팀의 모든 사용자가 통화에 응답할 수 있도록 받는 사람의 전화에 게 동시에 수신 전화를 연결 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-131">Team calling enables a user to have incoming calls simultaneously ring the phones of teammates so that anyone on the team can answer the call.</span></span>

<span data-ttu-id="ac403-132">Lync Server 2013 년 2 2013 월에 대 한 누적 업데이트의 새로운 기능인 그룹 호출 Pickup에서는 사용자가 자신의 휴대폰에서 자신의 동료에 게 들어오는 호출에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-132">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="ac403-133">그룹 통화 Pickup은 들어오는 전화가 의도 한 받는 사람의 휴대폰 에서만 울릴 수 있다는 점에서 팀 호출과는 다르며, 다른 모든 사용자는 통화 픽업 그룹 번호를 사용 하 여 전화를 걸어 응답 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-133">Group Call Pickup differs from team calling primarily in that an incoming call rings only at the intended recipient's phone, but any other user can choose to answer it by dialing a call pickup group number.</span></span>

<span data-ttu-id="ac403-p109">통화를 지정된 에이전트에 대기시키고 지능적으로 라우팅하도록 응답 그룹을 설정할 수 있습니다. 일반적으로 IT 헬프데스크, 인사 부서 직통 전화 및 기타 내부 연락 센터에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-p109">Response Groups can be set up for queuing and intelligently routing calls to designated agents. Common uses include IT helpdesks, human resources hotlines, and other internal contact centers.</span></span>

</div>

<div>

## <a name="enterprise-voice-administration"></a><span data-ttu-id="ac403-136">Enterprise Voice 관리</span><span class="sxs-lookup"><span data-stu-id="ac403-136">Enterprise Voice Administration</span></span>

<span data-ttu-id="ac403-137">Lync Server는 표준 및 게시 된 인터페이스를 사용 하 여 기존 인프라와 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-137">Lync Server uses standards and published interfaces to interoperate with existing infrastructure.</span></span> <span data-ttu-id="ac403-138">IP PBX 시스템 및 PSTN 네트워크에 대한 상호 연결에 게이트웨이 및 SIP 옵션(예: SIP 트렁크)을 지원하므로 중단을 최소화하면서 사용자를 천천히 Enterprise Voice로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-138">It supports both gateway and SIP options (such as SIP trunking) for interconnection to IP PBX systems and the PSTN networks, so that you can migrate users to Enterprise Voice over time, while minimizing disruption.</span></span> <span data-ttu-id="ac403-139">Lync Server는 전통적인 VoIP 솔루션과의 상호 운용성을 위해 g.711, 722 및 g.723.1와 같은 전통적인 코덱을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-139">Lync Server supports traditional codecs such as G.711, G.722, and G.723.1 for interoperability with traditional VoIP solutions.</span></span>

<span data-ttu-id="ac403-140">CAC (통화 허용 제어)를 사용 하는 경우 관리자는 제한 된 네트워크 링크에서 수행 되는 Lync Server 음성 및 비디오 트래픽 크기에 대 한 제한을 설정 하 고 새 통화가 제한을 초과 하는 경우 수행할 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-140">With call admission control (CAC), administrators can set limits on the amount of Lync Server voice and video traffic carried on constrained network links, and specify the action to be taken if a new call would exceed the limit.</span></span> <span data-ttu-id="ac403-141">이러한 작업에는 대체 경로를 사용한 라우팅 또는 통화 거부가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-141">The actions could include routing by an alternate path, or refusing the call.</span></span>

<span data-ttu-id="ac403-142">Lync Server는 타사 Sba (survivable 분기 기기와 함께 작동 하 여 중앙 사이트에서 WAN 오류가 발생 하는 경우 지사에서 로컬 통화 서비스 및 PSTN에 대 한 연결을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac403-142">Lync Server works with third-party Survivable Branch Appliances to provide local calling services and connection to PSTN at branch offices, in case of WAN failure at the central site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

