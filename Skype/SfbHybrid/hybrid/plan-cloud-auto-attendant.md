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
ms.localizationpriority: medium
ms.collection: ''
description: 2019에서 클라우드 자동 비즈니스용 Skype 서버 사용 개요
ms.openlocfilehash: 5d28618efc2b02240cdfe3e4c05945f9a6e4b575
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610175"
---
# <a name="plan-cloud-auto-attendants"></a>클라우드 자동 전화 교환 계획

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Exchange 통합 메시징(Exchange Server 2013 또는 Exchange Server 2016)에 사용되는 자동 전화 Exchange Server 2019 또는 Exchange Online. 비즈니스용 Skype 서버 2019의 구현이 이러한 Exchange 버전과 통합되는 경우 2019와 연결된 온라인 Cloud Voice 기능을 전화 시스템. Exchange server 2013 [및](plan-um-migration.md) 2016에 있는 Exchange UM 서비스를 클라우드로 이동하는 비즈니스용 Skype 서버 및 Exchange Server 마이그레이션 계획을 참조하세요.

이는 자동 회의와 같은 통합 메시징 기능을 사용하고자 하는 경우 비즈니스용 Skype 서버 2019의 하이브리드 구현을 하게 됩니다. 자세한 [내용은 Configure hybrid connectivity between 비즈니스용 Skype 서버 and Microsoft 365 or Office 365](configure-hybrid-connectivity.md) for details을 참조합니다.

자동 전화 건은 고객 통화를 수락하고 인사말을 재생하고, 메뉴 옵션을 제공하며, 음성 또는 다이얼 패드를 사용하여 발신자들과 상호 작용하여 통화를 올바른 대상로 라우팅하는 클라우드 서비스입니다. 각 자동 회의에는  비즈니스용 Skype 서버 2019 시스템의 리소스 계정(리소스 계정 구성 참조)이 할당되어 Microsoft Teams 관리 센터의 자동 Microsoft Teams 연결됩니다. [](configure-onprem-ra.md) 자동 [회의란](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) 무엇일까요? 자동 회의에 대한 자세한 내용과 자동 회의에 대한 옵션 및 기능에 대한 자세한 내용을 참조하세요.

> [!NOTE]
> 자동 전화 회의에 여러 Microsoft 서비스 번호, 직접 라우팅 번호 또는 하이브리드 번호를 할당할 수 있습니다.

클라우드 자동 전화 응답에 대한 수신 전화는 다음과 같이 여러 경로 중 하나를 사용할 수 있습니다.

![자동 회의용 다이어그램](../../SfBServer2019/media/AA-plan-concept.png)

1. 2019 비즈니스용 Skype 서버 통해
2. 세션 [경계 컨트롤러 및](/MicrosoftTeams/direct-routing-border-controllers.md) [직접 라우팅을 통해](/MicrosoftTeams/direct-routing-plan.md)
3. 온라인 Microsoft 365 또는 Office 365.

참고:

