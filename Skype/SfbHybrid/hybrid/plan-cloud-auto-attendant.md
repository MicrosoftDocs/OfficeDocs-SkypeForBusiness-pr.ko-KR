---
title: 클라우드 자동 회의 계획
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype 서버 2019에서 클라우드 자동 전화 전송 사용 개요
ms.openlocfilehash: 50cd9bb8b20e44d750dab68ec6fecb30bd02e203
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918694"
---
# <a name="plan-cloud-auto-attendants"></a>클라우드 자동 전화 교환 계획

Exchange 통합 메시징(Exchange Server 2013 또는 Exchange Server 2016)과 함께 사용되는 자동 전화 교환은 Exchange Server 2019 또는 Exchange Online에서 더 이상 사용할 수 없습니다. 비즈니스용 Skype 서버 2019 구현이 이러한 Exchange 버전 중 하나와 통합되는 경우 전화 시스템과 연결된 온라인 클라우드 음성 기능을 사용해야 합니다. Exchange server 2013 및 2016에 있는 Exchange UM 서비스를 클라우드로 이동하는 Exchange Server 대한 자세한 내용은 비즈니스용 Skype 서버 및 비즈니스용 [Skype](plan-um-migration.md) 서버 마이그레이션 계획을 참조하세요.

이는 자동 전화 연결과 같은 통합 메시징 기능을 사용하고자 하는 경우 비즈니스용 Skype 서버 2019의 하이브리드 구현을 사용하게 다는 의미입니다. 자세한 내용은 비즈니스용 Skype 서버와 [Microsoft 365 또는 Office 365](configure-hybrid-connectivity.md) 간에 하이브리드 연결 구성을 참조하세요.

자동 전화 건은 고객 통화를 수락하고 인사말을 재생하고, 메뉴 옵션을 제공하며, 음성 또는 다이얼 패드를 사용하여 발신자들과 상호 작용하여 통화를 올바른 대상로 라우팅하는 클라우드 서비스입니다. 각 자동 전화 연결에는 Microsoft [](configure-onprem-ra.md)Teams 관리 센터의 자동 전화 연결에 직접 연결될 비즈니스용 Skype 서버 2019 시스템에서 리소스 계정(리소스 계정 구성 참조)이 할당됩니다.  클라우드 [자동 Attendants란?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) 자동 회의란 무엇일지, 그리고 자동 회의에 대해 존재하는 옵션 및 기능에 대한 자세한 내용을 참조하세요.

> [!NOTE]
> 자동 전화 회의에 여러 Microsoft 서비스 번호, 직접 라우팅 번호 또는 하이브리드 번호를 할당할 수 있습니다.

클라우드 자동 전화 응답에 대한 수신 전화는 다음과 같이 여러 경로 중 하나를 사용할 수 있습니다.

![자동 회의 다이어그램](../../SfBServer2019/media/AA-plan-concept.png)

1. 비즈니스용 Skype 서버 2019를 통해
2. 세션 경계 [컨트롤러 및](/MicrosoftTeams/direct-routing-border-controllers.md) [직접 라우팅을 통해](/MicrosoftTeams/direct-routing-plan.md)
3. Microsoft 365 또는 Office 365에 온라인에 있는 번호를 통해

참고:

