---
title: 비즈니스용 Skype 서버에서 에지 서버 배포
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: '요약: 비즈니스용 Skype 서버 환경에 에지 서버 또는 에지 풀을 배포하는 방법을 알아보십시오.'
ms.openlocfilehash: edd2ff501320c4252b8032d1528ede7b83b8fcd6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804388"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="8de90-103">비즈니스용 Skype 서버에서 에지 서버 배포</span><span class="sxs-lookup"><span data-stu-id="8de90-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="8de90-104">**요약:** 비즈니스용 Skype 서버 환경에 에지 서버 또는 에지 풀을 배포하는 방법을 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="8de90-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="8de90-105">에지 서버 또는 에지 풀을 비즈니스용 Skype 서버 환경에 배포하는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="8de90-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="8de90-106">조직의 내부 네트워크에 로그인하지 않은 외부 사용자가 내부 사용자와 상호 작용할 수 있어야 하는 경우 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8de90-106">It's necessary if you need external users who aren't logged into your organization's internal network to be able to interact with internal users.</span></span> <span data-ttu-id="8de90-107">이러한 외부 사용자는 인증 및 익명 원격 사용자, 페더타 파트너 또는 기타 모바일 클라이언트일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8de90-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="8de90-108">비즈니스용 Skype 서버의 에지 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="8de90-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="8de90-109">위에서 설명한 대로 비즈니스용 Skype 서버의 에지 서버 배포에는 많은 것이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8de90-109">As noted above, a lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="8de90-110">이 검사 목록은 수행해야 하는 작업에 대한 개요와 보다 자세한 단계로 연결되는 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8de90-110">This checklist gives you an overview of the tasks you'll need to perform, and links to more detailed steps.</span></span>
  
<span data-ttu-id="8de90-111">비즈니스용 Skype 서버 섹션에서 에지 서버 배포 계획에 [시작해주시길 바랍니다.](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)</span><span class="sxs-lookup"><span data-stu-id="8de90-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="8de90-112">그렇지 않은 경우 참조하는 대부분의 내용은 자세히 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="8de90-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="8de90-113">배포 섹션에는 절차만 포함되어 있으므로 이러한 단계의 원인을 알고 싶으면 계획을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8de90-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="8de90-114">또한 이 설명서에서는 비즈니스용 Skype 서버의 기본 배포를 이미 완료했다고 전제합니다.</span><span class="sxs-lookup"><span data-stu-id="8de90-114">This documentation also presumes you've already completed the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="8de90-115">이 배포를 에지와 나란히 수행하고 있을 수도 있지만 먼저 이러한 단계를 따라야 합니다. 그런 다음 여기에 설명된 에지의 토폴로지 변경 작업을 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8de90-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="8de90-116">다음은 따라야 하는 높은 수준의 단계와 해당 단계를 찾을 수 있는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="8de90-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="8de90-117">비즈니스용 Skype 서버의 에지 서버 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8de90-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="8de90-118">비즈니스용 Skype 서버의 에지 서버 환경 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8de90-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="8de90-119">비즈니스용 Skype 서버에 대한 에지 토폴로지 만들기</span><span class="sxs-lookup"><span data-stu-id="8de90-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="8de90-120">비즈니스용 Skype 서버에서 에지 서버 배포</span><span class="sxs-lookup"><span data-stu-id="8de90-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="8de90-121">비즈니스용 Skype 서버에서 에지 배포 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="8de90-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

