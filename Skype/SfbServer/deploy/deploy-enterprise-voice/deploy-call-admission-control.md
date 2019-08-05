---
title: 비즈니스용 Skype 서버에서 통화 허용 제어 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: CAC (통화 허용 제어)는 사용 가능한 대역폭을 기준으로 실시간 세션을 설정할 수 있는지를 결정 하는 솔루션으로, 혼잡 네트워크 사용자에 게 좋지 않은 오디오/비디오 품질을 방지 하는 데 도움이 됩니다.
ms.openlocfilehash: 7f7f8dee4e25061533564ce517f797281bef042e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189033"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="3d250-103">비즈니스용 Skype 서버에서 통화 허용 제어 배포</span><span class="sxs-lookup"><span data-stu-id="3d250-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="3d250-104">CAC (통화 허용 제어)는 사용 가능한 대역폭을 기준으로 실시간 세션을 설정할 수 있는지를 결정 하는 솔루션으로, 혼잡 네트워크 사용자에 게 좋지 않은 오디오/비디오 품질을 방지 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d250-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="3d250-105">자세한 내용은 비즈니스용 [Skype 서버의 통화 허용 제어 계획](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d250-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="3d250-106">통화 허용 제어 배포</span><span class="sxs-lookup"><span data-stu-id="3d250-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="3d250-107">[예를 들어 비즈니스용 Skype 서버에서 통화 허용 제어에 대 한 요구 사항 수집](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)을 참조 하 여 엔터프라이즈 네트워크 토폴로지에 필요한 모든 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d250-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="3d250-108">아직 수행 하지 않은 경우 네트워크 지역과 사이트를 정의 하 고 서브넷을 네트워크 사이트와 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d250-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="3d250-109">자세한 내용은 [비즈니스용 Skype에서 네트워크 지역, 사이트 및 서브넷 배포](deploy-network.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d250-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="3d250-110">[비즈니스용 Skype 서버에서 대역폭 정책 프로필 만들기](create-bandwidth-policy-profiles.md) 에 자세히 설명 된 대로 대역폭 정책 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="3d250-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="3d250-111">[비즈니스용 Skype 서버의 네트워크 지역 링크 만들기](create-network-region-links.md)에 자세히 설명 된 대로 네트워크 지역 링크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3d250-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="3d250-112">[비즈니스용 Skype 서버의 네트워크 간 경로 만들기](create-network-interregional-routes.md)에 자세히 설명 된 대로 네트워크 교차 영역 경로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3d250-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="3d250-113">[비즈니스용 Skype 서버의 네트워크 사이트 간 정책 만들기](create-network-intersite-policies.md)에 자세히 설명 된 대로 네트워크 사이트 간 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3d250-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="3d250-114">[비즈니스용 Skype 서버에서 통화 허용 제어 사용](enable-call-admission-control.md)에 자세히 설명 된 대로 통화 허용 제어 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d250-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="3d250-115">일부 최종 설정을 확인 하 여 모든 항목이 올바르게 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d250-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="3d250-116">자세한 내용은 [통화 허용 제어 배포: 비즈니스용 Skype 서버에 대 한 최종 검사 목록](final-checklist.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="3d250-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

