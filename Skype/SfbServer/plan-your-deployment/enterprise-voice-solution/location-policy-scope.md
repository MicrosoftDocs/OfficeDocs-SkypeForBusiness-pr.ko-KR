---
title: 비즈니스용 Skype 서버에서 위치 정책 범위 할당
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: 비즈니스용 Skype 서버의 E9-1-1 배포에 대한 위치 Enterprise Voice.
ms.openlocfilehash: 586aabe919ea4236dc724446da717b5f300d88e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825528"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="cc3a2-103">비즈니스용 Skype 서버에서 위치 정책 범위 할당</span><span class="sxs-lookup"><span data-stu-id="cc3a2-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="cc3a2-104">비즈니스용 Skype 서버의 E9-1-1 배포에 대한 위치 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="cc3a2-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="cc3a2-105">다른 비즈니스용 Skype 서버 정책과 같은 위치 정책은 전역, 사이트 및 사용자와 같은 여러 범위 수준에서 할당될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc3a2-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="cc3a2-106">그러나 사용자 수준 위치 정책의 범위는 다른 비즈니스용 Skype 서버 정책과 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="cc3a2-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="cc3a2-107">사용자당 위치 정책을 끝점 개체(예: 사용자 및 공통 영역 전화 연락처 개체)에 적용할 수 있을 뿐만 아니라 비즈니스용 Skype 서버 네트워크 사이트에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc3a2-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="cc3a2-108">네트워크 사이트는 지리적 위치와 연결된 클라이언트 서브넷의 그룹이지만 전체 중앙 사이트 또는 분기 사이트의 모든 서브넷이 아닐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc3a2-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="cc3a2-109">네트워크 사이트의 서브넷에 연결된 모든 클라이언트는 해당 네트워크 사이트에 할당된 위치 정책을 자동으로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3a2-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="cc3a2-110">사용자 수준 위치 정책이 사용자와 네트워크 사이트에 모두 할당된 경우 네트워크 사이트 기반 위치 정책은 사용자 기준 정책 설정을 모두 대신합니다.</span><span class="sxs-lookup"><span data-stu-id="cc3a2-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="cc3a2-111">각 네트워크 사이트에는 위치 정책이 할당되어 있으며 각 정책에는 서로 다른 PSTN 사용, 알림 URI 및 회의 URI 값이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc3a2-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cc3a2-112">이러한 특수한 정책의 지정 동작은 한 사무실 사이트의 풀에 있는 사용자가 다른 사이트를 방문하여 긴급 통화를 하도록 하는 경우 해당 네트워크 사이트에 적합한 E9-1-1 통화 라우팅 설정이 사용자에게 할당된 풀 또는 사이트에 상관없이 적용하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cc3a2-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

