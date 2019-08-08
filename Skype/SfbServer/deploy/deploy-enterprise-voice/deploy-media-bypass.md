---
title: 비즈니스용 Skype 서버에서 미디어 바이패스 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: 비즈니스용 Skype Server Enterprise Voice에서 미디어 바이패스를 배포 합니다. 필수 구성 요소 및 배포 프로세스 검사 목록을 포함 합니다.
ms.openlocfilehash: 2cbb57499a4cdb38a83424b3c86445817b18b4c5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233515"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 미디어 바이패스 배포
 
비즈니스용 Skype Server Enterprise Voice에서 미디어 바이패스를 배포 합니다. 필수 구성 요소 및 배포 프로세스 검사 목록을 포함 합니다.
  
이 항목에서는 적어도 하나 이상의 중재 서버와 하나 이상의 게이트웨이 피어가 PSTN 연결을 제공 하도록 이미 게시 되 고 구성 되었다고 가정 합니다. 이러한 작업에 대 한 자세한 내용은 비즈니스용 [Skype 서버의 토폴로지 작성기에서 중재 서버 배포](deploy-a-mediation-server.md) 및 비즈니스용 [Skype 서버의 토폴로지 작성기에서 게이트웨이 정의](define-a-gateway.md)를 참조 하세요.
  
 연결 하는 피어가 SIP 트렁크 공급자의 SBC 인 경우 공급자가 정규화 된 공급자이 고 공급자가 미디어 바이패스를 지원 하는지 확인 합니다. 예를 들어 많은 SIP 트렁크 공급자는 해당 SBC만 중재 서버에서 트래픽을 수신할 수 있도록 허용 합니다. 그런 경우에는 해당 트렁크에 대해 bypass을 사용 하도록 설정 하지 않아야 합니다. 또한 조직에서 SIP 트렁크 공급자에 대 한 내부 네트워크 IP 주소를 표시 하지 않는 한 미디어 바이패스를 사용 하도록 설정할 수 없습니다.
  
> [!NOTE]
> 미디어 바이패스는 모든 PSTN 게이트웨이, IP PBX, SBC와 상호 작용 하지 않습니다. Microsoft는 인증 된 파트너와 함께 PSTN 게이트웨이 및 SBCs 집합을 테스트 했으며 Cisco IP-Pbx를 사용 하 여 테스트를 완료 했습니다. 미디어 바이패스는 [통합 커뮤니케이션 오픈 상호 운용성 프로그램-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406)에 나열 된 제품 및 버전 에서만 지원 됩니다. 
  
선택적으로 CAC (call 허용 제어)에 대 한 다른 고급 엔터프라이즈 음성 기능을 구성한 경우에는 호출 허용 제어에 의해 수행 되는 대역폭 예약이 미디어 바이패스를 사용 하는 모든 통화에 적용 되지 않는다는 점에 유의 하세요. 미디어 바이패스를 사용할 것인지 여부를 확인 하 고 미디어 바이패스를 사용 하는 경우 통화 허용 제어는 통화에 사용할 수 없습니다. 미디어 바이패스 검사에 실패 하는 경우에만 호출 허용 제어에 대 한 검사를 수행 합니다. 이러한 두 기능은 PSTN으로 라우팅되는 특정 통화에 대해 상호 배타적이 지 않습니다. 미디어 바이패스는 통화의 미디어 끝점 사이에 대역폭 제약 조건이 없는 것으로 간주 되므로이 논리를 사용 합니다. 제한 된 대역폭의 링크에서는 미디어 바이패스를 수행할 수 없습니다. 따라서 다음 중 하나가 PSTN 통화에 적용 됩니다. a) 미디어는 중재 서버를 우회 하 고 통화 허용 제어는 통화에 대 한 대역폭을 예약 하지 않습니다. 또는 b) 통화 허용 제어는 통화에 대역폭 예약을 적용 하 고, 통화와 관련 된 중재 서버에서 미디어를 처리 합니다.
  
