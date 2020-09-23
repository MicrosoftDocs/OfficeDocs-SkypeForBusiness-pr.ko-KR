---
title: Lync Server 2010용 에지 서버 옵션 추가
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
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 새에 지 서버 또는에 지 풀을 정의 하 고 새 서버 또는 풀에 대 한 기능을 정의할 수 있습니다. 선택할 수 있는 옵션은 다음과 같습니다.
ms.openlocfilehash: 273b2543fc3eea1373817ab38eab39379ec59132
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216599"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="a74e1-104">Lync Server 2010용 에지 서버 옵션 추가</span><span class="sxs-lookup"><span data-stu-id="a74e1-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="a74e1-105">새에 지 서버 또는에 지 풀을 정의 하 고 새 서버 또는 풀에 대 한 기능을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a74e1-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="a74e1-106">선택할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a74e1-106">The options that you can choose are:</span></span>

- <span data-ttu-id="a74e1-107">**단일 FQDN 및 IP 주소를 사용합니다.**: 외부 에지 인터페이스에 대해 단일 IPv4 또는 IPv6 주소(IPv4 및 IPv6을 둘 다 사용하려면 각 IP 주소 유형 중 하나를 정의해야 함)와 FQDN(정규화된 도메인 이름)을 사용하려면 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a74e1-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a74e1-108">이 옵션을 선택하는 경우 IP 주소를 하나만 사용하거나 IPv4 및 IPv6 주소를 하나씩 사용하지만 각 에지 인터페이스에 대해 서로 다른 포트 번호를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a74e1-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="a74e1-109">**페더레이션 사용(포트 5061)**: SIP(Session Initiation Protocol)를 사용하는 기타 SIP 페더레이션, 공급자 또는 호스트된 서비스와 페더레이션하려는 경우 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a74e1-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="a74e1-110">**이에 지 풀의 외부 ip 주소는 nat에서 변환**되며,에 지 외부 인터페이스에 대해 개인 IP 주소를 사용 하는 경우에는이 확인란을 선택 하 고,에 지 서버 또는에 지 풀을 논리적으로 배치할 NAT (network address translation) 장치를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a74e1-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="a74e1-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a74e1-111">See also</span></span>

[<span data-ttu-id="a74e1-112">외부 사용자 액세스 계획</span><span class="sxs-lookup"><span data-stu-id="a74e1-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="a74e1-113">외부 사용자 액세스 배포</span><span class="sxs-lookup"><span data-stu-id="a74e1-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
