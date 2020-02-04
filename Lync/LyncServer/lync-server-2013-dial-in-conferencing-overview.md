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
ms.openlocfilehash: 0a126e7e1ee61f48ff8857553b7677abf813a25e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="82038-102">Lync Server 2013의 전화 접속 회의 개요</span><span class="sxs-lookup"><span data-stu-id="82038-102">Overview of dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82038-103">_**마지막으로 수정한 주제:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="82038-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="82038-104">조직에서 office가 외부에 있거나 컴퓨터에 대 한 액세스 권한이 없는 경우 Lync Server 2013 온-프레미스 회의에 참가 해야 하는 사용자가 있는 경우, 공개 교환 전화를 사용 하 여 전화 접속 회의를 통해 회의에 참가할 수 있습니다. 네트워크 (PSTN) 휴대폰.</span><span class="sxs-lookup"><span data-stu-id="82038-104">If your organization has users who need to attend Lync Server 2013 on-premises conferences when they are out of the office or do not have access to a computer, you can deploy dial-in conferencing so that they can join the conference by using a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="82038-105">전화 접속 회의는 Lync Server 2013 회의를 배포할 때 구성할 수 있는 선택적 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="82038-105">Dial-in conferencing is an optional feature that you can configure when you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="82038-106">전화 접속 회의에서 Enterprise Voice에 사용 하는 것과 동일한 Lync Server 2013 구성 요소 중 일부를 사용 하는 경우에도 엔터프라이즈 음성을 배포 하지 않더라도 전화 접속 회의를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82038-106">Although dial-in conferencing uses some of the same Lync Server 2013 components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="82038-107">전화 접속 회의를 배포 하는 경우 Lync Server 2013 회의를 배포 하는 모든 풀에 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82038-107">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="82038-108">모든 풀에 액세스 번호를 할당할 필요는 없지만 모든 풀에 전화 접속 기능을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82038-108">You do not need to assign access numbers in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="82038-109">이 요구 사항은 사용자가 한 풀의 액세스 번호를 호출 하 여 다른 풀의 Lync Server 2013 컨퍼런스에 참가 하는 경우 기록 된 이름 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="82038-109">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

<span data-ttu-id="82038-110">모임 정책에서 전화 접속 액세스에 대 한 회의를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82038-110">Conferences must be enabled for dial-in access in meeting policy.</span></span> <span data-ttu-id="82038-111">기본적으로 전화 접속 액세스를 사용 하도록 설정 된 회의에는 회의 초대장에 다음 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82038-111">By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>

  - <span data-ttu-id="82038-112">회의를 식별 하는 숫자 회의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="82038-112">A numeric conference ID that identifies the conference.</span></span>

  - <span data-ttu-id="82038-113">하나 이상의 PSTN 액세스 번호.</span><span class="sxs-lookup"><span data-stu-id="82038-113">One or more PSTN access numbers.</span></span>

  - <span data-ttu-id="82038-114">연결 된 언어의 전체 액세스 번호 목록이 포함 된 전화 접속 회의 설정 페이지에 대 한 링크입니다. Pin (개인 식별 번호)을 만들거나, 다시 설정 하거나, 차단을 해제 하는 장소 이중 톤 다중 주파수 (DTMF) 컨트롤과 같은 기타 정보</span><span class="sxs-lookup"><span data-stu-id="82038-114">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls.</span></span>

<span data-ttu-id="82038-115">전화 접속 회의는 엔터프라이즈 및 익명 사용자를 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="82038-115">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="82038-116">엔터프라이즈 사용자의 조직 내에는 Active Directory 도메인 서비스 자격 증명과 Lync Server 2013 계정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82038-116">Enterprise users have Active Directory Domain Services credentials and Lync Server 2013 accounts within their organization.</span></span> <span data-ttu-id="82038-117">익명 사용자는 조직 내에서 엔터프라이즈 자격 증명을가지고 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82038-117">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="82038-118">전화 접속 회의 컨텍스트에서 PSTN을 사용 하 여 회의에 연결 하는 페더레이션 파트너 조직의 사용자가 익명 사용자와 같이 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82038-118">In the dial-in conferencing context, a user in a federated partner’s organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="82038-119">전화 접속 회의의 경우 다른 컨텍스트와 달리 페더레이션 사용자는 인증 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82038-119">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>

