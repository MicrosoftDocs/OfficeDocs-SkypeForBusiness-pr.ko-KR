---
title: 비즈니스용 Skype 서버에서 회의 정책 만들기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 만드는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 8e707e6da1a56fa1818d436714327936369b06fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828238"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="7c1f0-103">비즈니스용 Skype 서버에서 회의 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="7c1f0-103">Create conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="7c1f0-104">**요약:** 비즈니스용 Skype 서버에서 회의 정책을 만드는 방법을 자세히 알아보고,</span><span class="sxs-lookup"><span data-stu-id="7c1f0-104">**Summary:** Learn how to create conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="7c1f0-105">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-105">You can create conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="7c1f0-106">비즈니스용 Skype 서버 제어판을 사용하여 회의 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="7c1f0-106">Create conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7c1f0-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7c1f0-108">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="7c1f0-109">왼쪽 탐색 모음에서 회의를 클릭한 다음 회의 **정책을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c1f0-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="7c1f0-110">**다음** 을 클릭하고 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-110">Click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="7c1f0-p101">사용자 수준 정책을 만들려면 **사용자 정책** 을 클릭합니다. **새 회의 정책** 의 **이름** 에 정책에 대한 설명이 포함된 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-p101">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
   - <span data-ttu-id="7c1f0-p102">사이트 수준 정책을 만들려면 **사이트 정책** 을 클릭합니다. **사이트 선택** 검색 필드에 정책을 만들 사이트의 이름 전부 또는 일부를 입력합니다. 사이트 목록에서 원하는 사이트를 클릭하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-p102">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="7c1f0-116">사이트 이름은 회의 정책 이름이 됩니다. 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-116">The site name becomes the conferencing policy name; it cannot be changed.</span></span> 
  
5. <span data-ttu-id="7c1f0-117">**설명** 에 정책에 대한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-117">In **Description**, type a description for the policy.</span></span>
    
6. <span data-ttu-id="7c1f0-p103">**이끌이 정책** 아래의 **최대 모임 크기** 에 모임에 참가하도록 허용할 최대 사용자 수를 입력합니다. 기본적으로 최대 모임 크기는 250입니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-p103">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>
    
7. <span data-ttu-id="7c1f0-120">사용자가 익명 사용자를 모임에 초대하지 못하도록 하려면 **참가자가 익명 사용자를 초대할 수 있도록 허용** 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-120">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="7c1f0-121">익명 사용자는 조직의 Active Directory 도메인 서비스에 자격 증명이 없는 사용자로, 인증되지 않은 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-121">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="7c1f0-122">기본적으로 사용자는 익명 사용자를 모임에 초대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-122">By default, users can invite anonymous users to meetings.</span></span>
    
8. <span data-ttu-id="7c1f0-123">**녹음** 에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-123">In **Recording**, do one of the following:</span></span>
    
   - <span data-ttu-id="7c1f0-p105">참가자가 모임을 녹음하지 못하도록 하려면 **없음** 을 클릭합니다. 이것이 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-p105">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
   - <span data-ttu-id="7c1f0-126">참가자가 모임을 녹음하도록 허용하려면 **녹음 사용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-126">To allow participants to record meetings, click **Enable recording**.</span></span>
    
9. <span data-ttu-id="7c1f0-p106">외부 참가자가 모임을 녹음하도록 허용하려면 **페더레이션 참가자 및 익명 참가자가 녹음할 수 있도록 허용** 확인란을 선택합니다. 기본값은 외부 참가자가 모임을 녹음하지 못하도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-p106">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>
    
10. <span data-ttu-id="7c1f0-129">**오디오/비디오** 에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-129">In **Audio/video**, do one of the following:</span></span>
    
    - <span data-ttu-id="7c1f0-130">오디오 및 비디오 사용을 금지하려면 **없음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-130">To prevent the use of audio and video, click **None**.</span></span>
    
    - <span data-ttu-id="7c1f0-131">비디오는 사용하지 못하고 오디오만 사용하도록 허용하려면 **IP 오디오 사용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-131">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
    - <span data-ttu-id="7c1f0-p107">오디오와 비디오를 둘 다 사용하도록 허용하려면 **IP 오디오/비디오 사용** 을 클릭합니다. 이것이 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-p107">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>
    
