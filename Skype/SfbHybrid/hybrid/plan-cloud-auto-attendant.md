---
title: 클라우드 자동 전화 교환 계획
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 비즈니스용 Skype 서버 2019에서 클라우드 자동 전화 교환 사용 개요
ms.openlocfilehash: 635d9c6548ba807153876d63ad228f69646e93c8
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2019
ms.locfileid: "36207036"
---
# <a name="plan-cloud-auto-attendants"></a>클라우드 자동 전화 교환 계획

Exchange 통합 메시징에 사용 되는 자동 전화 교환 (Exchange Server 2013 또는 Exchange Server 2016)을 Exchange Server 2019 또는 Exchange Online에서 더 이상 사용할 수 없습니다. 비즈니스용 Skype 서버 2019이 이러한 Exchange 버전 중 하 나와 통합 된 경우에는 전화 시스템과 관련 된 온라인 클라우드 음성 기능을 사용 해야 합니다. Exchange server 2013 및 2016의 exchange UM 서비스를 클라우드로 이동 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버 및 Exchange server 마이그레이션 계획](plan-um-migration.md) 을 참조 하세요.

이것은 자동 전화 교환 같은 통합 메시징 기능을 사용 하려는 경우 비즈니스용 Skype 서버 2019을 하이브리드 구현 하는 것입니다. 자세한 내용은 [비즈니스용 Skype 서버 및 Office 365에서 하이브리드 연결 구성을](configure-hybrid-connectivity.md) 참조 하세요.

자동 전화 교환은 고객 전화를 받고, 인사말을 재생 하 고, 메뉴 옵션을 제공 하 고, 음성 또는 다이얼 패드를 사용 하는 호출자와 상호 작용 하 여 전화를 올바른 목적지로 라우팅하는 클라우드 서비스입니다. Microsoft 팀 관리 센터의 자동 전화 교환에 직접 연결 되는 비즈니스용 Skype Server 2019 시스템에서 각 자동 전화 교환에는 **리소스 계정** ([리소스 계정 구성](configure-onprem-ra.md)참조)이 할당 됩니다. 자동 전화 교환에 대 한 자세한 내용과 자동 전화 교환에 대 한 옵션 및 기능에 대 한 자세한 내용은 [클라우드 자동 전화 교환을](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) 참조 하세요.

> [!NOTE]
> 여러 개의 Microsoft 서비스 번호 또는 하이브리드 번호를 자동 전화 교환에 할당할 수 있습니다.

클라우드 자동 전화 교환으로 들어오는 호출은 다음과 같이 여러 경로 중 하나를 사용할 수 있습니다.

![자동 전화 교환 다이어그램](../../SfBServer2019/media/AA-plan-concept.png)

1. 비즈니스용 Skype 서버 2019을 통해
2. [세션 경계 컨트롤러](/MicrosoftTeams/direct-routing-border-controllers.md) 및 [직접 라우팅](/MicrosoftTeams/direct-routing-plan.md) 통해
3. Office 365에서 온라인으로 홈을 통해 전화를 나눌 수 있습니다.

또한 다음을 참조 하세요.

