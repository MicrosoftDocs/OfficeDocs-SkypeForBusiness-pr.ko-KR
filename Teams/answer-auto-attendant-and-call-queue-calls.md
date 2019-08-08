---
title: 팀에서 직접 자동 전화 교환 및 통화 대기열 통화에 응답
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: 클라우드 자동 전화 교환 및 통화 대기열에 대해 설명 하 고 팀에서 이러한 통화에 응답 하는 방법에 대해 설명 합니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5eb58a945f1a5ff06c9f92c9440e783e4df9cde0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241256"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a>팀에서 직접 자동 전화 교환 및 통화 대기열 통화에 응답
===========================================================

팀 사용자는 자신의 팀 클라이언트에서 직접 클라우드 자동 전화 교환 및 통화 대기열에서 전화를 걸고 받을 수 있습니다. 팀 사용자의 경우, 이제 자동 전화 교환 기능을 사용할 수 있으며, 통화 대기열 기능이 미리 보기에 있습니다. 

## <a name="what-are-auto-attendants-and-call-queues"></a>자동 전화 교환 및 통화 대기열 이란?

클라우드 자동 전화 교환 기능을 통해 조직에 전화를 거는 경우 사용자가 직접 교환원 대신 듣는 오디오 파일 및 일련의 음성 메시지가 제공 됩니다. 자동 전화 교환을 통해 발신자는 전화 키패드 (DTMF) 또는 음성 인식 기능을 사용 하 여 사용자를 찾을 수 있습니다.

클라우드 통화 큐에는 사용자가 조직의 전화 번호를 호출할 때 사용 되는 인사말, 통화 대기를 자동으로 전환 하는 기능, 전화를 거는 사용자가 통화를 처리 하기 위해 사용할 수 있는 다음 통화 에이전트 검색 기능 등이 포함 됩니다. 대기 중인 음악 듣기. 조직에 대 한 단일 또는 복수 통화 대기열을 만들 수 있습니다.

## <a name="handling-an-auto-attendant-or-call-queue-call"></a>자동 전화 교환 또는 통화 대기열 통화 처리

사용자는 전화를 받기 전에 자동 전화 교환 또는 통화 대기열에서 걸려오는 전화를 구분할 수 있습니다. 각 통화에는 호출자의 이름 및/또는 번호와 함께 호출자가 연락을 시도한 사람에 대 한 정보가 포함 되어 사용자에 게 호출자의 주소를 지정 하는 데 더 나은 컨텍스트를 제공 하 게 됩니다.

다음 그림에서는 자동 전화 교환 또는 통화 대기열에서 걸려온 통화가 사용자에 게 표시 되는 방식을 보여 줍니다.

![수신 전화 알림 스크린샷](media/answer-auto-attendant-and-call-queue-calls-image1.png)

자동 전화 교환 또는 통화 대기열 전화에 응답 한 후에는 다른 통화와 같은 통화를 처리할 수 &#x2014;,이 경우 사용자는 상대방과 회의를 추가 하거나 다른 사용자에 게 통화를 이전할 수 있습니다. 또한 자동 전화 교환 호출은 사용자의 구성을 기반으로 착신 전환 됩니다.

> [!NOTE] 
> 통화 대기열 호출은 사용자의 구성을 기반으로 착신 전환 되지 않습니다. 에이전트에서 전화를 받을 수 있고 호출자가 예기치 않게 착신 전환 되지 않을 때까지 호출자가 큐에 유지 되도록 하는 것입니다.

## <a name="supported-clients"></a>지원 되는 클라이언트

자동 전화 교환 및 통화 대기열 통화에 대 한 지원은 다음 클라이언트에서 사용할 수 있습니다.

-   Microsoft 팀 Windows 클라이언트 (32 및 64 비트 버전)
-   Microsoft 팀 Mac 클라이언트
-   Microsoft 팀 iPhone 앱
-   Microsoft 팀 Android 앱

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a>Microsoft 팀에 대 한 자동 전화 교환 및 통화 대기열 지원 구성

Microsoft 팀에서 자동 전화 교환 및 통화 대기열 통화를 받으려면 상호 운용성 정책 및 업그레이드 정책을 구성 해야 합니다. [비즈니스용 Skype로 함께 팀을 사용 하는 조직의 마이그레이션 및 상호 운용성](migration-interop-guidance-for-teams-with-skype.md)을 검토 하세요. 자동 전화 교환 및/또는 통화 대기열이 구성 되어 있지 않은 경우이 작업을 수행 하려면 [클라우드 자동 전화 교환 설정](create-a-phone-system-auto-attendant.md) 및 [클라우드 통화 대기열 만들기](create-a-phone-system-call-queue.md)를 참조 하세요.

## <a name="related-topics"></a>관련 항목

-   [Office 365의 전화 시스템 소개](what-is-phone-system-in-office-365.md)
-   [클라우드 통화 대기열 만들기](create-a-phone-system-call-queue.md)
-   [클라우드 자동 전화 교환 이란?](what-are-phone-system-auto-attendants.md)
-   [클라우드 자동 전화 교환 설정](create-a-phone-system-auto-attendant.md)