11. <span data-ttu-id="7c1f0-134">**오디오/비디오** 에서 오디오 사용을 허용하도록 선택한 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-134">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
    - <span data-ttu-id="7c1f0-p108">사용자가 전화 접속을 통해 모임에 참가하지 못하도록 하려면 **PSTN 전화 접속 회의 사용** 확인란의 선택을 취소합니다. 기본적으로 사용자는 PSTN(공중 전화망)을 사용하여 모임에 전화 접속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-p108">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
    - <span data-ttu-id="7c1f0-p109">사용자가 모임에 전화 접속할 수 있도록 허용하고 인증되지 않은(익명) 사용자가 전화 접속 전화를 사용하여 모임에 참가하도록 허용하려면 **익명 참가자가 전화를 걸 수 있도록 허용** 확인란을 선택합니다. 전화 접속 전화를 사용하면 전화 회의 서버에서 사용자에게 전화를 걸고 사용자는 이 전화에 응답하여 모임에 참가할 수 있습니다. 기본적으로 익명 사용자는 전화 접속 전화를 사용하여 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-p109">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>
    
12. <span data-ttu-id="7c1f0-140">오디오/비디오에서 비디오를 사용할 수 있도록 선택한 경우 여러 비디오 스트림 **허용을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c1f0-140">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams**.</span></span>
    
13. <span data-ttu-id="7c1f0-141">**데이터 공동 작업** 에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-141">In **Data collaboration**, do one of the following:</span></span>
    
    - <span data-ttu-id="7c1f0-142">데이터 공동 작업을 금지하려면 **없음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-142">To prevent data collaboration, click **None**.</span></span>
    
    - <span data-ttu-id="7c1f0-p110">데이터 공동 작업을 허용하려면 **데이터 공동 작업 사용** 을 클릭합니다. 이것이 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-p110">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>
    
14. <span data-ttu-id="7c1f0-145">**데이터 공동 작업** 에서 데이터 공동 작업을 허용하도록 선택한 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-145">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
    - <span data-ttu-id="7c1f0-p111">외부 다운로드를 금지하려면 **페더레이션 참가자 및 익명 참가자가 콘텐츠를 다운로드할 수 있도록 허용** 확인란의 선택을 취소합니다. 기본적으로 외부 사용자는 콘텐츠를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-p111">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
    - <span data-ttu-id="7c1f0-p112">파일 전송을 금지하려면 **참가자가 파일을 전송할 수 있도록 허용** 확인란의 선택을 취소합니다. 기본적으로 사용자는 파일을 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-p112">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
    - <span data-ttu-id="7c1f0-150">주석 사용을 금지하려면 **주석 사용** 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-150">To prevent the use of annotations, clear the **Enable annotations** check box.</span></span> <span data-ttu-id="7c1f0-151">공유 PowerPoint 프레젠테이션에서 주석을 사용하려면 PowerPoint 사용 주석의 **선택을 취소합니다.**</span><span class="sxs-lookup"><span data-stu-id="7c1f0-151">To the use of annotations in shared PowerPoint presentations, clear the **Enable PowerPoint annotations**.</span></span> <span data-ttu-id="7c1f0-152">기본적으로 주석은 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-152">By default, annotations are allowed.</span></span>
    
    - <span data-ttu-id="7c1f0-p114">설문 사용을 금지하려면 **설문 사용** 확인란의 선택을 취소합니다. 기본적으로 설문은 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-p114">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>
    
15. <span data-ttu-id="7c1f0-155">**응용 프로그램 공유** 에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-155">In **Application sharing**, do one of the following:</span></span>
    
    - <span data-ttu-id="7c1f0-156">응용 프로그램 공유 사용을 금지하려면 **응용 프로그램 공유 사용 안 함** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-156">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
    - <span data-ttu-id="7c1f0-p115">응용 프로그램 공유 사용을 허용하려면 **응용 프로그램 공유 사용** 을 클릭합니다. 이것이 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-p115">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>
    
