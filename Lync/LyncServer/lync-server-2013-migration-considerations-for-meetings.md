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
ms.openlocfilehash: 6af94514360509d4f608a21228b2fecf9a522007
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a><span data-ttu-id="750ea-102">Lync Server 2013의 모임 마이그레이션 고려 사항</span><span class="sxs-lookup"><span data-stu-id="750ea-102">Migration considerations for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="750ea-103">_**마지막으로 수정한 주제:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="750ea-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="750ea-104">이 섹션에서는 다음 항목에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-104">The following topics are discussed in this section:</span></span>

  - <span data-ttu-id="750ea-105">Microsoft Lync Server 2013의 모임 변경</span><span class="sxs-lookup"><span data-stu-id="750ea-105">Changes to meetings in Microsoft Lync Server 2013</span></span>

  - <span data-ttu-id="750ea-106">회의 요구 사항에 따라 사용자 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="750ea-106">Migrating users based on their conferencing needs</span></span>

  - <span data-ttu-id="750ea-107">기존 모임 및 모임 콘텐츠 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="750ea-107">Migrating existing meetings and meeting content</span></span>

  - <span data-ttu-id="750ea-108">Lync Server 2010 마이그레이션 중 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="750ea-108">User experience during Lync Server 2010 migration</span></span>

  - <span data-ttu-id="750ea-109">Office Communications Server 2007 R2 마이그레이션 중 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="750ea-109">User Experience during Office Communications Server 2007 R2 migration</span></span>

  - <span data-ttu-id="750ea-110">Microsoft Lync 2013 이전 서버 버전의 모임과 호환성</span><span class="sxs-lookup"><span data-stu-id="750ea-110">Microsoft Lync 2013 compatibility with meetings on earlier server versions</span></span>

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a><span data-ttu-id="750ea-111">Lync Server 2013의 모임 변경</span><span class="sxs-lookup"><span data-stu-id="750ea-111">Changes to Meetings in Lync Server 2013</span></span>

<span data-ttu-id="750ea-112">**Lync Server 2013 기능.**    Lync server 2013는 계정이 lync server 2013로 이동 하 고 lync 2013 클라이언트를 사용 하 여 로그인 한 후 사용자에 게 제공 되는 새로운 회의 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-112">**Lync Server 2013 features.**   Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="750ea-113">새로운 기능은 [Lync server 2013의 새로운 회의 기능과](lync-server-2013-new-conferencing-features.md) [lync server 2013의 클라이언트에 대 한 새로운](lync-server-2013-what-s-new-for-clients.md)기능에 개략적으로 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-113">New features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="750ea-114">**모임 URL입니다.**    Lync server 2010에서와 마찬가지로 lync server 2013의 모든 새로 예약 된 모임은 HTTPS://의 URL 접두사를 포함 하 고 있으며 기존 모임이 사용자 계정과 함께 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-114">**Meeting URL.**   As in Lync Server 2010, all newly scheduled meetings in Lync Server 2013 have a URL prefix of https:// and existing meetings migrate along with user accounts.</span></span> <span data-ttu-id="750ea-115">그러나 Lync Server 2013는 Office Communications Server 2007 R2 컨퍼런스 통화 (conf://URL 접두사) 또는 웹 컨퍼런스 (meet://URL 접두사)를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-115">However, Lync Server 2013 does not support the Office Communications Server 2007 R2 conference call (conf:// URL prefix) or web conference (meet:// URL prefix).</span></span> <span data-ttu-id="750ea-116">자세한 내용은이 항목의 뒷부분에 나오는 "Office Communications Server 2007 R2에서 모임 마이그레이션"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="750ea-116">See “Migrating Meetings from Office Communications Server 2007 R2” later in this topic for more information.</span></span>

<span data-ttu-id="750ea-117">**클라이언트 지원.**    Lync server 2010와 달리 lync server 2013에서는 전화 회의를 위한 Office Communicator 클라이언트를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-117">**Client support.**   Unlike Lync Server 2010, Lync Server 2013 does not support Office Communicator clients for conferencing.</span></span> <span data-ttu-id="750ea-118">Lync 2013의 온라인 모임 추가 기능을 통해 예약 된 모임에 참가 하는 데 다음 클라이언트를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-118">You cannot use the following clients to join meetings scheduled through the Online Meeting Add-in for Lync 2013:</span></span>

  - <span data-ttu-id="750ea-119">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="750ea-119">Office Communicator 2007 R2</span></span>

  - <span data-ttu-id="750ea-120">Microsoft Office Communications Server 2007 R2 전화 교환</span><span class="sxs-lookup"><span data-stu-id="750ea-120">Microsoft Office Communications Server 2007 R2 Attendant</span></span>

  - <span data-ttu-id="750ea-121">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="750ea-121">Office Communicator 2007</span></span>

  - <span data-ttu-id="750ea-122">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="750ea-122">Office Live Meeting 2007</span></span>

