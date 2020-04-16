---
title: 클라우드 자동 전화 교환 계획
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
description: 비즈니스용 Skype 서버 2019에서 클라우드 자동 전화 교환 사용 개요
ms.openlocfilehash: f0b8018e7a926444e7920ccac31ed3ff4ab5c15f
ms.sourcegitcommit: 477aac9e14fced139ee7dd827942ce35b9769b63
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2020
ms.locfileid: "43510807"
---
# <a name="plan-cloud-auto-attendants"></a>클라우드 자동 전화 교환 계획

Exchange 통합 메시징에 사용 되는 자동 전화 교환 (exchange Server 2013 또는 Exchange Server 2016)은 Exchange Server 2019 또는 Exchange Online에서 더 이상 사용할 수 없습니다. 비즈니스용 Skype 서버 2019이 이러한 Exchange 버전 중 하 나와 통합 된 경우 전화 시스템과 관련 된 온라인 클라우드 음성 기능을 사용 해야 합니다. Exchange server 2013 및 2016의 exchange UM 서비스를 클라우드로 이동 하는 방법에 대 한 자세한 내용은 [비즈니스용 Skype 서버 및 Exchange server 마이그레이션 계획](plan-um-migration.md) 을 참조 하십시오.

이 사실은 자동 전화 교환과 같은 통합 메시징 기능을 사용 하려는 경우 비즈니스용 Skype 서버 2019을 하이브리드 방식으로 구현 하는 것을 의미 합니다. 자세한 내용은 [비즈니스용 Skype 서버 및 Office 365에서 하이브리드 연결 구성을](configure-hybrid-connectivity.md) 참조 하세요.

자동 전화 교환은 고객 통화를 허용 하 고 인사말을 재생 하 고, 메뉴 옵션을 제공 하며, 음성 또는 다이얼 패드를 사용 하는 발신자와 상호 작용 하 여 호출을 올바른 대상으로 라우팅하는 클라우드 서비스입니다. 각 자동 전화 교환에는 Microsoft 팀 관리 센터의 자동 전화 교환에 직접 연결 될 비즈니스용 Skype 서버 2019 시스템에서 *리소스 계정* ( [구성 리소스 계정](configure-onprem-ra.md)참조)이 할당 됩니다. 자동 전화 교환에 대 한 자세한 내용 및 자동 전화 교환에 대 한 옵션 및 기능은 [클라우드 자동 전화 교환 란?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) 를 참조 하세요.

> [!NOTE]
> 자동 전화 교환에 여러 Microsoft 서비스 번호, 직접 라우팅 번호 또는 하이브리드 번호를 할당할 수 있습니다.

클라우드 자동 전화 교환에 대 한 수신 전화는 다음과 같이 여러 경로 중 하나를 사용할 수 있습니다.

![자동 전화 교환에 대 한 다이어그램](../../SfBServer2019/media/AA-plan-concept.png)

1. 비즈니스용 Skype 서버 2019
2. [세션 경계 컨트롤러](/MicrosoftTeams/direct-routing-border-controllers.md) 및 [직접 라우팅](/MicrosoftTeams/direct-routing-plan.md) 통해
3. Office 365에서 온라인으로 홈을 통해 전화를 수신 합니다.

참고:

