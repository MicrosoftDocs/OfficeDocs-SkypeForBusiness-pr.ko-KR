---
title: SBA(Survivable Branch Appliance) PSTN 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 지사 사이트의 Survivable Branch 기기에 대 한 PSTN (공용 전환 전화 네트워크) 게이트웨이를 정의 하려면 다음을 지정 합니다.
ms.openlocfilehash: 3a146a5bf9b879681b0d490a1d03198853c72305
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197454"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="c41ef-103">SBA(Survivable Branch Appliance) PSTN 추가</span><span class="sxs-lookup"><span data-stu-id="c41ef-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="c41ef-104">지사 사이트의 Survivable Branch 기기에 대 한 PSTN (공용 전환 전화 네트워크) 게이트웨이를 정의 하려면 다음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c41ef-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="c41ef-105">인바운드 및 아웃 바운드 PSTN 호출 라우팅에 Survivable Branch 기기 또는 Survivable Branch 서버가 연결 된 게이트웨이 피어의 FQDN (정규화 된 도메인 이름) 또는 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c41ef-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c41ef-106">Survivable Branch 기기를 정의 하는 경우, Survivable Branch 기기 내의 중재 서버가 PSTN 연결을 위해 연결 하는 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="c41ef-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="c41ef-p101">SIP(Session Initiation Protocol) 메시지에 사용할 수신 대기 포트. 기본적으로 게이트웨이, PBX(Private Branch Exchange) 또는 SBC(세션 경계 컨트롤러)에서 TCP(Transmission Control Protocol)에 사용되는 포트는 5066이고 TLS(전송 계층 보안)에 사용되는 포트는 5067입니다. 분기 사이트의 SBA(Survivable Branch Appliance)에서 TCP에 사용되는 기본 포트는 5081이고 TLS에 사용되는 기본 포트는 5082입니다.</span><span class="sxs-lookup"><span data-stu-id="c41ef-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="c41ef-110">보안상의 이유로, TLS를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c41ef-110">For security reasons, we strongly recommend that you use TLS.</span></span> <span data-ttu-id="c41ef-111">Survivable Branch 기기를 정의 하는 경우에는 Survivable Branch 기기 공급 업체 문서를 참조 하 여 Survivable Branch 기기가 TLS 프로토콜을 지원 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c41ef-111">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c41ef-112">보안을 위해 TLS를 사용할 수 있는 게이트웨이를 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c41ef-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c41ef-113">PSTN 게이트웨이를 추가하려는 경우 나중에 해당 게이트웨이를 설정할 수 있지만 전체 기능은 PSTN 게이트웨이가 정의 및 구성될 때까지 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c41ef-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

