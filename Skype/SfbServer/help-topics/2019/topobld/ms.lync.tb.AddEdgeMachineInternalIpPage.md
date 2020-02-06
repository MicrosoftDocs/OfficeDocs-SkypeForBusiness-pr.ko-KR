---
title: Edge 컴퓨터 내부 IP 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34717d03-5ece-4be3-9d05-25497250dc16
ROBOTS: NOINDEX, NOFOLLOW
description: 이 페이지를 사용 하 여 Edge 서버의 내부 IP 주소 및 FQDN (정규화 된 도메인 이름)을 지정 합니다.
ms.openlocfilehash: fba327a08d8998056c42a39190fd8b3bf44ff08b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798245"
---
# <a name="add-edge-machine-internal-ip"></a><span data-ttu-id="e24e2-103">Edge 컴퓨터 내부 IP 추가</span><span class="sxs-lookup"><span data-stu-id="e24e2-103">Add Edge Machine Internal IP</span></span>

<span data-ttu-id="e24e2-104">이 페이지를 사용 하 여 Edge 서버의 내부 IP 주소 및 FQDN (정규화 된 도메인 이름)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e24e2-104">Use this page to specify the internal IP address and internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

<span data-ttu-id="e24e2-105">지정 하는 FQDN은 서버에 구성 된 컴퓨터 이름과 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e24e2-105">The FQDN that you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="e24e2-106">기본적으로 도메인에 가입되지 않은 컴퓨터의 컴퓨터 이름은 FQDN이 아닌 짧은 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e24e2-106">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="e24e2-107">토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e24e2-107">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="e24e2-108">따라서 도메인에 가입 되어 있지 않은 Edge 서버로 배포할 컴퓨터의 이름에 DNS (Domain Name System) 접미사를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e24e2-108">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="e24e2-109">컴퓨터 이름에 DNS 접미사를 추가 하는 방법에 대 한 자세한 내용은 [Edge 지원에 대 한 Dns 구성을](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e24e2-109">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


