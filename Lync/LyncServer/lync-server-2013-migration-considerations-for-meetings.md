---
title: 'Lync Server 2013: 모임 마이그레이션 고려 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ec650c62b26775aeddf9f01ff8d455a6f6a7667
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185111"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a><span data-ttu-id="ab29f-102">Lync Server 2013의 모임에 대 한 마이그레이션 고려 사항</span><span class="sxs-lookup"><span data-stu-id="ab29f-102">Migration considerations for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab29f-103">_**마지막으로 수정 된 항목:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="ab29f-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="ab29f-104">이 섹션에서는 다음 항목에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-104">The following topics are discussed in this section:</span></span>

  - <span data-ttu-id="ab29f-105">Microsoft Lync Server 2013의 모임 변경 사항</span><span class="sxs-lookup"><span data-stu-id="ab29f-105">Changes to meetings in Microsoft Lync Server 2013</span></span>

  - <span data-ttu-id="ab29f-106">회의 요구에 따른 사용자 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="ab29f-106">Migrating users based on their conferencing needs</span></span>

  - <span data-ttu-id="ab29f-107">기존 모임 및 모임 콘텐츠 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="ab29f-107">Migrating existing meetings and meeting content</span></span>

  - <span data-ttu-id="ab29f-108">Lync Server 2010 마이그레이션 중 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="ab29f-108">User experience during Lync Server 2010 migration</span></span>

  - <span data-ttu-id="ab29f-109">Office Communications Server 2007 R2 마이그레이션 중 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="ab29f-109">User Experience during Office Communications Server 2007 R2 migration</span></span>

  - <span data-ttu-id="ab29f-110">이전 서버 버전의 모임과의 Microsoft Lync 2013 호환성</span><span class="sxs-lookup"><span data-stu-id="ab29f-110">Microsoft Lync 2013 compatibility with meetings on earlier server versions</span></span>

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a><span data-ttu-id="ab29f-111">Lync Server 2013의 모임 변경 사항</span><span class="sxs-lookup"><span data-stu-id="ab29f-111">Changes to Meetings in Lync Server 2013</span></span>

<span data-ttu-id="ab29f-112">**Lync Server 2013 기능**    Lync server 2013에서는 계정이 lync server 2013로 이동 되 고 lync 2013 클라이언트에 로그인 한 후 사용자에 게 제공 되는 새로운 회의 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-112">**Lync Server 2013 features.**   Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="ab29f-113">새로운 기능은 [Lync server 2013의 새로운 회의 기능과](lync-server-2013-new-conferencing-features.md) [lync server 2013의 클라이언트에 대 한](lync-server-2013-what-s-new-for-clients.md)새로운 기능에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-113">New features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="ab29f-114">**모임 URL**    Lync server 2010와 마찬가지로 lync server 2013의 새로 예약 된 모든 모임에는 HTTPS://의 URL 접두사가 있고 사용자 계정과 함께 기존 모임이 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-114">**Meeting URL.**   As in Lync Server 2010, all newly scheduled meetings in Lync Server 2013 have a URL prefix of https:// and existing meetings migrate along with user accounts.</span></span> <span data-ttu-id="ab29f-115">그러나 Lync Server 2013에서는 Office Communications Server 2007 R2 전화 회의 통화 (conf://URL 접두사) 또는 웹 회의 (meet://URL 접두사)를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-115">However, Lync Server 2013 does not support the Office Communications Server 2007 R2 conference call (conf:// URL prefix) or web conference (meet:// URL prefix).</span></span> <span data-ttu-id="ab29f-116">자세한 내용은이 항목의 뒷부분에 나오는 "Office Communications Server 2007 R2에서 모임 마이그레이션"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ab29f-116">See “Migrating Meetings from Office Communications Server 2007 R2” later in this topic for more information.</span></span>

<span data-ttu-id="ab29f-117">**클라이언트 지원**    Lync server 2010와 달리 lync server 2013에서는 Office Communicator 클라이언트에서 회의를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-117">**Client support.**   Unlike Lync Server 2010, Lync Server 2013 does not support Office Communicator clients for conferencing.</span></span> <span data-ttu-id="ab29f-118">Lync 2013 용 온라인 모임 추가 기능을 통해 예약 된 모임에 참가할 때에는 다음 클라이언트를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-118">You cannot use the following clients to join meetings scheduled through the Online Meeting Add-in for Lync 2013:</span></span>

  - <span data-ttu-id="ab29f-119">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="ab29f-119">Office Communicator 2007 R2</span></span>

  - <span data-ttu-id="ab29f-120">Microsoft Office Communications Server 2007 R2 Attendant</span><span class="sxs-lookup"><span data-stu-id="ab29f-120">Microsoft Office Communications Server 2007 R2 Attendant</span></span>

  - <span data-ttu-id="ab29f-121">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="ab29f-121">Office Communicator 2007</span></span>

  - <span data-ttu-id="ab29f-122">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="ab29f-122">Office Live Meeting 2007</span></span>

