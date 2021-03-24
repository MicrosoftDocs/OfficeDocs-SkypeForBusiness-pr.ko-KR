---
title: 에지 서버 내부 IP 2010 추가
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
- ms.lync.tb.AddEdgeServerInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 661dd74e-c42a-4905-a9c6-6efe02acc5f8
description: 이 페이지에서는 에지 서버의 내부 IP 주소 및 내부 FQDN(정규화된 도메인 이름)을 지정할 수 있습니다.
ms.openlocfilehash: c8e6c7fb4722d7d6e8b9b01057dc38d64cfe557e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103344"
---
# <a name="add-edge-server-internal-ip-2010"></a><span data-ttu-id="bac4e-103">에지 서버 내부 IP 2010 추가</span><span class="sxs-lookup"><span data-stu-id="bac4e-103">Add Edge Server Internal IP 2010</span></span>

<span data-ttu-id="bac4e-104">이 페이지에서는 에지 서버의 내부 IP 주소 및 내부 FQDN(정규화된 도메인 이름)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bac4e-104">Use this page to specify the internal IP address and internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

<span data-ttu-id="bac4e-105">지정하는 해당 FQDN은 서버에 구성된 컴퓨터 이름과 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac4e-105">That FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="bac4e-106">기본적으로 도메인에 가입되지 않은 컴퓨터의 컴퓨터 이름은 FQDN이 아닌 짧은 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bac4e-106">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="bac4e-107">토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bac4e-107">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="bac4e-108">따라서 도메인에 가입되지 않은 에지 서버로 배포할 컴퓨터의 이름에 DNS(Domain Name System) 접미사를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bac4e-108">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="bac4e-109">컴퓨터 이름에 DNS 접미사 추가에 대한 자세한 내용은 [Configure DNS for Edge Support을 참조합니다.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)</span><span class="sxs-lookup"><span data-stu-id="bac4e-109">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support).</span></span>