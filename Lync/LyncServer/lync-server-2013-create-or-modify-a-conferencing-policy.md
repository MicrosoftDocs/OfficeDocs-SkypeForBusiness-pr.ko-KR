---
title: 'Lync Server 2013: 회의 정책 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing policy
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49733844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f5deeab8d2df55f4f2e91a1a90909a3550a3a56
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="c9e06-102">Lync Server 2013에서 회의 정책 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="c9e06-102">Create or modify a conferencing policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9e06-103">_**마지막으로 수정 된 항목:** 2013-02-07_</span><span class="sxs-lookup"><span data-stu-id="c9e06-103">_**Topic Last Modified:** 2013-02-07_</span></span>

<span data-ttu-id="c9e06-104">다음 단계에 따라 사용자 수준 또는 사이트 수준의 회의 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-104">Follow these steps to create a user-level or a site-level conferencing policy.</span></span> <span data-ttu-id="c9e06-105">사용자에 게 사용자 수준 정책을 할당 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 사용자 단위 회의 정책 할당](lync-server-2013-assign-a-per-user-conferencing-policy.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c9e06-105">For details about how to assign a user-level policy to a user, see [Assign a per-user conferencing policy in Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span></span> <span data-ttu-id="c9e06-106">사용 가능한 모든 회의 정책 설정 목록은 [Lync Server 2013에 대 한 회의 정책 설정 참조](lync-server-2013-conferencing-policy-settings-reference.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c9e06-106">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-create-a-new-user-or-site-policy"></a><span data-ttu-id="c9e06-107">새 사용자 또는 사이트 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="c9e06-107">To create a new user or site policy</span></span>

1.  <span data-ttu-id="c9e06-108">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c9e06-109">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c9e06-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c9e06-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c9e06-111">왼쪽 탐색 모음에서 **회의**를 클릭하고 **회의 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-111">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="c9e06-112">**다음**을 클릭하고 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-112">Click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="c9e06-p103">사용자 수준 정책을 만들려면 **사용자 정책**을 클릭합니다. **새 회의 정책**의 **이름**에 정책에 대한 설명이 포함된 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p103">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
      - <span data-ttu-id="c9e06-p104">사이트 수준 정책을 만들려면 **사이트 정책**을 클릭합니다. **사이트 선택** 검색 필드에 정책을 만들 사이트의 이름 전부 또는 일부를 입력합니다. 사이트 목록에서 원하는 사이트를 클릭하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p104">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c9e06-118">사이트 이름이 회의 정책 이름이 되며 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-118">The site name becomes the conferencing policy name, and it cannot be changed.</span></span>

        
        </div>

5.  <span data-ttu-id="c9e06-119">**설명**에 정책에 대한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-119">In **Description**, type a description for the policy.</span></span>

6.  <span data-ttu-id="c9e06-p105">**이끌이 정책** 아래의 **최대 모임 크기**에 모임에 참가하도록 허용할 최대 사용자 수를 입력합니다. 기본적으로 최대 모임 크기는 250입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p105">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>

7.  <span data-ttu-id="c9e06-122">사용자가 익명 사용자를 모임에 초대하지 못하도록 하려면 **참가자가 익명 사용자를 초대할 수 있도록 허용** 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-122">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="c9e06-123">익명 사용자는 조직의 Active Directory 도메인 서비스에 자격 증명을 갖고 있지 않으며 인증 되지 않은 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-123">Anonymous users are users who do not have credentials in your organization’s Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="c9e06-124">기본적으로 사용자는 익명 사용자를 모임에 초대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-124">By default, users can invite anonymous users to meetings.</span></span>

8.  <span data-ttu-id="c9e06-125">**녹음**에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-125">In **Recording**, do one of the following:</span></span>
    
      - <span data-ttu-id="c9e06-p107">참가자가 모임을 녹음하지 못하도록 하려면 **없음**을 클릭합니다. 이것이 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p107">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
      - <span data-ttu-id="c9e06-128">참가자가 모임을 녹음하도록 허용하려면 **녹음 사용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-128">To allow participants to record meetings, click **Enable recording**.</span></span>

9.  <span data-ttu-id="c9e06-p108">외부 참가자가 모임을 녹음하도록 허용하려면 **페더레이션 참가자 및 익명 참가자가 녹음할 수 있도록 허용** 확인란을 선택합니다. 기본값은 외부 참가자가 모임을 녹음하지 못하도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p108">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>

10. <span data-ttu-id="c9e06-131">**오디오/비디오**에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-131">In **Audio/video**, do one of the following:</span></span>
    
      - <span data-ttu-id="c9e06-132">오디오 및 비디오 사용을 금지하려면 **없음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-132">To prevent the use of audio and video, click **None**.</span></span>
    
      - <span data-ttu-id="c9e06-133">비디오는 사용하지 못하고 오디오만 사용하도록 허용하려면 **IP 오디오 사용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-133">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
      - <span data-ttu-id="c9e06-p109">오디오와 비디오를 둘 다 사용하도록 허용하려면 **IP 오디오/비디오 사용**을 클릭합니다. 이것이 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p109">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>

11. <span data-ttu-id="c9e06-136">**오디오/비디오**에서 오디오 사용을 허용하도록 선택한 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-136">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
      - <span data-ttu-id="c9e06-p110">사용자가 전화 접속을 통해 모임에 참가하지 못하도록 하려면 **PSTN 전화 접속 회의 사용** 확인란의 선택을 취소합니다. 기본적으로 사용자는 PSTN(공중 전화망)을 사용하여 모임에 전화 접속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p110">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
      - <span data-ttu-id="c9e06-p111">사용자가 모임에 전화 접속할 수 있도록 허용하고 인증되지 않은(익명) 사용자가 전화 접속 전화를 사용하여 모임에 참가하도록 허용하려면 **익명 참가자가 전화를 걸 수 있도록 허용** 확인란을 선택합니다. 전화 접속 전화를 사용하면 전화 회의 서버에서 사용자에게 전화를 걸고 사용자는 이 전화에 응답하여 모임에 참가할 수 있습니다. 기본적으로 익명 사용자는 전화 접속 전화를 사용하여 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p111">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>

12. <span data-ttu-id="c9e06-142">**오디오/비디오**에서 비디오 사용을 허용하도록 선택한 경우 **여러 비디오 스트림 허용(Allow multiple video streams)** 을 선택합니다. .</span><span class="sxs-lookup"><span data-stu-id="c9e06-142">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams** .</span></span>

13. <span data-ttu-id="c9e06-143">**데이터 공동 작업**에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-143">In **Data collaboration**, do one of the following:</span></span>
    
      - <span data-ttu-id="c9e06-144">데이터 공동 작업을 금지하려면 **없음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-144">To prevent data collaboration, click **None**.</span></span>
    
      - <span data-ttu-id="c9e06-p112">데이터 공동 작업을 허용하려면 **데이터 공동 작업 사용**을 클릭합니다. 이것이 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p112">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>

14. <span data-ttu-id="c9e06-147">**데이터 공동 작업**에서 데이터 공동 작업을 허용하도록 선택한 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-147">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
      - <span data-ttu-id="c9e06-p113">외부 다운로드를 금지하려면 **페더레이션 참가자 및 익명 참가자가 콘텐츠를 다운로드할 수 있도록 허용** 확인란의 선택을 취소합니다. 기본적으로 외부 사용자는 콘텐츠를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p113">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
      - <span data-ttu-id="c9e06-p114">파일 전송을 금지하려면 **참가자가 파일을 전송할 수 있도록 허용** 확인란의 선택을 취소합니다. 기본적으로 사용자는 파일을 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p114">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
      - <span data-ttu-id="c9e06-p115">주석 사용을 금지하려면 **주석 사용** 확인란의 선택을 취소합니다. 분할된 PowerPoint 프레젠테이션에서 주석 사용을 금지하려면 **PowerPoint 주석 사용**의 선택을 취소합니다. 기본적으로 주석은 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p115">To prevent the use of annotations, clear the **Enable annotations** check box. To the use of annotations in shard PowerPoint presentations, clear the **Enable PowerPoint annotations**. By default, annotations are allowed.</span></span>
    
      - <span data-ttu-id="c9e06-p116">설문 사용을 금지하려면 **설문 사용** 확인란의 선택을 취소합니다. 기본적으로 설문은 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p116">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>

15. <span data-ttu-id="c9e06-157">**응용 프로그램 공유**에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-157">In **Application sharing**, do one of the following:</span></span>
    
      - <span data-ttu-id="c9e06-158">응용 프로그램 공유 사용을 금지하려면 **응용 프로그램 공유 사용 안 함**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-158">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
      - <span data-ttu-id="c9e06-p117">응용 프로그램 공유 사용을 허용하려면 **응용 프로그램 공유 사용**을 클릭합니다. 이것이 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p117">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>

16. <span data-ttu-id="c9e06-161">**응용 프로그램 공유**에서 응용 프로그램 공유를 허용하도록 선택한 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-161">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
      - <span data-ttu-id="c9e06-p118">모임 참가자가 응용 프로그램 공유를 제어하지 못하도록 하려면 **참가자가 제어할 수 있도록 허용** 확인란의 선택을 취소합니다. 기본적으로 참가자는 응용 프로그램 공유를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p118">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
      - <span data-ttu-id="c9e06-p119">모임 참가자가 응용 프로그램 공유를 제어할 수 있도록 선택한 경우 외부 사용자가 응용 프로그램 공유를 제어하도록 허용하려면 **페더레이션 참가자 및 익명 참가자가 제어할 수 있도록 허용** 확인란을 선택합니다. 기본적으로 외부 사용자는 응용 프로그램 공유를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p119">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>

17. <span data-ttu-id="c9e06-166">**참가자 정책**에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-166">Under **Participant policy**, do one of the following:</span></span>
    
      - <span data-ttu-id="c9e06-167">응용 프로그램 공유와 데스크톱 공유를 둘 다 금지하려면 **응용 프로그램 및 데스크톱 공유 사용 안 함**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-167">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
      - <span data-ttu-id="c9e06-168">데스크톱 공유는 허용하지 않고 응용 프로그램 공유만 허용하려면 **응용 프로그램 공유 사용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-168">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
      - <span data-ttu-id="c9e06-p120">응용 프로그램 공유와 데스크톱 공유를 둘 다 허용하려면 **응용 프로그램 및 데스크톱 공유 사용**을 클릭합니다. 이것이 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p120">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>

18. <span data-ttu-id="c9e06-p121">피어 투 피어 파일 전송을 금지하려면 **피어 투 피어 파일 전송 사용** 확인란의 선택을 취소합니다. 기본적으로 피어 투 피어 파일 전송은 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p121">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>

19. <span data-ttu-id="c9e06-p122">피어 투 피어 녹음을 허용하려면 **피어 투 피어 녹음 사용** 확인란을 선택합니다. 기본적으로 피어 투 피어 녹음은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p122">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>

20. <span data-ttu-id="c9e06-p123">참가자가 여러 비디오 스트림을 사용하여 참가하도록 허용하려면 **참가자가 여러 비디오 스트림을 사용하여 참가 가능(Enable participants to join with multiple video streams)** 확인란을 선택합니다. 기본적으로 여러 비디오 스트림이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-p123">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box. By default, multiple video streams are allowed.</span></span>

21. <span data-ttu-id="c9e06-177">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-177">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-user-or-site-policy"></a><span data-ttu-id="c9e06-178">기존 사용자 또는 사이트 정책을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="c9e06-178">To modify an existing user or site policy</span></span>

1.  <span data-ttu-id="c9e06-179">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-179">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c9e06-180">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-180">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c9e06-181">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c9e06-181">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c9e06-182">왼쪽 탐색 모음에서 **회의**를 클릭하고 **회의 정책**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-182">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="c9e06-183">회의 정책 목록에서 변경할 정책을 클릭하고 **편집**을 클릭한 다음 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-183">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c9e06-184">**회의 정책 편집**에서 수정이 불가능한 정책 이름을 제외한 정책 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-184">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>

6.  <span data-ttu-id="c9e06-185">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e06-185">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

