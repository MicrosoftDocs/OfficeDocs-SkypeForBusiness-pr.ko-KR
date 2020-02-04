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
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: 이 문서에서는 팀 또는 비즈니스용 Skype에 프록시 서버를 사용 하는 방법에 대 한 정보를 제공 합니다.
ms.openlocfilehash: e71dd21d8d359093b5dada84a8d0788e8dff6af3
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708834"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="baa8b-103">Teams 또는 비즈니스용 Skype Online 용 프록시 서버</span><span class="sxs-lookup"><span data-stu-id="baa8b-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="baa8b-104">이 문서에서는 팀 또는 비즈니스용 Skype에서 프록시 서버를 사용 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa8b-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="baa8b-105">프록시 서버를 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="baa8b-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="baa8b-106">프록시를 통해 팀 또는 비즈니스용 Skype 트래픽을 제공 하는 경우, Microsoft에서 프록시를 우회 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="baa8b-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="baa8b-107">프록시는 트래픽이 이미 암호화 되어 있기 때문에 비즈니스용 Skype를 더 안전 하 게 보호할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa8b-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="baa8b-108">프록시로 인해 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa8b-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="baa8b-109">성능 관련 문제는 대기 시간 및 패킷 손실을 통해 환경에 도입 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa8b-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="baa8b-110">이러한 문제가 발생 하면 이러한 팀 또는 비즈니스용 Skype 시나리오에서 실시간 스트림이 필수적인 오디오 및 비디오로 인 한 환경이 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="baa8b-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="baa8b-111">프록시 서버를 사용 해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="baa8b-111">If you need to use a proxy server</span></span>

<span data-ttu-id="baa8b-112">일부 조직에서는 팀 또는 비즈니스용 Skype 트래픽에 대 한 프록시를 우회 하는 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baa8b-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="baa8b-113">이러한 경우에는 위에서 설명한 문제를 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa8b-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="baa8b-114">Microsoft는 또한 다음을 적극 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa8b-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="baa8b-115">외부 DNS 확인 사용</span><span class="sxs-lookup"><span data-stu-id="baa8b-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="baa8b-116">직접 UDP 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="baa8b-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="baa8b-117">UDP 트래픽 허용</span><span class="sxs-lookup"><span data-stu-id="baa8b-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="baa8b-118">네트워킹 지침의 다른 권장 사항에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="baa8b-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="baa8b-119">비즈니스용 Skype Online의 미디어 품질과 네트워크 연결 성능</span><span class="sxs-lookup"><span data-stu-id="baa8b-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="baa8b-120">비즈니스용 Skype Online에 맞게 네트워크 최적화</span><span class="sxs-lookup"><span data-stu-id="baa8b-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="baa8b-121">이 지침을 팔 로우 하면 잠재적인 문제를 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baa8b-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="baa8b-122">관련 주제</span><span class="sxs-lookup"><span data-stu-id="baa8b-122">Related topics</span></span>

[<span data-ttu-id="baa8b-123">비즈니스용 Skype Online에 맞게 네트워크 최적화</span><span class="sxs-lookup"><span data-stu-id="baa8b-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 