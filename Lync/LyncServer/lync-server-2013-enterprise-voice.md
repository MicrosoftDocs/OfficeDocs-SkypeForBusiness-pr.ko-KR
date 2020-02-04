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
ms.openlocfilehash: e62224a7187c54222364045d0ac7b1aa70bccb9c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="2c82d-102">Lync Server 2013의 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="2c82d-102">Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c82d-103">_**마지막으로 수정한 주제:** 2015-04-08_</span><span class="sxs-lookup"><span data-stu-id="2c82d-103">_**Topic Last Modified:** 2015-04-08_</span></span>

<span data-ttu-id="2c82d-104">Lync Server는 엔터프라이즈 음성을 사용 하 여 기존 개인 분기 교환 (PBX) 시스템을 개선 하거나 바꾸기 위한 독립 실행형 VoIP (Voice over 인터넷 프로토콜)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-104">With Enterprise Voice, Lync Server delivers a stand-alone Voice over Internet Protocol (VoIP) offering to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="2c82d-105">엔터프라이즈 음성 사용자는 조직의 VoIP 네트워크 또는 PBX에서 동료에 게 전화를 걸 수 있으며 조직 외부의 일반 전화 번호로 통화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-105">Enterprise Voice users can call colleagues on your organization’s VoIP network or PBX, and they can call traditional phone numbers outside your organization.</span></span> <span data-ttu-id="2c82d-106">엔터프라이즈 음성 솔루션에는 answer, forward, transfer, 대기, 접속해, 릴리즈, 공원, 향상 된 9-1-1 (E9-1) 통화와 같은 일반적인 통화 기능이 포함 되어 있습니다 (E9-1-1은 미국 에서만 사용할 수 있음). 또한 Enterprise Voice는 다양 한 최신 및 구형 IP 및 USB 장치를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-106">The Enterprise Voice solution includes common calling features such as answer, forward, transfer, hold, divert, release and park, and Enhanced 9-1-1 (E9-1-1) calling (E9-1-1 is available only in the United States.) Enterprise Voice also supports a broad range of current and older IP and USB devices.</span></span>

<div>

## <a name="placing-and-receiving-calls"></a><span data-ttu-id="2c82d-107">전화 걸기 및 받기</span><span class="sxs-lookup"><span data-stu-id="2c82d-107">Placing and Receiving Calls</span></span>

<span data-ttu-id="2c82d-108">Lync를 사용 하 여 사용자는 키보드에 이름 또는 전화 번호를 입력 하거나 화면에 표시 되는 다이얼 패드를 사용 하 여 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-108">Using Lync, users can place calls by typing a name or phone number on their keyboard, or using a dial pad displayed on their screen.</span></span> <span data-ttu-id="2c82d-109">또한 사용자는 대화 상대 목록에서 직접 통화를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-109">Users can also initiate calls directly from their Contacts list.</span></span> <span data-ttu-id="2c82d-110">Microsoft 파트너가 제공 하는 독립 실행형 IP 전화 장치인 Lync Phone Edition 장치를 배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-110">You can also deploy Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

<span data-ttu-id="2c82d-111">사용자는 여러 개의 전화 장치를 Lync Server에 등록 하 여 쉽게 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-111">Users can have multiple phone devices registered with Lync Server, and can switch between them easily.</span></span>

<span data-ttu-id="2c82d-112">사용자는 IP 전화 장치의 사용자 지정 가능한 벨 소리와 PC의 인스턴트 메시지와 유사한 알림을 사용 하 여 모든 장치에서 수신 전화에 대 한 알림을 동시에 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-112">Users are alerted to incoming calls on all their devices simultaneously, with customizable ringtones on IP phone devices and a notification similar to an instant message on their PC.</span></span>

<span data-ttu-id="2c82d-113">또한 사용자는 일반 전화기, PC, 휴대 전화에 연결 하는 전화 번호를 설정 하 여 어디에서 든 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-113">Users can also set a single telephone number that connects to their desk phone, PC and mobile phone, so they can be reached no matter where they are.</span></span>

</div>

<div>

## <a name="basic-call-features"></a><span data-ttu-id="2c82d-114">기본 통화 기능</span><span class="sxs-lookup"><span data-stu-id="2c82d-114">Basic Call Features</span></span>

