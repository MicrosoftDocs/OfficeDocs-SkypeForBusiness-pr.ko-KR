---
title: 미디어 우회를 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: 미디어 우회를 비즈니스용 Skype 서버 Enterprise Voice. 선행 구성 및 배포 프로세스 검사 목록을 포함합니다.
ms.openlocfilehash: f5bed4cf31158ea170b78110f3b6f5561aedb21d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769666"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>미디어 우회를 비즈니스용 Skype 서버
 
미디어 우회를 비즈니스용 Skype 서버 Enterprise Voice. 선행 구성 및 배포 프로세스 검사 목록을 포함합니다.
  
이 항목에서는 PSTN 연결을 제공하기 위해 하나 이상의 중재 서버와 하나 이상의 게이트웨이 피어를 이미 게시하고 구성했다고 가정합니다. 이러한 작업에 대한 자세한 내용은 [Deploy a Mediation Server in topology Builder in 비즈니스용 Skype 서버](deploy-a-mediation-server.md) 및 Define a gateway in [topology Builder in 비즈니스용 Skype 서버.](define-a-gateway.md)
  
 연결한 피어가 SIP 트렁크 공급자의 SBC인 경우 공급자가 적격 공급자이고 공급자가 미디어 우회를 지원하는지 확인하십시오. 예를 들어 많은 SIP 트렁크 공급자는 SBC가 중재 서버에서 트래픽을 수신하도록 허용합니다. 이 경우 해당 트렁크에 대해 우회를 사용하도록 설정하지 말아야 합니다. 또한 조직에서 내부 네트워크 IP 주소를 SIP 트렁크 공급자에 공개하지 않는 한 미디어 우회를 사용하도록 설정할 수 없습니다.
  
> [!NOTE]
> 미디어 바이패스가 모든 PSTN 게이트웨이, IP-PBX 및 SBC에서 작동하지는 않습니다. Microsoft는 인증된 파트너와 함께 PSTN 게이트웨이 및 SBC 집합을 테스트하고 Cisco IP-PBX에 대한 몇 가지 테스트를 수행했습니다. 미디어 우회는 [Unified Communications Open Interoperability Program - Lync Server에](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)나열된 제품 및 버전에서만 지원됩니다. 
  
다른 고급 Enterprise Voice 기능인 CAC(통화 가능 제어)를 이미 구성한 경우 통화 제한에 의해 수행되는 대역폭 예약은 미디어 우회가 적용되는 통화에는 적용되지 않습니다. 미디어 우회를 사용할지 여부에 대한 확인이 먼저 수행됩니다. 미디어 우회가 사용되는 경우 통화에 통화 참가 제어가 사용되지 않습니다. 미디어 우회 확인이 실패하는 경우 통화 입장 제어에 대한 확인이 수행된 것입니다. 따라서 두 기능은 PSTN으로 라우팅된 특정 호출에 대해 함께 사용할 수 없습니다. 미디어 우회는 통화의 미디어 끝점 사이에 대역폭 제약 조건이 없다고 가정하기 때문에 논리입니다. 제한된 대역폭이 있는 링크에서는 미디어 우회를 수행할 수 없습니다. 따라서 PSTN 통화에 다음 중 한 가지가 적용됩니다. a) 미디어는 중재 서버를 우회하고 통화 참가 제어는 통화에 대한 대역폭을 예약하지 않습니다. 또는 b) 통화 참가 제어는 통화에 대역폭 예약을 적용하고 미디어는 통화에 관련된 중재 서버에 의해 처리됩니다.
  
피어와 연결된 개별 트렁크 연결에 대해 미디어 우회를 사용하도록 설정하는 것 외에도 미디어 우회를 전역적으로 사용하도록 설정해야 합니다. 전역 미디어 우회 설정은 통화를 위한 미디어 우회가 항상 PSTN에 대한 통화에 대해 시도된다고 지정하거나, 다른 고급 음성 기능인 통화 액세스 제어에서 수행되는 작업과 유사하게 네트워크 사이트 및 네트워크 지역에 서브넷을 매핑하여 미디어 우회가 사용된다고 지정할 수 있습니다. 미디어 우회 및 통화 액세스 제어를 둘 다 사용하도록 설정하면 미디어 우회를 사용할지 여부를 결정할 때 통화 액세스 제어에 대해 지정된 네트워크 지역, 네트워크 사이트 및 서브넷 정보가 자동으로 사용됩니다. 즉, 통화 가능 제어를 사용하도록 설정한 경우 PSTN에 대한 통화에 대해 미디어 우회가 항상 시도된다고 지정할 수 없습니다.
  
> [!NOTE]
> 여기서 설명하는 단계를 사용하여 미디어 바이패스를 구성하는 경우, 클라이언트와 중재 서버 피어(예: SIP 트렁크 공급자의 SBC, IP-PBX 또는 PSTN 게이트웨이) 간의 연결이 원활하다고 가정합니다. 링크에 대한 대역폭 제한이 있는 경우에는 미디어 바이패스를 통화에 적용할 수 없습니다. 미디어 바이패스가 모든 PSTN 게이트웨이, IP-PBX 및 SBC에서 작동하지는 않습니다. Microsoft는 인증된 파트너와 함께 PSTN 게이트웨이 및 SBC 집합을 테스트하고 Cisco IP-PBX에 대한 몇 가지 테스트를 수행했습니다. 미디어 우회는 [Unified Communications Open Interoperability Program - Lync Server에](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)나열된 제품 및 버전에서만 지원됩니다. 
  
## <a name="deployment-process-for-media-bypass"></a>미디어 우회 배포 프로세스

다음 표에서는 미디어 우회 배포 프로세스에 대한 개요를 제공합니다. 
  
|**작업 단계**|**단계**|**역할**|**배포 설명서**|
|:-----|:-----|:-----|:-----|
|미디어 우회에 대한 트렁크 구성  <br/> |아직 트렁크를 구성하지 않은 경우 미디어 우회에 대해 하나 이상의 트렁크를 구성합니다.  <br/> | RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원 <br/> |[미디어 우회를 통해 트렁크를 비즈니스용 Skype 서버](configure-trunk-with-media-bypass.md) <br/> |
|전역적으로 미디어 우회 구성  <br/> |PSTN에 대한 모든 호출 또는 네트워크 사이트 및 네트워크 지역에 따라 특정 통화에 대해 미디어 우회를 구성합니다.  <br/> | RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원 <br/> |[중재 서버를 비즈니스용 Skype 서버 우회하도록 미디어 우회 구성](bypass-the-mediation-server.md) <br/> [사이트 및 지역 정보를 비즈니스용 Skype 서버 미디어 우회 전역 설정 구성](use-site-and-region-information.md) <br/> |
|필요한 경우 서브넷을 네트워크 사이트와 연결  <br/> |사이트 및 지역 정보를 사용하도록 미디어 우회를 구성하는 경우 배포의 서브넷을 네트워크 사이트 및 지역과 연결해야 합니다(다른 음성 기능을 위해 아직 연결하지 않은 경우).  <br/> | RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원 <br/> |[네트워크 사이트에 서브넷 연결](deploy-network.md#BKMK_AssociateSubnets) <br/> |
