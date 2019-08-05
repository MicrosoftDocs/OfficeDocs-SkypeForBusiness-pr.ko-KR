---
title: 비즈니스용 Skype 서버에서 비상 전화에 대 한 요구 사항 정의
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
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: E9-1-1을 비즈니스용 Skype Server Enterprise Voice에서 사용 하도록 설정 하는 데 필요한 단계에 대 한 자세한 내용은 SIP 트렁크 E9-1-1 서비스 공급자 또는 게이트웨이에서 ELIN이 있는지 여부에 따라 간략하게 설명 합니다.
ms.openlocfilehash: 9e6ccd4b93416d49993dbc24ee0592d130e25de8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187737"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="c7a70-103">비즈니스용 Skype 서버에서 비상 전화에 대 한 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="c7a70-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="c7a70-104">E9-1-1을 비즈니스용 Skype Server Enterprise Voice에서 사용 하도록 설정 하는 데 필요한 단계에 대 한 자세한 내용은 SIP 트렁크 E9-1-1 서비스 공급자 또는 게이트웨이에서 ELIN이 있는지 여부에 따라 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7a70-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="c7a70-105">비즈니스용 Skype 서버 E9-1-1 배포를 시작 하기 전에 먼저 다음 섹션에서 설명 하는 질문에 대 한 답을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7a70-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="c7a70-106">수행 해야 하는 계획은 E9-1-1 솔루션 (SIP 트렁크 E9-1-1 서비스 공급자 또는 비상 위치 Id 번호 (ELIN) 게이트웨이)의 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="c7a70-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="c7a70-107">다음 표에서는 이러한 각 솔루션에 대해 검토 해야 하는 계획 통합 문서의 섹션을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7a70-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="c7a70-108">**E9의 유형별 계획 단계-1-1 솔루션**</span><span class="sxs-lookup"><span data-stu-id="c7a70-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="c7a70-109">**SIP 트렁크 서비스 공급자**</span><span class="sxs-lookup"><span data-stu-id="c7a70-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="c7a70-110">**ELIN gateway**</span><span class="sxs-lookup"><span data-stu-id="c7a70-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="c7a70-111">비즈니스용 Skype 서버에서 E9-1 배포의 범위를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7a70-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="c7a70-112">비즈니스용 Skype 서버에서 E9-1 배포의 범위를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7a70-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="c7a70-113">비즈니스용 Skype 서버에서 위치를 결정 하는 데 사용 되는 네트워크 요소 정의</span><span class="sxs-lookup"><span data-stu-id="c7a70-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="c7a70-114">비즈니스용 Skype 서버에서 위치를 결정 하는 데 사용 되는 네트워크 요소 정의</span><span class="sxs-lookup"><span data-stu-id="c7a70-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="c7a70-115">비즈니스용 Skype 서버에서 E9에 대 한 사용자 사용-1-1</span><span class="sxs-lookup"><span data-stu-id="c7a70-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="c7a70-116">비즈니스용 Skype 서버에서 E9에 대 한 사용자 사용-1-1</span><span class="sxs-lookup"><span data-stu-id="c7a70-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="c7a70-117">비즈니스용 Skype 서버에서 SIP 트렁크 서비스 공급자의 위치 관리</span><span class="sxs-lookup"><span data-stu-id="c7a70-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="c7a70-118">비즈니스용 Skype 서버의 게이트웨이에서 ELIN 대 한 위치 관리</span><span class="sxs-lookup"><span data-stu-id="c7a70-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="c7a70-119">비즈니스용 Skype 서버에서 위치를 수동으로 가져오는 사용자 환경 정의</span><span class="sxs-lookup"><span data-stu-id="c7a70-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="c7a70-120">비즈니스용 Skype 서버에서 위치를 수동으로 가져오는 사용자 환경 정의</span><span class="sxs-lookup"><span data-stu-id="c7a70-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="c7a70-121">비즈니스용 Skype 서버에서 E9-1에 대 한 SIP 트렁크 디자인</span><span class="sxs-lookup"><span data-stu-id="c7a70-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="c7a70-122">비즈니스용 Skype 서버에 보안 데스크 포함</span><span class="sxs-lookup"><span data-stu-id="c7a70-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="c7a70-123">비즈니스용 Skype 서버에 보안 데스크 포함</span><span class="sxs-lookup"><span data-stu-id="c7a70-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="c7a70-124">비즈니스용 Skype 서버에 대 한 계획 위치 정책</span><span class="sxs-lookup"><span data-stu-id="c7a70-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="c7a70-125">비즈니스용 Skype 서버용 E9-1-1 서비스 공급자 선택</span><span class="sxs-lookup"><span data-stu-id="c7a70-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="c7a70-126">비즈니스용 Skype 서버에서 위치 정책 범위 지정</span><span class="sxs-lookup"><span data-stu-id="c7a70-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="c7a70-127">비즈니스용 Skype 서버에 대 한 계획 위치 정책</span><span class="sxs-lookup"><span data-stu-id="c7a70-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="c7a70-128">비즈니스용 Skype 서버에서 위치 정책 범위 지정</span><span class="sxs-lookup"><span data-stu-id="c7a70-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

