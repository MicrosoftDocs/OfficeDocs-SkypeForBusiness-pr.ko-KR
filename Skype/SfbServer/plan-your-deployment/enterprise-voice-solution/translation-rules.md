---
title: 비즈니스용 Skype 서버의 변환 규칙
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: 비즈니스용 Skype 서버 2016의 변환 규칙 및 전화 걸기 문자열 정규화에 대해 Enterprise Voice.
ms.openlocfilehash: 0c00776dae502bfd28bbe27e90012fabb6e25c93
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802688"
---
# <a name="translation-rules-in-skype-for-business-server"></a><span data-ttu-id="e82be-103">비즈니스용 Skype 서버의 변환 규칙</span><span class="sxs-lookup"><span data-stu-id="e82be-103">Translation rules in Skype for Business Server</span></span>

<span data-ttu-id="e82be-104">비즈니스용 Skype 서버 2016의 변환 규칙 및 전화 걸기 문자열 정규화에 대해 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="e82be-104">Learn about translation rules and dial string normalization in Skype for Business Server Enterprise Voice.</span></span>

 <span data-ttu-id="e82be-105">Enterprise Voice에서는 RNL(역방향 번호 조회)을 수행하기 위한 목적으로 모든 전화 걸기 문자열이 E.164 형식으로 정규화될 것을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="e82be-105">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="e82be-106">호출된 번호와 호출 번호 모두에 대해 변환 규칙이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e82be-106">Translation rules are supported for both called numbers and calling numbers.</span></span> <span data-ttu-id="e82be-107">트렁크 피어(즉, 연결된 게이트웨이, PBX(Private Branch Exchange) 또는 SIP 트렁크)에는 번호가 로컬 전화 걸기 형식이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e82be-107">Thetrunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="e82be-108">번호를 E.164 형식에서 로컬 전화 걸기 형식으로 변환하기 위해 트렁크 피어로 라우팅하기 전에 요청 URI를 조작하는 변환 규칙을 하나 이상 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e82be-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="e82be-109">예를 들어 전화 걸기 문자열의 시작 부분에서 +44를 제거하고 대신 0144를 넣는 변환 규칙을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e82be-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="e82be-110">서버에서 아웃바운드 경로 변환을 수행하면 전화 번호를 로컬 전화 번호 형식으로 변환하기 위해 각 개별 트렁크 피어의 구성 요구 사항을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e82be-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="e82be-111">특정 중재 서버 클러스터와 연결하도록 게이트웨이 및 게이트웨이 수를 계획할 때 유사한 로컬 전화 걸기 요구 사항으로 트렁크 피어를 그룹화하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e82be-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="e82be-112">이렇게 하면 필요한 변환 규칙의 수와 규칙을 작성하는 데 걸리는 시간이 단축될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e82be-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e82be-113">하나 이상의 변환 규칙을 트렁크 Enterprise Voice 트렁크 피어에 대한 변환 규칙을 구성하는 대안으로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e82be-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="e82be-114">트렁크 피어에 변환 규칙을 구성한 경우 두 규칙이 충돌할 수 Enterprise Voice 변환 규칙을 트렁크 구성과 연결하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e82be-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>

## <a name="example-translation-rules"></a><span data-ttu-id="e82be-115">예제 변환 규칙</span><span class="sxs-lookup"><span data-stu-id="e82be-115">Example Translation Rules</span></span>

