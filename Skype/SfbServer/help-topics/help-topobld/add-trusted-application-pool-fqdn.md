---
title: 신뢰할 수 있는 응용 프로그램 풀 FQDN 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 신뢰할 수 있는 응용 프로그램 풀 FQDN (정규화 된 도메인 이름)을 정의 하려면 다음을 지정 합니다.
ms.openlocfilehash: 27957348d4c6dc6b277a37d458ff21bb5efabc17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197449"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="935e7-103">신뢰할 수 있는 응용 프로그램 풀 FQDN 추가</span><span class="sxs-lookup"><span data-stu-id="935e7-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="935e7-104">신뢰할 수 있는 응용 프로그램 풀 FQDN (정규화 된 도메인 이름)을 정의 하려면 다음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="935e7-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="935e7-105">신뢰할 수 있는 응용 프로그램을 호스팅하는 서버 또는 서버의 풀의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="935e7-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="935e7-106">부하 분산 및 고가용성에서 신뢰할 수 있는 응용 프로그램에 대 한 서버 풀을 배포 하거나 부하 분산 또는 고가용성이 필요 하지 않은 경우 **단일 컴퓨터 풀** 을 선택 하는 경우 **여러 컴퓨터 풀** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="935e7-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="935e7-107">한 개의 신뢰할 수 있는 응용 프로그램 서버를 나중에 서버 풀로 변환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="935e7-107">A single Trusted Applications Server cannot be converted to a pool of servers later.</span></span> <span data-ttu-id="935e7-108">나중에 풀이 필요 하다 고 생각 되는 경우, 이제 단일 컴퓨터를 포함 하는 다중 서버 풀을 배포 하 고 필요한 경우 서버를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="935e7-108">If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="935e7-109">신뢰할 수 있는 응용 프로그램 풀에 대 한 자세한 내용은 [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="935e7-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

