---
title: 비즈니스용 Skype 서버에서 통화 제어 배포
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: CAC(통화 가능 제어)는 사용 가능한 대역폭을 기반으로 실시간 세션을 설정하여 정체된 네트워크의 사용자에 대한 오디오/비디오 품질을 저해할 수 있는지 여부를 결정하는 솔루션입니다.
ms.openlocfilehash: af08afe02b1dc138aa38ded654d567aed6a09247
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836888"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="49a2e-103">비즈니스용 Skype 서버에서 통화 제어 배포</span><span class="sxs-lookup"><span data-stu-id="49a2e-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="49a2e-104">CAC(통화 가능 제어)는 사용 가능한 대역폭을 기반으로 실시간 세션을 설정하여 정체된 네트워크의 사용자에 대한 오디오/비디오 품질을 저해할 수 있는지 여부를 결정하는 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="49a2e-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="49a2e-105">자세한 내용은 비즈니스용 [Skype 서버의 통화 요금제 요금제(요금제)를 참조하세요.](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)</span><span class="sxs-lookup"><span data-stu-id="49a2e-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="49a2e-106">통화 수당 제어를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="49a2e-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="49a2e-107">예제: 비즈니스용 Skype 서버에서 통화 제어에 대한 요구 사항 수집에 설명된 엔터프라이즈 네트워크 토폴로지에 필요한 모든 [정보를 수집합니다.](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="49a2e-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="49a2e-108">아직 수행하지 않은 경우 네트워크 지역 및 사이트를 정의하고 서브넷을 네트워크 사이트에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a2e-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="49a2e-109">자세한 내용은 비즈니스용 Skype에서 네트워크 지역, 사이트 및 [서브넷 배포를 참조하세요.](deploy-network.md)</span><span class="sxs-lookup"><span data-stu-id="49a2e-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="49a2e-110">비즈니스용 Skype 서버에서 대역폭 정책 프로필 만들기에 자세히 설명된 대역폭 정책 프로필 [만들기](create-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="49a2e-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="49a2e-111">비즈니스용 Skype 서버에서 네트워크 지역 링크 만들기에 자세히 설명된 네트워크 지역 링크를 [만드시다.](create-network-region-links.md)</span><span class="sxs-lookup"><span data-stu-id="49a2e-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="49a2e-112">비즈니스용 Skype 서버에서 네트워크 지역 간 경로 만들기에 자세히 설명된 네트워크 지역 [간 경로를 만드시다.](create-network-interregional-routes.md)</span><span class="sxs-lookup"><span data-stu-id="49a2e-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="49a2e-113">비즈니스용 Skype 서버에서 네트워크 교차 정책 만들기에 자세히 설명된 네트워크 교차 [정책을 만드시다.](create-network-intersite-policies.md)</span><span class="sxs-lookup"><span data-stu-id="49a2e-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="49a2e-114">비즈니스용 Skype 서버에서 통화 입력 제어를 사용하도록 설정하는 데 자세히 설명된 통화 입력 [제어를 사용하도록 설정하십시오.](enable-call-admission-control.md)</span><span class="sxs-lookup"><span data-stu-id="49a2e-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="49a2e-115">몇 가지 최종 설정을 확인하여 모든 설정이 올바르게 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="49a2e-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="49a2e-116">자세한 내용은 통화 제어 배포: 비즈니스용 Skype 서버의 최종 검사 [목록을 참조하세요.](final-checklist.md)</span><span class="sxs-lookup"><span data-stu-id="49a2e-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

