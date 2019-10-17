---
title: 온-프레미스 통합 메시징과 비즈니스용 Skype 통합에 대 한 배포 프로세스 개요
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1bcadf0a-ca3d-436f-a2a0-09329d487b18
description: '요약: 비즈니스용 Skype 서버와 Exchange 2013 또는 2016을 통합 하기 위해 계획 하는 동안이 항목을 검토 하세요.'
ms.openlocfilehash: dfb9eb926cb1ebd046f06597eecc0c2204fea97b
ms.sourcegitcommit: fa55f9e3690fcca36b530bd13a9eeaa44120b87c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "37547271"
---
# <a name="deployment-process-overview-for-integrating-on-premises-unified-messaging-and-skype-for-business"></a>온-프레미스 통합 메시징과 비즈니스용 Skype 통합에 대 한 배포 프로세스 개요
 
**요약:** 비즈니스용 Skype 서버와 Exchange 2013 또는 2016을 통합 하기 위해 계획 하는 동안이 항목을 검토 하세요.
  
 비즈니스용 Skype 서버와 UM (Exchange 통합 메시징)을 통합 하려면이 항목에서 설명 하는 작업을 수행 해야 합니다. 또한 [비즈니스용 Skype의 Exchange 통합 메시징 통합 계획](unified-messaging.md)에 명시 된 계획 및 배포 모범 사례를 검토 하세요. 이 항목에서는 collocated 중재 서버를 사용 하 여 비즈니스용 Skype Server를 배포 했으며 비즈니스용 Skype Server에 대해 사용자를 사용 하도록 설정 했다고 가정 했지만, 다음과 같이 Enterprise Voice를 사용 하도록 설정 하는 모든 배포 및 구성 단계를 수행 하지는 않았습니다. 배포 설명서의 비즈니스용 [Skype 서버에서 Enterprise Voice 배포](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) 에 설명 되어 있습니다.
 
