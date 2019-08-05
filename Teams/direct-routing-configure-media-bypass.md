---
title: 직접 라우팅으로 미디어 우회 구성
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: 이 항목에서는 전화 시스템 다이렉트 라우팅과 함께 미디어 바이패스를 구성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 47b537a9feff22a24b97fa5c54669359992b8a31
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2019
ms.locfileid: "36185192"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="4cd1f-103">직접 라우팅으로 미디어 우회 구성</span><span class="sxs-lookup"><span data-stu-id="4cd1f-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="4cd1f-104">직접 라우팅으로 미디어 바이패스를 구성 하기 전에 [다이렉트 라우팅이 미디어 바이패스에 대 한 계획](direct-routing-plan-media-bypass.md)을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd1f-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="4cd1f-105">미디어 바이패스를 설정 하려면 다음 조건을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd1f-105">To turn on media bypass, the following conditions must be met:</span></span>

1.  <span data-ttu-id="4cd1f-106">선택 사항에 대 한 SBC (세션 경계 컨트롤러) 공급 업체가 미디어 바이패스를 지원 하는지 확인 하 고 SBC에서 bypass를 구성 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd1f-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="4cd1f-107">사용 중인 SBCs에 대 한 자세한 내용은 인증 페이지를 참조 하 고 미디어 바이패스에 대 한 지침을 제공 하세요.</span><span class="sxs-lookup"><span data-stu-id="4cd1f-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.  <span data-ttu-id="4cd1f-108">**CSOnlinePSTNGateway-id <sbc_FQDN>-MediaBypass $true**명령을 사용 하 여 트렁크에서 미디어 바이패스를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd1f-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.  <span data-ttu-id="4cd1f-109">필요한 포트가 열려 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd1f-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="4cd1f-110">우회 되지 않은 trunks에서 우회 가능 trunks 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="4cd1f-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="4cd1f-111">모든 사용자를 한 번에 전환 하거나 단계별 접근을 구현할 수 있습니다 (권장).</span><span class="sxs-lookup"><span data-stu-id="4cd1f-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="4cd1f-112">**모든 사용자를 한 번에 전환 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4cd1f-112">**Switch all users at once.**</span></span> <span data-ttu-id="4cd1f-113">모든 조건이 충족 되는 경우 우회 모드를 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd1f-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="4cd1f-114">그러나 모든 프로덕션 사용자가 동시에 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cd1f-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="4cd1f-115">Trunks 및 포트를 구성할 때 초기에 몇 가지 문제가 발생할 수 있으므로 프로덕션 사용자 환경에 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd1f-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="4cd1f-116">**단계적 접근. (권장)**.</span><span class="sxs-lookup"><span data-stu-id="4cd1f-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="4cd1f-117">동일한 SBC에 대해 다른 포트를 사용 하 여 새 트렁크를 만들고 테스트 한 다음 사용자가 새 트렁크를 가리키도록 온라인 음성 라우팅 정책을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd1f-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="4cd1f-118">이 방법을 사용 하는 것이 좋습니다. 전환 및 지속적으로 중단 되는 사용자 환경이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd1f-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="4cd1f-119">이 접근 방법에는 SBC, 새 FQDN 이름, 방화벽 구성 등의 구성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd1f-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="4cd1f-120">참고 인증서가 두 trunks를 모두 지원 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd1f-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="4cd1f-121">SAN에는 두 개의 이름 (**sbc1.contoso.com** 및 **sbc2.contoso.com**)이 있거나 와일드 카드 인증서가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd1f-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![무시할 수 없는 trunks에서 bypass trunks)로 마이그레이션](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="4cd1f-123">Trunks를 구성 하 고 마이그레이션을 수행 하는 방법에 대 한 지침은 SBC 공급 업체의 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4cd1f-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="4cd1f-124">오디오 코드 배포 설명서</span><span class="sxs-lookup"><span data-stu-id="4cd1f-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="4cd1f-125">Oracle 배포 문서</span><span class="sxs-lookup"><span data-stu-id="4cd1f-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="4cd1f-126">리본 커뮤니케이션 배포 문서</span><span class="sxs-lookup"><span data-stu-id="4cd1f-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="4cd1f-127">TE-시스템 (anynode) 배포 문서</span><span class="sxs-lookup"><span data-stu-id="4cd1f-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="4cd1f-128">직접 라우팅으로 인증 된 SBCs (세션 경계 컨트롤러) 목록은 [직접 라우팅에 대해 인증 된 세션 경계선 컨트롤러 목록을](direct-routing-border-controllers.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4cd1f-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="see-also"></a><span data-ttu-id="4cd1f-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4cd1f-129">See also</span></span>

[<span data-ttu-id="4cd1f-130">직접 라우팅으로 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="4cd1f-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



