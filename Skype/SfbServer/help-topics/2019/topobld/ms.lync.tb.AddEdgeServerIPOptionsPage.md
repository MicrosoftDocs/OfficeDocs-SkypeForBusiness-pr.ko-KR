---
title: Edge 서버 IP 옵션 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: 비즈니스용 Skype Server에서는 Edge 서버 및 Edge 풀의 각 인터페이스에 대해 IPv4 및 IPv6 주소를 구성할 수 있습니다. 이 작업을 수행 하려면 다음을 수행 합니다.
ms.openlocfilehash: 12b1cdb36809ac703bd3383795ea92bdf48cdd31
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197470"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="14968-104">Edge 서버 IP 옵션 추가</span><span class="sxs-lookup"><span data-stu-id="14968-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="14968-105">비즈니스용 Skype Server에서는 Edge 서버 및 Edge 풀의 각 인터페이스에 대해 IPv4 및 IPv6 주소를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14968-105">Skype for Business Server allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="14968-106">이 작업을 수행 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="14968-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="14968-107">**내부 인터페이스에 Ipv4 사용**: edge 서버 또는 edge 풀 내부 인터페이스에 ipv4 주소를 적용 하려면 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="14968-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="14968-108">**내부 인터페이스에 Ipv6 사용**: edge 서버 또는 edge 풀 내부 인터페이스에 ipv6 주소를 적용 하려면 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="14968-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="14968-109">**외부 인터페이스에 Ipv4 사용**: edge 서버 또는 edge 풀 외부 인터페이스에 ipv4 주소를 적용 하려면 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="14968-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="14968-110">**외부 인터페이스에 Ipv6 사용**: edge 서버 또는 edge 풀 외부 인터페이스에 ipv6 주소를 적용 하려면 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="14968-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="14968-111">또한 외부 IP 주소에 대 한 네트워크 주소 변환 주소를 사용 하도록 Edge 서버 또는 Edge 풀을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14968-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="14968-112">확인란을 선택 하 여이 작업을 수행 합니다. **이 Edge 풀의 외부 IP 주소가 NAT에서 번역 됩니다**.</span><span class="sxs-lookup"><span data-stu-id="14968-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="14968-113">NAT 지원.</span><span class="sxs-lookup"><span data-stu-id="14968-113">NAT support.</span></span> <span data-ttu-id="14968-114">하드웨어 부하 분산을 사용 중인 경우에는 NAT (Network address translation)가 지원 되지 않으므로 하드웨어 부하 분산으로 Edge 서버 풀을 배포 하는 경우에는 NAT 옵션을 선택 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="14968-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

