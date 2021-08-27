---
title: 클라우드 통화 큐 계획
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
description: 2019에서 클라우드 자동 비즈니스용 Skype 서버 사용하는 방법을 소개합니다.
ms.openlocfilehash: 1dffa2e0b92f9888fc9b24323c7fa638468c8b1b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578172"
---
# <a name="plan-cloud-call-queues"></a>클라우드 통화 큐 계획

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

클라우드 통화 큐는 고객 통화를 수락하고 인사말 메시지를 재생한 다음 미리 구성된 에이전트 목록을 검색하여 이러한 통화를 대기 큐에 두는 서비스입니다. 메일 사용이 가능한 메일 그룹 또는 보안 그룹에서 에이전트 집합을 정의할 수 있습니다. 조직에 통화 큐가 하나 이상일 수 있습니다. 통화 큐는 일반적으로 자동 전화 걸기와 함께 사용됩니다.

또한 클라우드 통화 큐는 다음을 제공할 수 있습니다.

- 음악 대기 중일 때
- 통화 큐 최대 크기, 시간 제한 및 통화 처리 옵션에 대한 사용자 지정된 설정

각 통화 큐에는  비즈니스용 Skype 서버 Microsoft Teams [](configure-onprem-ra.md)관리 센터의 통화 큐에 직접 연결될 리소스 계정(비즈니스용 Skype 서버 계정 구성 참조)이 할당됩니다. 통화 [큐의](/MicrosoftTeams/create-a-phone-system-call-queue) 기능과 통화 큐에 대한 옵션 및 기능에 대한 자세한 내용은 클라우드 통화 큐 만들기를 참조하세요.

> [!NOTE]
> 여러 전화 번호를 통화 큐에 할당할 수 있지만 Microsoft 서비스 번호, 직접 라우팅 번호 또는 하이브리드 번호로 지정해야 합니다.

## <a name="requirements"></a>요구 사항

다음 요구 사항은 지원되는 토폴로지에서 2019 비즈니스용 Skype 서버 이미 배포했다고 가정합니다.  요구 사항은 시나리오에 따라 다릅니다.

- 클라우드 통화 큐의 새 구성을 확인하려면 리소스 계정 구성에 설명된 [단계를 따르세요.](configure-onprem-ra.md) 2019년 8월에 온라인 또는 2019에서 리소스 계정을 만들어야 비즈니스용 Skype 서버 전화 번호를 통화 큐와 연결해야 할 수도 있습니다.

위의 요구 사항 외에도 Microsoft 클라우드 통화 큐 서비스에 연결하도록 아래 요구 사항을 구성해야 합니다.

- 하이브리드 연결. 이미 배포된 비즈니스용 Skype 서버 클라우드 통화 큐를 사용하도록 설정하려는 경우, 하이브리드 연결이 프레미스 환경과 온라인 환경 간에 설정되어 있는지 확인해야 합니다. 이를 분할 도메인 구성이라고도 합니다.

   자세한 내용은 비즈니스용 Skype 서버 [](plan-hybrid-connectivity.md) 및 Microsoft 365 또는 Office 365 간의 하이브리드 연결 계획 및 비즈니스용 Skype 서버 및 Microsoft 365 또는 [Office 365.](configure-hybrid-connectivity.md)

- 리소스 계정에 전화 번호를 할당하는 경우 이제 가상 사용자 라이선스를 무료로 사용할 전화 시스템 있습니다. 이렇게 하면 전화 시스템 전화 번호에 대한 여러 기능이 제공될 수 있으며, 자동 전화 걸기 및 통화 큐 기능을 만들 수 있습니다.

- 각 통화 큐에 대해 프레미스 [리소스](configure-onprem-ra.md) 계정을 만들고 필요한 경우 라이선스 및 전화 번호를 할당합니다.  

요구 사항을 충족하는 견고한 구조와 고객을 효율적으로 안내하는 스크립트가 있는 경우 리소스 계정 [구성으로 진행합니다.](configure-onprem-ra.md)

## <a name="see-also"></a>참고 항목

[리소스 계정 구성](configure-onprem-ra.md)

[전화 사용자 인터페이스를 사용하여 사용자 지정 음성 안내 녹음 사용](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[클라우드 자동 전화 교환이란?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[클라우드 자동 전화 교환 설정](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[비즈니스용 Skype 서버와 Microsoft 365, 또는 Office 365 간의 하이브리드 연결 플랜](plan-hybrid-connectivity.md)

[비즈니스용 Skype 서버 및 비즈니스용 Skype 서버 또는 Microsoft 365 하이브리드 Office 365](configure-hybrid-connectivity.md)

[Microsoft Teams에서 리소스 계정 관리](/MicrosoftTeams/manage-resource-accounts)