- [클라우드 자동 전화 교환 설정](/microsoftteams/create-a-phone-system-auto-attendant)
- [수신 전화 자동 응답 및 라우팅](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>요구 사항

다음 요구 사항에 따라 지원 되는 토폴로지에 비즈니스용 Skype 서버 2019이 이미 배포 되어 있다고 가정 합니다.  요구 사항은 시나리오에 따라 달라 집니다.

- 이미 Exchange UM online 또는 온-프레미스를 사용 중이 고 비즈니스용 Skype 2019로 업그레이드 하는 경우 자동 전화 교환의 구조를 캡처하여 클라우드 자동 전화 교환을 사용 하 여 클라우드에서 다시 만들어야 합니다. 자세한 내용은 [EXCHANGE UM 자동 전화 교환 또는 통화 큐를 전화 시스템으로 이동을](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)참조 하세요.

- 클라우드 자동 전화 교환에 대 한 새 구성을 보려면 [Configure resource accounts](configure-onprem-ra.md)에 설명 되어 있는 단계를 따르세요.

위의 요구 사항 외에도 다음 요구 사항을 Microsoft 클라우드 자동 전화 교환 서비스에 연결 하도록 구성 해야 합니다.

- 하이브리드 연결 비즈니스용 Skype 서버를 이미 배포 했으며 온-프레미스 사용자에 대해 클라우드 자동 전화 교환을 사용 하도록 설정 하려면 온-프레미스 환경과 온라인 환경 간에 하이브리드 연결이 설정 되어 있는지 확인 해야 합니다. 이를 분할 도메인 구성 이라고 합니다.

   자세한 내용은 비즈니스용 [Skype 서버 및 office 365의 하이브리드 연결 계획](plan-hybrid-connectivity.md) 및 [비즈니스용 Skype 서버 및 office 365 간의 하이브리드 연결 구성을](configure-hybrid-connectivity.md)참조 하세요.

- 자동 전화 교환에 전화 번호를 할당 하는 경우에는 [Office 365 Enterprise E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) 라이선스가 필요 합니다.
- 각 자동 전화 교환에 대 한 온라인 [리소스 계정](/MicrosoftTeams/manage-resource-accounts.md) 또는 온-프레미스 [리소스 계정을](configure-onprem-ra.md) 만들고 전화 번호 및 라이선스를 할당 합니다. 

## <a name="migration-and-interoperability"></a>마이그레이션 및 상호 운용성

비즈니스용 Skype 서버 2019 및/또는 Exchange Server 2019을 배포 하려는 경우에는 자동 전화 교환에 대 한 지속적인 지원을 위해 마이그레이션을 신중 하 게 계획 해야 합니다. 다음 사항에 유의해야 합니다.

- Exchange 서버 2019에서 더 이상 Exchange UM 기능을 제공 하지 않음
- Exchange 통합 메시징이 만료 모드에 있습니다.
- 비즈니스용 Skype 서버 2019이 더 이상 Exchange Online UM에 통합 되지 않음

클라우드 자동 전화 교환은 비즈니스용 Skype 서버 2019, 2015 및 2013을 사용 하 여 구성할 수 있습니다.

Microsoft는 다음과 같은 마이그레이션 경로를 권장 합니다.

- 비즈니스용 Skype 서버 2019로 업그레이드 하는 경우 exchange Server 2013 또는 2016에서 Exchange UM을 사용할 수 있지만 Exchange Server 2019을 사용 하는 경우에는 클라우드 자동 전화 교환으로 업그레이드 해야 합니다.

- Exchange Server 2019로 업그레이드 하는 경우 비즈니스용 Skype 서버 음성 메시징의 이전 버전의 Exchange Server UM을 사용 하는 경우에는 사서함 업그레이드 전에 비즈니스용 Skype 서버 2019로 업그레이드 하는 것이 좋습니다.  그렇지 않으면 음성 메시징 기능을 잃게 됩니다.

마이그레이션 계획에 대 한 자세한 내용은 [비즈니스용 Skype 서버 및 Exchange server 마이그레이션을 계획](plan-um-migration.md)합니다 .를 참조 하세요.

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>이전에 구현 된 Exchange UM 자동 전화 교환 시스템 마이그레이션

현재 Exchange 2013 또는 2016에서 만든 UM 자동 전화 교환 시스템의 클라우드로의 자동화 된 마이그레이션을 지원 하지 않습니다. 자동 전화 교환 시스템을 수동으로 다시 만들려면 다음을 수행 해야 합니다.

1. Exchange 관리 powershell 명령을 사용 하 여 중첩 된 자동 전화 교환 및 통화 큐를 포함 하 여 이전 자동 전화 교환 시스템의 구조를 검토 합니다.  
2. 각 UM 자동 전화 교환 노드와 연결 되는 텍스트 음성 변환 스크립트 또는 녹음 된 메시지의 복사본을 만듭니다.
3. 테스트 전화 번호 및 개체에 대 한 라이선스 할당을 포함 하 여 각 자동 전화 교환 노드의 온-프레미스 끝점을 만듭니다. 이제 전화 시스템과 같은 온라인 서비스에서 사용 하는 온-프레미스 전화 번호 라이선스를 할당할 수 있습니다.
4. 비즈니스용 Skype 온라인 및 전화 시스템을 사용 하 여 새 클라우드 자동 전화 교환 서비스를 구현 합니다. 구현에 대 한 자세한 내용은 [리소스 계정 구성을](configure-onprem-ra.md) 참조 하십시오. 이 작업을 수행 하는 동안 각 UM 자동 전화 교환 노드와 연결 된 텍스트 음성 변환 스크립트 또는 기록 된 메시지를 업로드 합니다.
5. 클라우드 자동 전화 교환 기능을 테스트 합니다.
6. 이전 Exchange UM 자동 전화 교환에 할당 된 전화 번호를 새로 만든 주 클라우드 자동 전화 교환에 다시 할당 합니다.

이러한 단계에 대 한 자세한 내용은 [EXCHANGE UM 자동 전화 교환 또는 통화 큐를 전화 시스템으로 이동을](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) 참조 하십시오.

## <a name="additional-planning-resources"></a>추가 계획 리소스

[Small business 예-Set up a auto attendant](/microsoftteams/tutorial-org-aa) 는 사용자 요구 사항에 대 한 정보를 수집 하 고, 자동 전화 교환 및 사용자의 구조를 계획 하 고, 메뉴 음성 안내를 작성 하 고, 해당 계획을 팀 관리 센터에서 구현 하는 프로세스를 통해 진행 됩니다. 자습서를 검토 하 고 연습을 사용 하 여 계획을 만듭니다.

사용자의 요구에 맞는 견고한 구조와 고객을 효율적으로 안내 하는 스크립트를 만들려면 [리소스 계정 구성을](configure-onprem-ra.md)계속 진행 합니다.

> [!CAUTION]
> [KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)에서 설명한 것 처럼 서버 2015에서 만든 Exchange UM 자동 전화 교환을 서버 2019을 실행 하는 서버로 이동 하지 않는 것이 좋습니다. 시간에 coexistance 모드에서 실행 되는 비즈니스용 Skype 서버 2015 풀에 해당 기간을 보관 해야 합니다.

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 및 Exchange Server 마이그레이션 계획](plan-um-migration.md)

[리소스 계정 구성](configure-onprem-ra.md)

[전화 사용자 인터페이스를 사용하여 사용자 지정 음성 안내 녹음 사용](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[클라우드 자동 전화 교환이란?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[클라우드 자동 전화 교환 설정](/microsoftteams/create-a-phone-system-auto-attendant)

Exchange UM: [수신 전화 자동 응답 및 라우팅](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[비즈니스용 Skype 서버와 Office 365 간의 하이브리드 연결 플랜](plan-hybrid-connectivity.md)

[비즈니스용 Skype 서버 및 Office 365 간 하이브리드 연결 구성](configure-hybrid-connectivity.md)

[KB4480742: 대화 상대 개체를 비즈니스용 Skype 서버 2019로 이동한 후 구독자 액세스 또는 자동 전화 교환에 대 한 통화가 빠른 사용 및 "500 서버 내부" 오류와 함께 실패 합니다.](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
