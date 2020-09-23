---
title: 에지 서버 IP 옵션 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: Microsoft Lync Server 2013에서는에 지 서버 및에 지 풀에 대 한 각 인터페이스에 대해 IPv4 및 IPv6 주소를 구성할 수 있습니다. 이렇게 하려면 다음을 수행합니다.
ms.openlocfilehash: 2c68fcfcb2e99759536224889a818639b61d5fcc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219793"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="079fb-104">에지 서버 IP 옵션 추가</span><span class="sxs-lookup"><span data-stu-id="079fb-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="079fb-105">Microsoft Lync Server 2013에서는에 지 서버 및에 지 풀에 대 한 각 인터페이스에 대해 IPv4 및 IPv6 주소를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079fb-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="079fb-106">이렇게 하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="079fb-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="079fb-107">**내부 인터페이스에서 Ipv4 사용**:에 지 서버 또는에 지 풀 내부 인터페이스에 ipv4 주소를 적용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="079fb-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="079fb-108">**내부 인터페이스에서 Ipv6 사용**:에 지 서버 또는에 지 풀 내부 인터페이스에 ipv6 주소를 적용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="079fb-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="079fb-109">**외부 인터페이스에서 Ipv4 사용**:에 지 서버 또는에 지 풀 외부 인터페이스에 ipv4 주소를 적용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="079fb-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="079fb-110">**외부 인터페이스에서 Ipv6 사용**:에 지 서버 또는에 지 풀 외부 인터페이스에 ipv6 주소를 적용 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="079fb-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="079fb-111">외부 IP 주소에 대 한 네트워크 주소 변환 주소를 사용 하도록에 지 서버 또는에 지 풀을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079fb-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="079fb-112">확인란을 선택 하 여이 작업을 수행 하는 경우이에 **지 풀의 외부 IP 주소가 NAT에 의해 변환 됩니다**.</span><span class="sxs-lookup"><span data-stu-id="079fb-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="079fb-p104">NAT 지원. 하드웨어 부하 분산을 사용하는 경우 NAT(Network Address Translation)가 지원되지 않으므로 하드웨어 부하 분산이 포함된 에지 서버 풀을 배포하는 경우 NAT 옵션을 선택하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="079fb-p104">NAT support. Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

