---
title: Lync Server 2010에 대 한 Edge 서버 옵션 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 새 Edge 서버 또는 Edge 풀을 정의 하 고 새 서버 또는 풀에 대 한 기능을 정의할 수 있는 기회가 제공 됩니다. 선택할 수 있는 옵션은 다음과 같습니다.
ms.openlocfilehash: 4bb364ee24f2e85ec16ff2f972dfe05aea9306cd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191664"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="1dcff-104">Lync Server 2010에 대 한 Edge 서버 옵션 추가</span><span class="sxs-lookup"><span data-stu-id="1dcff-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="1dcff-105">새 Edge 서버 또는 Edge 풀을 정의 하 고 새 서버 또는 풀에 대 한 기능을 정의할 수 있는 기회가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dcff-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="1dcff-106">선택할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1dcff-106">The options that you can choose are:</span></span>

- <span data-ttu-id="1dcff-107">**단일 FQDN과 IP 주소 사용**: 확인란을 선택 하 여 단일 Ipv4 또는 ipv6을 사용 하도록 선택한 경우 (Ipv4 및 ipv6을 모두 사용 하도록 선택 하는 경우) 외부 Edge 인터페이스에 대해 각 IP 주소 유형 중 하나를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dcff-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1dcff-108">이 옵션을 선택 하는 경우 하나의 IP 주소 또는 IPv4 및 IPv6 하나만 사용 하지만 각 Edge 인터페이스에 다른 포트 번호를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dcff-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="1dcff-109">**페더레이션 사용 (포트 5061)**: sip (세션 초기화 프로토콜)를 사용 하는 다른 sip 페더레이션, 공급자 또는 호스팅된 서비스를 페더레이션 하려면이 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dcff-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="1dcff-110">**이 edge 풀의 외부 IP 주소는 nat에 의해 번역 됩니다**. edge 외부 인터페이스에 개인 ip 주소를 사용 하 고 edge 서버 또는 edge 풀을 논리적으로 배치할 NAT (network address translation) 장치를 제공 하는 경우이 확인란을 선택 합니다. 나타나면.</span><span class="sxs-lookup"><span data-stu-id="1dcff-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="1dcff-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1dcff-111">See also</span></span>

[<span data-ttu-id="1dcff-112">외부 사용자 액세스 계획</span><span class="sxs-lookup"><span data-stu-id="1dcff-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="1dcff-113">외부 사용자 액세스 배포</span><span class="sxs-lookup"><span data-stu-id="1dcff-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
