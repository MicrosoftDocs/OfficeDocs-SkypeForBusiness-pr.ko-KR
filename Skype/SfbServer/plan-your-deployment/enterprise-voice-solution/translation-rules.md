---
title: 비즈니스용 Skype 서버의 번역 규칙
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: 비즈니스용 Skype Server Enterprise Voice에서 번역 규칙 및 다이얼 문자열 정규화에 대해 알아봅니다.
ms.openlocfilehash: 1f435db01b5b15c97ae577565e4ba43f5de554ea
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196897"
---
# <a name="translation-rules-in-skype-for-business-server"></a><span data-ttu-id="e97db-103">비즈니스용 Skype 서버의 번역 규칙</span><span class="sxs-lookup"><span data-stu-id="e97db-103">Translation rules in Skype for Business Server</span></span>

<span data-ttu-id="e97db-104">비즈니스용 Skype Server Enterprise Voice에서 번역 규칙 및 다이얼 문자열 정규화에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="e97db-104">Learn about translation rules and dial string normalization in Skype for Business Server Enterprise Voice.</span></span>

 <span data-ttu-id="e97db-105">Enterprise Voice에서는 역 번호 조회 (RNL)를 수행 하기 위해 모든 다이얼 문자열이 E 164 형식으로 정규화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e97db-105">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="e97db-106">번역 규칙은 숫자와 통화 번호를 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e97db-106">Translation rules are supported for both called numbers and calling numbers.</span></span> <span data-ttu-id="e97db-107">Thetrunk 피어 (즉, 연결 된 게이트웨이, PBX (사설 branch exchange) 또는 SIP 트렁크)는 해당 번호를 지역 전화 걸기 형식으로 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e97db-107">Thetrunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="e97db-108">E-164 형식의 숫자를 지역 전화 걸기 형식으로 번역 하려면 하나 이상의 번역 규칙을 정의 하 여 트렁크 피어로 라우팅하기 전에 요청 URI를 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e97db-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="e97db-109">예를 들어 전화 문자열의 앞부분에서 +44를 제거하고 0144로 바꾸는 전환 규칙을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e97db-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="e97db-110">서버에서 아웃 바운드 경로 변환을 수행 하 여 전화 번호를 지역 전화 걸기 형식으로 변환 하기 위해 각각의 각 트렁크 피어에 대 한 구성 요구 사항을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e97db-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="e97db-111">특정 조정 서버 클러스터와 연결할 게이트웨이 및 게이트웨이의 수를 계획 하는 경우에는 유사한 지역 전화 걸기 요구 사항으로 트렁크 피어를 그룹화 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e97db-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="e97db-112">이렇게 하면 필요한 번역 규칙의 수와 기록 하는 데 걸리는 시간을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e97db-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e97db-113">하나 이상의 번역 규칙을 엔터프라이즈 음성 트렁크 구성에 연결 하는 대신 트렁크 피어에서 번역 규칙을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e97db-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="e97db-114">두 규칙이 충돌할 수 있으므로 트렁크 피어에서 번역 규칙을 구성한 경우에는 번역 규칙을 엔터프라이즈 음성 트렁크 구성과 연결 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="e97db-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>

## <a name="example-translation-rules"></a><span data-ttu-id="e97db-115">예제 번역 규칙</span><span class="sxs-lookup"><span data-stu-id="e97db-115">Example Translation Rules</span></span>

