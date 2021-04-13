---
title: 온-프레미스 비즈니스용 Skype 환경 해제
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 비즈니스용 Skype 환경을 해제하는 방법에 대한 지침입니다.
ms.openlocfilehash: 46848c6730d37f549a8d5ee16f066fa67c789873
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656684"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a><span data-ttu-id="3d613-103">온-프레미스 비즈니스용 Skype 환경 해제</span><span class="sxs-lookup"><span data-stu-id="3d613-103">Decommission your on-premises Skype for Business environment</span></span>

<span data-ttu-id="3d613-104">조직에서 비즈니스용 Skype 서버의 온-프레미스 배포에서 Teams 또는 비즈니스용 Skype Online을 사용하는 경우 이러한 환경을 클라우드로 완전히 마이그레이션한 다음 비즈니스용 Skype 서버의 온-프레미스 배포를 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d613-104">If your organization uses Teams or Skype for Business Online with an on-premises deployment of Skype for Business Server, you can migrate these environments fully to the cloud, and then retire your on-premises deployment of Skype for Business Server.</span></span> 

> [!NOTE]
> <span data-ttu-id="3d613-105">사내 환경을 해제하기 전에, 사내 [](configure-hybrid-connectivity.md) 배포와 Microsoft 365 간에 하이브리드 연결을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d613-105">Before decommissioning your on-premises environment, you must [configure hybrid connectivity](configure-hybrid-connectivity.md) between your on-premises deployment and Microsoft 365.</span></span> <span data-ttu-id="3d613-106">하이브리드 연결을 구성한 후 사용자를 클라우드로 마이그레이션하면서 모임을 사내에서 마이그레이션하고 비즈니스용 Skype 서버에서 Teams로 연락처를 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d613-106">After configuring hybrid connectivity, you can migrate users to the cloud, while migrating their meetings from on-premises, and migrating any contacts from Skype for Business Server to Teams.</span></span> <span data-ttu-id="3d613-107">하이브리드 연결을 구성하는 것은 사용자를 사내에서 클라우드로 마이그레이션하고 전체 Teams 기능을 보장하는 데 필요한 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="3d613-107">Configuring hybrid connectivity is a required step to migrate users from on-premises to the cloud and to ensure full Teams functionality.</span></span>

<span data-ttu-id="3d613-108">사내에서 클라우드로의 이동을 완료하고 사내 비즈니스용 Skype 서버 환경을 해제하려면 다음 단계를 순서대로 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d613-108">To complete your move from on-premises to the cloud and decommission your on-premises Skype for Business Server environment, you must complete the following steps in the following order:</span></span>

- <span data-ttu-id="3d613-109">**1단계.**</span><span class="sxs-lookup"><span data-stu-id="3d613-109">**Step 1.**</span></span> <span data-ttu-id="3d613-110">필요한 모든 사용자를 프레미스에서 [온라인으로 이동](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="3d613-110">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="3d613-111">**2단계.**</span><span class="sxs-lookup"><span data-stu-id="3d613-111">**Step 2.**</span></span> <span data-ttu-id="3d613-112">[하이브리드 구성을 사용하지 않도록 설정합니다.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="3d613-112">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="3d613-113">**3단계.**</span><span class="sxs-lookup"><span data-stu-id="3d613-113">**Step 3.**</span></span> <span data-ttu-id="3d613-114">[하이브리드 응용 프로그램 끝점을](decommission-move-on-prem-endpoints.md)프레미스에서 온라인으로 이동</span><span class="sxs-lookup"><span data-stu-id="3d613-114">[Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="3d613-115">**4단계.**</span><span class="sxs-lookup"><span data-stu-id="3d613-115">**Step 4.**</span></span> <span data-ttu-id="3d613-116">[비즈니스용 Skype 배포를 제거합니다.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="3d613-116">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

