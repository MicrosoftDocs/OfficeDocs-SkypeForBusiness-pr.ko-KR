---
title: Lync Server 2013 전화 접속 회의 개요
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d088d07e5d49a916835da581af81ff7def581b6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="c7d0b-102">Lync Server 2013의 전화 접속 회의 개요</span><span class="sxs-lookup"><span data-stu-id="c7d0b-102">Overview of dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7d0b-103">_**마지막으로 수정 된 항목:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="c7d0b-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="c7d0b-104">조직에서 office 외부에 있거나 컴퓨터에 액세스할 수 없는 경우 Lync Server 2013 온-프레미스 전화 회의에 참가 해야 하는 사용자가 있는 경우에는 공개 전환 전화를 사용 하 여 회의에 참가 하는 데 도움이 되도록 다이얼 인 회의를 배포할 수 있습니다. 네트워크 (PSTN) 전화</span><span class="sxs-lookup"><span data-stu-id="c7d0b-104">If your organization has users who need to attend Lync Server 2013 on-premises conferences when they are out of the office or do not have access to a computer, you can deploy dial-in conferencing so that they can join the conference by using a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="c7d0b-105">전화 접속 회의는 Lync Server 2013 회의를 배포할 때 구성할 수 있는 선택적 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-105">Dial-in conferencing is an optional feature that you can configure when you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="c7d0b-106">전화 접속 회의에서 Enterprise Voice에 사용 되는 것과 동일한 Lync Server 2013 구성 요소 중 일부를 사용 하지만 Enterprise Voice를 배포 하지 않더라도 전화 접속 회의를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-106">Although dial-in conferencing uses some of the same Lync Server 2013 components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7d0b-107">전화 접속 회의를 배포 하는 경우 Lync Server 2013 회의를 배포 하는 모든 풀에 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-107">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="c7d0b-108">모든 풀에서 액세스 번호를 할당할 필요는 없지만 모든 풀에 전화 접속 기능을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-108">You do not need to assign access numbers in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="c7d0b-109">이 요구 사항은 사용자가 한 풀의 액세스 번호를 호출 하 여 다른 풀에서 Lync Server 2013 회의에 참가 하는 경우 기록 된 이름 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-109">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

<span data-ttu-id="c7d0b-110">모임 정책에서 전화 접속 액세스를 사용 하도록 회의를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-110">Conferences must be enabled for dial-in access in meeting policy.</span></span> <span data-ttu-id="c7d0b-111">기본적으로 전화 접속 액세스를 사용 하도록 설정 된 회의에는 전화 회의 초대장에 다음과 같은 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-111">By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>

  - <span data-ttu-id="c7d0b-112">전화 회의를 식별 하는 숫자 회의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-112">A numeric conference ID that identifies the conference.</span></span>

  - <span data-ttu-id="c7d0b-113">하나 이상의 PSTN 액세스 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-113">One or more PSTN access numbers.</span></span>

  - <span data-ttu-id="c7d0b-114">관련 언어의 전체 액세스 번호 목록이 포함 된 전화 접속 회의 설정 페이지로 연결 되는 링크입니다. Pin (개인 식별 번호)을 만들거나 다시 설정 하거나 차단을 해제 하는 장소입니다. 이중 톤 다중 주파수 (DTMF) 컨트롤 등의 기타 정보</span><span class="sxs-lookup"><span data-stu-id="c7d0b-114">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls.</span></span>

<span data-ttu-id="c7d0b-115">전화 접속 회의에서는 엔터프라이즈 및 익명 사용자를 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-115">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="c7d0b-116">기업 사용자는 조직 내에 Active Directory 도메인 서비스 자격 증명과 Lync Server 2013 계정을가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-116">Enterprise users have Active Directory Domain Services credentials and Lync Server 2013 accounts within their organization.</span></span> <span data-ttu-id="c7d0b-117">익명 사용자는 조직 내에 엔터프라이즈 자격 증명을 갖고 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-117">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="c7d0b-118">전화 접속 회의 컨텍스트에서 PSTN을 사용 하 여 회의에 연결 하는 페더레이션 파트너 조직의 사용자는 익명 사용자 처럼 취급 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-118">In the dial-in conferencing context, a user in a federated partner’s organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="c7d0b-119">전화 접속 회의의 경우 다른 컨텍스트와 달리 페더레이션 사용자는 인증 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-119">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>