<span data-ttu-id="e97db-116">다음 번역 규칙 예제에서는 서버에서 규칙을 개발 하 여 E. \ 164 형식의 숫자를 트렁크 피어의 로컬 형식으로 변환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e97db-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="e97db-117">번역 규칙을 구현 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [번역 규칙 정의](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e97db-117">For details about how to implement translation rules, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

|<span data-ttu-id="e97db-118">**설명**</span><span class="sxs-lookup"><span data-stu-id="e97db-118">**Description**</span></span>|<span data-ttu-id="e97db-119">**시작 번호**</span><span class="sxs-lookup"><span data-stu-id="e97db-119">**Starting Digits**</span></span>|<span data-ttu-id="e97db-120">**Content-length**</span><span class="sxs-lookup"><span data-stu-id="e97db-120">**Length**</span></span>|<span data-ttu-id="e97db-121">**제거할 숫자**</span><span class="sxs-lookup"><span data-stu-id="e97db-121">**Digits to Remove**</span></span>|<span data-ttu-id="e97db-122">**더할 숫자**</span><span class="sxs-lookup"><span data-stu-id="e97db-122">**Digits to Add**</span></span>|<span data-ttu-id="e97db-123">**일치 패턴**</span><span class="sxs-lookup"><span data-stu-id="e97db-123">**Matching Pattern**</span></span>|<span data-ttu-id="e97db-124">**변환용**</span><span class="sxs-lookup"><span data-stu-id="e97db-124">**Translation**</span></span>|<span data-ttu-id="e97db-125">**예**</span><span class="sxs-lookup"><span data-stu-id="e97db-125">**Example**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e97db-126">미국 내 기존 시외 전화 통화</span><span class="sxs-lookup"><span data-stu-id="e97db-126">Conventional long-distance dialing in U.S.</span></span>  <br/> <span data-ttu-id="e97db-127">(' + ' 제거)</span><span class="sxs-lookup"><span data-stu-id="e97db-127">(strip out the '+')</span></span>  <br/> |<span data-ttu-id="e97db-128">+ 1</span><span class="sxs-lookup"><span data-stu-id="e97db-128">+1</span></span>  <br/> |<span data-ttu-id="e97db-129">정확히 12</span><span class="sxs-lookup"><span data-stu-id="e97db-129">Exactly 12</span></span>  <br/> |<span data-ttu-id="e97db-130">raid-1</span><span class="sxs-lookup"><span data-stu-id="e97db-130">1</span></span>  <br/> |<span data-ttu-id="e97db-131">0</span><span class="sxs-lookup"><span data-stu-id="e97db-131">0</span></span>  <br/> |<span data-ttu-id="e97db-132">^\+(1 \ d{10}) $</span><span class="sxs-lookup"><span data-stu-id="e97db-132">^\+(1\d{10})$</span></span>  <br/> |<span data-ttu-id="e97db-133">$1</span><span class="sxs-lookup"><span data-stu-id="e97db-133">$1</span></span>  <br/> |<span data-ttu-id="e97db-134">+ 14255551010이 14255551010</span><span class="sxs-lookup"><span data-stu-id="e97db-134">+14255551010 becomes 14255551010</span></span>  <br/> |
|<span data-ttu-id="e97db-135">미국 국제 장거리 전화</span><span class="sxs-lookup"><span data-stu-id="e97db-135">U.S. international long-distance dialing</span></span>  <br/> <span data-ttu-id="e97db-136">(' + '를 제거 하 고 011을 추가 합니다.)</span><span class="sxs-lookup"><span data-stu-id="e97db-136">(strip out '+' and add 011)</span></span>  <br/> |+  <br/> |<span data-ttu-id="e97db-137">11 개 이상</span><span class="sxs-lookup"><span data-stu-id="e97db-137">At least 11</span></span>  <br/> |<span data-ttu-id="e97db-138">raid-1</span><span class="sxs-lookup"><span data-stu-id="e97db-138">1</span></span>  <br/> |<span data-ttu-id="e97db-139">011</span><span class="sxs-lookup"><span data-stu-id="e97db-139">011</span></span>  <br/> |<span data-ttu-id="e97db-140">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="e97db-140">^\+(\d{9}\d+)$</span></span>  <br/> |<span data-ttu-id="e97db-141">011 $1</span><span class="sxs-lookup"><span data-stu-id="e97db-141">011$1</span></span>  <br/> |<span data-ttu-id="e97db-142">+ 441235551010이 011441235551010</span><span class="sxs-lookup"><span data-stu-id="e97db-142">+441235551010 becomes 011441235551010</span></span>  <br/> |