- [클라우드 자동 전화 교환 설정](/microsoftteams/create-a-phone-system-auto-attendant)
- [수신 전화 자동 응답 및 라우팅](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>요구 사항

다음 요구 사항은 지원되는 토폴로지에서 비즈니스용 Skype 서버 2019를 이미 배포했다고 가정합니다.  요구 사항은 시나리오에 따라 다릅니다.

- 이미 Exchange UM 온라인 또는 프레미스를 사용하고 있으며 비즈니스용 Skype 2019로 업그레이드하는 경우 자동 전화 교환의 구조를 캡처하고 클라우드 자동 전화 교환을 사용하여 클라우드에서 다시 만들어야 합니다. 자세한 내용은 Exchange UM 자동 전화 교환 또는 통화 [큐를 전화 시스템으로 이동을 참조하십시오.](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)

- 클라우드 자동 회의의 새 구성을 위해 리소스 계정 구성에 설명된 [단계를 따르세요.](configure-onprem-ra.md)

위의 요구 사항 외에도 Microsoft 클라우드 자동 전화 접속 서비스에 연결하도록 아래 요구 사항을 구성해야 합니다.

- 하이브리드 연결. 비즈니스용 Skype 서버가 이미 배포되어 있으며, 비즈니스용 Skype 사용자에 대해 클라우드 자동 전화 접속을 사용하도록 설정하려는 경우, 하이브리드 연결이 온라인 환경과 온라인 환경 간에 설정되어 있는지를 확인해야 합니다. 이를 분할 도메인 구성이라고도 합니다.

   자세한 내용은 비즈니스용 Skype 서버와 [Microsoft 365 또는 Office 365](plan-hybrid-connectivity.md) 간의 하이브리드 연결 계획과 비즈니스용 [Skype 서버와 Microsoft 365 또는 Office 365](configure-hybrid-connectivity.md)간의 하이브리드 연결 구성을 참조하세요.

- 자동 전화 번호에 전화 번호를 할당하는 경우 [Office 365 Enterprise E5 라이선스가](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) 필요합니다.
- 각 자동 [](/MicrosoftTeams/manage-resource-accounts.md) 전화 회의에 대해 [](configure-onprem-ra.md) 온라인 리소스 계정 또는온-프레미스 리소스 계정을 만들고 전화 번호와 라이선스를 할당합니다. 

## <a name="migration-and-interoperability"></a>마이그레이션 및 상호 실행성

비즈니스용 Skype 서버 2019 및/또는 Exchange Server 2019를 배포하려는 경우 자동 전화 회의에 대한 지원을 계속할 수 있도록 마이그레이션을 신중하게 계획해야 합니다. 다음 사항에 유의해야 합니다.

- Exchange Server 2019에서 더 이상 Exchange UM 기능을 제공하지 않습니다.
- Exchange 통합 메시징이 사용 중지 모드에 있습니다.
- 비즈니스용 Skype 서버 2019가 Exchange Online UM과 더 이상 통합되지 않습니다.

클라우드 자동 전화 연결은 비즈니스용 Skype 서버 2019, 2015 및 2013을 사용하여 구성할 수 있습니다.

Microsoft는 다음과 같은 마이그레이션 경로를 권장합니다.

- 비즈니스용 Skype 서버 2019로 업그레이드하는 경우 Exchange Server 2013 또는 2016에서 Exchange UM을 사용할 수 있지만 Exchange Server 2019를 사용하는 경우 클라우드 자동 전화 교환으로 업그레이드해야 합니다.

- Exchange Server 2019로 업그레이드하는 경우 이전 버전의 Exchange Server UM for Business Server 음성 메시징을 사용하는 경우 사서함 업그레이드 전에 비즈니스용 Skype 서버 2019로 업그레이드하는 것이 좋습니다.  그렇지 않으면 음성 메시징 기능이 손실됩니다.

마이그레이션 계획에 대한 자세한 내용은 비즈니스용 Skype 서버 계획 및 마이그레이션 [Exchange Server 참조하세요.](plan-um-migration.md)

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>이전에 구현한 Exchange UM 자동 교환 시스템 마이그레이션

현재 Exchange 2013 또는 2016에서 만든 UM 자동 교환 시스템의 클라우드로의 자동 마이그레이션은 지원되지 않습니다. 자동 자동 수행 시스템을 수동으로 다시 만들하려면 다음을 수행해야 합니다.

1. Exchange 관리자 PowerShell 명령을 사용하여 중첩된 자동 전화 교환 및 통화 큐를 포함하여 이전 자동 전화 교환 시스템의 구조를 검토합니다.  
2. 텍스트 음성 음성 스크립트 또는 각 UM 자동 전화 통신 노드와 연결된 기록된 메시지의 복사본을 생성합니다.
3. 개체에 테스트 전화 번호 및 라이선스를 할당하는 등 각 자동 전화 회의 노드에 대한 프레미스 끝점을 만들 수 있습니다. 이제 전화 시스템과 같은 온라인 서비스에서 사용하는온-프레미스 전화 번호 라이선스를 할당할 수 있습니다.
4. Microsoft Teams 및 전화 시스템을 통해 새 클라우드 자동 전화 회의 서비스를 구현합니다. 구현에 [대한 자세한 내용은](configure-onprem-ra.md) 리소스 계정 구성을 참조합니다. 이렇게 하는 경우 텍스트 음성 음성 스크립트 또는 각 UM 자동 전화 통신 노드와 연결된 녹음된 메시지를 업로드합니다.
5. 클라우드 자동 회의의 기능을 테스트합니다.
6. 이전 Exchange UM 자동 전화 교환에 할당된 전화 번호를 새로 만든 기본 클라우드 자동 전화 교환에 다시 할당합니다.

이러한 단계에 대한 자세한 내용은 [Exchange UM 자동](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) 전화 교환 또는 통화 큐를 전화 시스템으로 이동을 참조하세요.

요구 사항을 충족하는 견고한 구조와 고객을 효율적으로 안내하는 스크립트가 있는 경우 리소스 계정 [구성을 진행합니다.](configure-onprem-ra.md)

> [!CAUTION]
> [KB4480742에서](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)설명한 것 처럼 Server 2015에서 만든 Exchange UM 자동 교환을 Server 2019를 실행하는 서버로 이동하는 것은 금지됩니다. 당분간은 동시 사용 모드로 실행되는 비즈니스용 Skype 서버 2015 풀에 유지해야 합니다.

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype Server 및 Exchange Server의 마이그레이션 계획](plan-um-migration.md)

[리소스 계정 구성](configure-onprem-ra.md)

[전화 사용자 인터페이스를 사용하여 사용자 지정 음성 안내 녹음 사용](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[클라우드 자동 전화 교환이란?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[클라우드 자동 전화 교환 설정](/microsoftteams/create-a-phone-system-auto-attendant)

Exchange UM: [수신 전화 자동 응답 및 라우팅](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간의 하이브리드 연결 계획](plan-hybrid-connectivity.md)

[비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간의 하이브리드 연결 구성](configure-hybrid-connectivity.md)

[KB4480742: 연락처 개체를 비즈니스용 Skype 서버 2019로 이동한 후 빠른 통화가 발생하고 "500 서버 내부" 오류와 함께 구독자 액세스 또는 자동 전화 접속에 실패](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
