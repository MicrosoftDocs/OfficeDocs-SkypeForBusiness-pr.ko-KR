---
title: 에지 서버 NAT IP 추가
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
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: 공용 IP 주소는 NAT(Network Address Translation)에서 사용되는 IP 주소입니다. IP 주소는 공개적으로 라우팅 가능해야 합니다. 이러한 이유는 이 마법사의 기능 선택 페이지에서 이 에지 풀의 외부 IP 주소가 NAT에 의해 변환됩니다 옵션을 선택했기 때문입니다.
ms.openlocfilehash: 42972caf9254eb4a7382b6f7066d2c781403616f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815218"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="f8d82-105">에지 서버 NAT IP 추가</span><span class="sxs-lookup"><span data-stu-id="f8d82-105">Add Edge Server NAT IP</span></span>

<span data-ttu-id="f8d82-p102">공용 IP 주소는 NAT(Network Address Translation)에서 사용되는 IP 주소입니다. IP 주소는 공개적으로 라우팅 가능해야 합니다. 이러한 이유는 이 마법사의 **기능 선택** 페이지에서 **이 에지 풀의 외부 IP 주소가 NAT에 의해 변환됩니다** 옵션을 선택했기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f8d82-p102">The public IP address is the IP address that is used by network address translation (NAT). The IP address must be publicly routable. This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="f8d82-p103">NAT(Network Address Translation)는 사설망(예: 192.168.0.0 범위)에 있는 클라이언트 또는 서버가 공용 인터넷 네트워크를 통해 원격 네트워크에 있는 시스템과 통신할 수 있도록 합니다. NAT는 외부 인터페이스에서 단일 공용 IP 주소를 사용하고 내부 IP 주소를 단일 공용 IP 주소와 연결하여 작동합니다. NAT 매핑은 내부 주소를 외부 공용 IP 주소에 매핑합니다. 원격 시스템에는 원본의 공용 주소만 표시됩니다. 원격 시스템은 원본에 응답하고 원본은 NAT 맵을 참조하여 응답을 반환해야 할 내부 IP 주소를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f8d82-p103">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks. NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address. NAT mapping maps an internal address to the external public IP address. The remote system sees only the public address of the source. The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span>

<span data-ttu-id="f8d82-114">초기 토폴로지 배포 시 또는 이후에 외부 사용자 액세스에 대한 지원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8d82-114">You can add support for external user access when you deploy your initial topology or afterward.</span></span> <span data-ttu-id="f8d82-115">기존 토폴로지에 에지 서버를 추가하는 방법에 대한 자세한 내용은 에지 서버 배포 설명서에서 [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f8d82-115">For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


