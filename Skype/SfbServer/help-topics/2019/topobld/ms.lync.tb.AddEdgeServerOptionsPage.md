---
title: 에지 서버 옵션 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
ROBOTS: NOINDEX, NOFOLLOW
description: 에지 풀에 대해 사용하도록 설정할 각 기능을 선택합니다. 기본적으로 에지 풀은 VPN(가상 사설망)을 사용하여 방화벽 외부에서 로그인하는 조직의 원격 사용자를 지원합니다. 또한 다음과 같은 에지 풀 기능 옵션도 있습니다.
ms.openlocfilehash: 943a2a7b96fa8bcfd00e3c21631f763ad056b31d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800938"
---
# <a name="add-edge-server-options"></a><span data-ttu-id="71229-105">에지 서버 옵션 추가</span><span class="sxs-lookup"><span data-stu-id="71229-105">Add Edge Server Options</span></span>

<span data-ttu-id="71229-106">에지 풀에 대해 사용하도록 설정할 각 기능을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71229-106">Select each feature that you want to enable for the Edge pool.</span></span> <span data-ttu-id="71229-107">기본적으로 에지 풀은 VPN(가상 사설망)을 사용하여 방화벽 외부에서 로그인하는 조직의 원격 사용자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="71229-107">By default, the Edge pool supports remote users in your organization who sign in to from outside the firewall by using a virtual private network (VPN).</span></span> <span data-ttu-id="71229-108">또한 다음과 같은 에지 풀 기능 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71229-108">You also have the following Edge pool feature options:</span></span>

- <span data-ttu-id="71229-109">액세스 에지 서비스, 웹 회의 에지 서비스 및 A/V 에지 서비스를 비롯한 모든 에지 서비스에 대해 단일 FQDN(FQDN) 및 IP 주소 사용</span><span class="sxs-lookup"><span data-stu-id="71229-109">Use of a single fully qualified domain name (FQDN) and IP address for all edge services, including the Access Edge service, Web Conferencing Edge service, and A/V Edge service.</span></span> <span data-ttu-id="71229-110">단일 FQDN 및 IP 주소를 사용하는 옵션을 선택하지 않는 경우 배포 프로세스의 일부로 이러한 세 가지 에지 서비스에 대해 별도의 FQDN 및 IP 주소를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71229-110">If you do not select the option to use a single FQDN and IP address, you will need to specify a separate FQDN and IP address for each of these three Edge services as part of the deployment process.</span></span> <span data-ttu-id="71229-111">에지 서비스에 대한 자세한 내용은 계획 설명서에서 외부 사용자 [액세스에 필요한](https://technet.microsoft.com/library/2d0f9817-14e7-4109-95dc-62420e3c29e2.aspx) 구성 요소를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="71229-111">For details about the Edge services, see [Components Required for External User Access](https://technet.microsoft.com/library/2d0f9817-14e7-4109-95dc-62420e3c29e2.aspx) in the Planning documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="71229-112">이 옵션을 선택하는 경우 각 에지 서비스에 대해 다른 포트 번호를 지정해야 합니다(권장 기본 포트 설정: 액세스 에지 서비스의 경우 444, 웹 회의 에지 서비스의 경우 8057 및 A/V 에지 서비스의 경우 443).</span><span class="sxs-lookup"><span data-stu-id="71229-112">If you select this option, you must specify a different port number for each of the Edge services (recommended default port settings: 444 for Access Edge service, 8057 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="71229-113">이 옵션을 선택하면 세 가지 서비스에 모두 사용되는 하나의 FQDN을 입력할 수 있기 때문에 잠재적인 연결 문제를 방지하고 구성을 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71229-113">Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then enter one FQDN that is used for all three services.</span></span>

- <span data-ttu-id="71229-114">페더전 지원.</span><span class="sxs-lookup"><span data-stu-id="71229-114">Support for federation.</span></span> <span data-ttu-id="71229-115">지원되는 공용 IM(인스턴트 메시징) 공급자의 사용자를 포함하여 조직 외부의 신뢰할 수 있는 도메인에 있는 사용자와 내부 사용자 간의 통신을 지원하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71229-115">Select this option if you want to support communication between internal users and users in trusted domains outside your organization, including any users of a supported public instant messaging (IM) provider.</span></span> <span data-ttu-id="71229-116">이 옵션을 선택하는 경우 지원할 특정 페더티된 도메인 및 공용 IM 연결 서비스 공급자에 대한 지원을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71229-116">If you select this option, you will need to configure support for the specific federated domains and public IM connectivity service providers that you want to support.</span></span> <span data-ttu-id="71229-117">페더링 및 기타 유형의 외부 사용자 액세스에 대한 지원을 구성하는 자세한 내용은 에지 서버 배포 설명서에서 외부 사용자 [액세스에](https://technet.microsoft.com/library/f8424f8c-f965-4414-8485-30f07e10214a.aspx) 대한 지원 구성을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="71229-117">For details about configuring support for federation and other types of external user access, see [Configuring Support for External User Access](https://technet.microsoft.com/library/f8424f8c-f965-4414-8485-30f07e10214a.aspx) in the Edge Server Deployment documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="71229-118">조직에 있는 하나의 프런트 엔드 풀 또는 표준 에지 서버만 페더에 대해 외부에 게시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71229-118">Only one Front End pool or Standard Edge Server in your organization may be published externally for federation.</span></span> <span data-ttu-id="71229-119">공용 IM 사용자를 포함하여 페더러티 사용자의 모든 액세스는 동일한 에지 풀 또는 단일 에지 서버를 거치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71229-119">All access by federated users, including public IM users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="71229-120">예를 들어 배포에 뉴욕에 배포된 에지 풀 또는 단일 에지 서버와 런던에 배포된 에지 풀 또는 단일 에지 서버가 포함된 경우 뉴욕 에지 풀 또는 단일 에지 서버에서 페더레이션 지원을 사용하도록 설정하면 페더레이션 사용자에 대한 신호 트래픽이 뉴욕 에지 풀 또는 단일 에지 서버를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="71229-120">For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="71229-121">이는 런던 페더레이션 사용자를 호출하는 런던 내부 사용자가 A/V 트래픽에 대해 런던 풀 또는 에지 서버를 사용하기는 하지만 런던 사용자와의 통신에도 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="71229-121">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

- <span data-ttu-id="71229-122">XMPP 페더ation을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="71229-122">Enable XMPP federation.</span></span> <span data-ttu-id="71229-123">내부 사용자와 신뢰할 수 있는 XMPP 파트너 간의 통신을 지원하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71229-123">Select this option if you want to support communication between internal users and trusted XMPP partners.</span></span>

<span data-ttu-id="71229-124">초기 토폴로지 배포 시 또는 이후에 외부 사용자 액세스에 대한 지원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71229-124">You can add support for external user access when you deploy your initial topology or afterward.</span></span> <span data-ttu-id="71229-125">기존 토폴로지에 에지 서버를 추가하는 방법에 대한 자세한 내용은 에지 서버 배포 설명서에서 [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="71229-125">For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


