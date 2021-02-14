---
title: 서버 추가
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
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 기존 서버 풀(풀이 다음 중 하나에 해당)에 새 서버를 추가하려면
ms.openlocfilehash: e40cf71b0ab52e66a3a28e0362de4f9106ddd831
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818628"
---
# <a name="add-server"></a><span data-ttu-id="2efa7-103">서버 추가</span><span class="sxs-lookup"><span data-stu-id="2efa7-103">Add Server</span></span>
 
<span data-ttu-id="2efa7-104">기존 서버 풀(풀이 다음 중 하나에 해당)에 새 서버를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="2efa7-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="2efa7-105">Enterprise Edition 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="2efa7-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="2efa7-106">디렉터 서버</span><span class="sxs-lookup"><span data-stu-id="2efa7-106">Director server</span></span>
    
- <span data-ttu-id="2efa7-107">중재 서버</span><span class="sxs-lookup"><span data-stu-id="2efa7-107">Mediation Server</span></span>
    
- <span data-ttu-id="2efa7-108">오디오/비디오 회의 서버</span><span class="sxs-lookup"><span data-stu-id="2efa7-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="2efa7-109">신뢰할 수 있는 응용 프로그램 서버</span><span class="sxs-lookup"><span data-stu-id="2efa7-109">Trusted Application server</span></span>
    
<span data-ttu-id="2efa7-p101">각 새 풀 서버의 요구 사항은 서로 다릅니다. 다음 섹션에서 기존 풀에 추가할 서버 유형을 찾아 각 서버 유형에 대해 정의된 대로 요청된 정보를 제공합니다. 새 풀 서버를 정의하려면 요청된 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2efa7-p101">Each of the new pool servers has different requirements. In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type. You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="2efa7-113">**Enterprise Edition 프런트 엔드 서버**</span><span class="sxs-lookup"><span data-stu-id="2efa7-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="2efa7-114">DNS(Domain Name System)에 정의된 대로 새 서버의 FQDN(정규화된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="2efa7-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="2efa7-p102">컴퓨터에 정의되어 있는 모든 IP 주소를 사용할 수 있음을 의미하는 **구성된 모든 IP 주소 사용** 을 선택합니다. 또는 **선택한 IP 주소로 서비스 사용 제한** 을 선택하고 새 서버에 대한 특정 주소를 입력할 수 있습니다. 입력한 IP 주소는 호스팅된 서비스에 응답하는 유일한 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2efa7-p102">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="2efa7-118">프런트 엔드 서버에 중재 서버가 배치된 경우 **PSTN IP 주소** 를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2efa7-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="2efa7-119">이 서버에 대해 IPv6을 사용하도록 설정하려면 **IPv6 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2efa7-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="2efa7-120">**디렉터 서버**</span><span class="sxs-lookup"><span data-stu-id="2efa7-120">**Director server**</span></span>
  
- <span data-ttu-id="2efa7-121">DNS에 정의된 대로 새 서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="2efa7-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="2efa7-p103">컴퓨터에 정의되어 있는 모든 IP 주소가 사용됨을 의미하는 **구성된 모든 IP 주소 사용** 을 선택합니다. 또는 **선택한 IP 주소로 서비스 사용 제한** 을 선택하고 새 서버에 대한 특정 IP 주소를 입력합니다. 입력한 IP 주소는 호스팅된 서비스에 응답하는 유일한 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2efa7-p103">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="2efa7-125">**중재 서버**</span><span class="sxs-lookup"><span data-stu-id="2efa7-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="2efa7-126">DNS에 정의된 대로 새 서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="2efa7-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="2efa7-p104">컴퓨터에 정의되어 있는 모든 IP 주소를 사용할 수 있음을 의미하는 **구성된 모든 IP 주소 사용** 을 선택합니다. 또는 **선택한 IP 주소로 서비스 사용 제한** 을 선택하고 기본 IP 주소로 새 서버에 대한 특정 IP 주소를 입력하고 PSTN(공중 전화망) IP 주소에 대한 IP 주소를 입력합니다. 입력한 IP 주소는 지정된 서비스에 응답하는 유일한 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2efa7-p104">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address. The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2efa7-p105">중재 서버의 경우 기본적으로 기본 IP 주소로 입력한 IP 주소와 PSTN IP 주소가 동일합니다. 전용 네트워크 인터페이스를 사용하거나 동일한 네트워크 인터페이스에서 서로 다른 IP 주소를 사용하는 경우 IP 주소를 서로 다르게 정의할 수 있습니다. 네트워크 인터페이스가 두 개이고 이 중 하나는 로컬 네트워크 연결용이고 다른 하나는 PSTN 연결용인 경우 서로 다른 IP 주소를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2efa7-p105">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default. The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface. If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="2efa7-133">**A/V 회의 서버**</span><span class="sxs-lookup"><span data-stu-id="2efa7-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="2efa7-134">DNS에 정의된 대로 새 서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="2efa7-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="2efa7-p106">컴퓨터에 정의되어 있는 모든 IP 주소를 사용할 수 있음을 의미하는 **구성된 모든 IP 주소 사용** 을 선택합니다. 또는 **선택한 IP 주소로 서비스 사용 제한** 을 선택하고 새 서버에 대한 특정 주소를 입력할 수 있습니다. 입력한 IP 주소는 호스팅된 서비스에 응답하는 유일한 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2efa7-p106">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="2efa7-138">**신뢰할 수 있는 응용 프로그램 서버**</span><span class="sxs-lookup"><span data-stu-id="2efa7-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="2efa7-139">DNS에 정의된 새 서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="2efa7-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

