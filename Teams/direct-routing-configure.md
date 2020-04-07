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
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Microsoft 전화 시스템 다이렉트 라우팅을 구성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: b596e5acb0002ad90f5c0298b56973f2490ad2e6
ms.sourcegitcommit: f3390e27bb63b66d1c4fb4f8afbda6b814fbbb5b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2020
ms.locfileid: "43170586"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="4d6ad-103">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="4d6ad-103">Configure Direct Routing</span></span>

<span data-ttu-id="4d6ad-104">Microsoft 전화 시스템 다이렉트 라우팅을 사용 하 여 온-프레미스 전화 통신 인프라를 Microsoft 팀에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d6ad-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="4d6ad-105">이 문서에는 지원 되는 온-프레미스 세션 경계 컨트롤러 (SBC)를 다이렉트 라우팅과 연결 하는 데 필요한 상위 단계와 팀 사용자가 PSTN (공개 통신 네트워크)에 연결 하기 위해 직접 라우팅을 사용 하도록 구성 하는 방법에 대 한 개요가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d6ad-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="4d6ad-106">이 문서는 관련 문서에 대 한 자세한 내용 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d6ad-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="4d6ad-107">직접 라우팅이 조직에 적합 한 솔루션 인지 여부에 대 한 자세한 내용은 [전화 시스템 직접 라우팅을](direct-routing-landing-page.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d6ad-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="4d6ad-108">필수 구성 요소 및 배포 계획에 대 한 자세한 내용은 [직접 라우팅 계획](direct-routing-plan.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d6ad-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="4d6ad-109">또한 다음 세션을 시청 하 여 다이렉트 라우팅의 이점과이를 위해 계획 하는 방법, 그리고 배포 하는 방법에 대해 알아볼 수 있습니다. [Microsoft 팀의 직접적인 라우팅](https://aka.ms/teams-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="4d6ad-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="4d6ad-110">이 문서에서 설명 하는 단계를 완료 하려면 관리자가 PowerShell cmdlet에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d6ad-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="4d6ad-111">PowerShell을 사용 하는 방법에 대 한 자세한 내용은 [Windows PowerShell 용 컴퓨터 설정을](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d6ad-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="4d6ad-112">이 문서의 단계를 수행 하기 전에 sbc 공급 업체에서 권장 하는 것으로 SBC가 이미 구성 되어 있는지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4d6ad-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="4d6ad-113">오디오 코드 배포 설명서</span><span class="sxs-lookup"><span data-stu-id="4d6ad-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="4d6ad-114">Oracle 배포 문서</span><span class="sxs-lookup"><span data-stu-id="4d6ad-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="4d6ad-115">리본 커뮤니케이션 배포 문서</span><span class="sxs-lookup"><span data-stu-id="4d6ad-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="4d6ad-116">TE-시스템 (anynode) 배포 문서</span><span class="sxs-lookup"><span data-stu-id="4d6ad-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="4d6ad-117">Metaswitch 배포 설명서</span><span class="sxs-lookup"><span data-stu-id="4d6ad-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="4d6ad-118">지원 되는 SBCs의 전체 목록은 [직접 라우팅으로 인증 된 세션 경계 컨트롤러 목록을](direct-routing-border-controllers.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d6ad-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="4d6ad-119">Microsoft 전화 시스템을 구성 하 고 사용자가 직접 라우팅을 사용할 수 있도록 설정 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4d6ad-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="4d6ad-120">**1 단계.**</span><span class="sxs-lookup"><span data-stu-id="4d6ad-120">**Step 1.**</span></span> [<span data-ttu-id="4d6ad-121">Microsoft 전화 시스템을 사용 하 여 SBC 연결 및 연결 확인</span><span class="sxs-lookup"><span data-stu-id="4d6ad-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="4d6ad-122">**2 단계.**</span><span class="sxs-lookup"><span data-stu-id="4d6ad-122">**Step 2.**</span></span> [<span data-ttu-id="4d6ad-123">사용자가 직접 라우팅, 음성, 보이스 메일을 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="4d6ad-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="4d6ad-124">**3 단계.**</span><span class="sxs-lookup"><span data-stu-id="4d6ad-124">**Step 3.**</span></span> [<span data-ttu-id="4d6ad-125">음성 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="4d6ad-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="4d6ad-126">**4 단계.**</span><span class="sxs-lookup"><span data-stu-id="4d6ad-126">**Step 4.**</span></span> [<span data-ttu-id="4d6ad-127">숫자를 대체 형식으로 번역</span><span class="sxs-lookup"><span data-stu-id="4d6ad-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="4d6ad-128">여러 테 넌 트에 대 한 SBC를 구성 하는 경우에는 [여러 테 넌 트에 대 한 Sbc 구성을](direct-routing-sbc-multiple-tenants.md)읽어 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d6ad-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="4d6ad-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d6ad-129">See also</span></span>

[<span data-ttu-id="4d6ad-130">전화 시스템 직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="4d6ad-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="4d6ad-131">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="4d6ad-131">Plan Direct Routing</span></span>](direct-routing-plan.md)

