---
title: 비즈니스용 Skype 서버 2019에서 더 이상 사용 되지 않는 기능
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 요약:이 기능은 비즈니스용 Skype 서버 2019에서 제거 되었습니다.
ms.openlocfilehash: f77ccecd0ab963c0707a7b1dc1d24083ed0c3729
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813986"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="065d9-103">비즈니스용 Skype 서버 2019에서 더 이상 사용 되지 않는 기능</span><span class="sxs-lookup"><span data-stu-id="065d9-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="065d9-104">비즈니스용 Skype 서버 2019에서 더 이상 사용 되지 않는 기능과 기능에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="065d9-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="065d9-105">비즈니스용 Skype Server 2019의 새로운 기능에 대 한 자세한 내용은 비즈니스용 [Skype server 2019의 내용을](whats-new.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="065d9-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="065d9-106">일부 de-de 기능은 이전 제품 버전과의 호환성을 위해 비즈니스용 Skype 서버 2019에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="065d9-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="065d9-107">비즈니스용 Skype 서버 2019에서 사용 되지 않는 기능</span><span class="sxs-lookup"><span data-stu-id="065d9-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="065d9-108">비즈니스용 Skype 서버용 XMPP 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="065d9-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="065d9-109">비즈니스용 Skype 서버 2015 및 해당 선행자는 Edge 서버에서 XMPP (Extensible Messaging 및 현재 상태 프로토콜) 프록시를 구성할 수 있도록 하 고 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="065d9-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="065d9-110">이 기능은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="065d9-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="065d9-111">비즈니스용 Skype 서버에 대 한 영구 채팅</span><span class="sxs-lookup"><span data-stu-id="065d9-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="065d9-112">영구 채팅 서버는 조직의 여러 사용자가 시간에 따라 유지 되는 채팅방 대화에 참여할 수 있도록 하는 선택적 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="065d9-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="065d9-113">영구 채팅은 비즈니스용 Skype 서버 2019에서 배포할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="065d9-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="065d9-114">이 서버 역할은 코드 뿐 아니라 토폴로지 작성기 에서도 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="065d9-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="065d9-115">팀 에서도 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="065d9-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="065d9-116">자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="065d9-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="065d9-117">비즈니스용 Skype 서버용 SQL 미러링</span><span class="sxs-lookup"><span data-stu-id="065d9-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="065d9-118">SQL 미러링은 비즈니스용 Skype 서버 2019에 배포할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="065d9-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="065d9-119">고가용성 및 재해 복구를 제공 하는 다른 옵션은 계속 지원 되며 이들 중에서 하나를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="065d9-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="065d9-120">[비즈니스용 Skype 서버에서 고가용성 및 재해 복구 계획](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 을 참조 하 여 옵션을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="065d9-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="065d9-121">현재 위치 업그레이드</span><span class="sxs-lookup"><span data-stu-id="065d9-121">In-place upgrades</span></span> 

<span data-ttu-id="065d9-122">현재 위치 업그레이드는 비즈니스용 Skype 서버 2015에서 사용할 수 있었지만 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="065d9-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="065d9-123">나란히 업그레이드 및 coexistance 지원 되는 경우 자세한 내용은 [비즈니스용 Skype 서버 2019 마이그레이션](migration/migration-to-skype-for-business-server-2019.md) (영문)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="065d9-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="065d9-124">모바일 서비스 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="065d9-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="065d9-125">레거시 모바일 클라이언트에서 사용 하는 모바일 서비스 지원은 더 이상 비즈니스용 Skype 서버 2019에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="065d9-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="065d9-126">이는 이전에 비즈니스용 Skype 서버 2015에서 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="065d9-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="065d9-127">현재 모든 비즈니스용 Skype 모바일 클라이언트는 이미 통합 커뮤니케이션 웹 API (인스턴트 메시징 (IM), 현재 상태, 대화 상대 지원)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="065d9-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="065d9-128">Mcx를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="065d9-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="065d9-129">자세한 내용은 비즈니스용 skype 서버 및 비즈니스용 [skype의 모바일 클라이언트 기능 비교](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)에 대 한 [이동성 계획](../SfbServer/plan-your-deployment/mobility.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="065d9-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="065d9-130">도구</span><span class="sxs-lookup"><span data-stu-id="065d9-130">Tools</span></span>

<span data-ttu-id="065d9-131">다음 도구는 비즈니스용 Skype 서버 2019의 초기 릴리스에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="065d9-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="065d9-132">비즈니스용 Skype 서버 용량 계획 계산기</span><span class="sxs-lookup"><span data-stu-id="065d9-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="065d9-133">비즈니스용 Skype 서버 디버깅 도구</span><span class="sxs-lookup"><span data-stu-id="065d9-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="065d9-134">비즈니스용 Skype Server Resource Kit 도구 (일부 도구는 제거 됨)</span><span class="sxs-lookup"><span data-stu-id="065d9-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="065d9-135">전화 Parkometer</span><span class="sxs-lookup"><span data-stu-id="065d9-135">Call Parkometer</span></span>
    - <span data-ttu-id="065d9-136">조회 사용자 콘솔</span><span class="sxs-lookup"><span data-stu-id="065d9-136">Lookup user console</span></span>
    - <span data-ttu-id="065d9-137">할당 되지 않은 번호 알림 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="065d9-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="065d9-138">다음 도구는 비즈니스용 Skype 서버 2019에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="065d9-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="065d9-139">통화 음질 방법론 (통화 품질 대시보드는 아님)</span><span class="sxs-lookup"><span data-stu-id="065d9-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="065d9-140">Microsoft 통화 품질 방법론 성과 기록표, v 1.5</span><span class="sxs-lookup"><span data-stu-id="065d9-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="065d9-141">계획 도구를 사용하여 Lync Server 2013의 토폴로지 디자인</span><span class="sxs-lookup"><span data-stu-id="065d9-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="065d9-142">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구</span><span class="sxs-lookup"><span data-stu-id="065d9-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="065d9-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="065d9-143">See also</span></span>

[<span data-ttu-id="065d9-144">비즈니스용 Skype Server 2019의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="065d9-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="065d9-145">XMPP 페더레이션 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="065d9-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
