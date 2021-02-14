---
title: SBA(Survivable Branch Appliance) PSTN 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
ROBOTS: NOINDEX, NOFOLLOW
description: 분기 사이트에서 SBA(Survivable Branch Appliance)에 대한 공중 전화망(PSTN) 게이트웨이를 정의하려면 다음을 지정합니다.
ms.openlocfilehash: 30b5922e3d18b4dfe57bef23ddb0f00a25df7f9f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811948"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="f7f68-103">SBA(Survivable Branch Appliance) PSTN 추가</span><span class="sxs-lookup"><span data-stu-id="f7f68-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="f7f68-104">분기 사이트에서 SBA(Survivable Branch Appliance)에 대한 공중 전화망(PSTN) 게이트웨이를 정의하려면 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f68-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="f7f68-105">인바운드 및 아웃바운드 PSTN 통화를 라우팅하기 위해 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버와 연결되어 있는 게이트웨이 피어의 FQDN(정규화된 도메인 이름) 또는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="f7f68-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f7f68-106">SBA(Survivable Branch Appliance)를 정의하는 경우 이는 SBA(Survivable Branch Appliance) 내의 중재 서버에서 PSTN 연결을 위해 연결하는 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="f7f68-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="f7f68-p101">SIP(Session Initiation Protocol) 메시지에 사용할 수신 대기 포트. 기본적으로 게이트웨이, PBX(Private Branch Exchange) 또는 SBC(세션 경계 컨트롤러)에서 TCP(Transmission Control Protocol)에 사용되는 포트는 5066이고 TLS(전송 계층 보안)에 사용되는 포트는 5067입니다. 분기 사이트의 SBA(Survivable Branch Appliance)에서 TCP에 사용되는 기본 포트는 5081이고 TLS에 사용되는 기본 포트는 5082입니다.</span><span class="sxs-lookup"><span data-stu-id="f7f68-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="f7f68-p102">보안을 위해 TLS를 사용하는 것이 좋습니다. SBA(Survivable Branch Appliance)를 정의하는 경우 SBA(Survivable Branch Appliance) 공급업체 설명서를 참조하여 SBA(Survivable Branch Appliance)에서 TLS 프로토콜을 지원하는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="f7f68-p102">For security reasons, we strongly recommend that you use TLS. If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f7f68-112">보안을 위해 TLS를 사용할 수 있는 게이트웨이를 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f68-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f7f68-113">PSTN 게이트웨이를 추가하려는 경우 나중에 해당 게이트웨이를 설정할 수 있지만 전체 기능은 PSTN 게이트웨이가 정의 및 구성될 때까지 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7f68-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

