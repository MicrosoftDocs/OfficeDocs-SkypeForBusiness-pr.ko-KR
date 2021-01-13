---
title: 비즈니스용 Skype 서버의 에지 서버 배포 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: '요약: 비즈니스용 Skype 서버 에지 환경을 계획합니다. 이 항목에서는 Edge 개념을 소개하고 보다 심층적인 항목으로 구성할 수 있습니다.'
ms.openlocfilehash: 277e344448f5229d15addf965695f19ec2884649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813808"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="2b9d1-104">비즈니스용 Skype 서버의 에지 서버 배포 계획</span><span class="sxs-lookup"><span data-stu-id="2b9d1-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="2b9d1-105">**요약:** 비즈니스용 Skype 서버 에지 환경을 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="2b9d1-106">이 항목에서는 Edge 개념을 소개하고 보다 심층적인 항목으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="2b9d1-107">내부적으로 잘 작동되는 비즈니스용 Skype 서버 환경이 있는 경우 다음 단계에서는 에지 서버 또는 에지 풀을 환경에 도입해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="2b9d1-108">비즈니스용 Skype 서버에서 제공하는 서비스를 내부 네트워크 외부에 있는 사용자가 사용하려는 경우 이 역할이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="2b9d1-109">이러한 데이터에는 다음이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-109">These can potentially include:</span></span>
  
- <span data-ttu-id="2b9d1-110">원격 사용자: 일시적으로 또는 지속적인 방식으로 오프사이트에 있는 직원입니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="2b9d1-111">페더타 사용자: 파트너 조직의 직원.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="2b9d1-112">모바일 사용자.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-112">Mobile Users.</span></span>
    
- <span data-ttu-id="2b9d1-113">모임 및 프레젠테이션에 초대하려는 잠재 고객, 파트너 및 익명 사용자.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="2b9d1-114">에지 서버에서 제공하는 외부 사용자 액세스는 이러한 모든 일이 발생하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="2b9d1-115">내부 사용자는 비즈니스용 Skype 서버 배포에서 호스팅하는 다음 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="2b9d1-116">통신을 위한 IM 및 현재 상태: 권한이 부여된 외부 사용자는 IM 대화 및 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="2b9d1-117">다른 사용자(현재 상태 정보도 얻음)에 대한 현재 상태 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="2b9d1-118">공용 IM 공급자(엄격히 피어 투 피어 통신)를 사용하는 경우 다국어 회의를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="2b9d1-119">그러나 SIP 및 XMPP 프로토콜이 모두 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="2b9d1-120">A/V(오디오/비디오) 회의: 권한이 부여된 외부 사용자는 비즈니스용 Skype 서버 오디오 및 비디오 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="2b9d1-121">웹 회의: 권한이 부여된 외부 사용자는 비즈니스용 Skype 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="2b9d1-122">원할 경우 원격 사용자, 페더타 사용자 및 익명 사용자에 대한 참가를 사용하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="2b9d1-123">공용 IM 사용자는 회의에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="2b9d1-124">이러한 사용자가 응용 프로그램 및 데스크톱 공유에 참여하고 모임 이끌이 또는 발표자 역할을 하게 하는 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="2b9d1-125">모바일 장치 액세스는 모바일 장치와 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="2b9d1-126">외부 사용자를 참석하려는 모임에 외부 사용자를 초대할 수 있습니다( 익명 사용자에게도 사용 권한을 부여하려는 경우).</span><span class="sxs-lookup"><span data-stu-id="2b9d1-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="2b9d1-127">조직에 필요한 경우 에지 환경을 계획하는 것이 배포에 큰 도움이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-127">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it.</span></span> <span data-ttu-id="2b9d1-128">자세한 내용은 아래 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-128">For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="2b9d1-129">XMPP 게이트웨이 및 XMPP 게이트웨이는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="2b9d1-130">자세한 [내용은 XMPP 페더링 마이그레이션을](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="2b9d1-131">계획 항목:</span><span class="sxs-lookup"><span data-stu-id="2b9d1-131">Planning topics:</span></span>

<span data-ttu-id="2b9d1-132">계획 문서는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="2b9d1-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="2b9d1-133">비즈니스용 Skype 서버 2015의 에지 서버 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b9d1-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="2b9d1-134">비즈니스용 Skype 서버 2015의 에지 서버 환경 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b9d1-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="2b9d1-135">비즈니스용 Skype 서버 2015의 에지 서버 시나리오</span><span class="sxs-lookup"><span data-stu-id="2b9d1-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

