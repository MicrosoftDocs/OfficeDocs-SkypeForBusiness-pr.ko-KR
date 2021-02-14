---
title: 비즈니스용 Skype 서버에서 긴급 통화에 대한 요구 사항 정의
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
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: SIP 트렁크 E9-1-1 서비스 공급자가 있는지 또는 ELIN 게이트웨이가 있는지에 따라 비즈니스용 Skype 서버 Enterprise Voice에서 E9-1-1을 사용하도록 설정하는 데 필요한 단계를 요약합니다.
ms.openlocfilehash: 8efd38657a80bee1ecd979e8730feacfb980053e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825818"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="c666c-103">비즈니스용 Skype 서버에서 긴급 통화에 대한 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="c666c-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="c666c-104">SIP 트렁크 E9-1-1 서비스 공급자가 있는지 또는 ELIN 게이트웨이가 있는지에 따라 비즈니스용 Skype 서버 Enterprise Voice에서 E9-1-1을 사용하도록 설정하는 데 필요한 단계를 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="c666c-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="c666c-105">비즈니스용 Skype 서버 E9-1-1 배포를 시작하기 전에 먼저 다음 섹션에 자세히 설명된 질문에 답변할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c666c-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="c666c-106">배포할 E9-1-1 솔루션 유형(SIP 트렁크 E9-1-1 서비스 공급자 또는 ELIN(Emergency Location Identification Number) 게이트웨이)에 따라 계획해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c666c-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="c666c-107">다음 표에서는 이러한 각 솔루션에 대해 검토해야 하는 이 계획 통합 문서의 섹션을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c666c-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="c666c-108">**E9-1-1 솔루션 유형별 계획 단계**</span><span class="sxs-lookup"><span data-stu-id="c666c-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="c666c-109">**SIP 트렁크 서비스 공급자**</span><span class="sxs-lookup"><span data-stu-id="c666c-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="c666c-110">**ELIN 게이트웨이**</span><span class="sxs-lookup"><span data-stu-id="c666c-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="c666c-111">비즈니스용 Skype 서버에서 E9-1-1 배포 범위 정의</span><span class="sxs-lookup"><span data-stu-id="c666c-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="c666c-112">비즈니스용 Skype 서버에서 E9-1-1 배포 범위 정의</span><span class="sxs-lookup"><span data-stu-id="c666c-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="c666c-113">비즈니스용 Skype 서버에서 위치를 결정하는 데 사용되는 네트워크 요소 정의</span><span class="sxs-lookup"><span data-stu-id="c666c-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="c666c-114">비즈니스용 Skype 서버에서 위치를 결정하는 데 사용되는 네트워크 요소 정의</span><span class="sxs-lookup"><span data-stu-id="c666c-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="c666c-115">비즈니스용 Skype 서버에서 사용자가 E9-1-1을 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="c666c-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="c666c-116">비즈니스용 Skype 서버에서 사용자가 E9-1-1을 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="c666c-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="c666c-117">비즈니스용 Skype 서버에서 SIP 트렁크 서비스 공급자의 위치 관리</span><span class="sxs-lookup"><span data-stu-id="c666c-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="c666c-118">비즈니스용 Skype 서버에서 ELIN 게이트웨이 위치 관리</span><span class="sxs-lookup"><span data-stu-id="c666c-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="c666c-119">비즈니스용 Skype 서버에서 위치를 수동으로 다운로드하기 위한 사용자 환경 정의</span><span class="sxs-lookup"><span data-stu-id="c666c-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="c666c-120">비즈니스용 Skype 서버에서 위치를 수동으로 다운로드하기 위한 사용자 환경 정의</span><span class="sxs-lookup"><span data-stu-id="c666c-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="c666c-121">비즈니스용 Skype 서버에서 E9-1-1용 SIP 트렁크 디자인</span><span class="sxs-lookup"><span data-stu-id="c666c-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="c666c-122">비즈니스용 Skype 서버에 보안 데스크 포함</span><span class="sxs-lookup"><span data-stu-id="c666c-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="c666c-123">비즈니스용 Skype 서버에 보안 데스크 포함</span><span class="sxs-lookup"><span data-stu-id="c666c-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="c666c-124">비즈니스용 Skype 서버의 위치 정책 계획</span><span class="sxs-lookup"><span data-stu-id="c666c-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="c666c-125">비즈니스용 Skype 서버의 E9-1-1 서비스 공급자 선택</span><span class="sxs-lookup"><span data-stu-id="c666c-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="c666c-126">비즈니스용 Skype 서버에서 위치 정책 범위 할당</span><span class="sxs-lookup"><span data-stu-id="c666c-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="c666c-127">비즈니스용 Skype 서버의 위치 정책 계획</span><span class="sxs-lookup"><span data-stu-id="c666c-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="c666c-128">비즈니스용 Skype 서버에서 위치 정책 범위 할당</span><span class="sxs-lookup"><span data-stu-id="c666c-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

