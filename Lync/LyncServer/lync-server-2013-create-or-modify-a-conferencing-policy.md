---
title: 'Lync Server 2013: 회의 정책 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a conferencing policy
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49733844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 898ffb4473fadd4470ef7e1559fa3cc0c54185c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="5c90d-102">Lync Server 2013에서 회의 정책 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="5c90d-102">Create or modify a conferencing policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c90d-103">_**마지막으로 수정한 주제:** 2013-02-07_</span><span class="sxs-lookup"><span data-stu-id="5c90d-103">_**Topic Last Modified:** 2013-02-07_</span></span>

<span data-ttu-id="5c90d-104">다음 단계에 따라 사용자 수준 또는 사이트 수준 회의 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-104">Follow these steps to create a user-level or a site-level conferencing policy.</span></span> <span data-ttu-id="5c90d-105">사용자에 게 사용자 수준 정책을 할당 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 사용자 단위 회의 정책 할당](lync-server-2013-assign-a-per-user-conferencing-policy.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5c90d-105">For details about how to assign a user-level policy to a user, see [Assign a per-user conferencing policy in Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span></span> <span data-ttu-id="5c90d-106">사용 가능한 모든 회의 정책 설정 목록은 [Lync Server 2013에 대 한 회의 정책 설정 참조](lync-server-2013-conferencing-policy-settings-reference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5c90d-106">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-create-a-new-user-or-site-policy"></a><span data-ttu-id="5c90d-107">새 사용자 또는 사이트 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="5c90d-107">To create a new user or site policy</span></span>

1.  <span data-ttu-id="5c90d-108">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5c90d-109">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5c90d-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5c90d-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5c90d-111">왼쪽 탐색 모음에서 **회의** 를 클릭 한 다음 **회의 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-111">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="5c90d-112">**새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-112">Click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="5c90d-113">사용자 수준 정책을 만들려면 **사용자 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-113">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="5c90d-114">**새 회의 정책의** **이름**에 정책에 대 한 설명이 포함 된 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-114">In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
      - <span data-ttu-id="5c90d-115">사이트 수준 정책을 만들려면 **사이트 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-115">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="5c90d-116">사이트 검색 **선택** 필드에 정책을 만들려는 사이트 이름의 전부 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-116">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="5c90d-117">사이트 목록에서 원하는 사이트를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-117">In the list of sites, click the site that you want, and then click **OK**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5c90d-118">사이트 이름은 회의 정책 이름이 되며 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-118">The site name becomes the conferencing policy name, and it cannot be changed.</span></span>

        
        </div>

5.  <span data-ttu-id="5c90d-119">**설명**에 정책에 대 한 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-119">In **Description**, type a description for the policy.</span></span>

6.  <span data-ttu-id="5c90d-120">**이끌이 정책의** **최대 모임 크기**에 모임에서 허용 하려는 최대 사용자 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-120">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting.</span></span> <span data-ttu-id="5c90d-121">기본적으로 최대 모임 크기는 250입니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-121">By default, the maximum meeting size is 250.</span></span>

7.  <span data-ttu-id="5c90d-122">사용자가 익명 사용자를 모임에 초대 하지 못하도록 하려면 **참가자가 익명 사용자 초대를 허용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-122">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="5c90d-123">익명 사용자는 조직의 Active Directory 도메인 서비스에 자격 증명이 없고 인증 되지 않은 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-123">Anonymous users are users who do not have credentials in your organization’s Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="5c90d-124">기본적으로 사용자는 모임에 익명 사용자를 초대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-124">By default, users can invite anonymous users to meetings.</span></span>

8.  <span data-ttu-id="5c90d-125">**기록**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-125">In **Recording**, do one of the following:</span></span>
    
      - <span data-ttu-id="5c90d-126">참가자가 모임을 녹음/녹화할 수 없도록 하려면 **없음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-126">To prevent participants from recording meetings, click **None**.</span></span> <span data-ttu-id="5c90d-127">이는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-127">This is the default setting.</span></span>
    
      - <span data-ttu-id="5c90d-128">참가자가 모임을 녹음/녹화할 수 있도록 하려면 **녹음/녹화 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-128">To allow participants to record meetings, click **Enable recording**.</span></span>

9.  <span data-ttu-id="5c90d-129">외부 참가자가 모임을 녹음/녹화할 수 있도록 하려면 **페더레이션 및 익명 참가자의 녹화 허용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-129">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box.</span></span> <span data-ttu-id="5c90d-130">기본적으로 외부 참가자가 모임을 녹음/녹화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-130">The default is to prevent external participants from recording meetings.</span></span>

10. <span data-ttu-id="5c90d-131">**오디오/비디오**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-131">In **Audio/video**, do one of the following:</span></span>
    
      - <span data-ttu-id="5c90d-132">오디오 및 비디오를 사용 하지 않으려면 **없음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-132">To prevent the use of audio and video, click **None**.</span></span>
    
      - <span data-ttu-id="5c90d-133">오디오만 사용 하 고 비디오는 허용 하지 않으려면 **IP 오디오 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-133">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
      - <span data-ttu-id="5c90d-134">오디오 및 비디오 사용을 허용 하려면 **IP 오디오/비디오 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-134">To allow the use of audio and video, click **Enable IP audio/video**.</span></span> <span data-ttu-id="5c90d-135">이는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-135">This is the default setting.</span></span>

11. <span data-ttu-id="5c90d-136">**오디오/비디오**에서 오디오를 사용 하도록 선택한 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-136">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
      - <span data-ttu-id="5c90d-137">사용자가에서 전화를 걸어 모임에 참가할 수 없도록 하려면 **PSTN 전화 접속 회의 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-137">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box.</span></span> <span data-ttu-id="5c90d-138">기본적으로 사용자는 PSTN (공개 교환 전화 네트워크)을 사용 하 여 모임에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-138">By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
      - <span data-ttu-id="5c90d-139">사용자가 모임에 전화를 걸 수 있도록 허용 하 고 인증 되지 않은 (익명) 사용자가 전화 접속 phoning을 사용 하 여 모임에 참가할 수 있도록 허용 하려면 **익명 참가자에 게 전화를 걸 수 있도록 허용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-139">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box.</span></span> <span data-ttu-id="5c90d-140">전화 걸기 phoning를 사용 하면 회의 서버에서 사용자에 게 전화를 걸고 사용자가 모임에 참가 하기 위해 휴대폰에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-140">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting.</span></span> <span data-ttu-id="5c90d-141">기본적으로 익명 사용자는 전화 걸기 phoning를 사용 하 여 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-141">By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>

12. <span data-ttu-id="5c90d-142">**오디오/비디오**에서 비디오를 사용 하도록 선택한 경우 **여러 비디오 스트림 허용** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-142">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams** .</span></span>

13. <span data-ttu-id="5c90d-143">**데이터 공동 작업**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-143">In **Data collaboration**, do one of the following:</span></span>
    
      - <span data-ttu-id="5c90d-144">데이터 공동 작업을 방지 하려면 **없음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-144">To prevent data collaboration, click **None**.</span></span>
    
      - <span data-ttu-id="5c90d-145">데이터 공동 작업을 허용 하려면 **데이터 공동 작업 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-145">To allow data collaboration, click **Enable data collaboration**.</span></span> <span data-ttu-id="5c90d-146">이는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-146">This is the default setting.</span></span>

14. <span data-ttu-id="5c90d-147">**데이터 공동 작업**에서 데이터 공동 작업을 허용 하도록 선택한 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-147">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
      - <span data-ttu-id="5c90d-148">외부 다운로드를 방지 하려면 **페더레이션 및 익명 참가자가 콘텐츠를 다운로드할 수 있도록 허용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-148">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box.</span></span> <span data-ttu-id="5c90d-149">기본적으로 외부 사용자는 콘텐츠를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-149">By default, external users can download content.</span></span>
    
      - <span data-ttu-id="5c90d-150">파일 전송을 방지 하려면 **참가자가 파일을 전송할 수 있도록 허용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-150">To prevent file transfers, clear the **Allow participants to transfer files** check box.</span></span> <span data-ttu-id="5c90d-151">기본적으로 사용자는 파일을 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-151">By default, users can transfer files.</span></span>
    
      - <span data-ttu-id="5c90d-152">주석을 사용 하지 않으려면 **주석 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-152">To prevent the use of annotations, clear the **Enable annotations** check box.</span></span> <span data-ttu-id="5c90d-153">샤 PowerPoint 프레젠테이션에서 주석을 사용 하려면 **powerpoint 주석 사용**을 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-153">To the use of annotations in shard PowerPoint presentations, clear the **Enable PowerPoint annotations**.</span></span> <span data-ttu-id="5c90d-154">기본적으로 주석은 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-154">By default, annotations are allowed.</span></span>
    
      - <span data-ttu-id="5c90d-155">설문을 사용 하지 않으려면 **설문 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-155">To prevent the use of polls, clear the **Enable polls** check box.</span></span> <span data-ttu-id="5c90d-156">기본적으로는 설문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-156">By default, polls are allowed.</span></span>

15. <span data-ttu-id="5c90d-157">**응용 프로그램 공유**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-157">In **Application sharing**, do one of the following:</span></span>
    
      - <span data-ttu-id="5c90d-158">응용 프로그램 공유를 사용 하지 않으려면 **응용 프로그램 공유 사용 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-158">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
      - <span data-ttu-id="5c90d-159">응용 프로그램 공유를 사용 하도록 허용 하려면 **응용 프로그램 공유 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-159">To allow the use of application sharing, click **Enable application sharing**.</span></span> <span data-ttu-id="5c90d-160">이는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-160">This is the default setting.</span></span>

16. <span data-ttu-id="5c90d-161">**응용 프로그램 공유**에서 응용 프로그램 공유를 허용 하도록 선택한 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-161">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
      - <span data-ttu-id="5c90d-162">모임 참가자가 응용 프로그램 공유를 제어 하지 못하도록 하려면 참가자가 **제어권을 가질 수 있도록 허용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-162">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box.</span></span> <span data-ttu-id="5c90d-163">기본적으로 참가자는 응용 프로그램 공유에 대 한 제어권을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-163">By default, participants can take control of application sharing.</span></span>
    
      - <span data-ttu-id="5c90d-164">모임 참가자가 응용 프로그램 공유를 제어할 수 있도록 하려면 외부 사용자가 응용 프로그램 공유를 제어할 수 있도록 **페더레이션 및 익명 참가자가 제어권을 가질** 수 있도록 허용 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-164">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing.</span></span> <span data-ttu-id="5c90d-165">기본적으로 외부 사용자는 응용 프로그램 공유에 대 한 제어권을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-165">By default, external users cannot take control of application sharing.</span></span>

17. <span data-ttu-id="5c90d-166">**참가자 정책**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-166">Under **Participant policy**, do one of the following:</span></span>
    
      - <span data-ttu-id="5c90d-167">응용 프로그램 공유 및 데스크톱 공유를 모두 방지 하려면 **응용 프로그램 및 데스크톱 공유 사용 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-167">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
      - <span data-ttu-id="5c90d-168">데스크톱 공유가 아닌 응용 프로그램 공유를 허용 하려면 **응용 프로그램 공유 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-168">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
      - <span data-ttu-id="5c90d-169">응용 프로그램 공유 및 데스크톱 공유 둘 다를 허용 하려면 **응용 프로그램 및 데스크톱 공유 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-169">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**.</span></span> <span data-ttu-id="5c90d-170">이는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-170">This is the default setting.</span></span>

18. <span data-ttu-id="5c90d-171">피어 투 피어 파일 전송을 방지 하려면 피어 투 피어 **파일 전송 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-171">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box.</span></span> <span data-ttu-id="5c90d-172">기본적으로 피어 투 피어 파일 전송은 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-172">By default, peer-to-peer file transfers are allowed.</span></span>

19. <span data-ttu-id="5c90d-173">피어 투 피어 기록을 허용 하려면 피어 투 피어 **기록 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-173">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box.</span></span> <span data-ttu-id="5c90d-174">기본적으로 피어 투 피어 기록은 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-174">By default, peer-to-peer recording is not allowed.</span></span>

20. <span data-ttu-id="5c90d-175">참가자가 여러 비디오 스트림에 참가할 수 있도록 허용 하려면 **참가자가 여러 비디오 스트림에 참가할 수 있도록 설정** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-175">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box.</span></span> <span data-ttu-id="5c90d-176">기본적으로 여러 비디오 스트림을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-176">By default, multiple video streams are allowed.</span></span>

21. <span data-ttu-id="5c90d-177">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-177">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-user-or-site-policy"></a><span data-ttu-id="5c90d-178">기존 사용자 또는 사이트 정책 수정</span><span class="sxs-lookup"><span data-stu-id="5c90d-178">To modify an existing user or site policy</span></span>

1.  <span data-ttu-id="5c90d-179">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-179">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5c90d-180">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-180">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5c90d-181">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5c90d-181">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5c90d-182">왼쪽 탐색 모음에서 **회의** 를 클릭 한 다음 **회의 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-182">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="5c90d-183">회의 정책 목록에서 변경 하려는 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-183">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="5c90d-184">**회의 편집 정책**에서 수정할 수 없는 정책 이름을 제외한 모든 정책 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-184">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>

6.  <span data-ttu-id="5c90d-185">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90d-185">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

