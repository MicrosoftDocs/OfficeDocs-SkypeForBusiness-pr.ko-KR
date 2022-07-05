---
title: 클라우드 호출 큐 계획
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
description: 비즈니스용 Skype 서버 2019에서 클라우드 자동 전화 교환을 사용하는 방법에 대한 개요입니다.
ms.openlocfilehash: df8013a4abc2029d585032b3d0bce810175e04f4
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615424"
---
# <a name="plan-cloud-call-queues"></a>클라우드 통화 큐 계획

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

클라우드 통화 큐는 고객 통화를 수락하고, 인사말 메시지를 재생한 다음, 미리 구성된 에이전트 목록을 검색하여 이러한 호출에 응답하는 동안 대기 큐에 이러한 호출을 배치하는 서비스입니다. 메일 사용 메일 그룹 또는 보안 그룹에서 에이전트 집합을 정의할 수 있습니다. 조직에는 하나 이상의 통화 큐가 있을 수 있습니다. 통화 큐는 일반적으로 자동 전화 교환과 함께 사용됩니다.

또한 클라우드 호출 큐는 다음을 제공할 수 있습니다.

- 발신자가 대기 중인 동안 음악
- 통화 큐 최대 크기, 시간 제한 및 통화 처리 옵션에 대한 사용자 지정된 설정

각 통화 큐에는 Microsoft Teams 관리 센터의 통화 큐에 직접 연결되는 비즈니스용 Skype 서버 2019 시스템의 **리소스 계정**([리소스 계정 구성](configure-onprem-ra.md) 참조)이 할당됩니다. 통화 큐의 내용과 [통화 큐](/MicrosoftTeams/create-a-phone-system-call-queue) 에 대해 존재하는 옵션 및 기능에 대한 자세한 내용은 클라우드 호출 큐 만들기를 참조하세요.

> [!NOTE]
> 통화 큐에 여러 전화 번호를 할당할 수 있지만 Microsoft 서비스 번호, 직접 라우팅 번호 또는 하이브리드 번호여야 합니다.

## <a name="requirements"></a>요구 사항

다음 요구 사항은 지원되는 토폴로지에서 이미 비즈니스용 Skype 서버 2019를 배포했다고 가정합니다.  요구 사항은 시나리오에 따라 달라집니다.

- 클라우드 호출 큐의 새 구성의 경우 [리소스 계정 구성](configure-onprem-ra.md)에 설명된 단계를 수행합니다. 온라인 또는 비즈니스용 Skype 서버 2019에서 리소스 계정을 만들어야 하며 전화 번호를 통화 큐에 연결해야 할 수도 있습니다.

위의 요구 사항 외에도 Microsoft 클라우드 호출 큐 서비스에 연결하도록 아래 요구 사항을 구성해야 합니다.

- 하이브리드 연결. 이미 비즈니스용 Skype 서버 배포했으며 온-프레미스 사용자에 대해 클라우드 호출 큐를 사용하도록 설정하려는 경우 온-프레미스 환경과 온라인 환경 간에 하이브리드 연결이 설정되어 있는지 확인해야 합니다. 이를 분할 도메인 구성이라고도 합니다.

   자세한 내용은 [비즈니스용 Skype 서버 및 Microsoft 365 간의 하이브리드 연결 계획 또는 Office 365](plan-hybrid-connectivity.md) 및 [비즈니스용 Skype 서버 및 Microsoft 365 또는 Office 365 간의 하이브리드 연결 구성](configure-hybrid-connectivity.md)을 참조하세요.

- 리소스 계정에 전화 번호를 할당하는 경우 이제 비용 없는 **Microsoft Teams 전화 Resource Account** 라이선스를 사용할 수 있습니다. 이렇게 하면 조직 수준에서 전화 번호에 전화 시스템 기능을 제공하고 자동 전화 교환 및 통화 큐 기능을 만들 수 있습니다.

- 각 통화 큐에 대한 온-프레미스 [리소스 계정을](configure-onprem-ra.md) 만들고 필요한 경우 라이선스 및 전화 번호를 할당합니다.  

요구 사항을 충족하는 견고한 구조와 고객을 효율적으로 안내하는 스크립트가 있는 경우  [리소스 계정 구성](configure-onprem-ra.md)을 진행합니다.

## <a name="see-also"></a>참고 항목

[리소스 계정 구성](configure-onprem-ra.md)

[전화 사용자 인터페이스를 사용하여 사용자 지정 음성 안내 녹음 사용](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[클라우드 자동 전화 교환이란?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[클라우드 자동 전화 교환 설정](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[비즈니스용 Skype 서버와 Microsoft 365, 또는 Office 365 간의 하이브리드 연결 플랜](plan-hybrid-connectivity.md)

[비즈니스용 Skype 서버 Microsoft 365 또는 Office 365 간의 하이브리드 연결 구성](configure-hybrid-connectivity.md)

[Microsoft Teams에서 리소스 계정 관리](/MicrosoftTeams/manage-resource-accounts)