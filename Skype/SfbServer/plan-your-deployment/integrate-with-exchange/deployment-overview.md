---
title: 배포 프로세스 개요-프레미스 통합 메시징 및 비즈니스용 Skype 통합
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1bcadf0a-ca3d-436f-a2a0-09329d487b18
description: '요약: 비즈니스용 Skype 서버와 Exchange 2013 또는 2016의 통합을 계획하는 동안 이 항목을 검토합니다.'
ms.openlocfilehash: 8171d8f7191b4b0db6fbb3deee76ab411b2ce25b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810128"
---
# <a name="deployment-process-overview-for-integrating-on-premises-unified-messaging-and-skype-for-business"></a>배포 프로세스 개요-프레미스 통합 메시징 및 비즈니스용 Skype 통합
 
**요약:** 비즈니스용 Skype 서버와 Exchange 2013 또는 2016의 통합을 계획하는 동안 이 항목을 검토하세요.
  
 Exchange UM(통합 메시징)을 비즈니스용 Skype 서버와 통합하려면 이 항목에 설명된 작업을 수행해야 합니다. 또한 비즈니스용 Skype의 Exchange 통합 메시징 통합 계획에 설명된 계획 및 배포 모범 사례를 [검토해야 합니다.](unified-messaging.md) 이 항목에서는 배치된 중재 서버와 함께 비즈니스용 Skype 서버를 배포하고 사용자가 비즈니스용 Skype 서버에 대해 사용자를 사용하도록 설정했지만 배포 설명서의 비즈니스용 [Skype](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) 서버 배포에 설명된 Enterprise Voice 배포에 설명된 Enterprise Voice 모든 배포 및 구성 단계를 수행하지 않은 것일 수 있습니다.
 
