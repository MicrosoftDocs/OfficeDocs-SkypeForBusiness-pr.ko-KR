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
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: 이 문서에서는 Microsoft 팀 또는 비즈니스용 Skype에서 프록시 서버를 사용 하는 방법에 대 한 정보를 제공 합니다.
ms.openlocfilehash: 3d8e2e067cce4214f51ee54ec08bafa1f4100770
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665960"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="19f45-103">Teams 또는 비즈니스용 Skype Online 용 프록시 서버</span><span class="sxs-lookup"><span data-stu-id="19f45-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="19f45-104">이 문서에서는 팀 또는 비즈니스용 Skype에서 프록시 서버를 사용 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="19f45-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="19f45-105">프록시 서버를 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="19f45-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="19f45-106">프록시를 통해 팀 또는 비즈니스용 Skype 트래픽을 제공 하는 경우, Microsoft에서 프록시를 우회 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="19f45-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="19f45-107">프록시는 트래픽이 이미 암호화 되어 있기 때문에 비즈니스용 Skype를 더 안전 하 게 보호할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19f45-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="19f45-108">프록시로 인해 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f45-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="19f45-109">성능 관련 문제는 대기 시간 및 패킷 손실을 통해 환경에 도입 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f45-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="19f45-110">이러한 문제가 발생 하면 이러한 팀 또는 비즈니스용 Skype 시나리오에서 실시간 스트림이 필수적인 오디오 및 비디오로 인 한 환경이 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19f45-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="19f45-111">프록시 서버를 사용 해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="19f45-111">If you need to use a proxy server</span></span>

<span data-ttu-id="19f45-112">일부 조직에서는 팀 또는 비즈니스용 Skype 트래픽에 대 한 프록시를 우회 하는 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19f45-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="19f45-113">이러한 경우에는 위에서 설명한 문제를 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19f45-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="19f45-114">Microsoft는 또한 다음을 적극 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="19f45-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="19f45-115">외부 DNS 확인 사용</span><span class="sxs-lookup"><span data-stu-id="19f45-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="19f45-116">직접 UDP 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="19f45-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="19f45-117">UDP 트래픽 허용</span><span class="sxs-lookup"><span data-stu-id="19f45-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="19f45-118">네트워킹 지침의 다른 권장 사항에 따라 [팀에 맞게 조직의 네트워크를 준비](prepare-network.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="19f45-118">Following the other recommendations in our networking guidelines: [Prepare your organization's network for Teams](prepare-network.md)</span></span>
  
    
<span data-ttu-id="19f45-119">이 지침을 팔 로우 하면 잠재적인 문제를 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19f45-119">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="19f45-120">관련 항목</span><span class="sxs-lookup"><span data-stu-id="19f45-120">Related topics</span></span>

[<span data-ttu-id="19f45-121">Microsoft 365 및 Office 365 네트워크 연결 원칙</span><span class="sxs-lookup"><span data-stu-id="19f45-121">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](https://aka.ms/pnc)

[<span data-ttu-id="19f45-122">Teams에 대한 조직의 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="19f45-122">Prepare your organization's network for Teams</span></span>](prepare-network.md)