<span data-ttu-id="750ea-123">마이그레이션 도중 Office Communicator 2007 R2 사용자는 클라이언트가 업그레이드 될 때까지 lync Web App 2013을 사용 하 여 Lync Server 2013 모임에 참가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-123">During migration, Office Communicator 2007 R2 users should use Lync Web App 2013 to join Lync Server 2013 meetings until their clients are upgraded.</span></span> <span data-ttu-id="750ea-124">Office Communicator 2007 R2 사용자는 현재 상태 및 메신저 기능에 대 한 Lync Server 2013에서 기존 클라이언트를 계속 사용할 수 있지만, 회의 기능은 지원 되지 않음에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="750ea-124">Note that Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a><span data-ttu-id="750ea-125">회의 요구 사항에 따라 사용자 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="750ea-125">Migrating Users Based on Their Conferencing Needs</span></span>

<span data-ttu-id="750ea-126">**빈번한 모임 이끌이.**     [Lync Server 2013의 새로운 회의 기능](lync-server-2013-new-conferencing-features.md) 및 lync server [2013의 클라이언트에 대 한 새로운](lync-server-2013-what-s-new-for-clients.md)기능의 새 lync server 2013 및 lync 2013 기능을 활용할 수 있도록 프로세스 초기에 자주 모임 이끌이를 마이그레이션하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-126">**Frequent meeting organizers.**   Consider migrating frequent meeting organizers early in the process so that they can take advantage of the new Lync Server 2013 and Lync 2013 features outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="750ea-127">**Live Meeting 사용자.**    Office Communications Server 2007 R2에서 마이그레이션하는 경우 Live Meeting (특히 대규모 모임 및 휴식 회의실 지원)과 관련 된 웹 회의 기능이 필요한 사용자는 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-127">**Live Meeting users.**   If you are migrating from Office Communications Server 2007 R2 and you have users who need web conferencing features specific to Live Meeting—particularly support for large meetings and break-out rooms—you have the following options:</span></span>

  - <span data-ttu-id="750ea-128">조직에서 사용할 수 있는 경우 이끌이에게 Live Meeting 서비스를 사용 하도록 조언 합니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-128">Advise organizers to use the Live Meeting service, if available in your organization.</span></span>

  - <span data-ttu-id="750ea-129">이전 버전의 Office Communications Server에 있는 조직자를 유지 하 여 서버 기반 Live Meeting 웹 회의를 계속 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-129">Leave the organizers homed on the earlier version of Office Communications Server, so they can continue to schedule server-based Live Meeting web conferences.</span></span>

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a><span data-ttu-id="750ea-130">기존 모임 및 모임 콘텐츠 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="750ea-130">Migrating Existing Meetings and Meeting Content</span></span>

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a><span data-ttu-id="750ea-131">Lync Server 2010에서 모임 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="750ea-131">Migrating Meetings from Lync Server 2010</span></span>

<span data-ttu-id="750ea-132">Lync Server 2010에서 Lync Server 2013로 사용자를 이동 하면 다음 정보가 사용자 계정과 함께 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-132">When you move a user from Lync Server 2010 to Lync Server 2013, the following information moves with the user’s account:</span></span>

  - <span data-ttu-id="750ea-133">사용자가 이미 예약한 모임</span><span class="sxs-lookup"><span data-stu-id="750ea-133">Meetings already scheduled by the user.</span></span> <span data-ttu-id="750ea-134">여기에는 회의 디렉터리 및 회의 데이터가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-134">This includes conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="750ea-135">사용자의 PIN (개인 식별 번호)입니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-135">The user’s personal identification number (PIN).</span></span> <span data-ttu-id="750ea-136">사용자의 현재 PIN이 만료 되거나 사용자가 새 PIN을 요청할 때까지 계속 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-136">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="750ea-137">그러나 다음 사용자 계정 정보는 새 서버로 이동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-137">However, the following user account information does not move to the new server:</span></span>

  - <span data-ttu-id="750ea-138">모임 콘텐츠 (예: PowerPoint 프레젠테이션, 화이트 보드 콘텐츠 및 설문 데이터)</span><span class="sxs-lookup"><span data-stu-id="750ea-138">Meeting content, for example PowerPoint presentations, whiteboard content, and poll data</span></span>

