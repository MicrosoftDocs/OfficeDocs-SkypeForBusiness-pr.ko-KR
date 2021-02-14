---
title: 비즈니스용 Skype 서버 2019에서 더 이상 사용되지 않습니다.
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '요약: 이러한 기능은 비즈니스용 Skype 서버 2019에서 제거되었습니다.'
ms.openlocfilehash: 5c5914493d7e2f4da4fd72d6acf7ff2b979d8e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808728"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="e43ce-103">비즈니스용 Skype 서버 2019에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e43ce-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="e43ce-104">비즈니스용 Skype 서버 2019에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e43ce-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="e43ce-105">비즈니스용 Skype 서버 2019의 새로운 기능에 대한 자세한 내용은 비즈니스용 [Skype 서버 2019의 기능을 참조하세요.](whats-new.md)</span><span class="sxs-lookup"><span data-stu-id="e43ce-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="e43ce-106">강조되지 않은 일부 기능은 이전 제품 버전과의 호환성을 위해 비즈니스용 Skype 서버 2019에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e43ce-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="e43ce-107">비즈니스용 Skype 서버 2019에서 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e43ce-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="e43ce-108">비즈니스용 Skype 서버용 XMPP 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="e43ce-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="e43ce-109">비즈니스용 Skype 서버 2015 및 해당 선행 서버에서는 에지 서버 및 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이에 XMPP(Extensible Messaging and Presence Protocol) 프록시를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e43ce-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="e43ce-110">이 기능은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e43ce-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="e43ce-111">영구 비즈니스용 Skype 서버 채팅</span><span class="sxs-lookup"><span data-stu-id="e43ce-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="e43ce-112">영구 채팅 서버는 조직의 여러 사용자가 시간이 지날 때 대화방 대화에 참가할 수 있는 선택적 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="e43ce-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="e43ce-113">영구 채팅은 비즈니스용 Skype 서버 2019와 함께 배포할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e43ce-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="e43ce-114">이 서버 역할은 코드뿐만 아니라 토폴로지 작성기에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="e43ce-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="e43ce-115">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e43ce-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="e43ce-116">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="e43ce-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="e43ce-117">SQL 비즈니스용 Skype 서버 미러링</span><span class="sxs-lookup"><span data-stu-id="e43ce-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="e43ce-118">SQL 미러링은 비즈니스용 Skype 서버 2019와 함께 배포할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e43ce-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="e43ce-119">고가용성 및 재해 복구를 제공하기 위한 다른 옵션은 여전히 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e43ce-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="e43ce-120">비즈니스용 [Skype 서버에서](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 고가용성 및 재해 복구 계획을 참조하여 옵션을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="e43ce-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="e43ce-121">인플레이스 업그레이드</span><span class="sxs-lookup"><span data-stu-id="e43ce-121">In-place upgrades</span></span> 

<span data-ttu-id="e43ce-122">현재 장소 업그레이드는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e43ce-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e43ce-123">나란히 업그레이드 및 동시 사용이 지원됩니다. 자세한 내용은 비즈니스용 [Skype 서버 2019로](migration/migration-to-skype-for-business-server-2019.md) 마이그레이션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e43ce-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="e43ce-124">Mobility Service(Mcx)</span><span class="sxs-lookup"><span data-stu-id="e43ce-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="e43ce-125">레거시 모바일 클라이언트가 사용하는 Mobility Service 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e43ce-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="e43ce-126">이는 이전에 비즈니스용 Skype 서버 2015에서 발표했습니다.</span><span class="sxs-lookup"><span data-stu-id="e43ce-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="e43ce-127">모든 현재 비즈니스용 Skype 모바일 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e43ce-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="e43ce-128">Mcx를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e43ce-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="e43ce-129">자세한 내용은 비즈니스용 Skype 서버 모바일 및 비즈니스용 [Skype의](../SfbServer/plan-your-deployment/mobility.md) 모바일 클라이언트 기능 비교를 [참조하세요.](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="e43ce-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="e43ce-130">도구</span><span class="sxs-lookup"><span data-stu-id="e43ce-130">Tools</span></span>

<span data-ttu-id="e43ce-131">비즈니스용 Skype 서버 2019의 초기 릴리스에서는 다음 도구를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e43ce-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="e43ce-132">비즈니스용 Skype 서버 용량 계획 계산기</span><span class="sxs-lookup"><span data-stu-id="e43ce-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="e43ce-133">비즈니스용 Skype 서버 디버깅 도구</span><span class="sxs-lookup"><span data-stu-id="e43ce-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="e43ce-134">비즈니스용 Skype 서버 리소스 키트 도구(일부 도구는 제거됨)</span><span class="sxs-lookup"><span data-stu-id="e43ce-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="e43ce-135">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="e43ce-135">Call Parkometer</span></span>
    - <span data-ttu-id="e43ce-136">사용자 콘솔을 찾아서</span><span class="sxs-lookup"><span data-stu-id="e43ce-136">Lookup user console</span></span>
    - <span data-ttu-id="e43ce-137">미지정 번호 공지 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="e43ce-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="e43ce-138">다음 도구는 비즈니스용 Skype 서버 2019에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e43ce-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="e43ce-139">통화 품질 방법론(통화 품질 대시보드는 호출 안 되지만)</span><span class="sxs-lookup"><span data-stu-id="e43ce-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="e43ce-140">Microsoft 통화 품질 방법론 Scorecard, v1.5</span><span class="sxs-lookup"><span data-stu-id="e43ce-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="e43ce-141">비즈니스용 Skype 서버 2015 계획 도구</span><span class="sxs-lookup"><span data-stu-id="e43ce-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="e43ce-142">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구</span><span class="sxs-lookup"><span data-stu-id="e43ce-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="e43ce-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e43ce-143">See also</span></span>

[<span data-ttu-id="e43ce-144">비즈니스용 Skype 서버 2019의 새로운</span><span class="sxs-lookup"><span data-stu-id="e43ce-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="e43ce-145">XMPP 페더레이션 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="e43ce-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
