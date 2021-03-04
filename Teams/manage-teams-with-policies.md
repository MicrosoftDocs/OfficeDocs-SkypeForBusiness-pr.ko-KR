---
title: 정책으로 Teams 관리
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: ''
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 368e71820100ba8cfccb28eef63864f47cd8ce85
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421303"
---
# <a name="manage-teams-with-policies"></a>정책으로 Teams 관리

정책은 Teams 관리의 중요한 부분입니다. 이 문서를 사용하여 정책을 사용하여 조직에 혜택을 주는 방법을 탐색합니다.

## <a name="what-you-use-policies-for"></a>정책 사용

정책은 메시징, 모임 및 애플리케이션과 같은 다양한 영역에서 조직에서 많은 작업을 수행하는 데 사용됩니다. 사용자가 팀 채널에서 모임을 예약할 수 있도록 허용하고, 사용자가 보낸 메시지를 편집할 수 있도록 허용하고, 사용자가 Teams 앱 표시줄에 앱을 고정할 수 있는지 여부를 제어할 수 있습니다.

## <a name="how-to-assign-policies"></a>정책을 할당하는 방법

조직에서 수행하려는 방식에 따라 여러 가지 방법으로 정책을 할당할 수 있습니다. Teams 관리 센터에서 과제를 수행하고 볼 수 있습니다.

![그룹 정책 할당 스크린샷.](media/group-policy-assignment.png)

정책 할당에 대한 자세한 내용은 여기를 [클릭하세요.](assign-policies.md)

## <a name="how-to-manage-policies"></a>정책을 관리하는 방법

정책은 Microsoft Teams 관리 센터 또는 [PowerShell을 사용하여 관리됩니다.](https://docs.microsoft.com/microsoftteams/teams-powershell-managing-teams#manage-policies-via-powershell)

예를 들어 앱 설정 정책을 사용하면 사용자가 사용자 지정 앱을 업로드하고, 사용자를 대신하여 앱을 설치하고, Teams 앱 표시줄에 앱을 고정할 수 있도록 설정할 수 있습니다. 이러한 정책은 Teams 관리 센터에 구성됩니다.

![앱 설정 정책 스크린샷.](media/app-setup-policy.png)

또한 모임 정책을 사용하여 전사, 클라우드 녹음 및 IP 오디오/비디오와 같은 Teams 모임에서 오디오 및 비디오 설정을 제어할 수 있습니다.

![모임 정책 스크린샷.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a>교육용 Teams

또한 교육용 [Teams 정책](easy-policy-setup-edu.md) 마법사를 사용하여 학습 환경에 대한 정책을 쉽게 설정하고 관리할 수 있습니다.

![교육용 Teams 정책 마법사의 스크린샷.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a>정책 유형

Microsoft Teams에서 다음 정책을 관리할 수 있습니다.

정책 유형 | 설명
------------|------------
[정책 패키지](manage-policy-packages.md) | Microsoft Teams의 정책 패키지는 조직에서 비슷한 역할을 하는 사용자에게 할당할 수 있는 미리 정의된 정책 및 설정의 컬렉션입니다.
[모임 정책](meeting-policies-in-teams.md) | 모임 정책은 조직의 사용자가 예약한 모임에 대해 모임 참가자에게 사용할 수 있는 기능을 제어하는 데 사용됩니다. 모임 정책에는 다음 토픽이 포함됩니다.<br> - 오디오 및 비디오 정책<br> - 콘텐츠 및 화면 공유 정책<br> - 참가자, 게스트 및 액세스 정책<br> - 일반 정책
[음성 및 통화 정책](voice-and-calling-policies.md)| 음성 및 통화 정책은 긴급 통화, 통화 라우팅 및 발신자 ID와 같은 팀을 통해 이러한 설정을 관리합니다.
[앱 정책](app-policies.md)| 앱 정책은 Microsoft Teams의 애플리케이션을 제어하는 데 사용됩니다. 관리자는 사용자가 설치할 수 있는 앱을 허용하거나 차단하고, 사용자의 Teams 앱 표시줄에 애플리케이션을 고정하고, 사용자를 대신하여 애플리케이션을 설치할 수 있습니다.
[메시징 정책](messaging-policies-in-teams.md)| 메시징 정책은 채팅 및 채널 기능 가용성을 제어합니다.

## <a name="related-topics"></a>관련 항목

* [Microsoft Teams에서 피드백 정책 관리](manage-feedback-policies-in-teams.md)
* [Microsoft Teams에서 팀 정책 관리](teams-policies.md)
* [Microsoft Teams에서 실시간 이벤트 설정](teams-live-events/set-up-for-teams-live-events.md)
* [교육 정책 및 정책 패키지에 대한 팀](policy-packages-edu.md)
