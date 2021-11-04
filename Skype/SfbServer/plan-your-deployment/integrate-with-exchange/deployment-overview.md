---
title: 배포 프로세스 개요-프레미스 통합 메시징 및 통합 비즈니스용 Skype
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1bcadf0a-ca3d-436f-a2a0-09329d487b18
description: '요약: 2013 또는 2016과 비즈니스용 Skype 서버 통합할 Exchange 이 항목을 검토합니다.'
ms.openlocfilehash: 1c2b0d34324c9945bdd5e5e3ed3bfa7a04566883
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773478"
---
# <a name="deployment-process-overview-for-integrating-on-premises-unified-messaging-and-skype-for-business"></a>배포 프로세스 개요-프레미스 통합 메시징 및 통합 비즈니스용 Skype
 
**요약:** 비즈니스용 Skype 서버 2013 또는 2016과 통합할 Exchange 이 항목을 검토하세요.
  
 UM(통합 메시징)Exchange 통합 메시징과 비즈니스용 Skype 서버 이 항목에 설명된 작업을 수행해야 합니다. 또한 Plan [for Exchange Unified Messaging integration in 비즈니스용 Skype에](unified-messaging.md)설명된 계획 및 배포 모범 사례를 검토해야 합니다. 이 항목에서는 배치된 중재 서버와 함께 비즈니스용 Skype 서버 배포했지만 사용자가 비즈니스용 Skype 서버를 사용하도록 설정했지만 Deploy Enterprise Voice in에 설명된 바와 같이 Enterprise Voice 배포 및 구성 단계를 모두 [수행하지 않은 것일 수 있습니다. 비즈니스용 Skype 서버](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) 배포 설명서에 설명된 문서를 참조하세요.
 