<span data-ttu-id="c7d0b-120">전화 접속 액세스를 사용 하도록 설정 된 전화 회의에 참가 하는 Enterprise 사용자 또는 회의 리더 전화 회의 액세스 번호 중 하나를 받은 다음 전화 회의 ID를 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-120">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID.</span></span> <span data-ttu-id="c7d0b-121">리더가 아직 모임에 참가 하지 않은 경우 사용자는 UC (통합 통신) 확장 (또는 전체 전화 번호)을 입력 하 고 전자 메일을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-121">If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader.</span></span> <span data-ttu-id="c7d0b-122">모임 이끌이가 자신의 PIN만 입력 하 여 모임에 리더로 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-122">The Meeting organizer can join the meeting as a leader by entering just their PIN.</span></span> <span data-ttu-id="c7d0b-123">프런트 엔드 서버는 전체 전화 번호나 내선 번호와 PIN을 함께 사용 하 여 엔터프라이즈 사용자를 해당 Active Directory 자격 증명에 고유 하 게 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-123">The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials.</span></span> <span data-ttu-id="c7d0b-124">따라서 엔터프라이즈 사용자는 전화 회의에서 이름으로 인증 되 고 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-124">As a result, enterprise users are authenticated and identified by name in the conference.</span></span> <span data-ttu-id="c7d0b-125">또한 엔터프라이즈 사용자는 이끌이를 통해 미리 정의 된 회의 역할을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-125">Enterprise users can also assume a conference role predefined by the organizer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7d0b-126">Office IP 전화나 Lync Server 2013 또는 Lync 2010 Attendant에서 전화를 거는 엔터프라이즈 사용자는 이미 인증 되었으므로 전화 번호를 입력 하 라는 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-126">Enterprise users who dial in from an office IP phone or from Lync Server 2013 or Lync 2010 Attendant are not prompted for their phone number because they are already authenticated.</span></span>



</div>

<span data-ttu-id="c7d0b-127">전화 접속 회의에 참가 하려는 익명 사용자 회의 액세스 번호 중 하나를 전화를 걸어 전화 회의 ID를 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-127">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID.</span></span> <span data-ttu-id="c7d0b-128">인증 되지 않은 익명 사용자의 이름을 기록 하 라는 메시지도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-128">Unauthenticated anonymous users are also prompted to record their name.</span></span> <span data-ttu-id="c7d0b-129">녹음 된 이름은 전화 회의의 인증 되지 않은 사용자를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-129">The recorded name identifies unauthenticated users in the conference.</span></span> <span data-ttu-id="c7d0b-130">익명 사용자는 하나 이상의 리더가 구독 되거나 인증 된 사용자가 참가 하지 않은 경우에만 회의에 참석할 수 있으며, 이러한 역할을 미리 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-130">Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7d0b-131">전화 번호와 PIN을 입력 하지 않으려는 엔터프라이즈 사용자는 인증 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-131">Enterprise users who choose not to enter their phone number and PIN are not authenticated.</span></span> <span data-ttu-id="c7d0b-132">전화 회의에서 익명 사용자로 처리 되는 이름을 기록 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-132">They are prompted to record their name and are treated as anonymous users in the conference.</span></span>



</div>

<span data-ttu-id="c7d0b-133">모임 이끌이는 일정 시간에 모임을 종료 하거나 잠가 모임에 대 한 액세스를 제한 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-133">At schedule time, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked.</span></span> <span data-ttu-id="c7d0b-134">이 경우에는 전화 접속 사용자가 인증을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-134">In this case, dial-in users are requested to authenticate.</span></span> <span data-ttu-id="c7d0b-135">전화 접속 사용자가 실패 하거나 인증 하지 않으면 로비로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-135">If dial-in users fail or choose not to authenticate, they are transferred to the lobby.</span></span> <span data-ttu-id="c7d0b-136">리더가 리더를 수락 또는 거부 하거나 시간이 초과 되어 연결을 끊을 때까지 로비에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-136">They wait in the lobby until a leader accepts or rejects them, or they time out and are disconnected.</span></span> <span data-ttu-id="c7d0b-137">전화 접속 사용자가 회의에 참가 하기 위해 대기 중인 경우 음악을 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-137">Dial-in users hear music if they are waiting to be admitted to the conference.</span></span> <span data-ttu-id="c7d0b-138">전화 회의에 참여 하 고 전화 접속 사용자는 회의의 오디오 부분에 참가할 수 있으며 전화기 키패드를 사용 하 여 이중 톤 멀티 주파수 (DTMF) 명령을 연습할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-138">After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad.</span></span> <span data-ttu-id="c7d0b-139">전화 접속 팀장은 DTMF 명령을 사용 하 여 참가자의 음소거를 설정/해제 하 고, 회의를 잠그거나 잠금을 해제 하 고, 로비에서 사용자를 허용 하 고, 입장 및 종료 알림을 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-139">Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off.</span></span> <span data-ttu-id="c7d0b-140">또한 리더는 DTMF 명령을 사용 하 여 로비에서 모든 사용자를 허용 하 고, 이후에 가입한 모든 사용자가 참석할 수 있도록 모임 권한을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-140">Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins.</span></span> <span data-ttu-id="c7d0b-141">모든 전화 접속 참가자는 DTMF 명령을 사용 하 여 도움을 듣고, 회의 명단을 듣고, 스스로 음소거 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-141">All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>

<span data-ttu-id="c7d0b-142">전화 접속 참가자 (즉, PSTN에서 전화를 거는 중인지 여부)는 전화 회의 중에 음소거 또는 음소거 해제 되었는지를 사용 하 여 녹음 중이거나, 모임이 기록 되 고 있거나, 다른 사용자가 로비에서 대기 중인지 여부와 같은 개인적인 알림을 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-142">Dial-in participants (that is, whether or not they dial from the PSTN), hear personal announcements during the conference, such as whether they have been muted or unmuted, the meeting is being recorded, or someone is waiting in the lobby.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7d0b-143">전화를 거는 대신 링크를 클릭 하 여 회의에 참가 한 참가자는 개인 알림을 듣지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7d0b-143">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