> [!NOTE]
> 이전에는 알려진 대로 Exchange 통합 메시징을 사용할 수 없습니다. 휴대폰 시스템을 사용 하 여 보이스 메일 메시지를 기록한 다음 사용자의 Exchange 사서함에 녹음/녹화를 종료 하는 비즈니스용 Skype 서버 2019에 더 이상 제공 되지 않습니다. 자세한 내용은 [클라우드 보이스 메일 서비스 계획](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 을 참조 하세요.
 
## <a name="unified-messaging-integration-process"></a>통합 메시징 통합 프로세스

> [!IMPORTANT]
> 원활한 성공적인 통합을 위해 각 사용자가 수행할 작업을 확인 하려면 조직의 Exchange 관리자와 협조 하는 것이 중요 합니다. 
  
|**단계의**|**방법은**|**필수 그룹 및 역할**|**배포 설명서**|
|:-----|:-----|:-----|:-----|
|다음 중 하나를 배포 합니다.  <br/> • 사서함  <br/> Microsoft Exchange Server 2010 또는 최신 서비스 팩  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2016  <br/>  |Microsoft Exchange Server 2013를 사용 하는 경우 비즈니스용 Skype 서버와 동일한 포리스트나 다른 포리스트에 다음 Exchange Server 역할을 설치 합니다.  <br/> • 클라이언트 액세스  <br/> • 사서함  <br/> Microsoft Exchange Server 2013 및 UM (통합 메시징)이 다른 포리스트에 설치 되어 있는 경우 비즈니스용 Skype 서버 포리스트를 신뢰 하도록 각 Exchange 포리스트를 구성 합니다.  <br/> Exchange 2010를 사용 하는 경우 비즈니스용 Skype 서버와 동일한 포리스트나 다른 포리스트에 다음 Exchange Server 역할을 설치 합니다.  <br/> • 통합 메시징  <br/> • Hub 전송  <br/> • 클라이언트 액세스  <br/> • 사서함  <br/> 비즈니스용 Skype 서버와 UM (통합 메시징)이 다른 포리스트에 설치 되어 있는 경우 비즈니스용 Skype 서버 포리스트를 신뢰 하도록 각 Exchange 포리스트를 구성 합니다.  <br/> |엔터프라이즈 관리자 (조직의 첫 번째 Exchange 서버인 경우)  <br/> 또는  <br/> Exchange 조직 관리자 (조직의 첫 번째 Exchange 서버가 아닌 경우)  <br/> |현재 버전의 Exchange Server에 대 한 적절 한 설명서를 참조 하세요.  <br/> Exchange Server 2010 또는 최신 서비스 팩 배포 설명서 <br/> Exchange Server 2013 계획 및 배포 <br/> Exchange Server 2016 계획 및 배포|
|인증서를 설치 합니다.  <br/> |신뢰할 수 있는 루트 CA (인증 기관)에서 각 Exchange UM 서버에 대 한 인증서를 다운로드 하 고 설치 합니다. 이 인증서는 Exchange UM을 실행 하는 서버와 비즈니스용 Skype 서버 간의 상호 전송 수준 보안 (MTLS)에 필요 합니다.  <br/> |관리자  <br/> |[Exchange Server 통합 메시징을 실행 하는 서버에서 인증서 구성](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-certificates-on-the-server-running-exchange-server-unified-messaging)|
|새 Exchange UM SIP 다이얼 플랜을 만들고 구성 합니다.  <br/> |Exchange UM 서버에서 조직의 특정 배포 요구 사항에 따라 SIP 다이얼 플랜을 만듭니다.  <br/> |Exchange 조직 관리자  <br/> | [Microsoft Exchange Server에서 통합 메시징 구성](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configuring-unified-messaging-on-microsoft-exchange-server) |
|Exchange UM SIP 다이얼 플랜에 대 한 보안 설정을 구성 합니다.  <br/> |엔터프라이즈 음성 트래픽을 암호화 하려면 **sip** 보안 또는 **보안이**설정 된 Exchange UM SIP 다이얼 플랜에서 보안 설정을 구성 합니다. 이는 환경에서 Lync Phone Edition 장치를 배포 하거나 배포 하는 경우 특히 중요 한 단계입니다. Exchange UM 통합을 사용 하는 환경에서 Lync Phone Edition 장치가 작동 하도록 하려면 비즈니스용 Skype 서버 암호화 설정이 Exchange UM 다이얼 플랜 보안 설정과 일치 해야 합니다. 자세한 내용은 배포 설명서를 참조 하세요.  <br/> |Exchange 조직 관리자  <br/> |Exchange 2010 또는 최신 서비스 팩은 다음을 참조 하세요.  <br/> [UM 다이얼 플랜에서 VoIP 보안을 구성](https://go.microsoft.com/fwlink/p/?LinkId=268697)합니다.  <br/> Exchange 2013의 경우 [통합 메시징을](https://go.microsoft.com/fwlink/p/?LinkId=266579)참조 하세요.  <br/> |
|Exchange UM SIP 다이얼 플랜에 통합 메시징 서버를 추가 합니다.  <br/> |새로 설치한 통합 메시징 서버에서 수신 전화에 응답 하 고 처리할 수 있도록 하려면 통합 메시징 서버를 UM 다이얼 플랜에 추가 해야 합니다. 이 경우 Exchange UM SIP 다이얼 플랜에 서버를 추가 합니다.  <br/> |관리자  <br/> Exchange Server 관리자  <br/> |Exchange 2010 또는 최신 서비스 팩의 경우 [UM 서버의 속성 보기 또는 구성을](https://go.microsoft.com/fwlink/p/?linkId=268682)참조 하세요.  <br/> Exchange 2013의 경우 [통합 메시징을](https://go.microsoft.com/fwlink/p/?LinkId=266579)참조 하세요.  <br/> |
|SIP 주소를 사용 하 여 사서함을 구성 합니다.  <br/> |Exchange UM 기능을 사용 하는 Enterprise Voice 사용자의 사서함에 SIP 주소를 할당 합니다.  <br/> |비즈니스용 Skype 서버 관리자  <br/> Exchange 받는 사람 관리자  <br/> |Exchange 2010 또는 최신 서비스 팩의 경우 [UM 사용이 가능한 사용자의 SIP 주소 수정을](https://go.microsoft.com/fwlink/p/?LinkId=268699)참조 하세요.  <br/> Exchange 2013의 경우 [통합 메시징을](https://go.microsoft.com/fwlink/p/?LinkId=266579)참조 하세요.  <br/> |
|Exchucutil 스크립트를 실행 합니다.  <br/> |Exchange UM 서비스를 실행 하는 서버에서 Exchange 관리 셸을 열고 다음을 수행 하는 exchucutil 스크립트를 실행 합니다. <br/> <br/> • Exchange UM Active Directory 도메인 서비스 개체, 특히 이전 작업에서 만든 SIP 다이얼 플랜을 읽을 수 있는 비즈니스용 Skype Server 권한을 부여 합니다.  <br/><br/> • Enterprise Voice를 사용 하도록 설정 된 사용자를 호스트 하는 각 비즈니스용 Skype Server Enterprise Edition pool 또는 Standard Edition Server에 대 한 Active Directory에 통합 메시징 IP 게이트웨이 개체를 만듭니다.  <br/><br/> • 각 게이트웨이에 대 한 Exchange UM 헌트 그룹을 만듭니다. 헌트 그룹 조종사 식별자는 해당 게이트웨이와 연결 된 다이얼 플랜의 이름이 됩니다. 다이얼 플랜을 두 개 이상 사용할 경우 1:1이 필요 합니다.  <br/> |Exchange 조직 관리자  <br/> Exchange 받는 사람 관리자  <br/> |[ExchUCUtil를 사용 하 여 Microsoft Exchange에서 통합 메시징 구성](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1) |
|비즈니스용 Skype 서버 다이얼 플랜을 구성 합니다.  <br/> |Exchange 2010와 통합 하는 경우 Exchange UM 다이얼 플랜의 FQDN (정규화 된 도메인 이름)과 일치 하는 이름을 사용 하 여 새 Enterprise Voice dial 계획을 만듭니다.  <br/> **참고:** 각 UM 다이얼 플랜에 대해이 작업을 수행 해야 합니다. <br/> Exchange 2010 SP1과 통합 하는 경우 적절 한 글로벌/사이트 수준 또는 풀 수준의 Enterprise Voice dial 요금제가 구성 되어 있는지 확인 합니다.  <br/> **참고:** Exchange 2010 SP1과 통합 하는 경우 비즈니스용 Skype Server 다이얼 플랜 및 Exchange UM SIP 다이얼 플랜 이름은 일치 하지 않아도 됩니다. <br/> |RTCUniversalServerAdmins  <br/> |[비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> |
|Exchange UM 통합 도구를 실행 합니다.  <br/> | 비즈니스용 Skype 서버에서 다음을 수행 하는 **ocsumutil**을 실행 합니다.  <br/>  구독자 액세스 및 자동 전화 교환 연락처 개체를 만듭니다. <br/>  Exchange UM 다이얼 플랜 FQDN과 일치 하는 이름을 사용 하는 Enterprise Voice dial 요금제가 있는지 확인 합니다. Exchange 2010 SP1 이상을 실행 중인 경우 다이얼 플랜 이름이 일치 하지 않아도 되며이에 대 한 도구의 경고는 무시할 수 있습니다. <br/>  이 도구는 Exchange UM 설정에 대 한 Active Directory를 검사 하 고 비즈니스용 Skype Server 관리자가 연락처 개체를 보고, 만들고, 편집할 수 있도록 하는 방식으로 작동 합니다. <br/> |RTCUniversalServerAdmins *및* RTCUniversalUserAdmins <br/> **중요:** Ocsumutil을 성공적으로 실행 하려면 사용자가 이러한 두 그룹 모두에 속해야 합니다. <br/> **참고:** 연락처 개체를 만들려면 ocsumutil을 실행 하는 사용자에 게 새 연락처 개체가 저장 된 Active Directory OU (조직 구성 단위)에 대 한 올바른 권한이 있어야 합니다. 이 권한은 **부여-CsOUPermission** cmdlet을 실행 하 여 부여할 수 있습니다. 자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서를 참조 하세요. <br/> |[비즈니스용 Skype 서버 2015 음성 사서함에 대해 Exchange Server 2013 통합 메시징 구성](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md) <br/> |
|필요한 경우 다른 엔터프라이즈 음성 구성 단계를 수행 합니다.  <br/> |서버나 사용자에 게 Enterprise Voice 설정을 아직 구성 하지 않은 경우 다음 중 하나 이상을 수행 합니다.  <br/> • 배포 및 구성  <br/> PSTN (공개 교환 전화 네트워크) 게이트웨이 및 중재 서버  <br/> • 음성 정책, PSTN 사용 레코드 및 아웃 바운드 통화 경로를 정의 합니다.  <br/> • 사용자가 엔터프라이즈 음성을 사용할 수 있도록 합니다.  <br/> • 필요에 따라 다이얼 플랜을 사용 하 여 특정 사용자를 구성할 수 있습니다.  <br/> 사용 하도록 설정 하는 Enterprise 음성 기능에 따라 다른 구성 단계가 필요할 수 있습니다.  <br/> |RTCUniversalServerAdmins  <br/> RTCUniversalUserAdmins  <br/> |다음 섹션의 항목을 참조 하세요.  <br/> • [비즈니스용 Skype에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성](../../deploy/deploy-enterprise-voice/voice-and-pstn.md) <br/> • [비즈니스용 Skype 서버에서 Enterprise Voice 배포](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) <br/> |
|Exchange UM에 대해 Enterprise Voice 사용자를 사용 하도록 설정 합니다.  <br/> |Exchange UM 서버에서 통합 메시징 사서함 정책이 만들어졌으며 각 사용자에 게 고유한 내선 번호 할당이 있는지 확인 한 다음 사용자가 통합 메시징을 사용할 수 있도록 설정 합니다.  <br/> |Exchange 받는 사람 관리자  <br/> |Exchange 2010 또는 최신 서비스 팩의 경우 [사용자가 통합 메시징을 사용할 수 있도록 설정](https://go.microsoft.com/fwlink/p/?LinkId=268701)을 참조 하세요.  <br/> Exchange 2013의 경우 [통합 메시징을](https://go.microsoft.com/fwlink/p/?LinkId=266579)참조 하세요.  <br/> |
   




## <a name="see-also"></a>참고 항목

[비즈니스용 Skype에서 Exchange 통합 메시징 통합 계획](unified-messaging.md)