> [!NOTE]
> Exchange 이전에 알려진 통합 메시징은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다. 이 전화 시스템 사용하여 음성 메일 메시지를 녹음한 다음 사용자의 Exchange 사서함에 떠날 수 있습니다. 자세한 [클라우드 음성 사서함 서비스](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 계획을 참조하세요.
 
## <a name="unified-messaging-integration-process"></a>통합 메시징 통합 프로세스

> [!IMPORTANT]
> 조직의 관리자와 협의하여 원활하고 성공적인 통합을 Exchange 수행할 작업을 확인하는 것이 중요합니다. 
  
|**작업 단계**|**단계**|**필수 그룹 및 역할**|**배포 설명서**|
|:-----|:-----|:-----|:-----|
|다음 중 하나를 배포합니다.  <br/> • 사서함  <br/> Microsoft Exchange Server 2010 또는 최신 서비스 팩  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2016  <br/>  |Microsoft Exchange Server 2013을 사용하는 경우 동일한 Exchange Server 다른 포리스트에 다음 비즈니스용 Skype 서버.  <br/> • 클라이언트 액세스  <br/> • 사서함  <br/> 2013 및 Exchange UM(통합 메시징)이 다른 포리스트에 설치되어 있는 경우 Exchange 포리스트를 트러스트하도록 각 비즈니스용 Skype 서버 구성합니다. Microsoft Exchange Server  <br/> Exchange 2010을 사용하는 경우 동일한 Exchange Server 다른 포리스트에 다음 비즈니스용 Skype 서버.  <br/> • 통합 메시징  <br/> • 허브 전송  <br/> • 클라이언트 액세스  <br/> • 사서함  <br/> UM(비즈니스용 Skype 서버 및 Exchange)이 서로 다른 포리스트에 설치되어 있는 경우 각 Exchange 포리스트를 트러스트하도록 비즈니스용 Skype 서버 구성합니다.  <br/> |Enterprise 관리자(조직에서 첫 번째 Exchange Server 경우)  <br/> -또는-  <br/> Exchange 조직 관리자(조직에서 첫 번째 Exchange Server 아닌 경우)  <br/> |다음 버전에 대한 적절한 설명서를 Exchange Server.  <br/> Exchange Server 2010 또는 최신 서비스 팩 배포 설명서 <br/> Exchange Server 2013 계획 및 배포 <br/> Exchange Server 2016 계획 및 배포|
|인증서를 설치합니다.  <br/> |신뢰할 수 있는 루트 CA(Exchange 기관)에서 각 UM 서버에 대한 인증서를 다운로드하고 설치합니다. 인증서는 UM과 UM을 실행하는 서버 간의 MTLS(상호 전송 수준 보안)에 Exchange 비즈니스용 Skype 서버.  <br/> |관리자  <br/> |[통합 메시징을 실행하는 서버에서 Exchange Server 구성](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-certificates-on-the-server-running-exchange-server-unified-messaging)|
|새 UM SIP Exchange 계획을 만들고 구성합니다.  <br/> |UM Exchange 조직의 특정 배포 요구 사항에 따라 SIP 다이얼 플랜을 생성합니다.  <br/> |Exchange 조직 관리자  <br/> | [통합 메시징에서 Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configuring-unified-messaging-on-microsoft-exchange-server) |
|UM SIP 다이얼 Exchange 보안 설정을 구성합니다.  <br/> |사용자 Enterprise Voice 암호화하려면 UM SIP 다이얼 Exchange **SIP 보안** 또는 보안으로 **구성합니다.** 이 단계는 사용자 환경에 Lync 전화 장치를 배포하거나 배포할 계획인 경우 특히 중요한 단계입니다. Lync 전화 Edition 장치가 Exchange 통합된 환경에서 작동하려면 비즈니스용 Skype 서버 암호화 설정이 Exchange UM 다이얼 플랜 보안 설정과 일치해야 합니다. 자세한 내용은 배포 설명서를 참조하십시오.  <br/> |Exchange 조직 관리자  <br/> |2010 Exchange 또는 최신 서비스 팩에 대한 자세한 내용은 다음을 참조합니다.  <br/> [UM 다이얼 플랜에서 VoIP 보안을 구성합니다.](/previous-versions/office/exchange-server-2010/bb201721(v=exchg.141))  <br/> 2013 Exchange 통합 [메시징을 참조합니다.](/exchange/unified-messaging-exchange-2013-help)  <br/> |
|UM SIP 다이얼 Exchange 통합 메시징 서버를 추가합니다.  <br/> |새로 설치된 통합 메시징 서버에서 들어오는 호출에 응답하고 처리하도록 설정하려면 통합 메시징 서버를 UM 다이얼 플랜에 추가해야 합니다. 이 경우 UM SIP 다이얼 Exchange 서버를 추가합니다.  <br/> |관리자  <br/> Exchange Server 관리자  <br/> |2010 또는 Exchange 팩에 대한 자세한 내용은 [View or Configure the Properties of a UM Server을 참조합니다.](/previous-versions/office/exchange-server-2010/aa998815(v=exchg.141))  <br/> 2013 Exchange 통합 [메시징을 참조합니다.](/exchange/unified-messaging-exchange-2013-help)  <br/> |
|SIP 주소를 통해 사서함을 구성합니다.  <br/> |UM 기능을 사용할 Enterprise Voice 사용자의 사서함에 SIP Exchange 할당합니다.  <br/> |비즈니스용 Skype 서버 관리자  <br/> Exchange 받는 사람 관리자  <br/> |Exchange 2010 또는 최신 서비스 팩에 대한 자세한 내용은 [Modify a SIP Address for a UM-Enabled User 을 참조하세요.](/previous-versions/office/exchange-server-2010/dd335189(v=exchg.141))  <br/> 2013 Exchange 통합 [메시징을 참조합니다.](/exchange/unified-messaging-exchange-2013-help)  <br/> |
|스크립트를 exchucutil.ps1 실행합니다.  <br/> |UM Exchange 실행 서버에서 Exchange 관리 셸을 열고 다음 작업을 exchucutil.ps1 스크립트를 실행합니다. <br/> <br/> • 비즈니스용 Skype 서버 UM Active Directory 도메인 서비스 Exchange, 특히 이전 작업에서 만든 SIP 다이얼 플랜을 읽을 수 있는 권한을 부여합니다.  <br/><br/> • Active Directory에서 사용자를 호스팅하는 각 비즈니스용 Skype 서버 Enterprise Edition 풀 또는 Standard Edition 서버에 대해 통합 메시징 IP 게이트웨이 개체를 Enterprise Voice.  <br/><br/> • 각 Exchange UM 헌트 그룹을 만듭니다. 헌트 그룹 파일럿 식별자는 해당 게이트웨이와 연결된 다이얼 플랜의 이름이 됩니다. 다이얼 플랜이 두 개 이상인 경우 1:1로 매핑해야 합니다.  <br/> |Exchange 조직 관리자  <br/> Exchange 받는 사람 관리자  <br/> |[Microsoft 365에서 통합 메시징 Exchange ExchUCUtil.ps1](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1) |
|다이얼 비즈니스용 Skype 서버 구성합니다.  <br/> |Exchange 2010과 통합하는 경우 Enterprise Voice UM 다이얼 플랜 FQDN(Exchange 도메인 이름)에 일치하는 이름으로 새 Exchange 다이얼 플랜을 만드시오.  <br/> **참고:** 각 UM 다이얼 플랜에 대해 이 작업을 해야 합니다. <br/> Exchange 2010 SP1과 통합하는 경우 적절한 전역/사이트 수준 또는 풀 수준 Enterprise Voice 다이얼 플랜이 구성되어 있는지 확인하십시오.  <br/> **참고:** Exchange 2010 SP1과 통합하는 경우 비즈니스용 Skype 서버 다이얼 플랜 및 Exchange UM SIP 다이얼 플랜 이름과 일치할 필요가 없습니다. <br/> |RTCUniversalServerAdmins  <br/> |[2013에서 다이얼 플랜을 만들거나 비즈니스용 Skype 서버](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> |
|UM Exchange 도구를 실행합니다.  <br/> | 다음 비즈니스용 Skype 서버 를 **ocsumutil.exe** 실행합니다.  <br/>  구독자 액세스 및 연락처 자동 전화 교환 만듭니다. <br/>  UM 다이얼 Enterprise Voice FQDN과 일치하는 이름의 Exchange 다이얼 플랜이 있는지 검사합니다. Exchange 2010 SP1 이상을 실행하는 경우 다이얼 플랜 이름이 일치할 필요가 없습니다. 이에 대한 도구 경고를 무시해도 됩니다. <br/>  이 도구는 Active Directory에서 UM Exchange 검색하고 비즈니스용 Skype 서버 개체를 보고 만들고 편집할 수 있도록 하여 작동합니다. <br/> |RTCUniversalServerAdmins  *및*  RTCUniversalUserAdmins <br/> **중요:** 이 ocsumutil.exe 실행하려면 사용자가 이러한 두 그룹에 모두 속해야 합니다. <br/> **참고:** Contact 개체를 만들 ocsumutil.exe 새 연락처 개체가 저장되는 Active Directory OU(조직 구성 단위)에 대한 올바른 권한이 있어야 합니다. 이 사용 권한은 **Grant-CsOUPermission** cmdlet을 실행하여 부여할 수 있습니다. 자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서를 참조하십시오. <br/> |[음성 Exchange Server 통합 메시징에 비즈니스용 Skype 서버 구성](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md) <br/> |
|필요한 경우 다른 구성 Enterprise Voice 수행합니다.  <br/> |서버 또는 사용자에 대한 Enterprise Voice 아직 구성하지 않은 경우 다음 중 하나 이상을 실행합니다.  <br/> • 배포 및 구성  <br/> PSTN(Public Switched Telephone Network) 게이트웨이 및 중재 서버  <br/> • 음성 정책, PSTN 사용 레코드 및 아웃바운드 통화 경로를 정의합니다.  <br/> • 사용자가 해당 사용자에 대해 Enterprise Voice.  <br/> • 선택적으로 다이얼 플랜을 사용하여 특정 사용자를 구성합니다.  <br/> 다른 구성 단계는 사용하도록 설정하는 Enterprise Voice 따라 요구될 수 있습니다.  <br/> |RTCUniversalServerAdmins  <br/> RTCUniversalUserAdmins  <br/> |다음 섹션의 항목을 참조하세요.  <br/> • [음성 정책, PSTN](../../deploy/deploy-enterprise-voice/voice-and-pstn.md) 사용 레코드 및 음성 경로를 비즈니스용 Skype <br/> • [Enterprise Voice 배포할 비즈니스용 Skype 서버](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) <br/> |
|사용자가 Enterprise Voice UM에 대해 Exchange 사용하도록 설정  <br/> |Exchange UM 서버에서 통합 메시징 사서함 정책이 만들어지며 각 사용자에게 고유한 내선 번호 할당이 지정되어 있는지 확인한 다음 사용자가 통합 메시징을 사용할 수 있도록 합니다.  <br/> |Exchange 받는 사람 관리자  <br/> |2010 Exchange 또는 최신 서비스 팩에 대한 자세한 내용은 [Enable a User for Unified Messaging을 참조합니다.](/previous-versions/office/exchange-server-2010/bb124147(v=exchg.141))  <br/> 2013 Exchange 통합 [메시징을 참조합니다.](/exchange/unified-messaging-exchange-2013-help)  <br/> |
   




## <a name="see-also"></a>참고 항목

[Exchange 통합 메시징 통합 비즈니스용 Skype](unified-messaging.md)