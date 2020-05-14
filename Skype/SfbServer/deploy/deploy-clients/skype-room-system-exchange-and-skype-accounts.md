---
title: Skype 대화방 시스템 Exchange 및 Skype 계정 프로 비전
ms.author: v-lanac
author: lanachin
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
description: Skype 대화방 시스템용 Exchange 및 Skype 계정을 프로 비전 하는 방법에 대 한 자세한 내용은 다음 항목을 참조 하십시오.
ms.openlocfilehash: be43e732a97dc81fdd2e3a6bdb355afaff4db37d
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220918"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="9be74-103">Skype 대화방 시스템 Exchange 및 Skype 계정 프로 비전</span><span class="sxs-lookup"><span data-stu-id="9be74-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="9be74-104">Skype 대화방 시스템용 Exchange 및 Skype 계정을 프로 비전 하는 방법에 대 한 자세한 내용은 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9be74-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="9be74-105">Microsoft 팀 대화방은 서로 다른 종속성 및 배포 절차를 사용 하는 다른 제품입니다.</span><span class="sxs-lookup"><span data-stu-id="9be74-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="9be74-106">Microsoft 팀 대화방에 대 한 자세한 내용은 Microsoft 팀원 대화방 [배포 개요](room-systems-v2.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9be74-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9be74-107">Skype 대화방 시스템 계정 프로 비전은 조직에 있는 토폴로지의 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="9be74-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="9be74-108">Active Directory 토폴로지에 대 한 자세한 내용은 [비즈니스용 Skype 서버 2015에 대 한 환경 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9be74-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="9be74-109">Skype 대화방 시스템 프로 비전 비즈니스용 &amp; Skype 계정</span><span class="sxs-lookup"><span data-stu-id="9be74-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="9be74-110">다음 항목에서는 다음에 대 한 Skype 대화방 시스템 교환 및 비즈니스용 Skype 계정을 구축 하 고 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9be74-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="9be74-111">단일 포리스트 온-프레미스 배포</span><span class="sxs-lookup"><span data-stu-id="9be74-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="9be74-112">다중 포리스트 온-프레미스 배포</span><span class="sxs-lookup"><span data-stu-id="9be74-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="9be74-113">Microsoft 365 또는 Office 365</span><span class="sxs-lookup"><span data-stu-id="9be74-113">Microsoft 365 or Office 365</span></span>
    
- <span data-ttu-id="9be74-114">하이브리드 배포</span><span class="sxs-lookup"><span data-stu-id="9be74-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="9be74-115">비즈니스용 skype 대화방 시스템 및 비즈니스용 Skype 페더레이션 파트너</span><span class="sxs-lookup"><span data-stu-id="9be74-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="9be74-116">Skype 대화방 시스템 계정 관리</span><span class="sxs-lookup"><span data-stu-id="9be74-116">Manage Skype Room System accounts</span></span>
    