<span data-ttu-id="2c82d-115">통화 중에는 사용자가 추가 수신 전화에 응답 하거나, 나가는 통화를 시작할 수 있으며, 기존 활성 통화가 자동으로 대기 상태로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-115">While on a call, a user can answer additional incoming calls or initiate outgoing calls, and the existing active call is automatically put on hold.</span></span> <span data-ttu-id="2c82d-116">다른 사용자에 게 전화를 거는 경우 직접 또는 첫 사용자가 두 번째 사용자에 게 말할 때에만 통화를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-116">Calls can be transferred from one user to another, either directly or after the first user speaks privately with the second user.</span></span> <span data-ttu-id="2c82d-117">또한 사용자는 다른 장치로 통화를 전송할 수 있습니다. 예를 들어 활성 통화를 휴대 전화를 통해 사무실의 도어를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-117">Users can also transfer calls to another device; for example, they could transfer an active call to their mobile phone as they walk out the door of their office.</span></span>

</div>

<div>

## <a name="richer-communications"></a><span data-ttu-id="2c82d-118">다양 한 의사 소통</span><span class="sxs-lookup"><span data-stu-id="2c82d-118">Richer Communications</span></span>

<span data-ttu-id="2c82d-119">Lync를 사용 하 여 다른 사용자에 게 대화를 하는 경우 사용자는 통화에 텍스트, 비디오 또는 데스크톱 공유를 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-119">When talking to another user with Lync, users can easily add text, video, or desktop sharing to the call.</span></span> <span data-ttu-id="2c82d-120">방해 금지 기능은 Lync의 현재 상태 설정과 통합 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-120">The Do-Not-Disturb feature is integrated with the presence settings in Lync.</span></span>

<span data-ttu-id="2c82d-121">Exchange UM (통합 메시징)을 사용 하 여 Lync 및 Lync Server를 Microsoft Exchange Server 2013 및 Microsoft Outlook 2013과 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-121">With Exchange Unified Messaging (UM), Lync and Lync Server integrate with Microsoft Exchange Server 2013 and Microsoft Outlook 2013.</span></span> <span data-ttu-id="2c82d-122">사용자는 Lync 창 및 전자 메일에 새 음성 메일이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-122">Users can see if they have new voice mail both in their Lync window and in email.</span></span> <span data-ttu-id="2c82d-123">전자 메일에 있는 동안 전자 메일 메시지에서 음성 메일 오디오를 재생 하거나 음성 메일 메시지의 기록 보기를 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-123">While in email they can click to play the voice mail audio in an email message, or view a transcript of the voice mail message.</span></span>

</div>

<div>

## <a name="advanced-calling-features"></a><span data-ttu-id="2c82d-124">고급 통화 기능</span><span class="sxs-lookup"><span data-stu-id="2c82d-124">Advanced Calling Features</span></span>

<span data-ttu-id="2c82d-125">Enterprise Voice에는 Lync 통화 위임, 팀 통화, 그룹 통화 픽업, 응답 그룹 등의 다양 한 고급 통화 기능도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-125">Enterprise Voice includes several advanced calling features as well, such as Lync call delegation, team calling, Group Call Pickup, and Response Groups.</span></span>

<span data-ttu-id="2c82d-126">Lync 통화 위임을 통해 사용자는 **도구** \> **옵션** \> **착신 전환 설정**으로 전환 하 여 하나 이상의 도우미에 대 한 통화 처리를 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-126">Lync call delegation enables users to delegate call handling to one or more assistants, by going to **Tools** \> **Options** \> **Call Forwarding Settings**.</span></span> <span data-ttu-id="2c82d-127">대리인은 차단 통화, 통화 걸기, 회의 시작을 포함 하 여 사용자를 대신 하 여 여러 호출 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-127">The delegate can perform multiple calling tasks on behalf of the user, including screening calls, placing calls, and initiating conferences.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2c82d-128">유사한 다른 명명 된 기능, Lync 일정 위임을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-128">You may be looking for another similarly named feature, Lync calendar delegation.</span></span> <span data-ttu-id="2c82d-129">엔터프라이즈 음성 기능이 필요 하지 않으며 사용자가 Outlook에서 온라인 Lync 모임을 예약할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-129">It doesn't require the Enterprise Voice feature and does allow users to schedule online Lync meetings from Outlook.</span></span> <span data-ttu-id="2c82d-130">여기에서 해당 정보를 찾고 있다면 Exchange 대리인 동기화를 사용 하도록 설정 하는 방법에 대 한 정보에 대해 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> 를 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-130">If you've come here looking for that info, we recommend checking out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> for information on enabling Exchange delegate sync.</span></span>



