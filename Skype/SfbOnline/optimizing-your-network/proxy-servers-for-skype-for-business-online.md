---
title: Teams 또는 비즈니스용 Skype Online 용 프록시 서버
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: 이 문서에서는 프록시 서버와 함께 프록시 서버를 사용하는 비즈니스용 Skype.
ms.openlocfilehash: 09ed98c5f69d6e244a5f87125e4ad607e4d16226
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240417"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="87999-103">온라인용 프록시 비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="87999-103">Proxy servers for Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="87999-104">이 문서에서는 프록시 서버와 함께 프록시 서버를 사용하는 방법에 대한 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="87999-104">This article provides guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="87999-105">프록시 서버를 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="87999-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="87999-106">xies를 통해 트래픽을 비즈니스용 Skype 경우 Microsoft는 프로시전을 무시하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="87999-106">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="87999-107">Proxies는 트래픽이 이미 암호화되어 비즈니스용 Skype 보안이 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87999-107">Proxies don't make Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="87999-108">프록시가 있는 경우 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87999-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="87999-109">성능 관련 문제는 대기 시간 및 패킷 손실을 통해 환경에 도입될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87999-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="87999-110">이러한 문제로 인해 실시간 스트림이 필수인 오디오 Teams 비즈니스용 Skype 시나리오에서 부정적인 환경을 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87999-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="87999-111">프록시 서버를 사용해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="87999-111">If you need to use a proxy server</span></span>

<span data-ttu-id="87999-112">일부 조직에서는 트래픽에 대한 프록시를 비즈니스용 Skype 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87999-112">Some organizations have no option to bypass a proxy for Skype for Business traffic.</span></span> <span data-ttu-id="87999-113">이 경우 위에서 언급한 문제를 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87999-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="87999-114">Microsoft는 또한 강력하게 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="87999-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="87999-115">외부 DNS 확인 사용</span><span class="sxs-lookup"><span data-stu-id="87999-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="87999-116">직접 UDP 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="87999-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="87999-117">UDP 트래픽 허용</span><span class="sxs-lookup"><span data-stu-id="87999-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="87999-118">네트워킹 지침의 다른 권장 사항을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="87999-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="87999-119">온라인에서 미디어 품질 및 비즈니스용 Skype 성능</span><span class="sxs-lookup"><span data-stu-id="87999-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](media-quality-and-network-connectivity-performance.md)
    
  - [<span data-ttu-id="87999-120">온라인용 네트워크 비즈니스용 Skype 최적화</span><span class="sxs-lookup"><span data-stu-id="87999-120">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
    
<span data-ttu-id="87999-121">이 지침을 따라 잠재적인 문제를 최소화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87999-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="87999-122">관련 항목</span><span class="sxs-lookup"><span data-stu-id="87999-122">Related topics</span></span>

[<span data-ttu-id="87999-123">온라인용 네트워크 비즈니스용 Skype 최적화</span><span class="sxs-lookup"><span data-stu-id="87999-123">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
 
