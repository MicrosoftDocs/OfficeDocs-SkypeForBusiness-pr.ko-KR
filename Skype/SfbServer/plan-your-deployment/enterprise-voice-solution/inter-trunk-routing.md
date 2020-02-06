---
title: 비즈니스용 Skype 서버의 트렁크 간 라우팅
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: 비즈니스용 Skype Server Enterprise Voice에서 트렁크 간 라우팅을 지 원하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 85a77fea8fb414a90b556e5862c42e2c59046dec
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802858"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="13dc4-103">비즈니스용 Skype 서버의 트렁크 간 라우팅</span><span class="sxs-lookup"><span data-stu-id="13dc4-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="13dc4-104">비즈니스용 Skype Server Enterprise Voice에서 트렁크 간 라우팅을 지 원하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="13dc4-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="13dc4-105">비즈니스용 Skype Server는 intertrunk 라우팅 지원을 통해 기본적인 세션 관리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="13dc4-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="13dc4-106">이렇게 하면 비즈니스용 Skype 서버에서 다운스트림 전화 통신 시스템에 대 한 통화 제어 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13dc4-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="13dc4-107">Intertrunk 라우팅은 IP-PBX (사설 브랜치 교환) 휴대폰의 호출을 PSTN으로 라우팅할 수 있고 들어오는 PSTN 통화를 PBX 전화기로 라우팅할 수 있도록 IP PBX를 PSTN (공개 전환 통신 네트워크) 게이트웨이와 상호 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13dc4-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="13dc4-108">마찬가지로, 비즈니스용 Skype 서버는 두 개 이상의 IP PBX 시스템을 상호 연결 하 여 여러 IP PBX 시스템에서 PBX 전화기 간에 전화를 걸고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13dc4-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="13dc4-109">다음 그림에서는 PSTN 게이트웨이와 IP PBX 간의 interconnectivity을 제공 하는 비즈니스용 Skype 서버를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="13dc4-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Lync Server 연결 PSTN 게이트웨이/IP-PBX 다이어그램](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="13dc4-111">다음 그림은 두 개의 IP PBX 시스템을 연결 하는 비즈니스용 Skype 서버를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="13dc4-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Lync Server 상호 연결 IP-PAX 시스템 다이어그램](../../media/inter_trunk02.jpg)
  

