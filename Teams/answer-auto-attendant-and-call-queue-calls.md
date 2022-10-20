---
title: 자동 전화 교환 및 통화 큐 통화에 응답
ms.reviewer: colongma
author: DaniEASmith
ms.author: danismith
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: 클라우드 자동 전화 교환 및 통화 큐에 대해 설명하고 Teams에서 이러한 통화에 응답하는 방법을 설명합니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1653f1a994da168126c06d10950c7db8e22e37c6
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614201"
---
# <a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>자동 전화 교환에 응답하고 Teams에서 직접 큐에 전화 걸기

Teams 사용자는 클라우드 자동 전화 교환에서 전화를 받고 응답하고 Teams 클라이언트에서 직접 큐를 호출할 수 있습니다.

## <a name="what-are-auto-attendants-and-call-queues"></a>자동 전화 교환 및 통화 큐란?

클라우드 자동 전화 교환은 일련의 음성 프롬프트 또는 발신자가 조직에 전화할 때 휴먼 운영자 대신 듣는 오디오 파일을 제공합니다. 자동 전화 교환을 사용하면 발신자가 메뉴 시스템을 통해 이동하거나, 전화를 걸거나, 음성 인식을 사용하여 전화 키패드(DTMF) 또는 음성 입력을 사용하여 사용자를 찾을 수 있습니다.

클라우드 통화 큐에는 누군가가 조직의 전화 번호로 전화를 걸 때 사용되는 인사말, 자동으로 통화를 보류할 수 있는 기능, 통화하는 사용자가 대기 중인 음악을 수신하는 동안 통화를 처리할 수 있는 다음 통화 에이전트를 검색하는 기능이 포함됩니다. 조직에 대한 단일 또는 여러 통화 큐를 만들 수 있습니다.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>자동 전화 교환 또는 통화 큐 호출 처리

사용자는 통화에 응답하기 전에 자동 전화 교환 또는 통화 큐에서 수신 전화를 구분할 수 있습니다. 호출자의 이름 및/또는 번호와 함께 각 호출에는 호출자가 도달하려는 사용자에 대한 정보가 포함되어 사용자에게 호출자 주소를 지정하기 위한 더 나은 컨텍스트를 제공합니다.

다음 그림에서는 자동 전화 교환 또는 통화 큐에서 들어오는 호출이 사용자에게 표시되는 방법을 보여 줍니다.

![들어오는 통화 알림의 스크린샷.](media/answer-auto-attendant-and-call-queue-calls-image1.png)

자동 전화 교환 또는 통화 큐 호출이 응답되면 사용자는 다른 사용자에 추가하거나 전화 회의를 하거나 다른 당사자에게 통화를 전송할 수 &#x2014; 다른 통화와 같이 통화를 처리할 수 있습니다. 또한 자동 전화 교환 호출은 사용자의 구성에 따라 전달됩니다.

> [!NOTE] 
> 통화 큐 호출은 사용자의 통화 응답 규칙 구성에 따라 전달되지 않습니다. 이는 에이전트가 통화에 응답할 수 있고 호출자가 예기치 않게 전달되지 않을 때까지 호출자가 큐에 남아 있도록 하기 위한 것입니다.
>
> 통화 큐에서 전화를 받는 사용자는 PSTN에서 제공되거나 호출자의 번호가 대상 사용자의 로컬 팀의 클라이언트 연락처와 일치하는 경우에만 호출자의 이름이 표시됩니다.
>
> 에이전트는 통화 큐 호출에 대한 부재 중 통화 또는 음성 메일에 대한 알림을 받지 않습니다.

## <a name="supported-clients"></a>지원되는 클라이언트

자동 전화 교환 및 통화 큐 호출에 대한 지원은 다음 클라이언트에서 사용할 수 있습니다.

-    Microsoft Teams Windows 클라이언트(32비트 및 64비트 버전)
-    Microsoft Teams Mac 클라이언트
-    Microsoft Teams iPhone 앱
-    Microsoft Teams Android 앱

Teams 클라이언트는 [Teams만의 공존 모드](/microsoftteams/setting-your-coexistence-and-upgrade-settings)에서만 지원됩니다.

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Microsoft Teams에 대한 자동 전화 교환 및 통화 큐 지원 구성

Microsoft Teams에서 자동 전화 교환 및 통화 큐 호출을 받으려면 상호 운용성 정책 및 업그레이드 정책을 구성해야 합니다. [비즈니스용 Skype 함께 Teams를 사용하는 조직의 마이그레이션 및 상호 운용성을](migration-interop-guidance-for-teams-with-skype.md) 검토하세요. 자동 전화 교환 및/또는 통화 큐가 구성되어 있지 않고 이렇게 하려면 [클라우드 자동 전화 교환 설정](create-a-phone-system-auto-attendant.md) 및 [클라우드 호출 큐 만들기를](create-a-phone-system-call-queue.md) 참조하세요.

## <a name="known-issues"></a>알려진 문제

통화 큐 에이전트가 모바일 디바이스에서 전화를 받으면 디바이스가 잠겨 있는 경우 통화가 보류될 수 있습니다. 사용자는 먼저 디바이스의 잠금을 해제한 다음 통화에 응답해야 합니다.


## <a name="related-topics"></a>관련 주제

[클라우드 통화 큐 만들기](create-a-phone-system-call-queue.md)

[클라우드 자동 전화 교환이란?](what-are-phone-system-auto-attendants.md)

[클라우드 자동 전화 교환 설정](create-a-phone-system-auto-attendant.md)

