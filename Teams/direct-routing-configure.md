---
title: 직접 라우팅 구성
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Microsoft Phone System Direct 라우팅을 구성하여온-프레미스 전화 통신 인프라를 Microsoft Teams에 연결하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ecd8579ccd092e6b82deb06aa670901cdfc3b023
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122242"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="7dee8-103">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="7dee8-103">Configure Direct Routing</span></span>

<span data-ttu-id="7dee8-104">Microsoft Phone System 직접 라우팅을 사용하면온-프레미스 전화 통신 인프라를 Microsoft Teams에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dee8-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="7dee8-105">이 문서에서는 지원되는 SBC(On-Premises Session Border Controller)를 직접 라우팅에 연결하는 데 필요한 고급 단계와 PSTN(공용 전환 전화 네트워크)에 연결하는 직접 라우팅을 사용하도록 Teams 사용자를 구성하는 방법을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="7dee8-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="7dee8-106">이 문서는 관련 문서에 연결하여 자세한 내용을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7dee8-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="7dee8-107">직접 라우팅이 조직에 적합한 솔루션인지 여부에 대한 자세한 내용은 전화 시스템 직접 라우팅 [을 참조하세요.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="7dee8-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="7dee8-108">필요한 구성 및 배포 계획에 대한 자세한 내용은 직접 라우팅 계획 [을 참조하세요.](direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="7dee8-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="7dee8-109">또한 다음 세션을 통해 직접 라우팅의 이점, 계획을 세우는 방법 및 배포 방법: Microsoft Teams의 직접 라우팅에 대해 자세히 알아보는 방법을 볼 [수 있습니다.](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="7dee8-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="7dee8-110">이 문서에서 설명하는 단계를 완료하려면 관리자는 PowerShell cmdlet에 익숙해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dee8-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="7dee8-111">PowerShell 사용에 대한 자세한 내용은 에 대한 컴퓨터 [Windows PowerShell.](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="7dee8-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="7dee8-112">이 문서의 단계를 수행하기 전에 Microsoft는 SBC 공급업체에서 권장하는 SBC가 이미 구성되어 있는지 확인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7dee8-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="7dee8-113">AudioCodes 배포 설명서</span><span class="sxs-lookup"><span data-stu-id="7dee8-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="7dee8-114">Oracle 배포 설명서</span><span class="sxs-lookup"><span data-stu-id="7dee8-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="7dee8-115">리본 통신 배포 설명서</span><span class="sxs-lookup"><span data-stu-id="7dee8-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="7dee8-116">TE-Systems(anynode) 배포 설명서</span><span class="sxs-lookup"><span data-stu-id="7dee8-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="7dee8-117">Metaswitch 배포 설명서</span><span class="sxs-lookup"><span data-stu-id="7dee8-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="7dee8-118">지원되는 SBC의 전체 목록은 직접 라우팅에 대해 인증된 세션 테두리 컨트롤러 [목록을 참조하세요.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="7dee8-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="7dee8-119">Microsoft Phone System을 구성하고 사용자가 직접 라우팅을 사용할 수 있도록 설정하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7dee8-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="7dee8-120">**1단계.**</span><span class="sxs-lookup"><span data-stu-id="7dee8-120">**Step 1.**</span></span> [<span data-ttu-id="7dee8-121">Microsoft Phone System을 사용하여 SBC 연결 및 연결 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="7dee8-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="7dee8-122">**2단계.**</span><span class="sxs-lookup"><span data-stu-id="7dee8-122">**Step 2.**</span></span> [<span data-ttu-id="7dee8-123">직접 라우팅, 음성 및 음성메일에 사용자를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="7dee8-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="7dee8-124">**3단계.**</span><span class="sxs-lookup"><span data-stu-id="7dee8-124">**Step 3.**</span></span> [<span data-ttu-id="7dee8-125">음성 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="7dee8-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="7dee8-126">**4단계.**</span><span class="sxs-lookup"><span data-stu-id="7dee8-126">**Step 4.**</span></span> [<span data-ttu-id="7dee8-127">숫자를 대체 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="7dee8-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="7dee8-128">여러 테넌트에 대한 SBC를 구성하는 경우 여러 테넌트에 대한 SBC 구성 [을 읽어야 합니다.](direct-routing-sbc-multiple-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="7dee8-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="7dee8-129">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7dee8-129">Related topics</span></span>

[<span data-ttu-id="7dee8-130">전화 시스템 직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="7dee8-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="7dee8-131">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="7dee8-131">Plan Direct Routing</span></span>](direct-routing-plan.md)