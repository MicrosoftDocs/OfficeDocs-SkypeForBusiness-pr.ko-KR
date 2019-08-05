---
title: 비즈니스용 Skype 서버에서 Edge 서버 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: '요약: Edge 서버 또는 Edge 풀을 비즈니스용 Skype 서버 환경에 배포 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: bcb6f7fdd7b322411e793fe3466418db1dd00894
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197785"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="26cbb-103">비즈니스용 Skype 서버에서 Edge 서버 배포</span><span class="sxs-lookup"><span data-stu-id="26cbb-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="26cbb-104">**요약:** 비즈니스용 Skype 서버 환경에 Edge 서버나 Edge 풀을 배포 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="26cbb-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="26cbb-105">Edge 서버나 Edge 풀을 비즈니스용 Skype 서버 환경에 배포 하는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="26cbb-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="26cbb-106">내부 사용자와 상호 작용할 수 있으려면 조직 내부 네트워크에 로그인 하지 않은 외부 사용자가 필요한 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cbb-106">It's necessary if you need external users who aren't logged into your organizations internal network to be able to interact with internal users.</span></span> <span data-ttu-id="26cbb-107">이러한 외부 사용자는 인증 되 고 익명의 원격 사용자, 페더레이션 파트너 또는 기타 모바일 클라이언트가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26cbb-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="26cbb-108">Edge에 대 한 배포 검사 목록 (비즈니스용 Skype 서버용)</span><span class="sxs-lookup"><span data-stu-id="26cbb-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="26cbb-109">위에서 언급 한 것 처럼 비즈니스용 Skype 서버에 대 한 Edge 서버 배포에 많은 시간이 들어갑니다.</span><span class="sxs-lookup"><span data-stu-id="26cbb-109">As noted above,, A lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="26cbb-110">이 검사 목록에서는 수행할 작업에 대 한 개요와 자세한 단계 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cbb-110">This checklist gives you an overview of the tasks you'll need to do, and links to more detailed steps.</span></span>
  
<span data-ttu-id="26cbb-111">[비즈니스용 Skype 서버에서 Edge 서버 배포 계획](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) 섹션을 시작 했을 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="26cbb-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="26cbb-112">그렇지 않은 경우에는 대부분 참조 하는 항목이 여기에 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26cbb-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="26cbb-113">배포 섹션에는 프로시저만 포함 되어 있으므로 이러한 단계를 수행 하는 이유를 알고 싶으면 계획 수립이 시작 되는 곳입니다.</span><span class="sxs-lookup"><span data-stu-id="26cbb-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="26cbb-114">이 문서에서는 또한 비즈니스용 Skype Server의 기본 배포를 완료 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cbb-114">This documentation also presumes you've also done the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="26cbb-115">해당 배포를 Edge와 나란히 표시할 수 있지만 먼저 해당 단계를 수행 해야 하는 경우에는 여기에서 설명 하는 가장자리에 대 한 토폴로지 변경을 수행할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26cbb-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="26cbb-116">다음은 따라야 할 상위 수준 단계와 이러한 단계를 찾는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="26cbb-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="26cbb-117">비즈니스용 Skype 서버의 Edge 서버 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="26cbb-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="26cbb-118">비즈니스용 Skype 서버의 Edge 서버 환경 요구 사항</span><span class="sxs-lookup"><span data-stu-id="26cbb-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="26cbb-119">비즈니스용 Skype 서버에 대 한 Edge 토폴로지 만들기</span><span class="sxs-lookup"><span data-stu-id="26cbb-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="26cbb-120">비즈니스용 Skype 서버에 Edge 서버 배포</span><span class="sxs-lookup"><span data-stu-id="26cbb-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="26cbb-121">비즈니스용 Skype 서버에서 Edge 배포의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="26cbb-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

