---
title: 비즈니스용 Skype 서버에서 트렁크 구성
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
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: '요약: 비즈니스용 Skype 서버에서 중재 서버와 비즈니스용 피어 Enterprise Voice 트렁크를 구성하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: f2e9f3a5e9fa9d89ef9db63aa82b6a3ce3a86c6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824958"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="00d7a-103">비즈니스용 Skype 서버에서 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="00d7a-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="00d7a-104">**요약:** 비즈니스용 Skype 서버에서 중재 서버와 비즈니스용 피어 Enterprise Voice 트렁크를 구성하는 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="00d7a-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="00d7a-105">Enterprise Voice 배포의 일부로 중재 서버와 다음 피어 중 하나 이상 간에 트렁크를 구성하여 조직의 Enterprise Voice 클라이언트 및 장치에 대해 PSTN(공용 전화망) 연결을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00d7a-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="00d7a-106">ITSP(인터넷 전화 통신 서비스 공급자)에 대한 SIP 트렁크 연결</span><span class="sxs-lookup"><span data-stu-id="00d7a-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="00d7a-107">PSTN 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="00d7a-107">PSTN gateway</span></span>
    
- <span data-ttu-id="00d7a-108">PBX(Private Branch Exchange)</span><span class="sxs-lookup"><span data-stu-id="00d7a-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="00d7a-109">자세한 내용은 비즈니스용 Skype 서버의 [PSTN 연결 계획(Plan for PSTN connectivity)을 참조하세요.](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)</span><span class="sxs-lookup"><span data-stu-id="00d7a-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="00d7a-110">비즈니스용 Skype 서버 기능은 게이트웨이와 중재 서버 간의 여러 연결 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="00d7a-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="00d7a-111">이러한 연결은 중재 서버 풀과 PSTN(Public Switched Telephone Network) 게이트웨이, SBC(Session Border Controller) 또는 IP-PBX 간의 논리적 연결인 트렁크를 정의하여 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="00d7a-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="00d7a-112">토폴로지 작성기에서 게이트웨이를 중재 서버(즉, 트렁크)와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="00d7a-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="00d7a-113">비즈니스용 Skype 서버에서 트렁크를 할당하거나 제거하려면 먼저 토폴로지 작성기에서 트렁크를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00d7a-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="00d7a-114">트렁크는 중재 서버 FQDN(정식 도메인 이름), 중재 서버 수신 포트, 게이트웨이 FQDN 및 게이트웨이 수신 포트와의 연결로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="00d7a-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="00d7a-115">여러 트렁크를 구성하기 위해 동일한 게이트웨이와 중재 서버 간에 여러 개의 연관을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00d7a-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="00d7a-116">이렇게 하면 PBX(Private Branch Exchange) 상호 Enterprise Voice 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="00d7a-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="00d7a-117">트렁크가 정의된 경우 트렁크를 경로에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00d7a-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="00d7a-118">트렁크를 경로에 연결하기 위해 토폴로지 작성기에서 트렁크의 간단한 이름을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="00d7a-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="00d7a-119">이 간단한 이름은 트렁크를 경로와 연결될 수 있는 비즈니스용 Skype 서버 제어판에서 트렁크 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="00d7a-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="00d7a-120">간단한 트렁크 이름은 비즈니스용 Skype 서버 관리 셸의 게이트웨이 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="00d7a-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="00d7a-121">관리자는 중재 서버와 연결된 기본 트렁크를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00d7a-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="00d7a-122">토폴로지 작성기에서 연결된 중재 서버를 마우스 오른쪽 단추로 클릭한 다음 **속성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="00d7a-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="00d7a-123">중재 서버의 기본 게이트웨이를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="00d7a-123">Specify the default gateway for the Mediation Server.</span></span> 
  

