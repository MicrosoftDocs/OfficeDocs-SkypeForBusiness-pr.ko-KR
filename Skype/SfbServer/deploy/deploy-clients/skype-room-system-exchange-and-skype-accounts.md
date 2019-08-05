---
title: Skype 대화방 시스템 교환 및 Skype 계정 프로비저닝
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fa71a2da-2cc9-4ad1-8ec9-08d1c9c5247a
ms.collection: M365-voice
description: 이 항목에서는 Skype 대화방 시스템용 Exchange 및 Skype 계정을 구축 하는 방법에 대해 알아보세요.
ms.openlocfilehash: 504c1551cdda30bef46ba30584de8a557c5a4941
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190995"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="8a77f-103">Skype 대화방 시스템 교환 및 Skype 계정 프로비저닝</span><span class="sxs-lookup"><span data-stu-id="8a77f-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="8a77f-104">이 항목에서는 Skype 대화방 시스템용 Exchange 및 Skype 계정을 구축 하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="8a77f-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="8a77f-105">Microsoft 팀 대화방은 서로 다른 종속성 및 배포 절차와 다른 제품입니다.</span><span class="sxs-lookup"><span data-stu-id="8a77f-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="8a77f-106">Microsoft 팀 대화방에 대 한 자세한 내용은 Microsoft 팀 대화방 [배포 개요](room-systems-v2.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a77f-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="8a77f-107">Skype 룸 시스템 계정 프로 비전은 조직의 토폴로지 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="8a77f-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="8a77f-108">Active Directory 토폴로지에 대해 자세히 알아보려면 [비즈니스용 Skype 서버 2015의 환경 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a77f-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="8a77f-109">Skype 대화방 시스템의 프로 비전 &amp; 비즈니스용 Skype 계정 교환</span><span class="sxs-lookup"><span data-stu-id="8a77f-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="8a77f-110">다음 항목에서는 Skype 대화방 시스템 교환 및 비즈니스용 Skype 계정을 제공 하 고 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a77f-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="8a77f-111">단일 포리스트 온-프레미스 배포</span><span class="sxs-lookup"><span data-stu-id="8a77f-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="8a77f-112">다중 포리스트 온-프레미스 배포</span><span class="sxs-lookup"><span data-stu-id="8a77f-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="8a77f-113">Office 365</span><span class="sxs-lookup"><span data-stu-id="8a77f-113">Office 365</span></span>
    
- <span data-ttu-id="8a77f-114">하이브리드 배포</span><span class="sxs-lookup"><span data-stu-id="8a77f-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="8a77f-115">Skype 실 시스템 및 비즈니스용 Skype 페더레이션 파트너</span><span class="sxs-lookup"><span data-stu-id="8a77f-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="8a77f-116">Skype 대화방 시스템 계정 관리</span><span class="sxs-lookup"><span data-stu-id="8a77f-116">Manage Skype Room System accounts</span></span>
    

