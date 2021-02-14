---
title: 직접 라우팅을 위한 미디어 바이패스 구성
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 모든 사용자를 한에 전환하거나 단계적 접근 방식을 구현하여 Microsoft Teams에 대한 전화 시스템 직접 라우팅을 사용하여 미디어 우회를 구성하는 방법을 배워야 합니다(권장).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416898"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="bc777-103">직접 라우팅을 위한 미디어 바이패스 구성</span><span class="sxs-lookup"><span data-stu-id="bc777-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="bc777-104">직접 라우팅을 통해 미디어 우회를 구성하기 전에 직접 라우팅을 사용하는 미디어 우회에 대한 계획을 [읽어야 합니다.](direct-routing-plan-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="bc777-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="bc777-105">미디어 우회를 설정하려면 다음 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc777-105">To turn on media bypass, the following conditions must be met:</span></span>

1.    <span data-ttu-id="bc777-106">선택한 SBC(세션 테두리 컨트롤러) 공급업체가 미디어 우회를 지원하고 SBC에서 우회를 구성하는 방법에 대한 지침을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc777-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="bc777-107">SBC에 대해 알아보고 미디어 우회를 지원하는 SBC 및 지침은 인증 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc777-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.    <span data-ttu-id="bc777-108">**Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass**$true.</span><span class="sxs-lookup"><span data-stu-id="bc777-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.    <span data-ttu-id="bc777-109">필요한 포트가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="bc777-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="bc777-110">무시되지 않은 트렁크에서 우회 사용 트렁크로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="bc777-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="bc777-111">모든 사용자를 한에 전환하거나 단계적 접근 방식을 구현할 수 있습니다(권장).</span><span class="sxs-lookup"><span data-stu-id="bc777-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="bc777-112">**모든 사용자를 한 번씩 전환합니다.**</span><span class="sxs-lookup"><span data-stu-id="bc777-112">**Switch all users at once.**</span></span> <span data-ttu-id="bc777-113">모든 조건이 충족된 경우 우회 모드를 켜면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc777-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="bc777-114">그러나 모든 프로덕션 사용자는 동시에 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc777-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="bc777-115">트렁크 및 포트를 구성할 때 처음에 몇 가지 문제가 있을 수 있기 때문에 프로덕션 사용자 환경이 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc777-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="bc777-116">**단계적 접근 방식입니다. (권장)**.</span><span class="sxs-lookup"><span data-stu-id="bc777-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="bc777-117">동일한 SBC(다른 포트 사용)에 대한 새 트렁크를 만들고, 테스트하고, 사용자가 새 트렁크를 지점으로 하여 온라인 음성 라우팅 정책을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="bc777-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="bc777-118">이는 더 원활한 전환 및 사용자 환경을 위한 것이기 때문에 권장되는 접근 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="bc777-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="bc777-119">이 방법을 사용하려면 SBC 구성, 새 FQDN 이름 및 방화벽 구성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bc777-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="bc777-120">인증서가 두 트렁크를 모두 지원하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc777-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="bc777-121">SAN에서 두 개의 이름(sbc1.contoso.com 및 sbc2.contoso.com)이 필요하거나 와일드카드 **인증서가** 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bc777-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![무시되지 않은 트렁크에서 우회 사용 트렁크로 마이그레이션)](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="bc777-123">트렁크를 구성하고 마이그레이션을 수행하는 방법에 대한 지침은 SBC 공급업체의 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc777-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="bc777-124">AudioCodes 배포 설명서</span><span class="sxs-lookup"><span data-stu-id="bc777-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="bc777-125">Oracle 배포 설명서</span><span class="sxs-lookup"><span data-stu-id="bc777-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="bc777-126">리본 메뉴 통신 배포 설명서</span><span class="sxs-lookup"><span data-stu-id="bc777-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="bc777-127">TE-Systems(anynode) 배포 설명서</span><span class="sxs-lookup"><span data-stu-id="bc777-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="bc777-128">직접 라우팅을 위해 인증된 SBC(세션 테두리 컨트롤러) 목록은 직접 라우팅에 대해 인증된 세션 브로더 컨트롤러 [목록을 참조하세요.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="bc777-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="bc777-129">관련 항목</span><span class="sxs-lookup"><span data-stu-id="bc777-129">Related topics</span></span>

[<span data-ttu-id="bc777-130">직접 라우팅을 통해 미디어 우회 계획</span><span class="sxs-lookup"><span data-stu-id="bc777-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



