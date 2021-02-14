---
title: 에지 컴퓨터 내부 IP 2010 추가
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
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: 이 페이지에서는 에지 서버의 내부 IP 주소 및 내부 FQDN(정규화된 도메인 이름)을 지정할 수 있습니다.
ms.openlocfilehash: eb5d2d8aa7dd0d7827e13089f7588f5090b6744a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828788"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="2585f-103">에지 컴퓨터 내부 IP 2010 추가</span><span class="sxs-lookup"><span data-stu-id="2585f-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="2585f-104">이 페이지에서는 에지 서버의 내부 IP 주소 및 내부 FQDN(정규화된 도메인 이름)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2585f-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="2585f-105">내부 **IPv4 주소에** 풀에 추가할 에지 서버의 IP 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2585f-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="2585f-106">내부 **FQDN에** 풀에 추가할 에지 서버의 FQDN(FQDN)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2585f-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="2585f-107">지정하는 FQDN은 서버에 구성된 컴퓨터 이름과 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2585f-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="2585f-108">기본적으로 도메인에 가입되지 않은 컴퓨터의 컴퓨터 이름은 FQDN이 아닌 짧은 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2585f-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="2585f-109">토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2585f-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="2585f-110">따라서 도메인에 가입되지 않은 에지 서버로 배포할 컴퓨터의 이름에 DNS(Domain Name System) 접미사를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2585f-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="2585f-111">컴퓨터 이름에 DNS 접미사를 추가하는 방법에 대한 자세한 내용은 [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2585f-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