<span data-ttu-id="ab29f-123">마이그레이션 중에 Office Communicator 2007 R2 사용자는 Lync Web App 2013을 사용 하 여 클라이언트가 업그레이드 될 때까지 Lync Server 2013 모임에 참가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-123">During migration, Office Communicator 2007 R2 users should use Lync Web App 2013 to join Lync Server 2013 meetings until their clients are upgraded.</span></span> <span data-ttu-id="ab29f-124">Office Communicator 2007 R2 사용자는 현재 상태 및 IM 기능에 대해 Lync Server 2013에서 기존 클라이언트를 계속 사용할 수 있지만 회의 기능은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-124">Note that Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a><span data-ttu-id="ab29f-125">회의 요구에 따른 사용자 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="ab29f-125">Migrating Users Based on Their Conferencing Needs</span></span>

<span data-ttu-id="ab29f-126">**모임 이끌이가 잦은 경우**     [Lync Server 2013의 새 회의 기능과](lync-server-2013-new-conferencing-features.md) lync [server 2013의 새로운 클라이언트](lync-server-2013-what-s-new-for-clients.md)기능에 설명 된 새로운 lync server 2013 및 lync 2013 기능을 활용할 수 있도록 프로세스 초기에 자주 모임 이끌이를 마이그레이션하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-126">**Frequent meeting organizers.**   Consider migrating frequent meeting organizers early in the process so that they can take advantage of the new Lync Server 2013 and Lync 2013 features outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="ab29f-127">**Live Meeting 사용자**    Office Communications Server 2007 r 2 r 2에서 마이그레이션하고 Live Meeting과 관련 된 웹 회의 기능을 사용 해야 하는 사용자가 있는 경우 (특히 대규모 모임 및 휴식을 지 원하는 경우) 다음과 같은 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-127">**Live Meeting users.**   If you are migrating from Office Communications Server 2007 R2 and you have users who need web conferencing features specific to Live Meeting—particularly support for large meetings and break-out rooms—you have the following options:</span></span>

  - <span data-ttu-id="ab29f-128">조직에서 사용 가능한 경우 이끌이가 Live Meeting 서비스를 사용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-128">Advise organizers to use the Live Meeting service, if available in your organization.</span></span>

  - <span data-ttu-id="ab29f-129">서버 기반 Live Meeting 웹 회의를 계속 예약할 수 있도록 이전 버전의 Office Communications Server에서 조직자를 그대로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-129">Leave the organizers homed on the earlier version of Office Communications Server, so they can continue to schedule server-based Live Meeting web conferences.</span></span>

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a><span data-ttu-id="ab29f-130">기존 모임 및 모임 콘텐츠 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="ab29f-130">Migrating Existing Meetings and Meeting Content</span></span>

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a><span data-ttu-id="ab29f-131">Lync Server 2010에서 모임 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="ab29f-131">Migrating Meetings from Lync Server 2010</span></span>

<span data-ttu-id="ab29f-132">사용자 계정을 Lync Server 2010에서 Lync Server 2013로 이동 하면 사용자 계정과 함께 다음 정보가 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-132">When you move a user from Lync Server 2010 to Lync Server 2013, the following information moves with the user’s account:</span></span>

  - <span data-ttu-id="ab29f-133">사용자가 이미 예약한 모임.</span><span class="sxs-lookup"><span data-stu-id="ab29f-133">Meetings already scheduled by the user.</span></span> <span data-ttu-id="ab29f-134">여기에는 회의 디렉터리 및 회의 데이터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-134">This includes conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="ab29f-135">사용자의 PIN(개인 ID 번호).</span><span class="sxs-lookup"><span data-stu-id="ab29f-135">The user’s personal identification number (PIN).</span></span> <span data-ttu-id="ab29f-136">사용자의 현재 PIN은 만료되거나 사용자가 새 PIN을 요청할 때까지 계속 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-136">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="ab29f-137">그러나 다음 사용자 계정 정보는 새 서버로 이동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-137">However, the following user account information does not move to the new server:</span></span>

  - <span data-ttu-id="ab29f-138">모임 콘텐츠 (예: PowerPoint 프레젠테이션, 화이트 보드 콘텐츠 및 설문 조사 데이터)</span><span class="sxs-lookup"><span data-stu-id="ab29f-138">Meeting content, for example PowerPoint presentations, whiteboard content, and poll data</span></span>

