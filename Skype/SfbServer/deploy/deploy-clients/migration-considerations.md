---
title: Skype 실 시스템 마이그레이션 고려 사항
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: 이 항목에서는 비즈니스용 Skype Server 및 Lync Server의 여러 버전이 있는 환경에서 Skype 대화방 시스템을 배포 하는 방법에 대해 자세히 알아보세요.
ms.openlocfilehash: a4856977931d459fba3b11a65b21e49a25cc418b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768841"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="c8b81-103">Skype 실 시스템 마이그레이션 고려 사항</span><span class="sxs-lookup"><span data-stu-id="c8b81-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="c8b81-104">이 항목에서는 비즈니스용 Skype Server 및 Lync Server의 여러 버전이 있는 환경에서 Skype 대화방 시스템을 배포 하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="c8b81-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="c8b81-105">마이그레이션 고려 사항</span><span class="sxs-lookup"><span data-stu-id="c8b81-105">Migration considerations</span></span>

<span data-ttu-id="c8b81-106">이 섹션에서는 다른 버전의 비즈니스용 Skype Server 또는 Lync Server를 포함 하는 다중 풀 환경에서 Skype 대화방 시스템을 배포 하는 경우에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="c8b81-107">Lync 서버의 사용자 복제기 (UR) 구성 요소는 Active Directory에서 사용자 개체를 가져와 Lync Server 백 엔드 SQL Server 데이터베이스에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="c8b81-108">Lync Server 2013의 UR만은 Skype 대화방 시스템 개체를 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="c8b81-109">이전 버전의 Lync Server 및 Office 통신 서버는 LRS 개체를 지정 하는 Active Directory 특성을 검색 하지 않으므로이를 인식 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="c8b81-110">Skype 채팅방 시스템 계정에서 Lync에 로그인 하 고 SRV 레코드 또는 DNS 레코드를 기준으로 자동 검색을 수행 하는 경우, 해당 계정이 Lync Server 또는 Office Communications Server의 이전 버전을 가리키는 경우 LRS에서 404을 찾을 수 없음 응답을 수신 합니다.  레거시 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="c8b81-111">레거시 풀은 Skype 대화방 시스템을 해당 Lync Server 2013 홈 풀로 리디렉션할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="c8b81-112">다음 옵션을 사용 하 여이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="c8b81-113">자동 검색 SRV 레코드 (_sipinternaltls _tcp)를 Lync Server 2013 풀에 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="c8b81-114">첫 번째 옵션을 사용할 수 없는 경우 수동으로 LRS를 구성 하 고 Skype 대화방 시스템 콘솔 응용 프로그램에서 직접 구성 하 여 Lync Server 2013 풀 주소를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="c8b81-115">Skype Room 시스템을 회사 네트워크 외부에 배포 하 고 Lync Edge 서버를 배포 하 여 레거시 풀이나 디렉터를 가리키도록 구성한 경우에는 Lync Server 2013 풀을 가리키는 보조 Edge 서버 사이트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="c8b81-116">보조 Edge 서버 배포에 대 한 자세한 내용은 Edge 서버 배포 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8b81-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="c8b81-117">Lync Server 2010 풀과 Skype 대화방 시스템의 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="c8b81-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="c8b81-118">마이그레이션 중에 Lync Server 2010 풀에 있는 사용자가 모임을 예약 하 고 Skype 대화방 시스템 계정을 초대 하는 경우, 모임에 참석 하는 동안 Skype 대화방 시스템 클라이언트의 기능이 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="c8b81-119">Skype 대화방 시스템 클라이언트가 Lync Server 2010에서 사용자가 구성한 예약 된 컨퍼런스 통화에 참가 하는 경우, Skype 대화방 시스템에는 다음과 같은 모임 시간 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="c8b81-120">Skype 채팅방 시스템에서 다중 보기 비디오 갤러리를 표시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="c8b81-121">Skype 대화방 시스템 클라이언트가 발표자 인 경우 참가자에 대해 비디오 잠금을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="c8b81-122">다음과 같은 이유로 인해 Skype 대화방 시스템은 Lync Server 2013 회의 정책에서 허용 하는 경우에도 1080p 비디오 해상도 (인바운드 또는 아웃 바운드)를 표시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="c8b81-123">Lync Server 2010는 1080p resolution을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="c8b81-124">Skype 채팅방 시스템은 비디오 해상도에 대 한 이끌이 회의 정책에 의해 항상 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="c8b81-125">따라서 Lync 2010 풀에서 720p 해상도를 지원 하더라도, 이끌이 정책에서 지원 하지 않는 한, Skype 채팅방 시스템은 720p 해상도를 이용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="c8b81-126">Lync 2013 클라이언트는 회의실에서 LRS 현재 상태를 감지 하 고 실제 회의실에 에코를 방지 하기 위해 자동으로 음소거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-126">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room.</span></span> <span data-ttu-id="c8b81-127">Lync Server 2010에서 호스팅하는 모임에서는이 기능이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-127">This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="c8b81-128">Lync Server 2010에서 호스트 되는 모임에 대 한 데스크톱 공유 성능에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="c8b81-129">사용자는 Skype 대화방 시스템을 사용 하 여 Lync 2010에서 호스팅되는 개인 (제한 된) 모임에 참가할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8b81-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