피어에 연결 된 개별 트렁크 연결에 대해 미디어 바이패스를 사용 하도록 설정 하는 것 외에도 미디어 우회를 전역적으로 사용 하도록 설정 해야 합니다. 전역 미디어 우회 설정에서는 미디어 bypass을 PSTN에 대 한 통화에 항상 시도 하도록 지정할 수 있으며, 호출 허용 제어에서 수행 하는 것과 유사 하 게 네트워크 사이트 및 네트워크 영역에 대 한 서브넷 매핑을 사용 하 여 미디어 바이패스를 적용 하는 방법도 있습니다. 고급 음성 기능. 미디어 바이패스 및 통화 허용 제어를 모두 사용 하는 경우에는 미디어 바이패스를 사용할지 여부를 결정할 때 호출 허용 컨트롤에 대해 지정 되는 네트워크 지역, 네트워크 사이트 및 서브넷 정보가 자동으로 사용 됩니다. 즉, 통화 허용 제어를 사용 하는 경우 PSTN에 대 한 통화에 대 한 미디어 바이패스를 항상 시도 하도록 지정할 수 없습니다.
  
> [!NOTE]
> 이러한 단계를 사용 하 여 미디어 바이패스를 구성 하는 경우 클라이언트와 중재 서버 피어 (예: PSTN 게이트웨이, IP PBX 또는 SIP 트렁크 공급자의 SBC) 간에 적절 한 연결을 설정 하는 것으로 가정 합니다. 링크에 대역폭이 제한 되어 있으면 미디어 우회를 통화에 적용할 수 없습니다. 미디어 바이패스는 모든 PSTN 게이트웨이, IP PBX, SBC와 상호 작용 하지 않습니다. Microsoft는 인증 된 파트너와 함께 PSTN 게이트웨이 및 SBCs 집합을 테스트 했으며 Cisco IP-Pbx를 사용 하 여 테스트를 완료 했습니다. 미디어 바이패스는 [통합 커뮤니케이션 오픈 상호 운용성 프로그램-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406)에 나열 된 제품 및 버전 에서만 지원 됩니다. 
  
## <a name="deployment-process-for-media-bypass"></a>미디어 바이패스 배포 프로세스

다음 표에서는 미디어 바이패스 배포 프로세스에 대해 간략하게 설명 합니다. 
  
|**단계의**|**방법은**|**역할**|**배포 설명서**|
|:-----|:-----|:-----|:-----|
|미디어 바이패스에 대 한 trunks 구성  <br/> |아직 수행 하지 않은 경우 미디어 바이패스에 대해 하나 이상의 trunks를 구성 합니다.  <br/> | RTCUniversalServerAdmins 그룹 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원 인 구성원 <br/> |[비즈니스용 Skype 서버에서 미디어 바이패스를 사용 하 여 트렁크 구성](configure-trunk-with-media-bypass.md) <br/> |
|미디어 우회 전역 구성  <br/> |PSTN에 대 한 모든 통화 또는 네트워크 사이트 및 네트워크 지역을 기반으로 특정 통화에 대 한 미디어 우회를 구성 합니다.  <br/> | RTCUniversalServerAdmins 그룹 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원 인 구성원 <br/> |[비즈니스용 Skype 서버에서 미디어 바이패스를 구성 하 여 항상 중재 서버를 우회 합니다.](bypass-the-mediation-server.md) <br/> [미디어 구성 비즈니스용 Skype 서버의 전역 설정 무시 사이트 및 지역 정보 사용](use-site-and-region-information.md) <br/> |
|필요한 경우 서브넷을 네트워크 사이트와 연결  <br/> |사이트 및 지역 정보를 사용 하도록 미디어 우회를 구성 하는 경우 배포의 서브넷을 네트워크 사이트 및 영역과 연결 해야 합니다 (다른 음성 기능을 사용할 수 있도록 아직 하지 않은 경우).  <br/> | RTCUniversalServerAdmins 그룹 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원 인 구성원 <br/> |[네트워크 사이트에 서브넷 연결](deploy-network.md#BKMK_AssociateSubnets) <br/> |
   