<span data-ttu-id="ab29f-139">모임에서 공유 된 콘텐츠를 이동 하려면 CsUser cmdlet의 MoveMeetingContent 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-139">To move the content that has been shared in meetings, use the MoveMeetingContent parameter of the Move-CsUser cmdlet.</span></span> <span data-ttu-id="ab29f-140">이 cmdlet을 사용 하는 방법에 대 한 자세한 내용은 Lync Server 2013 cmdlet 설명서의 [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ab29f-140">For details about using this cmdlet, see [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) in the Lync Server 2013 cmdlets documentation.</span></span>

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a><span data-ttu-id="ab29f-141">Office Communications Server 2007 R2에서 모임 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="ab29f-141">Migrating Meetings from Office Communications Server 2007 R2</span></span>

<span data-ttu-id="ab29f-142">Office Communications Server 2007 R2 모임은 전화 회의 통화 (conf://URL 접두사) 또는 웹 회의 (meet://URL 접두사)입니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-142">Office Communications Server 2007 R2 meetings are either conference calls (conf:// URL prefix) or web conferences (meet:// URL prefix).</span></span> <span data-ttu-id="ab29f-143">Lync Server 2013에서는 이러한 이전 conf://및 meet://회의를 지원 하지 않으며 사용자 계정과 함께 마이그레이션되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-143">Lync Server 2013 does not support these earlier conf:// and meet:// conferences, and they are not migrated along with the user account.</span></span> <span data-ttu-id="ab29f-144">마이그레이션 후 사용자에 게 예약 된 온라인 모임의 링크를 업데이트 하 라고 지시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-144">After migration, you should instruct users to update the links for any online meetings they have scheduled.</span></span> <span data-ttu-id="ab29f-145">Lync 2013 클라이언트를 설치한 후 모임 URL을 업데이트 하는 예약 된 모임 초대를 열고 참석자에 게 초대를 다시 보내는 방법으로이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-145">They can do this after installing the Lync 2013 client by opening a scheduled meeting invitation—which updates the meeting URL—and resending the invitation to participants.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a><span data-ttu-id="ab29f-146">Lync Server 2010 마이그레이션 중 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="ab29f-146">User Experience during Lync Server 2010 Migration</span></span>

<span data-ttu-id="ab29f-147">이 섹션에서는 Lync 2010에서 마이그레이션할 때 사용자의 회의 환경에 대 한 요약 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-147">This section provides a summary of users’ conferencing experience when migrating from Lync 2010.</span></span> <span data-ttu-id="ab29f-148">Lync Server 2013 클라이언트를 이전 버전의 클라이언트 및 서버 버전과 함께 사용 하 고 상호 작용할 수 있는 방법에 대 한 자세한 내용은 [lync 2013의 클라이언트 상호 운용성](lync-server-2013-client-interoperability-in-lync-2013.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ab29f-148">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a><span data-ttu-id="ab29f-149">Lync 2013 클라이언트와 함께 Lync Server 2010 모임 참가</span><span class="sxs-lookup"><span data-stu-id="ab29f-149">Joining Lync Server 2010 Meetings with a Lync 2013 Client</span></span>

<span data-ttu-id="ab29f-150">Lync Server 2010에서 마이그레이션하는 동안 사용자가 lync Server 2010 모임에 lync 2013 클라이언트를 연결할 때 동시 사용 기간이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-150">During migration from Lync Server 2010, there may be a period of coexistence when users join Lync Server 2010 meetings with a Lync 2013 client.</span></span> <span data-ttu-id="ab29f-151">이러한 사용자는 다음과 같은 예외를 제외 하 고 Lync 2013 클라이언트 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-151">These users have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="ab29f-152">모임 창에서 사람 아이콘을 가리켜 액세스할 수 있는 **참가자** 관리 옵션에서 **모임 메신저 대화** 상대가 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-152">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="ab29f-153">갤러리 보기가 비디오 회의에서 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-153">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="ab29f-154">사용자는 모든 스피커가 아닌 활성 발표자만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-154">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="ab29f-155">**레이아웃 옵션 선택** 목록에서 **갤러리 보기** 를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="ab29f-155">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="ab29f-156">참가자 목록은 비디오 회의에 기본적으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-156">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="ab29f-157">참가자 목록에서 사용자를 마우스 오른쪽 단추로 클릭 하는 경우에는 **비디오 스포트라이트** 및 **Pin을 갤러리** 참가자 관리 옵션으로 잠글 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-157">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a><span data-ttu-id="ab29f-158">Office Communications Server 2007 R2 마이그레이션 중 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="ab29f-158">User Experience during Office Communications Server 2007 R2 Migration</span></span>

<span data-ttu-id="ab29f-159">이 섹션에서는 Lync 2013가 설치 되기 전과 후에 Office Communications Server 2007 r 2에서 마이그레이션할 때 사용자의 회의 환경에 대 한 요약 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-159">This section provides a summary of users’ conferencing experience when migrating from Office Communications Server 2007 R2, both before and after Lync 2013 is installed.</span></span> <span data-ttu-id="ab29f-160">Lync Server 2013 클라이언트를 이전 버전의 클라이언트 및 서버 버전과 함께 사용 하 고 상호 작용할 수 있는 방법에 대 한 자세한 내용은 [lync 2013의 클라이언트 상호 운용성](lync-server-2013-client-interoperability-in-lync-2013.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ab29f-160">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a><span data-ttu-id="ab29f-161">사용자 계정이 마이그레이션된 후 Lync 2013가 설치 되기 전에</span><span class="sxs-lookup"><span data-stu-id="ab29f-161">After User Account is Migrated, Before Lync 2013 Is Installed</span></span>

<span data-ttu-id="ab29f-162">사용자를 Lync Server 2013 Server로 마이그레이션한 후에 새 클라이언트를 설치 하기 전에 Office Communicator 2007 R2 사용자는 현재 상태 및 IM 기능에 대해 Lync Server 2013에 대해 기존 클라이언트를 계속 사용할 수 있지만 회의 기능은 없습니다. 지원.</span><span class="sxs-lookup"><span data-stu-id="ab29f-162">After a user is migrated to the Lync Server 2013 server, but before new clients are installed, Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a><span data-ttu-id="ab29f-163">사용자 계정이 마이그레이션된 후에 Lync 2013이 설치 된 후</span><span class="sxs-lookup"><span data-stu-id="ab29f-163">After User Account is Migrated, After Lync 2013 Is Installed</span></span>

<span data-ttu-id="ab29f-164">마이그레이션된 사용자가 Lync 2013을 설치 하면 Lync 2013 용 온라인 모임 추가 기능이 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-164">When a migrated user installs Lync 2013, the Online Meeting Add-in for Lync 2013 is installed too.</span></span> <span data-ttu-id="ab29f-165">다음과 같은 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-165">This has the following effects:</span></span>

  - <span data-ttu-id="ab29f-166">이후에 예약된 모든 모임에는 레거시 meet:// Live Meeting 주소 대신 https:// 주소를 사용하는 새 모임 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-166">All subsequently scheduled meetings use the new meeting format, which uses an https:// address instead of the legacy meet:// Live Meeting address.</span></span>

  - <span data-ttu-id="ab29f-167">IT가 관리 하는 Lync 2013 배포에서 관리자는 Live Meeting server 및 서비스 기반 모임을 예약 하는 데 사용 되는 Microsoft Office Outlook 용 회의 추가 기능을 제거 하는 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-167">In an IT-managed deployment of Lync 2013, the administrator has the option of uninstalling the Conferencing Add-in for Microsoft Office Outlook, which is used to schedule Live Meeting server and service-based meetings.</span></span> <span data-ttu-id="ab29f-168">하지만 Live Meeting 서비스 모임을 계속 예약해야 하는 사용자가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-168">However, you may have users who need to continue to schedule Live Meeting service meetings.</span></span> <span data-ttu-id="ab29f-169">이 경우 두 추가 기능의 동시 사용을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-169">In this case, you can allow both add-ins to coexist.</span></span>

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a><span data-ttu-id="ab29f-170">이전 클라이언트를 사용하는 페더레이션된 조직과의 모임</span><span class="sxs-lookup"><span data-stu-id="ab29f-170">Meetings with Federated Organizations that Use Previous Clients</span></span>

<span data-ttu-id="ab29f-171">Microsoft Office Communicator 2007을 사용 하는 페더레이션 조직의 사용자는 이끌이가 해당 모임을 잠근 경우 조직의 Lync Server 2013 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-171">Users in federated organizations who are using Microsoft Office Communicator 2007 cannot join Lync Server 2013 meetings in your organization if those meetings are locked by the organizer.</span></span> <span data-ttu-id="ab29f-172">Lync Server 2013에서 이러한 모임을 다시 예약 해야 페더레이션 참가자가 새 https://모임 URL을 사용 하 여 모임에 참가할 때 Lync Web App을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab29f-172">You have to reschedule these meetings in Lync Server 2013 so when federated participants join the meeting by using the new https:// meeting URL, they can use Lync Web App.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