<span data-ttu-id="82038-120">전화 접속 액세스를 사용 하도록 설정 된 회의에 참가 하는 Enterprise 사용자 또는 회의 리더 회의 액세스 번호 중 하나로 전화를 걸고, 전화 회의 ID를 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82038-120">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID.</span></span> <span data-ttu-id="82038-121">리더가 아직 모임에 참가 하지 않은 경우 사용자는 통합 커뮤니케이션 (UC) 확장 (또는 전체 전화 번호)을 입력 하 고, PIN 또는 리더의 참여를 대기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82038-121">If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader.</span></span> <span data-ttu-id="82038-122">모임 이끌이는 자신의 PIN만 입력 하 여 모임에 리더로 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82038-122">The Meeting organizer can join the meeting as a leader by entering just their PIN.</span></span> <span data-ttu-id="82038-123">프런트 엔드 서버는 전체 전화 번호 또는 확장명 조합 및 PIN을 사용 하 여 엔터프라이즈 사용자를 Active Directory 자격 증명에 고유 하 게 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="82038-123">The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials.</span></span> <span data-ttu-id="82038-124">결과적으로 엔터프라이즈 사용자는 회의에서 이름으로 인증 되 고 식별 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82038-124">As a result, enterprise users are authenticated and identified by name in the conference.</span></span> <span data-ttu-id="82038-125">기업 사용자는 주최자가 미리 정의한 컨퍼런스 역할을 맡을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82038-125">Enterprise users can also assume a conference role predefined by the organizer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="82038-126">Office IP 휴대폰 또는 Lync Server 2013 또는 Lync 2010 Attendant에서 전화를 거는 Enterprise 사용자는 이미 인증 되어 있으므로 전화 번호를 묻는 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82038-126">Enterprise users who dial in from an office IP phone or from Lync Server 2013 or Lync 2010 Attendant are not prompted for their phone number because they are already authenticated.</span></span>



</div>

<span data-ttu-id="82038-127">전화 접속 회의에 참가 하려는 익명 사용자에 게 전화 회의 액세스 번호 중 하나를 입력 한 다음, 전화 회의 ID를 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82038-127">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID.</span></span> <span data-ttu-id="82038-128">인증 되지 않은 익명 사용자에 게 이름을 기록 하 라는 메시지가 표시 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82038-128">Unauthenticated anonymous users are also prompted to record their name.</span></span> <span data-ttu-id="82038-129">기록 된 이름은 회의에서 인증 되지 않은 사용자를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="82038-129">The recorded name identifies unauthenticated users in the conference.</span></span> <span data-ttu-id="82038-130">익명 사용자는 하나 이상의 리더 또는 인증 된 사용자가 참가 해야만 회의에 참석할 수 있으며, 미리 정의 된 역할에 할당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82038-130">Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="82038-131">전화 번호 및 PIN을 입력 하지 않도록 선택 하는 Enterprise 사용자는 인증 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82038-131">Enterprise users who choose not to enter their phone number and PIN are not authenticated.</span></span> <span data-ttu-id="82038-132">해당 이름을 기록 하 라는 메시지가 표시 되 고 회의에서 익명 사용자로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82038-132">They are prompted to record their name and are treated as anonymous users in the conference.</span></span>



</div>

<span data-ttu-id="82038-133">모임 이끌이는 일정 시간에 모임을 종료 하거나 잠금 상태로 만들어 모임에 대 한 액세스를 제한 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82038-133">At schedule time, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked.</span></span> <span data-ttu-id="82038-134">이 경우 전화 접속 사용자가 인증을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="82038-134">In this case, dial-in users are requested to authenticate.</span></span> <span data-ttu-id="82038-135">전화 접속 사용자가 실패 하거나 인증 하지 않도록 선택 하는 경우 대기실로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82038-135">If dial-in users fail or choose not to authenticate, they are transferred to the lobby.</span></span> <span data-ttu-id="82038-136">리더가이를 수락 또는 거부 하거나 시간이 초과 되어 연결이 끊어질 때까지 대기실에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="82038-136">They wait in the lobby until a leader accepts or rejects them, or they time out and are disconnected.</span></span> <span data-ttu-id="82038-137">전화 접속 사용자가 회의에 참석할 때까지 음악을 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82038-137">Dial-in users hear music if they are waiting to be admitted to the conference.</span></span> <span data-ttu-id="82038-138">전화 회의에 참가 한 후에는 휴대폰 번호를 사용 하 여 회의의 오디오 부분에 참가할 수 있으며, 전화 키패드를 통해 이중 톤 멀티 주파수 (DTMF) 명령을 연습할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82038-138">After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad.</span></span> <span data-ttu-id="82038-139">전화 접속 리더는 참가자의 기능을 설정 하거나 해제 하 고, 회의를 잠그거나 잠금 해제 하 고, 로비에서 사용자를 허용 하 고, 알림 기능을 설정 하거나 종료 하는 등의 DTMF 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82038-139">Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off.</span></span> <span data-ttu-id="82038-140">또한 팀장은 DTMF 명령을 사용 하 여 모든 사용자가 대기실에서 참석할 수 있으며,이는 팔 로우 하는 모든 사용자에 게 모임 사용 권한을 변경 하는 것을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="82038-140">Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins.</span></span> <span data-ttu-id="82038-141">모든 전화 접속 참가자는 DTMF 명령을 사용 하 여 도움을 듣고, 컨퍼런스 명단을 청취 하 고, 스스로 음소거 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82038-141">All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>

<span data-ttu-id="82038-142">전화 접속 참가자 (즉, PSTN에서 전화를 걸지 여부에 관계 없이), 회의 중에 음소거 또는 음소거 됨, 모임이 기록 중인지 또는 누군가 대기실에서 대기 중인지 등의 개인 알림을 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82038-142">Dial-in participants (that is, whether or not they dial from the PSTN), hear personal announcements during the conference, such as whether they have been muted or unmuted, the meeting is being recorded, or someone is waiting in the lobby.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="82038-143">전화 접속 대신 링크를 클릭 하 여 회의에 참가 한 참가자는 개인 알림을 들리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82038-143">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

