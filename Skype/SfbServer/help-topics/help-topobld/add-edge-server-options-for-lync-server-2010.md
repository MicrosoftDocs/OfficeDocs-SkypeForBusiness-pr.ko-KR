---
title: Lync Server 2010용 에지 서버 옵션 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 새 에지 서버 또는 에지 풀을 정의하고 새 서버 또는 풀에 대한 기능을 정의할 수 있는 기회가 표시됩니다. 선택할 수 있는 옵션은 다음과 같습니다.
ms.openlocfilehash: b6f6e07c3555101103aeaad7f1c45f4449c25078
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835518"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="b4d34-104">Lync Server 2010용 에지 서버 옵션 추가</span><span class="sxs-lookup"><span data-stu-id="b4d34-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="b4d34-105">새 에지 서버 또는 에지 풀을 정의하고 새 서버 또는 풀에 대한 기능을 정의할 수 있는 기회가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4d34-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="b4d34-106">선택할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b4d34-106">The options that you can choose are:</span></span>

- <span data-ttu-id="b4d34-107">**단일 FQDN 및 IP 주소를 사용합니다.**: 외부 에지 인터페이스에 대해 단일 IPv4 또는 IPv6 주소(IPv4 및 IPv6을 둘 다 사용하려면 각 IP 주소 유형 중 하나를 정의해야 함)와 FQDN(정규화된 도메인 이름)을 사용하려면 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b4d34-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b4d34-108">이 옵션을 선택하는 경우 IP 주소를 하나만 사용하거나 IPv4 및 IPv6 주소를 하나씩 사용하지만 각 에지 인터페이스에 대해 서로 다른 포트 번호를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4d34-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="b4d34-109">**페더레이션 사용(포트 5061)**: SIP(Session Initiation Protocol)를 사용하는 기타 SIP 페더레이션, 공급자 또는 호스트된 서비스와 페더레이션하려는 경우 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b4d34-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="b4d34-110">이 에지 풀의 외부 IP 주소는 **NAT에** 의해 변환됩니다. 에지 외부 인터페이스에 대해 개인 IP 주소를 사용하며 에지 서버 또는 에지 풀을 논리적으로 뒤에 두는 NAT(Network Address Translation) 장치를 제공하는 경우 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b4d34-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4d34-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4d34-111">See also</span></span>

[<span data-ttu-id="b4d34-112">외부 사용자 액세스 계획</span><span class="sxs-lookup"><span data-stu-id="b4d34-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="b4d34-113">외부 사용자 액세스 배포</span><span class="sxs-lookup"><span data-stu-id="b4d34-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
