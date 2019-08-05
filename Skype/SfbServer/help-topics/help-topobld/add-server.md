---
title: 서버 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 기존 서버 풀에 새 서버를 추가 하려면 풀이 다음 중 하나입니다.
ms.openlocfilehash: 32033d7d758528fc925c5c228971c040828bd654
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191724"
---
# <a name="add-server"></a><span data-ttu-id="2d326-103">서버 추가</span><span class="sxs-lookup"><span data-stu-id="2d326-103">Add Server</span></span>
 
<span data-ttu-id="2d326-104">기존 서버 풀에 새 서버를 추가 하려면 풀이 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="2d326-105">Enterprise Edition 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="2d326-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="2d326-106">디렉터 서버</span><span class="sxs-lookup"><span data-stu-id="2d326-106">Director server</span></span>
    
- <span data-ttu-id="2d326-107">중재 서버</span><span class="sxs-lookup"><span data-stu-id="2d326-107">Mediation Server</span></span>
    
- <span data-ttu-id="2d326-108">오디오/비디오 회의 서버</span><span class="sxs-lookup"><span data-stu-id="2d326-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="2d326-109">신뢰할 수 있는 응용 프로그램 서버</span><span class="sxs-lookup"><span data-stu-id="2d326-109">Trusted Application server</span></span>
    
<span data-ttu-id="2d326-110">각각의 새 풀 서버에는 서로 다른 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="2d326-111">다음 섹션에서 기존 풀에 추가 하는 서버의 유형을 찾아 각 서버 유형에 대해 정의 된 대로 요청 된 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="2d326-112">새 풀 서버를 정의 하는 데 필요한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="2d326-113">**Enterprise Edition 프런트 엔드 서버**</span><span class="sxs-lookup"><span data-stu-id="2d326-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="2d326-114">DNS (Domain Name System)에 정의 되어 있는 새 서버의 FQDN (정규화 된 도메인 이름)</span><span class="sxs-lookup"><span data-stu-id="2d326-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="2d326-115">컴퓨터에 정의 된 모든 IP 주소를 사용할 수 있음을 의미 하는 **구성 된 모든 ip 주소 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="2d326-116">또는 **선택한 IP 주소로 서비스 사용량 제한을** 선택 하 고 새 서버에 특정 주소를 입력할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="2d326-117">입력 된 IP 주소는 호스팅된 서비스에 대해 응답 하는 유일한 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="2d326-118">중재 서버가 프런트 엔드 서버에서 collocated 경우 **PSTN IP 주소** 를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="2d326-119">**Ipv6 사용** 을 선택 하 여이 서버에 ipv6을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="2d326-120">**디렉터 서버**</span><span class="sxs-lookup"><span data-stu-id="2d326-120">**Director server**</span></span>
  
- <span data-ttu-id="2d326-121">DNS에 정의 된 새 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="2d326-122">**구성 된 모든 ip 주소 사용**을 선택 하면 컴퓨터에 정의 된 모든 ip 주소가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="2d326-123">또는 **선택한 IP 주소로 서비스 사용량 제한을** 선택 하 고 새 서버에 특정 IP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="2d326-124">입력 된 IP 주소는 호스팅된 서비스에 대해 응답 하는 유일한 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="2d326-125">**중재 서버**</span><span class="sxs-lookup"><span data-stu-id="2d326-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="2d326-126">DNS에 정의 된 새 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="2d326-127">컴퓨터에 정의 된 모든 IP 주소를 사용할 수 있음을 의미 하는 **구성 된 모든 ip 주소 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="2d326-128">또는 **서비스 사용량을 선택한 IP 주소로 제한** 을 선택 하 고 새 서버의 특정 ip 주소를 기본 ip 주소로 입력 하 고 PSTN (공개 통신 네트워크) IP 주소의 ip 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="2d326-129">입력 한 IP 주소만 지정 된 서비스에 대해 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2d326-130">중재 서버의 경우 기본 IP 주소 및 PSTN IP 주소에 대해 입력 된 IP 주소가 기본적으로 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="2d326-131">전용 네트워크 인터페이스 또는 동일한 네트워크 인터페이스에서 별도의 IP 주소를 사용 하는 경우 IP 주소를 별도로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="2d326-132">두 개의 네트워크 인터페이스가 있는데, 하나는 로컬 네트워크 연결을 위한 것이 고, 하나는 PSTN 연결에 사용 하는 경우 다른 IP 주소를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="2d326-133">**오디오/비디오 회의 서버**</span><span class="sxs-lookup"><span data-stu-id="2d326-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="2d326-134">DNS에 정의 된 새 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="2d326-135">컴퓨터에 정의 된 모든 IP 주소를 사용할 수 있음을 의미 하는 **구성 된 모든 ip 주소 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="2d326-136">또는 **선택한 IP 주소로 서비스 사용량 제한을** 선택 하 고 새 서버에 특정 주소를 입력할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="2d326-137">입력 된 IP 주소는 호스팅된 서비스에 대해 응답 하는 유일한 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="2d326-138">**신뢰할 수 있는 응용 프로그램 서버**</span><span class="sxs-lookup"><span data-stu-id="2d326-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="2d326-139">DNS에 정의 된 새 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="2d326-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