<span data-ttu-id="e82be-116">다음 변환 규칙 예제에서는 번호를 E.164 형식에서 트렁크 피어에 대한 로컬 형식으로 변환하는 규칙을 서버에서 개발하는 방법을 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e82be-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="e82be-117">변환 규칙을 구현하는 방법에 대한 자세한 내용은 배포 설명서에서 변환 규칙 [정의를](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e82be-117">For details about how to implement translation rules, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

|<span data-ttu-id="e82be-118">**설명**</span><span class="sxs-lookup"><span data-stu-id="e82be-118">**Description**</span></span>|<span data-ttu-id="e82be-119">**시작 숫자**</span><span class="sxs-lookup"><span data-stu-id="e82be-119">**Starting Digits**</span></span>|<span data-ttu-id="e82be-120">**Length**</span><span class="sxs-lookup"><span data-stu-id="e82be-120">**Length**</span></span>|<span data-ttu-id="e82be-121">**제거할 숫자**</span><span class="sxs-lookup"><span data-stu-id="e82be-121">**Digits to Remove**</span></span>|<span data-ttu-id="e82be-122">**추가할 숫자**</span><span class="sxs-lookup"><span data-stu-id="e82be-122">**Digits to Add**</span></span>|<span data-ttu-id="e82be-123">**일치 패턴**</span><span class="sxs-lookup"><span data-stu-id="e82be-123">**Matching Pattern**</span></span>|<span data-ttu-id="e82be-124">**Translation**</span><span class="sxs-lookup"><span data-stu-id="e82be-124">**Translation**</span></span>|<span data-ttu-id="e82be-125">**예**</span><span class="sxs-lookup"><span data-stu-id="e82be-125">**Example**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e82be-126">미국의 기존 시거리 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="e82be-126">Conventional long-distance dialing in U.S.</span></span>  <br/> <span data-ttu-id="e82be-127">('+'를 제거합니다.)</span><span class="sxs-lookup"><span data-stu-id="e82be-127">(strip out the '+')</span></span>  <br/> |<span data-ttu-id="e82be-128">+1</span><span class="sxs-lookup"><span data-stu-id="e82be-128">+1</span></span>  <br/> |<span data-ttu-id="e82be-129">정확히 12</span><span class="sxs-lookup"><span data-stu-id="e82be-129">Exactly 12</span></span>  <br/> |<span data-ttu-id="e82be-130">1 </span><span class="sxs-lookup"><span data-stu-id="e82be-130">1</span></span>  <br/> |<span data-ttu-id="e82be-131">0</span><span class="sxs-lookup"><span data-stu-id="e82be-131">0</span></span>  <br/> |<span data-ttu-id="e82be-132">^\+(1\d) {10} $</span><span class="sxs-lookup"><span data-stu-id="e82be-132">^\+(1\d{10})$</span></span>  <br/> |<span data-ttu-id="e82be-133">$1</span><span class="sxs-lookup"><span data-stu-id="e82be-133">$1</span></span>  <br/> |<span data-ttu-id="e82be-134">+14255551010이 14255551010이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e82be-134">+14255551010 becomes 14255551010</span></span>  <br/> |
|<span data-ttu-id="e82be-135">미국 국제 장거리 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="e82be-135">U.S. international long-distance dialing</span></span>  <br/> <span data-ttu-id="e82be-136">('+'를 제거하고 011 추가)</span><span class="sxs-lookup"><span data-stu-id="e82be-136">(strip out '+' and add 011)</span></span>  <br/> |+  <br/> |<span data-ttu-id="e82be-137">11개 이상</span><span class="sxs-lookup"><span data-stu-id="e82be-137">At least 11</span></span>  <br/> |<span data-ttu-id="e82be-138">1 </span><span class="sxs-lookup"><span data-stu-id="e82be-138">1</span></span>  <br/> |<span data-ttu-id="e82be-139">011</span><span class="sxs-lookup"><span data-stu-id="e82be-139">011</span></span>  <br/> |<span data-ttu-id="e82be-140">^\+(\d {9} \d+)$</span><span class="sxs-lookup"><span data-stu-id="e82be-140">^\+(\d{9}\d+)$</span></span>  <br/> |<span data-ttu-id="e82be-141">011$1</span><span class="sxs-lookup"><span data-stu-id="e82be-141">011$1</span></span>  <br/> |<span data-ttu-id="e82be-142">+441235551010이 011441235551010이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e82be-142">+441235551010 becomes 011441235551010</span></span>  <br/> |


