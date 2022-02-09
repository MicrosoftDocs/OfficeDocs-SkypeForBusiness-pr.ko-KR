---
title: SBA(Survivable Branch Appliance) PSTN 추가
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
ROBOTS: NOINDEX, NOFOLLOW
description: 분기 사이트에서 SBA(Survivable Branch Appliance)에 대한 공중 전화망(PSTN) 게이트웨이를 정의하려면 다음을 지정합니다.
ms.openlocfilehash: c7cd0a04790fa646870d7d2002af6ba455780f9e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401012"
---
# <a name="add-survivable-branch-appliance-pstn"></a>SBA(Survivable Branch Appliance) PSTN 추가
 
분기 사이트에서 SBA(Survivable Branch Appliance)에 대한 공중 전화망(PSTN) 게이트웨이를 정의하려면 다음을 지정합니다. 
  
- 인바운드 및 아웃바운드 PSTN 통화를 라우팅하기 위해 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버와 연결되어 있는 게이트웨이 피어의 FQDN(정규화된 도메인 이름) 또는 IP 주소
    
    > [!IMPORTANT]
    > SBA(Survivable Branch Appliance)를 정의하는 경우 이는 SBA(Survivable Branch Appliance) 내의 중재 서버에서 PSTN 연결을 위해 연결하는 게이트웨이입니다. 
  
- SIP(Session Initiation Protocol) 메시지에 사용할 수신 대기 포트. 기본적으로 게이트웨이, PBX(Private Branch Exchange) 또는 SBC(세션 경계 컨트롤러)에서 TCP(Transmission Control Protocol)에 사용되는 포트는 5066이고 TLS(전송 계층 보안)에 사용되는 포트는 5067입니다. 분기 사이트의 SBA(Survivable Branch Appliance)에서 TCP에 사용되는 기본 포트는 5081이고 TLS에 사용되는 기본 포트는 5082입니다.
    
- 보안을 위해 TLS를 사용하는 것이 좋습니다. SBA(Survivable Branch Appliance)를 정의하는 경우 SBA(Survivable Branch Appliance) 공급업체 설명서를 참조하여 SBA(Survivable Branch Appliance)에서 TLS 프로토콜을 지원하는지 확인하십시오.
    
    > [!IMPORTANT]
    > 보안을 위해 TLS를 사용할 수 있는 게이트웨이를 배포하는 것이 좋습니다. 
  
> [!NOTE]
> PSTN 게이트웨이를 추가하려는 경우 나중에 해당 게이트웨이를 설정할 수 있지만 전체 기능은 PSTN 게이트웨이가 정의 및 구성될 때까지 제한됩니다. 
  

