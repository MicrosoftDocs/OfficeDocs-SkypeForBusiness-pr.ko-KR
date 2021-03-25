---
title: 신뢰할 수 있는 응용 프로그램 풀 FQDN 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 신뢰할 수 있는 응용 프로그램 풀 FQDN(정규화된 도메인 이름)을 정의하려면 다음을 지정합니다.
ms.openlocfilehash: 575d4b5464b4a109bc34908f8cb86b802a20a5c0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122679"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="58346-103">신뢰할 수 있는 응용 프로그램 풀 FQDN 추가</span><span class="sxs-lookup"><span data-stu-id="58346-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="58346-104">신뢰할 수 있는 응용 프로그램 풀 FQDN(정규화된 도메인 이름)을 정의하려면 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="58346-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="58346-105">신뢰할 수 있는 응용 프로그램을 호스팅할 서버 또는 서버 풀의 FQDN</span><span class="sxs-lookup"><span data-stu-id="58346-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="58346-106">부하 분산 및 고가용성의 신뢰할 수 있는 응용 프로그램에 대한 서버 풀을 배포하는 경우 **다중 컴퓨터 풀** 을 선택하고 부하 분산이나 고가용성이 필요하지 않은 경우 **단일 컴퓨터 풀** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58346-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="58346-p101">단일 신뢰할 수 있는 응용 프로그램 서버를 나중에 서버 풀로 변환할 수는 없습니다. 나중에 풀이 필요할 수도 있다고 생각되는 경우 지금 단일 컴퓨터가 포함된 다중 서버 풀을 배포하고 필요할 때 서버를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58346-p101">A single Trusted Applications Server cannot be converted to a pool of servers later. If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="58346-109">신뢰할 수 있는 응용 프로그램 풀에 대한 자세한 내용은 [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="58346-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
