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
ms.openlocfilehash: 02c13f2b1fa312394edfaba01ecd05179f86a0c9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="d2dac-102">Lync Server 2013에서 갤러리 보기 구성</span><span class="sxs-lookup"><span data-stu-id="d2dac-102">Configuring Gallery View in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2dac-103">_**마지막으로 수정 된 항목:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="d2dac-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="d2dac-104">Lync Server 2013에서는 회의 정책에서 갤러리 보기 비디오 회의를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-104">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="d2dac-105">갤러리 보기는 기본적으로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-105">Gallery View is turned on by default.</span></span> <span data-ttu-id="d2dac-106">갤러리 보기를 허용하지 않거나 일부 사용자에게만 허용하려는 경우 회의 정책에서 이 기능을 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-106">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="d2dac-107">전화 회의 참가자의 비디오를 사용할 수 없는 경우 고해상도 사진을 배포할 경우 Lync Server 2013의 새로운 기능인 사용자 갤러리 보기 환경을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-107">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="d2dac-108">고해상도 사진을 사용 하면 Active Directory 도메인 서비스에 저장 된 작고 제한 된 연락처 사진을 보다 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-108">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="d2dac-109">고해상도 사진은 사용자의 Exchange 2013 사서함에 저장 되므로 Lync Server 2013과 Exchange 2013을 통합 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-109">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="d2dac-110">자세한 내용은 다음 홉 블로그 문서 "Exchange 2013 및 Lync Server 2013 통합"을 참조 [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987)하세요.</span><span class="sxs-lookup"><span data-stu-id="d2dac-110">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d2dac-111">각 블로그의 콘텐츠와 해당 URL은 사전 통지 없이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-111">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="d2dac-112">Lync Server 2013 제어판을 사용 하거나 다음 cmdlet 중 하나를 사용 하 여 갤러리 보기 매개 변수를 보거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-112">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="d2dac-113">**Get-csconferencingpolicy**</span><span class="sxs-lookup"><span data-stu-id="d2dac-113">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="d2dac-114">**Get-csconferencingpolicy**</span><span class="sxs-lookup"><span data-stu-id="d2dac-114">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="d2dac-115">**Get-csconferencingpolicy**</span><span class="sxs-lookup"><span data-stu-id="d2dac-115">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="d2dac-116">다음 회의 정책 설정으로 갤러리 보기를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-116">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="d2dac-117">**AllowMultiview**   이 매개 변수는 사용자가 갤러리 보기 비디오 회의를 구성할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-117">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="d2dac-118">이 매개 변수는 사용자가 만드는 예약 모임 및 임시 모임에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-118">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="d2dac-119">예제:</span><span class="sxs-lookup"><span data-stu-id="d2dac-119">Examples:</span></span>
    
      - <span data-ttu-id="d2dac-120">이 매개 변수는 Lync Server 2013 풀에 있는 사용자 A에 대해 True로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-120">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="d2dac-121">사용자 A가 구성하는 모임에서는 사용자가 모임에 참가하고 여러 비디오 스트림을 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-121">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="d2dac-122">Lync Server 2013 풀에 있는 사용자 B에 대해이 매개 변수는 False로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-122">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="d2dac-123">사용자 B가 구성한 모임에는 Lync Server 2010에서 제공 하는 비디오 회의 환경과 유사한 단일 비디오 스트림이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-123">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="d2dac-p106">이 매개 변수는 여러 비디오 스트림을 허용하는 모임을 구성할 수 있는 사용자를 결정합니다. 여러 비디오 스트림을 허용하는 모임의 참가자는 개별 권한에 따라 여러 비디오 스트림을 수신하도록 허용되거나 허용되지 않을 수 있습니다(EnableMultiviewJoin 매개 변수 설명 참조).</span><span class="sxs-lookup"><span data-stu-id="d2dac-p106">This parameter determines who can organize meetings that allow multiple video streams. Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="d2dac-126">**EnableMultiviewJoin**   이 매개 변수는 모임 참가자가 허용 되는 모임에서 갤러리 보기 비디오 환경을 받는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-126">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="d2dac-127">이 매개 변수는 사용자가 참가하는 모임에서 사용자의 경험을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-127">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="d2dac-128">예제:</span><span class="sxs-lookup"><span data-stu-id="d2dac-128">Examples:</span></span>
    
      - <span data-ttu-id="d2dac-129">이 매개 변수는 사용자 A가 구성 하거나 시작한 모임에 참가 하는 경우 여러 비디오 스트림을 받을 수 있습니다. User c는 다음과 같은 경우 Lync Server 2010에서 제공 하는 비디오 회의 환경과 유사한 단일 비디오 스트림을 받습니다. 사용자 B가 구성 하거나 시작한 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-129">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="d2dac-130">이 매개 변수는 사용자 D에 대해 False로 설정 됩니다. user D는 사용자 A 또는 사용자 B가 구성한 모든 모임에 참여할 때 Lync Server 2010에서 제공 하는 비디오 회의 환경과 유사한 단일 비디오 스트림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-130">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="d2dac-131">다음 절차는 Lync Server 관리 셸을 사용 하 여 갤러리 보기 비디오 회의를 사용 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-131">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="d2dac-132">갤러리 보기 비디오 회의에 대한 회의 정책을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="d2dac-132">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="d2dac-133">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d2dac-134">명령줄에서 다음 cmdlet을 실행하여 회의 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="d2dac-134">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