> [!NOTE]
> 이전에 알려진 Exchange 통합 메시징은 전화 시스템을 사용하여 음성 메일 메시지를 녹음한 다음 사용자의 Exchange 사서함에 그대로 두는 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다. 자세한 [내용은 클라우드 음성메일 서비스](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 계획을 참조하세요.
 
## <a name="unified-messaging-integration-process"></a>통합 메시징 통합 프로세스

> [!IMPORTANT]
> 원활하고 성공적인 통합을 위해 조직의 Exchange 관리자와 협의하여 각 사용자가 수행할 작업을 확인하는 것이 중요합니다. 
  
|**작업 단계**|**단계**|**필수 그룹 및 역할**|**배포 설명서**|
|:-----|:-----|:-----|:-----|
|다음 중 하나를 배포합니다.  <br/> • 사서함  <br/> Microsoft Exchange Server 2010 또는 최신 서비스 팩  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2016  <br/>  |Microsoft Exchange Server 2013을 사용하는 경우 비즈니스용 Skype Exchange Server 같은 포리스트 또는 다른 포리스트에 다음 Exchange Server 역할을 설치합니다.  <br/> • 클라이언트 액세스  <br/> • 사서함  <br/> 다른 Microsoft Exchange Server 2013 및 Exchange UM(통합 메시징)이 서로 다른 포리스트에 설치되어 있는 경우 비즈니스용 Skype 서버 포리스트를 신뢰하도록 각 Exchange 포리스트를 구성합니다.  <br/> Exchange 2010을 사용하는 경우 비즈니스용 Skype Exchange Server 같은 포리스트 또는 다른 포리스트에 다음 포리스트 역할을 설치합니다.  <br/> • 통합 메시징  <br/> • 허브 전송  <br/> • 클라이언트 액세스  <br/> • 사서함  <br/> 비즈니스용 Skype 서버 및 Exchange UM(통합 메시징)이 서로 다른 포리스트에 설치되어 있는 경우 비즈니스용 Skype 서버 포리스트를 신뢰하도록 각 Exchange 포리스트를 구성합니다.  <br/> |엔터프라이즈 관리자(조직에서 첫 번째 Exchange Server 경우)  <br/> -또는-  <br/> Exchange 조직 관리자(조직에서 첫 번째 Exchange Server 않은 경우)  <br/> |다음 버전의 해당 설명서를 Exchange Server.  <br/> Exchange Server 2010 또는 최신 서비스 팩 배포 설명서 <br/> Exchange Server 2013 계획 및 배포 <br/> Exchange Server 2016 계획 및 배포|
|인증서를 설치합니다.  <br/> |신뢰할 수 있는 루트 CA(인증 기관)에서 각 Exchange UM 서버에 대한 인증서를 다운로드하고 설치합니다. 인증서는 Exchange UM을 실행하는 서버와 비즈니스용 Skype 서버 간의 MTLS(상호 전송 수준 보안)에 필요합니다.  <br/> |관리자  <br/> |[통합 메시징을 실행하는 서버에서 Exchange Server 구성](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-certificates-on-the-server-running-exchange-server-unified-messaging)|
|새 Exchange UM SIP 다이얼 플랜을 만들고 구성합니다.  <br/> |Exchange UM 서버에서 조직의 특정 배포 요구 사항에 따라 SIP 다이얼 플랜을 생성합니다.  <br/> |Exchange 조직 관리자  <br/> | [통합 메시징의 구성 Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configuring-unified-messaging-on-microsoft-exchange-server) |
|Exchange UM SIP 다이얼 플랜에 대한 보안 설정을 구성합니다.  <br/> |사용자 Enterprise Voice 암호화하려면 Exchange UM SIP 다이얼 플랜의 보안 설정을 **SIP 보안** 또는 보안으로 **구성합니다.** 이 단계는 환경에 Lync Phone Edition 장치를 배포하거나 배포할 계획인 경우 특히 중요합니다. Lync Phone Edition 장치가 Exchange UM 통합을 사용하는 환경에서 작동하려면 비즈니스용 Skype 서버 암호화 설정이 Exchange UM 다이얼 플랜 보안 설정과 일치해야 합니다. 자세한 내용은 배포 설명서를 참조하십시오.  <br/> |Exchange 조직 관리자  <br/> |Exchange 2010 또는 최신 서비스 팩의 경우 다음을 참조합니다.  <br/> [UM 다이얼 플랜에서 VoIP 보안을 구성합니다.](https://go.microsoft.com/fwlink/p/?LinkId=268697)  <br/> Exchange 2013의 경우 통합 [메시징을 참조합니다.](https://go.microsoft.com/fwlink/p/?LinkId=266579)  <br/> |
|Exchange UM SIP 다이얼 플랜에 통합 메시징 서버를 추가합니다.  <br/> |새로 설치된 통합 메시징 서버가 수신 전화에 응답하고 처리하도록 설정하려면 통합 메시징 서버를 UM 다이얼 플랜에 추가해야 합니다. 이 경우 서버를 Exchange UM SIP 다이얼 플랜에 추가합니다.  <br/> |관리자  <br/> Exchange Server 관리자  <br/> |Exchange 2010 또는 최신 서비스 팩의 경우 UM 서버의 속성 보기 또는 [구성을 참조합니다.](https://go.microsoft.com/fwlink/p/?linkId=268682)  <br/> Exchange 2013의 경우 통합 [메시징을 참조합니다.](https://go.microsoft.com/fwlink/p/?LinkId=266579)  <br/> |
|SIP 주소로 사서함을 구성합니다.  <br/> |Exchange UM 기능을 사용할 Enterprise Voice 사용자의 사서함에 SIP 주소를 할당합니다.  <br/> |비즈니스용 Skype 서버 관리자  <br/> Exchange 받는 사람 관리자  <br/> |Exchange 2010 또는 최신 서비스 팩의 경우 사용자에 대한 [SIP UM-Enabled 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=268699)  <br/> Exchange 2013의 경우 통합 [메시징을 참조합니다.](https://go.microsoft.com/fwlink/p/?LinkId=266579)  <br/> |
|실행 exchucutil.ps1 실행합니다.  <br/> |Exchange UM 서비스를 실행하는 서버에서 Exchange 관리 셸을 열고 다음을 exchucutil.ps1 스크립트를 실행합니다. <br/> <br/> • 비즈니스용 Skype 서버에 Exchange UM Active Directory 도메인 서비스 개체, 특히 이전 작업에서 만든 SIP 다이얼 플랜을 읽을 수 있는 권한을 부여합니다.  <br/><br/> • Active Directory에서 비즈니스용 Skype 서버 Enterprise Edition 풀 또는 비즈니스용 Skype 서버 사용이 가능한 사용자를 호스팅하는 Standard Edition 서버의 통합 메시징 IP 게이트웨이 개체를 Enterprise Voice.  <br/><br/> • 각 게이트웨이에 대해 Exchange UM 헌트 그룹을 만듭니다. 헌트 그룹 파일럿 식별자는 해당 게이트웨이와 연결된 다이얼 플랜의 이름이 됩니다. 다이얼 플랜이 여러 개 있는 경우 1:1에 매핑해야 합니다.  <br/> |Exchange 조직 관리자  <br/> Exchange 받는 사람 관리자  <br/> |[통합 메시징을 사용하여 Microsoft Exchange에서 ExchUCUtil.ps1](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1) |
|비즈니스용 Skype 서버 다이얼 플랜을 구성합니다.  <br/> |Exchange 2010과 통합하는 경우 Exchange UM Enterprise Voice FQDN(정식 도메인 이름)에 일치하는 이름을 사용하여 새 Enterprise Voice 다이얼 플랜을 만드시다.  <br/> **참고:** 각 UM 다이얼 플랜에 대해 이 작업을 해야 합니다. <br/> Exchange 2010 SP1과 통합하는 경우 적절한 전역/사이트 수준 또는 풀 수준의 풀 수준 다이얼 Enterprise Voice 구성되어 있는지 확인하십시오.  <br/> **참고:** Exchange 2010 SP1과 통합하는 경우 비즈니스용 Skype 서버 다이얼 플랜 및 Exchange UM SIP 다이얼 플랜 이름이 일치할 필요가 없습니다. <br/> |RTCUniversalServerAdmins  <br/> |[비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> |
|Exchange UM 통합 도구를 실행합니다.  <br/> | 비즈니스용 Skype 서버에서 **다음** ocsumutil.exe실행합니다.  <br/>  구독자 액세스를 만들고 연락처 자동 전화 교환 만듭니다. <br/>  Exchange UM 다이얼 Enterprise Voice FQDN과 일치하는 이름의 다이얼 플랜이 있는지 검사합니다. Exchange 2010 SP1 이상을 실행하는 경우 다이얼 플랜 이름이 일치할 필요가 없습니다. 이에 대한 도구 경고를 무시해도 됩니다. <br/>  이 도구는 Active Directory에서 Exchange UM 설정을 검색하고 비즈니스용 Skype 서버 관리자가 연락처 개체를 보고 만들고 편집할 수 있도록 하여 작동합니다. <br/> |RTCUniversalServerAdmins  *및*  RTCUniversalUserAdmins <br/> **중요:** 이 ocsumutil.exe 실행하려면 사용자가 이러한 두 그룹에 모두 속해야 합니다. <br/> **참고:** 연락처 개체를 만들 ocsumutil.exe 새 연락처 개체가 저장되는 Active Directory OU(조직 구성 단위)에 대한 올바른 권한이 있어야 합니다. 이 사용 권한은 **Grant-CsOUPermission** cmdlet을 실행하여 부여할 수 있습니다. 자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서를 참조하십시오. <br/> |[비즈니스 Exchange Server 음성 메일에 대한 통합 메시징 구성](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md) <br/> |
|필요한 경우 다른 구성 Enterprise Voice 수행합니다.  <br/> |서버 또는 사용자에 대해 Enterprise Voice 설정을 아직 구성하지 않은 경우 다음 중 하나 이상을 실행합니다.  <br/> • 배포 및 구성  <br/> PSTN(Public Switched Telephone Network) 게이트웨이 및 중재 서버  <br/> • 음성 정책, PSTN 사용 레코드 및 아웃바운드 통화 경로를 정의합니다.  <br/> • 사용자가 해당 사용자에 대해 Enterprise Voice.  <br/> • 선택적으로 다이얼 플랜을 사용하여 특정 사용자를 구성합니다.  <br/> 다른 구성 단계는 사용하도록 설정하는 Enterprise Voice 따라 요구될 수 있습니다.  <br/> |RTCUniversalServerAdmins  <br/> RTCUniversalUserAdmins  <br/> |다음 섹션의 항목을 참조하세요.  <br/> • [비즈니스용 Skype에서 음성 정책, PSTN](../../deploy/deploy-enterprise-voice/voice-and-pstn.md) 사용 레코드 및 음성 경로 구성 <br/> • [비즈니스용 Skype Enterprise Voice 배포](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) <br/> |
|Exchange Enterprise Voice 사용할 수 있도록 합니다.  <br/> |Exchange UM 서버에서 통합 메시징 사서함 정책이 만들어지며 각 사용자에게 고유한 내선 번호 할당이 지정되어 있는지 확인한 다음 사용자가 통합 메시징을 사용할 수 있도록 합니다.  <br/> |Exchange 받는 사람 관리자  <br/> |Exchange 2010 또는 최신 서비스 팩의 경우 통합 메시징에 대해 사용자 사용을 [참조합니다.](https://go.microsoft.com/fwlink/p/?LinkId=268701)  <br/> Exchange 2013의 경우 통합 [메시징을 참조합니다.](https://go.microsoft.com/fwlink/p/?LinkId=266579)  <br/> |
   




## <a name="see-also"></a>참고 항목

[비즈니스용 Skype의 Exchange 통합 메시징 통합 계획](unified-messaging.md)
