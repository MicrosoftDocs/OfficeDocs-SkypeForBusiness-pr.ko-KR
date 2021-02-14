---
title: 비즈니스용 Skype 서버의 음성 사용량 및 트래픽 예측
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 621b08fb-f894-4d91-ac38-e443401b098b
description: 다음 메트릭을 사용하여 각 사이트의 사용자 트래픽과 해당 트래픽을 지원하는 데 필요한 포트 수를 예측할 수 있습니다.
ms.openlocfilehash: c631361a7ef6d4706632f59366adac3384a6d255
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827688"
---
# <a name="estimating-voice-usage-and-traffic-for-skype-for-business-server"></a><span data-ttu-id="40031-103">비즈니스용 Skype 서버의 음성 사용량 및 트래픽 예측</span><span class="sxs-lookup"><span data-stu-id="40031-103">Estimating voice usage and traffic for Skype for Business Server</span></span>
 
<span data-ttu-id="40031-104">다음 메트릭을 사용하여 각 사이트의 사용자 트래픽과 해당 트래픽을 지원하는 데 필요한 포트 수를 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40031-104">You can use the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="40031-105">**경량 트래픽**(매시간 사용자당 PSTN 호출 하나)의 경우 포트당 사용자 15명</span><span class="sxs-lookup"><span data-stu-id="40031-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="40031-106">**중간 정도의 트래픽**(매시간 사용자당 PSTN 호출 두 개)의 경우 포트당 사용자 10명</span><span class="sxs-lookup"><span data-stu-id="40031-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="40031-107">**높은 트래픽**(매시간 사용자당 PSTN 호출 세 개 이상)의 경우 포트당 사용자 5명</span><span class="sxs-lookup"><span data-stu-id="40031-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="40031-108">포트 수에 따라 필요한 중재 서버 및 게이트웨이의 수가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="40031-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="40031-109">대부분의 조직에서 배포를 고려하는 PSTN(공중 전화망) 게이트웨이의 크기는 포트 2개에서 포트 960개까지 다양합니다.</span><span class="sxs-lookup"><span data-stu-id="40031-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="40031-110">훨씬 더 큰 게이트웨이도 있지만 이러한 게이트웨이는 주로 전화 서비스 공급자가 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="40031-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="40031-p102">예를 들어 사용자 수가 1만 명이고 트래픽은 중간 정도인 조직의 경우 1,000개의 포트가 필요합니다. 필요한 게이트웨이 수는 총 게이트웨이 용량에 따라 결정되는 필요한 총 포트 수와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="40031-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  

