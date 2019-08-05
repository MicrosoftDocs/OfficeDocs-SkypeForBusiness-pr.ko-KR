---
title: 비즈니스용 Skype 서버에서 trunks 구성
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
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: '요약: 비즈니스용 Skype 서버에서 중재 서버와 Enterprise Voice 용 피어 간 트렁크를 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 5e5fc044e5217ef4661e716ba02ba286c7a631f8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191361"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="fe043-103">비즈니스용 Skype 서버에서 trunks 구성</span><span class="sxs-lookup"><span data-stu-id="fe043-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="fe043-104">**요약:** 비즈니스용 Skype 서버에서 중재 서버와 Enterprise Voice 용 피어 간의 트렁크를 구성 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="fe043-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="fe043-105">엔터프라이즈 음성 배포의 일부로, 중재 서버와 다음 피어 중 하나 이상을 구성할 수 있으므로 조직의 엔터프라이즈 음성 클라이언트 및 장치에 대 한 PSTN (공개 통신 네트워크) 연결을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe043-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="fe043-106">인터넷 전화 통신 서비스 공급자 (ITSP)에 대 한 SIP 트렁크 연결</span><span class="sxs-lookup"><span data-stu-id="fe043-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="fe043-107">PSTN 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="fe043-107">PSTN gateway</span></span>
    
- <span data-ttu-id="fe043-108">PBX (사설 분기 교환)</span><span class="sxs-lookup"><span data-stu-id="fe043-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="fe043-109">자세한 내용은 비즈니스용 [Skype 서버의 PSTN 연결 계획](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe043-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="fe043-110">비즈니스용 Skype 서버 기능은 게이트웨이와 중재 서버 간의 복수 연결을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe043-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="fe043-111">이러한 연결은 중재 서버 풀과 PSTN (공개 교환 통신 네트워크) 게이트웨이, SBC (세션 경계 컨트롤러) 또는 IP-PBX 간의 논리적 연결 인 트렁크를 정의 하 여 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="fe043-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="fe043-112">토폴로지 작성기를 사용 하 여 게이트웨이를 중재 서버와 연결 합니다 (즉, trunks).</span><span class="sxs-lookup"><span data-stu-id="fe043-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="fe043-113">비즈니스용 Skype 서버에서 트렁크를 할당 또는 제거 하려면 먼저 토폴로지 작성기에서 트렁크를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe043-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="fe043-114">트렁크는 다음 연결로 구성 됩니다. 중재 서버 FQDN (정규화 된 도메인 이름), 중재 서버 수신 포트, 게이트웨이 FQDN 및 게이트웨이 수신 대기 포트.</span><span class="sxs-lookup"><span data-stu-id="fe043-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="fe043-115">여러 trunks를 구성 하려면 동일한 게이트웨이와 중재 서버 간에 여러 연결을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe043-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="fe043-116">이렇게 하면 PBX (개인 브랜치 교환) interoperational 시나리오에서 특히 유용한 엔터프라이즈 음성 인프라에 대 한 추가 탄력성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe043-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="fe043-117">트렁크가 정의 되 면 경로에 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe043-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="fe043-118">트렁크를 경로에 연결 하려면 토폴로지 작성기에서 트렁크에 대 한 간단한 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe043-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="fe043-119">이 간단한 이름은 비즈니스용 Skype Server 제어판에서 트렁크 이름으로 사용 되며, trunks 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe043-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="fe043-120">간단한 트렁크 이름을 비즈니스용 Skype 서버 관리 셸에서의 게이트웨이 이름으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe043-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="fe043-121">관리자는 중재 서버와 연결 된 기본 트렁크를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe043-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="fe043-122">토폴로지 작성기에서 연결 된 중재 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe043-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="fe043-123">중재 서버의 기본 게이트웨이를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe043-123">Specify the default gateway for the Mediation Server.</span></span> 
  

