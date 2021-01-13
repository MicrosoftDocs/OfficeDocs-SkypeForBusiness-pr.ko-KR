---
title: 비즈니스용 Skype 서버의 여러 트렁크 지원
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 비즈니스용 Skype 서버 기능은 게이트웨이와 중재 서버 간의 여러 연결 기능을 지원합니다. 이러한 연결은 중재 서버 풀과 PSTN(Public Switched Telephone Network) 게이트웨이, SBC(Session Border Controller) 또는 IP-PBX 간의 논리적 연결인 트렁크를 정의하여 설정됩니다. 토폴로지 작성기에서 게이트웨이를 중재 서버(즉, 트렁크)와 연결합니다.
ms.openlocfilehash: 0f4c8d2ee16c900ef666c12230964a9abb8f5a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826228"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="33485-105">비즈니스용 Skype 서버의 여러 트렁크 지원</span><span class="sxs-lookup"><span data-stu-id="33485-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="33485-106">비즈니스용 Skype 서버 기능은 게이트웨이와 중재 서버 간의 여러 연결 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="33485-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="33485-107">이러한 연결은 중재 서버 풀과 PSTN(Public Switched Telephone Network) 게이트웨이, SBC(Session Border Controller) 또는 IP-PBX 간의 논리적 연결인 트렁크를 정의하여 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="33485-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="33485-108">토폴로지 작성기에서 게이트웨이를 중재 서버(즉, 트렁크)와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="33485-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="33485-109">비즈니스용 Skype 서버에서 트렁크를 할당하거나 제거하려면 먼저 토폴로지 작성기에서 트렁크를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33485-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="33485-110">트렁크는 중재 서버 FQDN(정식 도메인 이름), 중재 서버 수신 포트, 게이트웨이 FQDN 및 게이트웨이 수신 포트와 같은 연결로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="33485-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="33485-111">여러 트렁크를 구성하기 위해 동일한 게이트웨이와 중재 서버 간에 여러 개의 연관을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33485-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="33485-112">이렇게 하면 PBX(Private Branch Exchange) 상호 Enterprise Voice 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="33485-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="33485-113">트렁크가 정의된 경우 트렁크를 경로에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33485-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="33485-114">트렁크를 경로에 연결하기 위해 토폴로지 작성기에서 트렁크의 간단한 이름을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="33485-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="33485-115">이 간단한 이름은 트렁크를 경로와 연결될 수 있는 비즈니스용 Skype 서버 제어판에서 트렁크 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="33485-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="33485-116">단순 트렁크 이름은 비즈니스용 Skype 서버 관리 셸의 게이트웨이 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="33485-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="33485-117">관리자는 중재 서버와 연결된 기본 트렁크를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33485-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="33485-118">토폴로지 작성기에서 연결된 중재 서버를 마우스 오른쪽 단추로 클릭한 다음 **속성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="33485-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="33485-119">중재 서버의 기본 게이트웨이를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33485-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="33485-120">다음 다이어그램에서는 각 중재 서버 및 게이트웨이에 대해 정의된 여러 트렁크를 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33485-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![여러 트렁크 할당](../../media/multiple-trunk-assignments.jpg)
