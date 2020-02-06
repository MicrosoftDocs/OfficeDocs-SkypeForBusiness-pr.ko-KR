---
title: 비즈니스용 Skype 서버에서 회의 정책 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 만드는 방법에 대해 알아보세요.'
ms.openlocfilehash: 6fc8145e5f7c4dc0ee4b824a92248e365df56213
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818619"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="aa874-103">비즈니스용 Skype 서버에서 회의 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="aa874-103">Create conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="aa874-104">**요약:** 비즈니스용 Skype 서버에서 회의 정책을 만드는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-104">**Summary:** Learn how to create conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="aa874-105">Skype for Business Server 제어판을 사용 하거나 비즈니스용 Skype 서버 관리 셸을 사용 하 여 회의 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-105">You can create conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="aa874-106">비즈니스용 Skype 서버 제어판을 사용 하 여 회의 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="aa874-106">Create conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="aa874-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="aa874-108">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="aa874-109">왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **회의 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="aa874-110">**새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-110">Click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="aa874-111">사용자 수준 정책을 만들려면 **사용자 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-111">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="aa874-112">**새 회의 정책의** **이름**에 정책에 대 한 설명이 포함 된 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-112">In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
   - <span data-ttu-id="aa874-113">사이트 수준 정책을 만들려면 **사이트 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-113">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="aa874-114">사이트 검색 **선택** 필드에 정책을 만들려는 사이트 이름의 전부 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-114">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="aa874-115">사이트 목록에서 원하는 사이트를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-115">In the list of sites, click the site that you want, and then click **OK**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="aa874-116">사이트 이름이 회의 정책 이름이 됩니다. 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-116">The site name becomes the conferencing policy name; it cannot be changed.</span></span> 
  
5. <span data-ttu-id="aa874-117">**설명**에 정책에 대 한 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-117">In **Description**, type a description for the policy.</span></span>
    
6. <span data-ttu-id="aa874-118">**이끌이 정책의** **최대 모임 크기**에 모임에서 허용 하려는 최대 사용자 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-118">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting.</span></span> <span data-ttu-id="aa874-119">기본적으로 최대 모임 크기는 250입니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-119">By default, the maximum meeting size is 250.</span></span>
    
7. <span data-ttu-id="aa874-120">사용자가 익명 사용자를 모임에 초대 하지 못하도록 하려면 **참가자가 익명 사용자 초대를 허용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-120">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="aa874-121">익명 사용자는 조직의 Active Directory 도메인 서비스에 자격 증명이 없고 인증 되지 않은 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-121">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="aa874-122">기본적으로 사용자는 모임에 익명 사용자를 초대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-122">By default, users can invite anonymous users to meetings.</span></span>
    
8. <span data-ttu-id="aa874-123">**기록**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-123">In **Recording**, do one of the following:</span></span>
    
   - <span data-ttu-id="aa874-124">참가자가 모임을 녹음/녹화할 수 없도록 하려면 **없음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-124">To prevent participants from recording meetings, click **None**.</span></span> <span data-ttu-id="aa874-125">이는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-125">This is the default setting.</span></span>
    
   - <span data-ttu-id="aa874-126">참가자가 모임을 녹음/녹화할 수 있도록 하려면 **녹음/녹화 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-126">To allow participants to record meetings, click **Enable recording**.</span></span>
    
9. <span data-ttu-id="aa874-127">외부 참가자가 모임을 녹음/녹화할 수 있도록 하려면 **페더레이션 및 익명 참가자의 녹화 허용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-127">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box.</span></span> <span data-ttu-id="aa874-128">기본적으로 외부 참가자가 모임을 녹음/녹화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-128">The default is to prevent external participants from recording meetings.</span></span>
    
10. <span data-ttu-id="aa874-129">**오디오/비디오**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-129">In **Audio/video**, do one of the following:</span></span>
    
    - <span data-ttu-id="aa874-130">오디오 및 비디오를 사용 하지 않으려면 **없음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-130">To prevent the use of audio and video, click **None**.</span></span>
    
    - <span data-ttu-id="aa874-131">오디오만 사용 하 고 비디오는 허용 하지 않으려면 **IP 오디오 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-131">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
    - <span data-ttu-id="aa874-132">오디오 및 비디오 사용을 허용 하려면 **IP 오디오/비디오 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-132">To allow the use of audio and video, click **Enable IP audio/video**.</span></span> <span data-ttu-id="aa874-133">이는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-133">This is the default setting.</span></span>
    
