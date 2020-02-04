---
title: 'Lync Server 2013: 갤러리 보기 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06054e1728245c87e8bf35419d3890f4e379543a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="31193-102">Lync Server 2013에서 갤러리 보기 구성</span><span class="sxs-lookup"><span data-stu-id="31193-102">Configuring Gallery View in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31193-103">_**마지막으로 수정한 주제:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="31193-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="31193-104">Lync Server 2013에서 전화 회의 정책으로 갤러리 보기 영상 회의를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="31193-104">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="31193-105">갤러리 보기는 기본적으로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31193-105">Gallery View is turned on by default.</span></span> <span data-ttu-id="31193-106">갤러리 보기를 허용 하지 않거나 일부 사용자만 사용할 수 있도록 하려면, 회의 정책에서 기능을 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31193-106">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="31193-107">회의 참가자의 비디오를 사용할 수 없는 경우 Lync Server 2013의 새로운 기능인 고해상도 사진을 배포 하는 경우 사용자의 갤러리 보기 환경을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31193-107">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="31193-108">고해상도 사진에는 Active Directory 도메인 서비스에 저장 된 작고 제한적인 해상도의 연락처 사진이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31193-108">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="31193-109">고해상도 사진은 사용자의 Exchange 2013 사서함에 저장 되므로 Lync Server 2013을 Exchange 2013과 통합 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31193-109">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="31193-110">자세한 내용은의 NextHop 블로그 문서 "Exchange 2013 및 Lync Server 2013 통합"을 참조 하세요 [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987).</span><span class="sxs-lookup"><span data-stu-id="31193-110">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="31193-111">각 블로그 및 해당 URL의 콘텐츠는 예 고 없이 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31193-111">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="31193-112">Lync Server 2013 제어판을 사용 하거나 다음 cmdlet 중 하나를 사용 하 여 갤러리 보기 매개 변수를 보거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31193-112">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="31193-113">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="31193-113">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="31193-114">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="31193-114">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="31193-115">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="31193-115">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="31193-116">다음 회의 정책 설정을 사용 하 여 갤러리 보기를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="31193-116">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="31193-117">**AllowMultiview**   이 매개 변수는 사용자가 갤러리 보기 영상 회의를 구성할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="31193-117">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="31193-118">이 매개 변수는 사용자가 만든 예약 및 임시 모임에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31193-118">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="31193-119">예제의</span><span class="sxs-lookup"><span data-stu-id="31193-119">Examples:</span></span>
    
      - <span data-ttu-id="31193-120">이 매개 변수는 사용자 A에 대해 True로 설정 되며,이는 Lync Server 2013 풀에 속한 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="31193-120">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="31193-121">사용자가 구성 된 모임-사용자가 여러 비디오 스트림을 연결 하 고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31193-121">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="31193-122">이 매개 변수는 사용자 B에 대해 False로 설정 되며, Lync Server 2013 풀에는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31193-122">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="31193-123">사용자 B가 구성한 모임에는 Lync Server 2010에서 제공 하는 비디오 컨퍼런스 환경과 비슷한 단일 비디오 스트림이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31193-123">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="31193-124">이 매개 변수는 여러 비디오 스트림을 허용 하는 모임을 구성할 수 있는 사용자를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31193-124">This parameter determines who can organize meetings that allow multiple video streams.</span></span> <span data-ttu-id="31193-125">여러 비디오 스트림을 허용 하는 모임의 참가자는 개별 사용 권한에 따라 여러 비디오 스트림을 받을 수 있거나 허용 하지 않을 수 있습니다 (EnableMultiviewJoin 매개 변수에 대 한 설명 참조).</span><span class="sxs-lookup"><span data-stu-id="31193-125">Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="31193-126">**EnableMultiviewJoin**   이 매개 변수는 모임 참가자가 모임을 허용 하는 모임에서 갤러리 보기 비디오 환경을 받을지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="31193-126">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="31193-127">이 매개 변수는 자신이 참여 한 모든 모임에서 사용자 환경을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="31193-127">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="31193-128">예제의</span><span class="sxs-lookup"><span data-stu-id="31193-128">Examples:</span></span>
    
      - <span data-ttu-id="31193-129">이 매개 변수는 사용자 A가 구성 하거나 시작 하는 모임에 참가할 때 여러 비디오 스트림을 받을 수 있습니다. 사용자 C는 Lync Server 2010에서 제공 하는 비디오 컨퍼런스 환경과 비슷한 단일 비디오 스트림을 받습니다. 사용자 B가 구성 하거나 시작한 모임 참가</span><span class="sxs-lookup"><span data-stu-id="31193-129">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="31193-130">이 매개 변수는 사용자 D에 대해 False로 설정 됩니다. 사용자 D는 사용자 A 또는 사용자 B가 구성한 모임에 참가할 때 Lync Server 2010에서 제공 하는 비디오 컨퍼런스 환경과 비슷한 단일 비디오 스트림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="31193-130">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="31193-131">다음 절차는 Lync Server Management Shell을 사용 하 여 갤러리 보기 영상 회의를 사용 하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="31193-131">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="31193-132">갤러리에서 비디오 회의를 보기 위해 회의 정책을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="31193-132">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="31193-133">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="31193-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="31193-134">명령줄에서 다음 cmdlet을 실행 하 여 회의 정책을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="31193-134">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