<span data-ttu-id="750ea-139">모임에서 공유 된 콘텐츠를 이동 하려면 CsUser cmdlet의 MoveMeetingContent 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-139">To move the content that has been shared in meetings, use the MoveMeetingContent parameter of the Move-CsUser cmdlet.</span></span> <span data-ttu-id="750ea-140">이 cmdlet을 사용 하는 방법에 대 한 자세한 내용은 Lync Server 2013 cmdlet 설명서에서 [-CsUser 이동을](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="750ea-140">For details about using this cmdlet, see [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) in the Lync Server 2013 cmdlets documentation.</span></span>

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a><span data-ttu-id="750ea-141">Office Communications Server 2007 R2에서 모임 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="750ea-141">Migrating Meetings from Office Communications Server 2007 R2</span></span>

<span data-ttu-id="750ea-142">Office Communications Server 2007 R2 모임은 컨퍼런스 통화 (conf://URL 접두사) 또는 웹 컨퍼런스 (meet://URL 접두사)입니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-142">Office Communications Server 2007 R2 meetings are either conference calls (conf:// URL prefix) or web conferences (meet:// URL prefix).</span></span> <span data-ttu-id="750ea-143">Lync Server 2013는 이러한 이전 conf://및 meet://회의를 지원 하지 않으며 사용자 계정과 함께 마이그레이션되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-143">Lync Server 2013 does not support these earlier conf:// and meet:// conferences, and they are not migrated along with the user account.</span></span> <span data-ttu-id="750ea-144">마이그레이션 후에는 사용자가 예약한 모든 온라인 모임에 대 한 링크를 업데이트 하도록 알려 주어 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-144">After migration, you should instruct users to update the links for any online meetings they have scheduled.</span></span> <span data-ttu-id="750ea-145">이 작업은 모임 URL을 업데이트 하는 예약 된 모임 초대를 열고 참가자에 게 초대를 다시 보내는 방법으로 Lync 2013 클라이언트를 설치한 후에 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-145">They can do this after installing the Lync 2013 client by opening a scheduled meeting invitation—which updates the meeting URL—and resending the invitation to participants.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a><span data-ttu-id="750ea-146">Lync Server 2010 마이그레이션 중 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="750ea-146">User Experience during Lync Server 2010 Migration</span></span>

<span data-ttu-id="750ea-147">이 섹션에서는 Lync 2010에서 마이그레이션할 때 사용자의 회의 경험을 요약 하 여 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-147">This section provides a summary of users’ conferencing experience when migrating from Lync 2010.</span></span> <span data-ttu-id="750ea-148">Lync Server 2013 클라이언트가 이전 클라이언트 및 서버 버전과 공존 하 고 상호 작용할 수 있는 방법에 대 한 자세한 내용은 [lync 2013의 클라이언트 상호 운용성](lync-server-2013-client-interoperability-in-lync-2013.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="750ea-148">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a><span data-ttu-id="750ea-149">Lync 2013 클라이언트를 사용 하 여 Lync Server 2010 모임 참가</span><span class="sxs-lookup"><span data-stu-id="750ea-149">Joining Lync Server 2010 Meetings with a Lync 2013 Client</span></span>

<span data-ttu-id="750ea-150">Lync Server 2010에서 마이그레이션하는 동안 사용자가 lync 2013 클라이언트를 사용 하 여 Lync Server 2010 모임에 참가할 때 함께 사용할 수 있는 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-150">During migration from Lync Server 2010, there may be a period of coexistence when users join Lync Server 2010 meetings with a Lync 2013 client.</span></span> <span data-ttu-id="750ea-151">이러한 사용자는 다음과 같은 예외로 Lync 2013 클라이언트 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-151">These users have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="750ea-152">모임 창에서 사람 아이콘을 가리켜 액세스할 수 있는 **참가자** 관리 옵션에서 **모임 메신저 대화 없음** 옵션이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-152">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="750ea-153">갤러리 보기는 영상 회의에서 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-153">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="750ea-154">사용자는 모든 스피커가 아닌 활성 스피커로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-154">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="750ea-155">**레이아웃 옵션 선택** 목록에서 **갤러리 보기** 를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="750ea-155">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="750ea-156">참가자 목록은 기본적으로 비디오 회의에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-156">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="750ea-157">참가자 목록에서 사용자를 마우스 오른쪽 단추로 클릭 하면 **비디오 스포트라이트** 및 **갤러리에 대 한 Pin** 참가 관리 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-157">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a><span data-ttu-id="750ea-158">Office Communications Server 2007 R2 마이그레이션 중 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="750ea-158">User Experience during Office Communications Server 2007 R2 Migration</span></span>

<span data-ttu-id="750ea-159">이 섹션에서는 Lync 2013을 설치 하기 전과 후에 Office Communications Server 2007 R2에서 마이그레이션할 때 사용자의 회의 경험을 요약 하 여 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-159">This section provides a summary of users’ conferencing experience when migrating from Office Communications Server 2007 R2, both before and after Lync 2013 is installed.</span></span> <span data-ttu-id="750ea-160">Lync Server 2013 클라이언트가 이전 클라이언트 및 서버 버전과 공존 하 고 상호 작용할 수 있는 방법에 대 한 자세한 내용은 [lync 2013의 클라이언트 상호 운용성](lync-server-2013-client-interoperability-in-lync-2013.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="750ea-160">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a><span data-ttu-id="750ea-161">사용자 계정이 마이그레이션된 후에 Lync 2013을 설치 하기 전에</span><span class="sxs-lookup"><span data-stu-id="750ea-161">After User Account is Migrated, Before Lync 2013 Is Installed</span></span>

<span data-ttu-id="750ea-162">사용자를 Lync Server 2013 서버로 마이그레이션한 후 새 클라이언트를 설치 하기 전에 Office Communicator 2007 R2 사용자가 현재 상태 및 메신저 기능에 대 한 Lync Server 2013에 대해 기존 클라이언트를 계속 사용할 수 있지만, 회의 기능은 없습니다. 지원.</span><span class="sxs-lookup"><span data-stu-id="750ea-162">After a user is migrated to the Lync Server 2013 server, but before new clients are installed, Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a><span data-ttu-id="750ea-163">사용자 계정이 마이그레이션된 후에 Lync 2013가 설치 된 후</span><span class="sxs-lookup"><span data-stu-id="750ea-163">After User Account is Migrated, After Lync 2013 Is Installed</span></span>

<span data-ttu-id="750ea-164">마이그레이션된 사용자가 Lync 2013을 설치 하는 경우 Lync 2013 용 온라인 모임 추가 기능이 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-164">When a migrated user installs Lync 2013, the Online Meeting Add-in for Lync 2013 is installed too.</span></span> <span data-ttu-id="750ea-165">여기에는 다음과 같은 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-165">This has the following effects:</span></span>

  - <span data-ttu-id="750ea-166">모든 후속 예약 모임에는 레거시 meet://Live 모임 주소 대신 https://주소를 사용 하는 새 모임 형식이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-166">All subsequently scheduled meetings use the new meeting format, which uses an https:// address instead of the legacy meet:// Live Meeting address.</span></span>

  - <span data-ttu-id="750ea-167">Lync 2013의 IT 관리 배포에서 관리자는 Live Meeting server 및 서비스 기반 모임을 예약 하는 데 사용 되는 Microsoft Office Outlook 용 회의 추가 기능을 제거 하는 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-167">In an IT-managed deployment of Lync 2013, the administrator has the option of uninstalling the Conferencing Add-in for Microsoft Office Outlook, which is used to schedule Live Meeting server and service-based meetings.</span></span> <span data-ttu-id="750ea-168">그러나 Live Meeting 서비스 모임을 계속 예약 해야 하는 사용자가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-168">However, you may have users who need to continue to schedule Live Meeting service meetings.</span></span> <span data-ttu-id="750ea-169">이 경우 두 추가 기능을 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-169">In this case, you can allow both add-ins to coexist.</span></span>

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a><span data-ttu-id="750ea-170">이전 클라이언트를 사용 하는 페더레이션 조직이 있는 모임</span><span class="sxs-lookup"><span data-stu-id="750ea-170">Meetings with Federated Organizations that Use Previous Clients</span></span>

<span data-ttu-id="750ea-171">Microsoft Office Communicator 2007를 사용 하는 페더레이션 조직의 사용자는 이끌이가 해당 모임을 잠근 경우 조직의 Lync Server 2013 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-171">Users in federated organizations who are using Microsoft Office Communicator 2007 cannot join Lync Server 2013 meetings in your organization if those meetings are locked by the organizer.</span></span> <span data-ttu-id="750ea-172">Lync Server 2013에서 이러한 모임을 예약 해야 하므로, 페더레이션 참가자가 새 https://모임 URL을 사용 하 여 모임에 참가할 때 Lync Web App을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="750ea-172">You have to reschedule these meetings in Lync Server 2013 so when federated participants join the meeting by using the new https:// meeting URL, they can use Lync Web App.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