- [클라우드 자동 전화 교환 설정](/microsoftteams/create-a-phone-system-auto-attendant)
- [수신 전화 자동 응답 및 라우팅](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>요구 사항

다음 요구 사항은 지원되는 토폴로지에서 2019 비즈니스용 Skype 서버 이미 배포했다고 가정합니다.  요구 사항은 시나리오에 따라 다릅니다.

- 이미 Exchange UM 온라인 또는 Exchange 사용 중이고 비즈니스용 Skype 2019로 업그레이드하는 경우 자동 전화 회의의 구조를 캡처한 후 클라우드에서 클라우드에서 다시 만들어야 합니다. 자세한 내용은 [Moving an Exchange UM auto attendant or call queue to 전화 시스템.](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)

- 클라우드 자동 회의의 새 구성을 위해 리소스 계정 구성에 설명된 [단계를 따르세요.](configure-onprem-ra.md)

위의 요구 사항 외에도 Microsoft 클라우드 자동 전화 접속 서비스에 연결하도록 아래 요구 사항을 구성해야 합니다.

- 하이브리드 연결. 이미 배포된 비즈니스용 Skype 서버 클라우드 자동 회의를 사용하도록 설정하려는 경우, 사내 환경과 온라인 환경 간에 하이브리드 연결을 설정해야 합니다. 이를 분할 도메인 구성이라고도 합니다.

   자세한 내용은 비즈니스용 Skype 서버 [](plan-hybrid-connectivity.md) 및 Microsoft 365 또는 Office 365 간의 하이브리드 연결 계획 및 비즈니스용 Skype 서버 및 Microsoft 365 또는 [Office 365.](configure-hybrid-connectivity.md)

- 자동 전화 번호에 전화 번호를 할당하는 경우 [E5](../../SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing.md) 라이선스가 Office 365 Enterprise 합니다.
- 각 자동 전화 [회의에](/MicrosoftTeams/manage-resource-accounts.md) 대해 [](configure-onprem-ra.md) 온라인 리소스 계정 또는온-프레미스 리소스 계정을 만들고 전화 번호와 라이선스를 할당합니다. 

## <a name="migration-and-interoperability"></a>마이그레이션 및 상호 실행성

비즈니스용 Skype 서버 2019 및/또는 Exchange Server 2019를 배포하려는 경우 자동 회의에 대한 지원을 계속할 수 있도록 마이그레이션을 신중하게 계획해야 합니다. 다음 사항에 유의해야 합니다.

- Exchange Server 2019에서는 더 이상 UM Exchange 제공하지 못합니다.
- Exchange 통합 메시징이 사용 중지 모드에 있습니다.
- 비즈니스용 Skype 서버 2019는 더 이상 Exchange Online UM과 통합하지 않습니다.

2019, 2015 및 2013에서 클라우드 자동 비즈니스용 Skype 서버 구성할 수 있습니다.

Microsoft에서는 다음과 같은 마이그레이션 경로를 권장합니다.

- 비즈니스용 Skype 서버 2019로 업그레이드하는 경우 Exchange Server 2013 또는 2016에서 Exchange UM을 사용할 수 있지만 2019년 2019를 사용하는 경우 클라우드 자동 전화 Exchange Server 업그레이드해야 합니다.

- Exchange Server 2019로 업그레이드하는 경우 비즈니스용 Skype 서버 음성 메시징에 이전 버전의 Exchange Server UM을 사용하는 경우 사서함 업그레이드 전에 비즈니스용 Skype 서버 2019로 업그레이드하는 것이 좋습니다.  그렇지 않으면 음성 메시징 기능이 손실됩니다.

마이그레이션 계획에 대한 자세한 내용은 [Plan for 비즈니스용 Skype 서버 and Exchange Server migration을 참조하십시오.](plan-um-migration.md)

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>이전에 구현한 UM Exchange 시스템 마이그레이션

현재는 2013 또는 2016에서 만든 UM 자동 Exchange 클라우드로의 자동 마이그레이션을 지원하지 않습니다. 자동 자동 회의 시스템을 수동으로 다시 만들하려면 다음을 수행해야 합니다.

1. 관리자 Exchange PowerShell 명령을 사용하여 중첩된 자동 전화 걸기 및 통화 큐를 포함하여 이전 자동 전화 전송 시스템의 구조를 검토할 수 있습니다.  
2. 각 UM 자동 전화 통신 노드와 연결된 텍스트 음성 음성 스크립트 또는 녹음된 메시지의 복사본을 생성합니다.
3. 개체에 테스트 전화 번호 및 라이선스를 할당하는 등 각 자동 전화 회의 노드에 대한 프레미스 끝점을 만들 수 있습니다. 이제 사용자 지정과 같은 온라인 서비스에서 사용하는 프레미스 전화 번호 라이선스를 할당할 수 전화 시스템.
4. 새 클라우드 자동 자동 Microsoft Teams 구현 전화 시스템. 구현에 [대한 자세한 내용은 리소스](configure-onprem-ra.md) 계정 구성을 참조합니다. 이렇게 하는 경우 각 UM 자동 전화 통신 노드와 연결된 텍스트 음성 음성 스크립트 또는 녹음된 메시지를 업로드합니다.
5. 클라우드 자동 회의의 기능을 테스트합니다.
6. 이전 Exchange 할당된 전화 번호를 새로 만든 기본 클라우드 자동 전화 Exchange 다시 할당합니다.

이러한 Exchange 대한 자세한 내용은 [전화 시스템 UM](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) 자동 전화 전화 시스템 큐 이동을 참조하세요.

요구 사항을 충족하는 견고한 구조와 고객을 효율적으로 안내하는 스크립트가 있는 경우 리소스 계정 [구성으로 진행합니다.](configure-onprem-ra.md)

> [!CAUTION]
> [KB4480742에서](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)설명한 Exchange Server 2015에서 만든 UM 자동 회의를 Server 2019를 실행하는 서버로 이동하는 것은 금지됩니다. 당분간은 동시 사용 모드로 실행되는 비즈니스용 Skype 서버 풀에 유지해야 합니다.

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype Server 및 Exchange Server의 마이그레이션 계획](plan-um-migration.md)

[리소스 계정 구성](configure-onprem-ra.md)

[전화 사용자 인터페이스를 사용하여 사용자 지정 음성 안내 녹음 사용](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[클라우드 자동 전화 교환이란?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[클라우드 자동 전화 교환 설정](/microsoftteams/create-a-phone-system-auto-attendant)

Exchange UM: [수신 전화 자동](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls) 응답 및 라우팅

[비즈니스용 Skype 서버와 Microsoft 365, 또는 Office 365 간의 하이브리드 연결 플랜](plan-hybrid-connectivity.md)

[비즈니스용 Skype 서버 및 비즈니스용 Skype 서버 또는 Microsoft 365 하이브리드 Office 365](configure-hybrid-connectivity.md)

[KB4480742: 연락처 개체를 비즈니스용 Skype 서버 2019로 이동한 후 빠른 통화로 구독자 액세스 또는 자동 전화 접속에 실패하고 "500 서버 내부" 오류](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)