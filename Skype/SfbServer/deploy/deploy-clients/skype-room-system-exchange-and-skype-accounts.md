---
title: Skype 룸 시스템 Exchange 및 Skype 계정 프로비전
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fa71a2da-2cc9-4ad1-8ec9-08d1c9c5247a
ms.collection: M365-voice
description: 다음 항목을 읽고 Skype 룸 시스템에 대한 Exchange 및 Skype 계정을 프로비전하는 방법을 배워야 합니다.
ms.openlocfilehash: 0e8c73bc83a62465dc711b4a6f2725f1d9c576f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113064"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="247e6-103">Skype 룸 시스템 Exchange 및 Skype 계정 프로비전</span><span class="sxs-lookup"><span data-stu-id="247e6-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="247e6-104">다음 항목을 읽고 Skype 룸 시스템에 대한 Exchange 및 Skype 계정을 프로비전하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="247e6-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="247e6-105">Microsoft Teams 룸은 종속성 및 배포 절차가 서로 다른 제품입니다.</span><span class="sxs-lookup"><span data-stu-id="247e6-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="247e6-106">Microsoft Teams 룸에 대한 자세한 내용은 Microsoft Teams 룸 배포 [개요 를 참조하세요.](/MicrosoftTeams/rooms/rooms-deploy)</span><span class="sxs-lookup"><span data-stu-id="247e6-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](/MicrosoftTeams/rooms/rooms-deploy).</span></span>
  
> [!NOTE]
> <span data-ttu-id="247e6-107">Skype 룸 시스템 계정 프로비전은 조직에 있는 토폴로지 유형에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="247e6-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="247e6-108">Active Directory 토폴로지에 대한 자세한 내용은 [Environmental requirements for Skype for Business Server 2015을 참조하세요.](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="247e6-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="247e6-109">Skype 룸 시스템 Exchange 비즈니스용 &amp; Skype 계정 프로비전</span><span class="sxs-lookup"><span data-stu-id="247e6-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="247e6-110">다음 항목에서는 Skype 룸 시스템 Exchange 및 비즈니스용 Skype 계정을 프로비전하고 관리하는 방법에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="247e6-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="247e6-111">단일 포리스트 온-프레미스 배포</span><span class="sxs-lookup"><span data-stu-id="247e6-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="247e6-112">다중 포리스트 온-프레미스 배포</span><span class="sxs-lookup"><span data-stu-id="247e6-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="247e6-113">Microsoft 365 또는 Office 365</span><span class="sxs-lookup"><span data-stu-id="247e6-113">Microsoft 365 or Office 365</span></span>
    
- <span data-ttu-id="247e6-114">하이브리드 배포</span><span class="sxs-lookup"><span data-stu-id="247e6-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="247e6-115">Skype 룸 시스템 및 비즈니스용 Skype 페더맹 파트너</span><span class="sxs-lookup"><span data-stu-id="247e6-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="247e6-116">Skype 룸 시스템 계정 관리</span><span class="sxs-lookup"><span data-stu-id="247e6-116">Manage Skype Room System accounts</span></span>