- [클라우드 자동 전화 교환 설정](/microsoftteams/create-a-phone-system-auto-attendant)
- [자동으로 수신 전화 응답 및 라우팅](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>요구 사항

다음 요구 사항은 지원 되는 토폴로지에서 비즈니스용 Skype 서버 2019이 이미 배포 되어 있다고 가정 합니다.  요구 사항은 시나리오에 따라 달라 집니다.

- 이미 Exchange UM online 또는 온-프레미스를 사용 하 고 있고 비즈니스용 Skype 2019으로 업그레이드 한 경우 자동 전화 교환의 구조를 캡처하여 클라우드 자동 전화 교환을 사용 하 여 클라우드에서 다시 만들어야 합니다. 자세한 내용은 [EXCHANGE UM 자동 전화 교환 또는 통화 대기열을 전화 시스템으로 이동](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)을 참조 하세요.

- 클라우드 자동 전화 교환에 대 한 새로운 구성을 보려면 [리소스 계정 구성](configure-onprem-ra.md)에 설명 된 단계를 따릅니다.

위의 요구 사항 외에도 다음 요구 사항을 Microsoft 클라우드 자동 전화 교환 서비스에 연결 하도록 구성 해야 합니다.

- 하이브리드 연결. 비즈니스용 Skype 서버를 이미 배포 하 고 온-프레미스 사용자에 대해 클라우드 자동 전화 교환을 사용 하려면 온-프레미스 및 온라인 환경 간에 하이브리드 연결이 설정 되어 있는지 확인 해야 합니다. 이를 도메인 분할 구성이 라고도 합니다.

   자세한 내용은 비즈니스용 [Skype 서버 및 office 365 하이브리드 연결 계획](plan-hybrid-connectivity.md) 을 참조 하 고 비즈니스용 [Skype 서버와 office 365의 하이브리드 연결을 구성](configure-hybrid-connectivity.md)합니다.

- 자동 전화 교환에 전화 번호를 할당 하는 경우에는 [Office 365 Enterprise E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing) 라이선스가 필요 합니다.
- 각 자동 전화 교환에 대해 온라인 [리소스 계정](/MicrosoftTeams/manage-resource-accounts.md) 또는 온-프레미스 [리소스 계정을](configure-onprem-ra.md)만들고 전화 번호와 라이선스를 할당 합니다. 

## <a name="migration-and-interoperability"></a>마이그레이션 및 상호 운용성

비즈니스용 Skype 서버 2019 및/또는 Exchange Server 2019을 배포 하려는 경우, 자동 전화 교환을 계속 지원 하도록 마이그레이션을 신중 하 게 계획 해야 합니다. 다음 사항에 유의 하세요.

- Exchange Server 2019에서 더 이상 Exchange UM 기능을 제공 하지 않음
- Exchange 통합 메시징이 만료 모드입니다.
- 비즈니스용 Skype 서버 2019이 더 이상 Exchange Online UM과 통합 되지 않음

클라우드 자동 전화 교환는 비즈니스용 Skype 서버 2019, 2015 및 2013으로 구성할 수 있습니다.

Microsoft는 다음 마이그레이션 경로를 권장 합니다.

- 비즈니스용 Skype 서버 2019으로 업그레이드 하는 경우 exchange Server 2013 또는 2016에서 Exchange UM을 사용할 수 있지만 Exchange Server 2019을 사용 하는 경우에는 클라우드 자동 전화 교환으로 업그레이드 해야 합니다.

- Exchange Server 2019으로 업그레이드 하는 경우 비즈니스용 Skype Server voice messaging 용 Exchange Server UM의 이전 버전을 사용 하는 경우 사서함 업그레이드 전에 비즈니스용 Skype Server 2019으로 업그레이드 하는 것이 좋습니다.  그렇지 않으면 음성 메시지 기능이 손실 됩니다.

마이그레이션 계획에 대 한 자세한 내용은 비즈니스용 [Skype 서버 및 Exchange server 마이그레이션 계획](plan-um-migration.md)을 참조 하세요.

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>이전에 구현 된 Exchange UM 자동 전화 교환 시스템 마이그레이션

현재는 Exchange 2013 또는 2016에서 만든 UM 자동 전화 교환 시스템의 클라우드로 자동화 된 마이그레이션을 지원 하지 않습니다. 자동 전화 교환 시스템을 수동으로 다시 만들려면 다음이 필요 합니다.

1. Exchange 관리 powershell 명령을 사용 하 여 중첩 된 자동 전화 교환 및 통화 대기열을 포함 하 여 이전 자동 교환 시스템의 구조를 검토 합니다.  
2. 각 UM 자동 전화 교환 노드와 연결 된 텍스트 음성 변환 스크립트 또는 기록 된 메시지의 복사본을 만듭니다.
3. 테스트 전화 번호 및 개체에 대 한 라이선스 할당을 포함 하 여 각 자동 전화 교환 노드에 대 한 온-프레미스 끝점을 만듭니다. 이제 전화 시스템 같은 온라인 서비스에서 사용 하는 온-프레미스 전화 번호 라이선스를 할당할 수 있습니다.
4. 비즈니스용 Skype Online 및 전화 시스템을 사용 하 여 새 클라우드 자동 전화 교환 서비스를 구현 합니다. 자세한 내용은 구현 세부 정보에 대 한 [리소스 계정 구성을](configure-onprem-ra.md) 참조 하세요. 이 작업을 수행할 때 각 UM 자동 전화 교환 노드와 연결 된 텍스트 음성 변환 스크립트 또는 기록 된 메시지를 업로드 합니다.
5. 클라우드 자동 전화 교환의 기능을 테스트 합니다.
6. 이전 Exchange UM 자동 전화 교환에 할당 된 전화 번호를 새로 만든 주 클라우드 자동 전화 교환에 다시 할당 합니다.

이러한 단계에 대 한 자세한 내용은 [EXCHANGE UM 자동 전화 교환 또는 통화 대기열을 전화 시스템으로 이동을](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system) 참조 하세요.

## <a name="additional-planning-resources"></a>추가 계획 리소스

사용자 요구에 대 한 정보를 수집 하는 프로세스, 자동 전화 교환 및 사용자의 구조 계획, 메뉴 프롬프트를 작성 하는 등의 간단한 비즈니스와 같은 자습서에서 [자동 전화 교환을 설정](/microsoftteams/tutorial-org-aa) 하면 팀 관리 센터에서 계획을 구현 합니다. 자습서를 검토 하 고 연습을 사용 하 여 계획을 만듭니다.

사용자의 요구에 맞는 솔리드 구조와 고객을 효율적으로 안내 하는 스크립트를 사용 하는 경우 [리소스 계정 구성을](configure-onprem-ra.md)진행 합니다.

> [!CAUTION]
> [KB4480742](https://support.microsoft.com/en-us/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)에서 설명한 대로 서버 2015에서 만든 Exchange UM 자동 전화 교환을 서버 2019를 실행 하는 서버로 이동 하지 않는 것이 좋습니다. 시간이 coexistance 모드로 실행 되는 비즈니스용 Skype Server 2015 풀에 보관 해야 합니다.

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 및 Exchange Server 마이그레이션 계획](plan-um-migration.md)

[자원 계정 구성](configure-onprem-ra.md)

[전화 사용자 인터페이스를 사용 하 여 사용자 지정 음성 안내 기록 사용](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[클라우드 자동 전화 교환 이란?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[클라우드 자동 전화 교환 설정](/microsoftteams/create-a-phone-system-auto-attendant)

Exchange UM: [자동으로 수신 전화 응답 및 라우팅](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[비즈니스용 Skype 서버와 Office 365 하이브리드 연결 계획](plan-hybrid-connectivity.md)

[비즈니스용 Skype 서버와 Office 365 하이브리드 연결 구성](configure-hybrid-connectivity.md)

[KB4480742: 연락처 개체를 비즈니스용 Skype Server 2019로 이동한 후 구독자 액세스 또는 자동 전화 교환에 대 한 빠른 사용량이 나 "500 Server Internal" 오류가 발생 함](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
