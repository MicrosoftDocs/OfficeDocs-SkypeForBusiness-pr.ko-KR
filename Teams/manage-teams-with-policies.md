---
title: 정책을 준수하여 Teams 관리
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Teams 정책에 대해 자세히 알아봅니다.
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: e369403e17136aaec6341e46b4851d18fb778a89
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641869"
---
# <a name="manage-teams-with-policies"></a>정책을 준수하여 Teams 관리

정책은 Teams 관리의 중요한 부분입니다. 이 문서를 사용하여 정책을 사용하여 조직에 혜택을 주는 방법을 탐색합니다.

## <a name="what-you-use-policies-for"></a>정책을 사용하는 항목

정책은 메시징, 모임 및 애플리케이션과 같은 다양한 영역에서 조직에서 많은 작업을 수행하는 데 사용됩니다. 사용자가 팀 채널에서 모임을 예약할 수 있도록 허용하고, 사용자가 보낸 메시지를 편집할 수 있도록 하고, 사용자가 Teams 앱 바에 앱을 고정할 수 있는지 여부를 제어하는 작업을 수행할 수 있습니다.

## <a name="how-to-assign-policies"></a>정책을 할당하는 방법

정책은 조직에서 수행하려는 내용에 따라 여러 가지 방법으로 할당할 수 있습니다. Teams 관리 센터에서 할당을 만들고 볼 수 있습니다.

:::image type="content" source="media/group-policy-assignment.png" alt-text="Teams 그룹 정책 할당의 스크린샷." lightbox="media/group-policy-assignment.png":::

여기에서 정책 할당에 대해 자세히 알아봅니 [다](policy-assignment-overview.md).

> [!NOTE]
> 정책을 할당 취소하려면 정책에 직접 할당된 모든 사용자에 대한 할당을 대량으로 제거할 수 있습니다. 자세한 내용은 [정책 할당 취소를 대량으로](assign-policies-users-and-groups.md#unassign-policies-in-bulk) 읽어보세요.

## <a name="how-to-manage-policies"></a>정책을 관리하는 방법

정책은 Microsoft Teams 관리 센터 또는 [PowerShell을 사용하여](./teams-powershell-managing-teams.md#manage-policies-via-powershell) 관리됩니다.

예를 들어 앱 설정 정책을 사용하면 사용자가 사용자 지정 앱을 업로드하고, 사용자를 대신하여 앱을 설치하고, Teams 앱 모음에 앱을 고정할 수 있습니다. 이러한 정책은 Teams 관리 센터에서 구성됩니다.

:::image type="content" source="media/app-setup-policy.png" alt-text="앱 설정 정책의 스크린샷." lightbox="media/app-setup-policy.png":::

또한 모임 정책을 사용하여 전사, 클라우드 녹음 및 IP 오디오/비디오와 같은 Teams 모임의 오디오 및 비디오 설정을 제어할 수 있습니다.

:::image type="content" source="media/engineering-meeting-policy.png" alt-text="모임 정책의 스크린샷." lightbox="media/engineering-meeting-policy.png":::

### <a name="teams-for-education"></a>교육용 Teams

[교육용 Teams 정책 마법사](easy-policy-setup-edu.md)를 사용하여 학습 환경에 대한 정책을 쉽게 설정하고 관리할 수도 있습니다.

:::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="교육용 Teams 정책 마법사의 스크린샷." lightbox="media/easy-policy-setup-quick-setup.png":::

## <a name="types-of-policies"></a>정책 유형

다음 정책은 Microsoft Teams를 사용하여 관리할 수 있습니다.

정책 유형 | 설명
------------|------------
[정책 패키지](manage-policy-packages.md) | Microsoft Teams의 정책 패키지는 조직에서 비슷한 역할을 가진 사용자에게 할당할 수 있는 미리 정의된 정책 및 설정 모음입니다.
[모임 정책](meeting-policies-overview.md) | 모임 정책은 조직의 사용자가 예약한 모임에 대해 모임 참가자가 사용할 수 있는 기능을 제어하는 데 사용됩니다. 모임 정책에는 다음 항목이 포함됩니다.<br> - 오디오 및 비디오 정책<br> - 콘텐츠 및 화면 공유 정책<br> - 참가자, 게스트 및 액세스 정책<br> - 일반 정책
[음성 및 통화 정책](voice-and-calling-policies.md)| 음성 및 통화 정책은 긴급 통화, 통화 라우팅 및 발신자 ID와 같은 팀을 통해 이러한 설정을 관리합니다.
[앱 정책](app-policies.md)| 앱 정책은 Microsoft Teams에서 애플리케이션을 제어하는 데 사용됩니다. 관리자는 사용자가 설치할 수 있는 앱을 허용하거나 차단하고, 애플리케이션을 사용자의 Teams 앱 바에 고정하고, 사용자를 대신하여 애플리케이션을 설치할 수 있습니다.
[메시징 정책](messaging-policies-in-teams.md)| 메시징 정책은 채팅 및 채널 기능 가용성을 제어합니다.

## <a name="related-topics"></a>관련 주제

* [Teams에서 정책 할당 - 시작](policy-assignment-overview.md)
* [Microsoft Teams에서 피드백 정책 관리](manage-feedback-policies-in-teams.md)
* [Microsoft Teams에서 팀 정책 관리](teams-policies.md)
* [Microsoft Teams에서 실시간 이벤트 설정](teams-live-events/set-up-for-teams-live-events.md)
* [교육용 Teams 정책 및 정책 패키지](policy-packages-edu.md)