11. <span data-ttu-id="aa874-134">**오디오/비디오**에서 오디오를 사용 하도록 선택한 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-134">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
    - <span data-ttu-id="aa874-135">사용자가에서 전화를 걸어 모임에 참가할 수 없도록 하려면 **PSTN 전화 접속 회의 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-135">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box.</span></span> <span data-ttu-id="aa874-136">기본적으로 사용자는 PSTN (공개 교환 전화 네트워크)을 사용 하 여 모임에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-136">By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
    - <span data-ttu-id="aa874-137">사용자가 모임에 전화를 걸 수 있도록 허용 하 고 인증 되지 않은 (익명) 사용자가 전화 접속 phoning을 사용 하 여 모임에 참가할 수 있도록 허용 하려면 **익명 참가자에 게 전화를 걸 수 있도록 허용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-137">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box.</span></span> <span data-ttu-id="aa874-138">전화 걸기 phoning를 사용 하면 회의 서버에서 사용자에 게 전화를 걸고 사용자가 모임에 참가 하기 위해 휴대폰에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-138">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting.</span></span> <span data-ttu-id="aa874-139">기본적으로 익명 사용자는 전화 걸기 phoning를 사용 하 여 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-139">By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>
    
12. <span data-ttu-id="aa874-140">**오디오/비디오**에서 비디오를 사용 하도록 선택한 경우 **여러 비디오 스트림 허용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-140">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams**.</span></span>
    
13. <span data-ttu-id="aa874-141">**데이터 공동 작업**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-141">In **Data collaboration**, do one of the following:</span></span>
    
    - <span data-ttu-id="aa874-142">데이터 공동 작업을 방지 하려면 **없음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-142">To prevent data collaboration, click **None**.</span></span>
    
    - <span data-ttu-id="aa874-143">데이터 공동 작업을 허용 하려면 **데이터 공동 작업 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-143">To allow data collaboration, click **Enable data collaboration**.</span></span> <span data-ttu-id="aa874-144">이는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-144">This is the default setting.</span></span>
    
14. <span data-ttu-id="aa874-145">**데이터 공동 작업**에서 데이터 공동 작업을 허용 하도록 선택한 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-145">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
    - <span data-ttu-id="aa874-146">외부 다운로드를 방지 하려면 **페더레이션 및 익명 참가자가 콘텐츠를 다운로드할 수 있도록 허용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-146">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box.</span></span> <span data-ttu-id="aa874-147">기본적으로 외부 사용자는 콘텐츠를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-147">By default, external users can download content.</span></span>
    
    - <span data-ttu-id="aa874-148">파일 전송을 방지 하려면 **참가자가 파일을 전송할 수 있도록 허용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-148">To prevent file transfers, clear the **Allow participants to transfer files** check box.</span></span> <span data-ttu-id="aa874-149">기본적으로 사용자는 파일을 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-149">By default, users can transfer files.</span></span>
    
    - <span data-ttu-id="aa874-150">주석을 사용 하지 않으려면 **주석 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-150">To prevent the use of annotations, clear the **Enable annotations** check box.</span></span> <span data-ttu-id="aa874-151">PowerPoint 프레젠테이션 공유에서 주석을 사용 하려면 **powerpoint 주석 사용**을 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-151">To the use of annotations in shared PowerPoint presentations, clear the **Enable PowerPoint annotations**.</span></span> <span data-ttu-id="aa874-152">기본적으로 주석은 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-152">By default, annotations are allowed.</span></span>
    
    - <span data-ttu-id="aa874-153">설문을 사용 하지 않으려면 **설문 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-153">To prevent the use of polls, clear the **Enable polls** check box.</span></span> <span data-ttu-id="aa874-154">기본적으로는 설문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-154">By default, polls are allowed.</span></span>
    
15. <span data-ttu-id="aa874-155">**응용 프로그램 공유**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-155">In **Application sharing**, do one of the following:</span></span>
    
    - <span data-ttu-id="aa874-156">응용 프로그램 공유를 사용 하지 않으려면 **응용 프로그램 공유 사용 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-156">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
    - <span data-ttu-id="aa874-157">응용 프로그램 공유를 사용 하도록 허용 하려면 **응용 프로그램 공유 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-157">To allow the use of application sharing, click **Enable application sharing**.</span></span> <span data-ttu-id="aa874-158">이는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-158">This is the default setting.</span></span>
    
