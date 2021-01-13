---
title: Skype 룸 시스템 마이그레이션 고려 사항
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: 이 항목을 통해 비즈니스용 Skype 서버 및 Lync Server의 여러 버전이 있는 환경에서 Skype 룸 시스템을 배포하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 30b2a4733ea2e2e42b8a879914a2e0e3c4903c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805788"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="0ce64-103">Skype 룸 시스템 마이그레이션 고려 사항</span><span class="sxs-lookup"><span data-stu-id="0ce64-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="0ce64-104">이 항목을 통해 비즈니스용 Skype 서버 및 Lync Server의 여러 버전이 있는 환경에서 Skype 룸 시스템을 배포하는 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="0ce64-105">마이그레이션 고려 사항</span><span class="sxs-lookup"><span data-stu-id="0ce64-105">Migration considerations</span></span>

<span data-ttu-id="0ce64-106">이 섹션에서는 서로 다른 버전의 비즈니스용 Skype 서버 또는 Lync Server를 포함하는 다중 풀 환경에서 Skype 룸 시스템을 배포하는 경우 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="0ce64-107">Lync Server의 UR(User Replicator) 구성 요소는 Active Directory에서 사용자 개체를 사용하여 Lync Server 백 엔드 서버 SQL Server 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="0ce64-108">Lync Server 2013의 UR만 Skype 룸 시스템 개체를 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="0ce64-109">이전 버전의 Lync Server 및 Office Communications Server의 UR는 LRS 개체를 지정하는 Active Directory 특성을 검색하지 못하므로 이를 인식하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="0ce64-110">Skype 채팅방 시스템 계정이 Lync에 로그인을 시도하고 SRV 레코드 또는 DNS A 레코드를 기반으로 자동 검색을 수행하는 경우 해당 계정이 이전 버전의 Lync Server 또는 Office Communications Server를 기준으로 하는 경우 LRS는 레거시 풀에서 404 찾을 수 없는 응답을 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="0ce64-111">레거시 풀은 Skype 룸 시스템을 Lync Server 2013 홈 풀로 리디렉션할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="0ce64-112">다음 옵션으로 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="0ce64-113">자동 검색 SRV 레코드(_sipinternaltls._tcp.contoso.com)를 Lync Server 2013 풀을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="0ce64-114">첫 번째 옵션을 사용할 수 없는 경우 LRS를 수동으로 구성하고 Skype 룸 시스템 콘솔 응용 프로그램에서 직접 구성하여 Lync Server 2013 풀 주소를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="0ce64-115">Skype 룸 시스템이 회사 네트워크 외부에 배포되고 Lync 에지 서버가 배포되고 레거시 풀 또는 감독을 사용하도록 구성된 경우 Lync Server 2013 풀을 지점으로 하는 보조 에지 서버 사이트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="0ce64-116">보조 에지 서버 배포에 대한 자세한 내용은 에지 서버 배포 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0ce64-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="0ce64-117">Lync Server 2010 풀과의 Skype 룸 시스템 상호 운영성</span><span class="sxs-lookup"><span data-stu-id="0ce64-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="0ce64-118">마이그레이션 중 Lync Server 2010 풀에 있는 사용자가 모임을 예약하고 Skype 룸 시스템 계정을 초대하는 경우 Skype 채팅방 시스템 클라이언트는 모임에 참석하는 동안 제한된 기능을 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="0ce64-119">Skype 룸 시스템 클라이언트가 Lync Server 2010에 있는 사용자가 구성한 예약된 전화 회의에 참가하면 Skype 채팅방 시스템에 다음과 같은 모임 내 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="0ce64-120">Skype 룸 시스템에서 다중 보기 비디오 갤러리를 표시하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="0ce64-121">Skype 채팅방 시스템 클라이언트가 발표자인 경우 참가자에 비디오 잠금을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="0ce64-122">Skype 채팅방 시스템은 다음 때문에 Lync Server 2013 회의 정책에서 허용하는 경우에도 1080p 비디오 해상도(인바운드 또는 아웃바운드)를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="0ce64-123">Lync Server 2010은 1080p 해상도를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="0ce64-124">Skype 룸 시스템은 항상 비디오 해상도에 대한 이끌이의 회의 정책에 의해 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="0ce64-125">따라서 Lync 2010 풀이 720p 해상도를 지원하는 경우에도 이끌이의 정책이 720p 해상도를 지원하지 않는 한 Skype 룸 시스템에서 720p 해상도를 활용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="0ce64-126">Lync 2013 클라이언트는 회의실에서 LRS 현재 상태 확인 및 실제 회의실에서 에코를 방지하기 위해 자동으로 음소거합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-126">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room.</span></span> <span data-ttu-id="0ce64-127">이 기능은 Lync Server 2010에서 호스팅되는 모임에서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-127">This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="0ce64-128">Lync Server 2010에서 호스팅되는 모임의 데스크톱 공유 성능에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="0ce64-129">사용자는 Skype 룸 시스템을 통해 Lync 2010에서 호스팅되는 비공개(제한된) 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce64-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

