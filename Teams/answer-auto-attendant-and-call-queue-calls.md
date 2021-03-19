---
title: 자동 참석자 응답 및 큐 호출
ms.reviewer: colongma
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Cloud 자동 참석자 및 호출 큐를 설명하고 Teams에서 이러한 호출에 응답하는 방법을 설명합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cca068ab1194a48eb775550e4bf3f99826d82d2a
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874668"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>자동 전화 교환에 응답하고 Teams에서 직접 큐에 전화 걸기
===========================================================

Teams 사용자는 Cloud 자동 참석자로부터 전화를 받고 응답하고 Teams 클라이언트에서 직접 큐를 호출할 수 있습니다.

## <a name="what-are-auto-attendants-and-call-queues"></a>자동 참석자 및 호출 큐란?

클라우드 자동 참석자는 조직에 전화를 걸 때 사용자 연산자 대신 발신자가 듣는 일련의 음성 프롬프트 또는 오디오 파일을 제공합니다. 자동 참석자는 음성 인식을 사용하여 전화 키패드(DTMF) 또는 음성 입력을 사용하여 발신자가 메뉴 시스템을 이동하거나, 전화를 걸거나, 사용자를 찾을 수 있습니다.

클라우드 호출 큐에는 다른 사용자가 조직의 전화 번호로 전화를 걸 때 사용되는 인사말, 자동으로 통화를 보류할 수 있는 능력, 통화 중인 사용자가 대기 중이면서 통화를 처리하기 위해 사용할 수 있는 다음 통화 에이전트를 검색하는 기능을 포함합니다. 조직에 대해 단일 또는 여러 개의 호출 큐를 만들 수 있습니다.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>자동 참석자 또는 호출 큐 호출 처리

사용자는 전화에 응답하기 전에 자동 참석자 또는 통화 큐에서 들어오는 호출을 차별화할 수 있습니다. 발신자 이름 및/또는 수와 함께 각 호출에는 발신자에 도달하려는 사람에 대한 정보가 포함되어 사용자에게 발신자 주소를 지정하기 위한 더 나은 컨텍스트를 제공합니다.

다음 그림에서는 자동 참석자 또는 통화 큐에서 들어오는 호출이 사용자에게 어떻게 나타나는지 보여 주며,

![들어오는 통화 알림 스크린샷](media/answer-auto-attendant-and-call-queue-calls-image1.png)

자동 참석자 또는 통화 큐 호출에 응답하면 사용자가 다른 사용자에서 추가 또는 회의를 추가하거나 다른 &#x2014; 다른 통화와 같이 통화를 처리 할 수 있습니다. 또한 사용자의 구성에 따라 자동 참석자 호출이 전달됩니다.

> [!NOTE] 
> 호출 큐 호출은 사용자의 구성에 따라 전달되지 않습니다. 이는 에이전트가 호출에 응답할 수 있으며 발신자는 예기치 않게 전달되지 않는 때까지 발신자는 큐에 남아 있도록 합니다.

> 에이전트는 통화 큐 호출에 대한 부재 중 전화 또는 음성 메일에 대해 알림을 들이지 않습니다.

## <a name="supported-clients"></a>지원되는 클라이언트

자동 참석자 및 호출 큐 호출에 대한 지원은 다음 클라이언트에서 사용할 수 있습니다.

-    Microsoft Teams Windows 클라이언트(32비트 및 64비트 버전)
-    Microsoft Teams Mac 클라이언트
-    Microsoft Teams iPhone 앱
-    Microsoft Teams Android 앱

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Microsoft Teams에 대한 자동 참석자 및 호출 큐 지원 구성

Microsoft Teams에서 자동 참석을 수신하고 큐 호출을 수신하려면 상호 운영성 정책 및 업그레이드 정책을 구성해야 합니다. 비즈니스용 Skype와 함께 Teams를 사용하는 조직의 마이그레이션 및 상호 [연동성을 검토하세요.](migration-interop-guidance-for-teams-with-skype.md) 자동 참석자 및/또는 호출 큐가 구성되지 않은 경우 클라우드 [](create-a-phone-system-auto-attendant.md) 자동 참석자 설정 및 클라우드 호출 큐 만들기를 [참조합니다.](create-a-phone-system-call-queue.md)

## <a name="known-issues"></a>알려진 문제

통화 큐 에이전트가 모바일 디바이스에서 전화를 받으면 디바이스가 잠겨 있는 경우 통화가 보류될 수 있습니다. 사용자는 먼저 디바이스의 잠금을 해제한 다음 통화에 응답해야 합니다.


## <a name="related-topics"></a>관련 주제

-    [Microsoft 365 또는 Office 365의 전화 시스템](what-is-phone-system-in-office-365.md)
-    [클라우드 통화 큐 만들기](create-a-phone-system-call-queue.md)
-    [클라우드 자동 전화 교환이란?](what-are-phone-system-auto-attendants.md)
-    [클라우드 자동 전화 교환 설정](create-a-phone-system-auto-attendant.md)