</div>

<span data-ttu-id="2c82d-131">팀 통화를 통해 사용자는 팀의 모든 사용자가 전화를 받을 수 있도록 받는 사람의 전화를 동시에 착신 지를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-131">Team calling enables a user to have incoming calls simultaneously ring the phones of teammates so that anyone on the team can answer the call.</span></span>

<span data-ttu-id="2c82d-132">그룹 통화 픽업 (Lync Server 2013 2013 년 2 월)에 대 한 누적 업데이트의 새로운 기능인 사용자는 자신의 전화기에서 자신의 동료에 게 걸려오는 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-132">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="2c82d-133">그룹 통화는 받는 사람이 의도 한 수신자의 전화기에만 연결 된다는 점에서 팀 호출과는 다르며, 다른 사용자는 통화 픽업 그룹 번호로 전화를 걸어 응답을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-133">Group Call Pickup differs from team calling primarily in that an incoming call rings only at the intended recipient's phone, but any other user can choose to answer it by dialing a call pickup group number.</span></span>

<span data-ttu-id="2c82d-134">응답 그룹은 지정 된 에이전트로 전화를 걸고 지능적으로 라우팅 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-134">Response Groups can be set up for queuing and intelligently routing calls to designated agents.</span></span> <span data-ttu-id="2c82d-135">일반적인 용도에는 IT helpdesks, 인적 자원 hotlines, 기타 내부 연락처 센터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-135">Common uses include IT helpdesks, human resources hotlines, and other internal contact centers.</span></span>

</div>

<div>

## <a name="enterprise-voice-administration"></a><span data-ttu-id="2c82d-136">엔터프라이즈 음성 관리</span><span class="sxs-lookup"><span data-stu-id="2c82d-136">Enterprise Voice Administration</span></span>

<span data-ttu-id="2c82d-137">Lync Server는 표준 및 게시 된 인터페이스를 사용 하 여 기존 인프라와 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-137">Lync Server uses standards and published interfaces to interoperate with existing infrastructure.</span></span> <span data-ttu-id="2c82d-138">IP PBX 시스템 및 PSTN 네트워크에 상호 연결할 수 있도록 게이트웨이 및 SIP 옵션 (예: SIP 트렁크)을 모두 지원 하므로 시간에 따라 사용자를 엔터프라이즈 음성으로 마이그레이션하도록 하 고 중단을 최소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-138">It supports both gateway and SIP options (such as SIP trunking) for interconnection to IP PBX systems and the PSTN networks, so that you can migrate users to Enterprise Voice over time, while minimizing disruption.</span></span> <span data-ttu-id="2c82d-139">Lync Server는 기존 VoIP 솔루션과의 상호 운용성을 위해 711, 722, 723.1 등의 일반적인 코덱을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-139">Lync Server supports traditional codecs such as G.711, G.722, and G.723.1 for interoperability with traditional VoIP solutions.</span></span>

<span data-ttu-id="2c82d-140">관리자는 호출 허용 제어 (CAC)를 사용 하 여 제한 된 네트워크 링크에 전달 되는 Lync Server voice 및 비디오 트래픽 크기에 대 한 제한을 설정 하 고 새 통화가 제한을 초과 하는 경우 수행할 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-140">With call admission control (CAC), administrators can set limits on the amount of Lync Server voice and video traffic carried on constrained network links, and specify the action to be taken if a new call would exceed the limit.</span></span> <span data-ttu-id="2c82d-141">이 작업에는 대체 경로로 라우팅이 포함 되거나 호출을 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-141">The actions could include routing by an alternate path, or refusing the call.</span></span>

<span data-ttu-id="2c82d-142">Lync Server는 중앙 사이트에서 WAN 장애가 발생 하는 경우 지역 통화 서비스 및 지사에서 PSTN에 대 한 연결을 제공 하기 위해 타사 Survivable 분기 기기와 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c82d-142">Lync Server works with third-party Survivable Branch Appliances to provide local calling services and connection to PSTN at branch offices, in case of WAN failure at the central site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

