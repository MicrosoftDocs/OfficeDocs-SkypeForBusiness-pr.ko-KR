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
description: 이 문서에서는 Microsoft Teams 또는 비즈니스용 Skype와 함께 프록시 서버를 사용하는 방법을 제공합니다.
ms.openlocfilehash: 0e2089cfa327a610c3ee98f1f20862a28939fd0c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117726"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="3546d-103">Teams 또는 비즈니스용 Skype Online 용 프록시 서버</span><span class="sxs-lookup"><span data-stu-id="3546d-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="3546d-104">이 문서에서는 Teams 또는 비즈니스용 Skype와 함께 프록시 서버를 사용하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3546d-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="3546d-105">프록시 서버를 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3546d-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="3546d-106">Proxies를 통해 Teams 또는 비즈니스용 Skype 트래픽에 관해서는 Microsoft에서 프록시를 우회하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3546d-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="3546d-107">트래픽이 이미 암호화되어 있기 때문에 Proxies는 Teams 또는 비즈니스용 Skype를 더 안전하게 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3546d-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="3546d-108">프록시가 있는 경우 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3546d-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="3546d-109">성능 관련 문제는 대기 시간 및 패킷 손실을 통해 환경에 도입될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3546d-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="3546d-110">이러한 문제로 인해 실시간 스트림이 필수인 오디오 및 비디오와 같은 Teams 또는 비즈니스용 Skype 시나리오에서 부정적인 환경이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="3546d-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="3546d-111">프록시 서버를 사용해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="3546d-111">If you need to use a proxy server</span></span>

<span data-ttu-id="3546d-112">일부 조직에서는 Teams 또는 비즈니스용 Skype 트래픽에 대한 프록시를 우회할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3546d-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="3546d-113">이 경우 위에서 언급한 문제를 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3546d-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="3546d-114">Microsoft는 또한 강력하게 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="3546d-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="3546d-115">외부 DNS 확인 사용</span><span class="sxs-lookup"><span data-stu-id="3546d-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="3546d-116">직접 UDP 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="3546d-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="3546d-117">UDP 트래픽 허용</span><span class="sxs-lookup"><span data-stu-id="3546d-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="3546d-118">네트워킹 지침의 다른 권장 사항: [Teams에 대한](prepare-network.md) 조직의 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="3546d-118">Following the other recommendations in our networking guidelines: [Prepare your organization's network for Teams](prepare-network.md)</span></span>
  
    
<span data-ttu-id="3546d-119">이 지침을 따라 잠재적인 문제를 최소화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3546d-119">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3546d-120">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3546d-120">Related topics</span></span>

[<span data-ttu-id="3546d-121">Microsoft 365 및 Office 365 네트워크 연결 원칙</span><span class="sxs-lookup"><span data-stu-id="3546d-121">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="3546d-122">Teams에 대한 조직의 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="3546d-122">Prepare your organization's network for Teams</span></span>](prepare-network.md)