16. <span data-ttu-id="7c1f0-159">**응용 프로그램 공유** 에서 응용 프로그램 공유를 허용하도록 선택한 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-159">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
    - <span data-ttu-id="7c1f0-p116">모임 참가자가 응용 프로그램 공유를 제어하지 못하도록 하려면 **참가자가 제어할 수 있도록 허용** 확인란의 선택을 취소합니다. 기본적으로 참가자는 응용 프로그램 공유를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-p116">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
    - <span data-ttu-id="7c1f0-p117">모임 참가자가 응용 프로그램 공유를 제어할 수 있도록 선택한 경우 외부 사용자가 응용 프로그램 공유를 제어하도록 허용하려면 **페더레이션 참가자 및 익명 참가자가 제어할 수 있도록 허용** 확인란을 선택합니다. 기본적으로 외부 사용자는 응용 프로그램 공유를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-p117">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>
    
17. <span data-ttu-id="7c1f0-164">**참가자 정책** 에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-164">Under **Participant policy**, do one of the following:</span></span>
    
    - <span data-ttu-id="7c1f0-165">응용 프로그램 공유와 데스크톱 공유를 둘 다 금지하려면 **응용 프로그램 및 데스크톱 공유 사용 안 함** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-165">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
    - <span data-ttu-id="7c1f0-166">데스크톱 공유는 허용하지 않고 응용 프로그램 공유만 허용하려면 **응용 프로그램 공유 사용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-166">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
    - <span data-ttu-id="7c1f0-p118">응용 프로그램 공유와 데스크톱 공유를 둘 다 허용하려면 **응용 프로그램 및 데스크톱 공유 사용** 을 클릭합니다. 이것이 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-p118">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>
    
18. <span data-ttu-id="7c1f0-p119">피어 투 피어 파일 전송을 금지하려면 **피어 투 피어 파일 전송 사용** 확인란의 선택을 취소합니다. 기본적으로 피어 투 피어 파일 전송은 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-p119">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>
    
19. <span data-ttu-id="7c1f0-p120">피어 투 피어 녹음을 허용하려면 **피어 투 피어 녹음 사용** 확인란을 선택합니다. 기본적으로 피어 투 피어 녹음은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-p120">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>
    
20. <span data-ttu-id="7c1f0-p121">참가자가 여러 비디오 스트림을 사용하여 참가하도록 허용하려면 **참가자가 여러 비디오 스트림을 사용하여 참가 가능(Enable participants to join with multiple video streams)** 확인란을 선택합니다. 기본적으로 여러 비디오 스트림이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-p121">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box. By default, multiple video streams are allowed.</span></span>
    
21. <span data-ttu-id="7c1f0-175">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-175">Click **Commit**.</span></span>
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="7c1f0-176">비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="7c1f0-176">Create conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="7c1f0-177">회의 정책을 만들 경우 **New-CsConferencingPolicy** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-177">To create conferencing policies, use the **New-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="7c1f0-178">다음 예에서는 ID가 SalesConferencingPolicy인 새 회의 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-178">The following example creates a new conferencing policy with the Identity SalesConferencingPolicy.</span></span> <span data-ttu-id="7c1f0-179">이 정책은 MaxMeetingSize를 제외한 회의 정책에 대한 모든 기본값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-179">This policy will use all the default values for a conferencing policy except one: MaxMeetingSize.</span></span> <span data-ttu-id="7c1f0-180">이 예에서 모임의 최대 크기는 기본값 250이 아닌 50으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c1f0-180">In this example, the maximum size for a meeting will be set to 50 instead of the default value of 250:</span></span>
  
```PowerShell
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

<span data-ttu-id="7c1f0-181">전체 구문 설명 및 매개 변수 목록을 비롯한 자세한 내용은 [New-CsConferencingPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="7c1f0-181">For more information, including a complete syntax description and list of parameters, see [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span></span>
  