16. <span data-ttu-id="aa874-159">**응용 프로그램 공유**에서 응용 프로그램 공유를 허용 하도록 선택한 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-159">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
    - <span data-ttu-id="aa874-160">모임 참가자가 응용 프로그램 공유를 제어 하지 못하도록 하려면 참가자가 **제어권을 가질 수 있도록 허용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-160">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box.</span></span> <span data-ttu-id="aa874-161">기본적으로 참가자는 응용 프로그램 공유에 대 한 제어권을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-161">By default, participants can take control of application sharing.</span></span>
    
    - <span data-ttu-id="aa874-162">모임 참가자가 응용 프로그램 공유를 제어할 수 있도록 하려면 외부 사용자가 응용 프로그램 공유를 제어할 수 있도록 **페더레이션 및 익명 참가자가 제어권을 가질** 수 있도록 허용 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-162">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing.</span></span> <span data-ttu-id="aa874-163">기본적으로 외부 사용자는 응용 프로그램 공유에 대 한 제어권을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-163">By default, external users cannot take control of application sharing.</span></span>
    
17. <span data-ttu-id="aa874-164">**참가자 정책**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-164">Under **Participant policy**, do one of the following:</span></span>
    
    - <span data-ttu-id="aa874-165">응용 프로그램 공유 및 데스크톱 공유를 모두 방지 하려면 **응용 프로그램 및 데스크톱 공유 사용 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-165">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
    - <span data-ttu-id="aa874-166">데스크톱 공유가 아닌 응용 프로그램 공유를 허용 하려면 **응용 프로그램 공유 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-166">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
    - <span data-ttu-id="aa874-167">응용 프로그램 공유 및 데스크톱 공유 둘 다를 허용 하려면 **응용 프로그램 및 데스크톱 공유 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-167">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**.</span></span> <span data-ttu-id="aa874-168">이는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-168">This is the default setting.</span></span>
    
18. <span data-ttu-id="aa874-169">피어 투 피어 파일 전송을 방지 하려면 피어 투 피어 **파일 전송 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-169">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box.</span></span> <span data-ttu-id="aa874-170">기본적으로 피어 투 피어 파일 전송은 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-170">By default, peer-to-peer file transfers are allowed.</span></span>
    
19. <span data-ttu-id="aa874-171">피어 투 피어 기록을 허용 하려면 피어 투 피어 **기록 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-171">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box.</span></span> <span data-ttu-id="aa874-172">기본적으로 피어 투 피어 기록은 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-172">By default, peer-to-peer recording is not allowed.</span></span>
    
20. <span data-ttu-id="aa874-173">참가자가 여러 비디오 스트림에 참가할 수 있도록 허용 하려면 **참가자가 여러 비디오 스트림에 참가할 수 있도록 설정** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-173">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box.</span></span> <span data-ttu-id="aa874-174">기본적으로 여러 비디오 스트림을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-174">By default, multiple video streams are allowed.</span></span>
    
21. <span data-ttu-id="aa874-175">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-175">Click **Commit**.</span></span>
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="aa874-176">비즈니스용 Skype Server Management Shell을 사용 하 여 회의 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="aa874-176">Create conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="aa874-177">회의 정책을 만들려면 **새 CsConferencingPolicy** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-177">To create conferencing policies, use the **New-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="aa874-178">다음 예에서는 Id SalesConferencingPolicy를 사용 하 여 새 회의 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-178">The following example creates a new conferencing policy with the Identity SalesConferencingPolicy.</span></span> <span data-ttu-id="aa874-179">이 정책은 1: MaxMeetingSize를 제외한 회의 정책에 대 한 모든 기본값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-179">This policy will use all the default values for a conferencing policy except one: MaxMeetingSize.</span></span> <span data-ttu-id="aa874-180">이 예제에서 모임의 최대 크기는 250의 기본값 대신 50로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa874-180">In this example, the maximum size for a meeting will be set to 50 instead of the default value of 250:</span></span>
  
```PowerShell
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

<span data-ttu-id="aa874-181">전체 구문 설명과 매개 변수 목록을 비롯 한 자세한 내용은 [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa874-181">For more information, including a complete syntax description and list of parameters, see [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span></span>
  

