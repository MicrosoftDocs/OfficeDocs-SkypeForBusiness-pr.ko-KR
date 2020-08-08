---
title: Microsoft 팀과 통신 준수
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Microsoft 팀 관점에서의 참가자 위험 솔루션 집합의 일부인 통신 준수에 대해 자세히 알아보세요 (이는 M365 통신 준수 기능의 일부).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a8fa1bcc7190050fd06c15717aebf8648f94b090
ms.sourcegitcommit: 8816b58e175031cb0a71e0d0e89e447a7b83a760
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597152"
---
# <a name="communication-compliance-with-microsoft-teams"></a>Microsoft 팀과 통신 준수

통신 준수는 조직의 부적절 한 메시지를 감지 하 고, 캡처하고, 작동 하 여 통신 위험을 최소화 하는 Microsoft 365의 참가자 위험 솔루션입니다.

Microsoft 팀의 경우 통신 준수는 팀 채널 또는 1:1 및 그룹 채팅에서 [다음 유형의](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) 부적절 한 콘텐츠를 식별 하는 데 도움이 됩니다.

- 비속어, 비속어 및 희롱 language
- 성인용, racy 및 gory 이미지
- 중요 한 정보 공유

>[!IMPORTANT]
>개인 Microsoft 팀 채널은 통신 준수에서 지원 되지 않습니다. 게스트 사용자가 팀에 게 보낸 채팅 통신은 부적절 한 콘텐츠로 모니터링 되지 않습니다.

통신 준수에 대 한 자세한 내용과 조직의 정책을 구성 하는 방법에 대 한 자세한 내용은 [Microsoft 365의 통신 준수](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)를 참조 하세요.

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>Microsoft 팀에서 통신 준수를 사용 하는 방법

의사 소통 준수와 Microsoft 팀이 긴밀 하 게 통합 되어 조직의 통신 위험을 최소화 하는 데 도움이 될 수 있습니다. 첫 번째 통신 준수 정책을 구성한 후에는 알림에 자동으로 플래그가 지정 된 부적절 한 Microsoft 팀 메시지와 콘텐츠를 적극적으로 관리할 수 있습니다.

### <a name="getting-started"></a>시작

Microsoft 팀의 의사 소통 준수 시작은 미리 정의 된 또는 사용자 지정 정책을 [계획](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) 하 고 만들어 팀 채널 또는 1:1 및 그룹에서 부적절 한 사용자 작업을 식별 하는 데부터 시작 합니다. 구성 프로세스의 일부로 일부 사용 권한과 기본 필수 구성 요소를 [구성](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) 해야 한다는 점에 유의 하세요.

팀 관리자는 다음 수준으로 통신 준수 정책을 구성할 수 있습니다.

- **사용자 수준**:이 수준의 정책은 개별 팀 사용자에 게 적용 되거나 조직의 모든 팀 사용자에 게 적용 될 수 있습니다. 이러한 정책은 해당 사용자가 1:1 또는 그룹 채팅에서 보낼 수 있는 메시지를 포함 합니다. 사용자에 대 한 채팅 통신은 사용자가 구성원 인 모든 Microsoft 팀에서 자동으로 모니터링 됩니다.
- **팀 수준**:이 수준의 정책은 Microsoft 팀 채널에 적용 됩니다. 이러한 정책은 팀 채널 에서만 전송 된 메시지를 다룹니다.

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>Microsoft 팀에서 부적절 한 메시지에 대 한 활동 수행

정책을 구성 하 고 Microsoft 팀 메시지에 대 한 통신 준수 알림을 받은 후에는 조직의 승인 검토자가 이러한 메시지에 대해 조치를 취할 수 있습니다. 검토자는 통신 준수 알림을 검토 하 고 Microsoft 팀의 보기에서 플래그가 지정 된 메시지를 제거 하 여 조직을 안전 하 게 보호할 수 있습니다.

![팀에서 메시지 제거](./media/communication-compliance-remove-teams-message.png)

제거 된 메시지와 콘텐츠는 메시지 또는 콘텐츠가 제거 되었고 제거에 적용 되는 정책을 설명 하는 알림으로 바뀝니다. 제거 된 메시지의 보낸 사람이 제거 상태에 대 한 알림을 받고 제거와 관련 한 컨텍스트에 대 한 원본 메시지 콘텐츠를 제공할 수 있습니다. 또한 보낸 사람은 메시지 제거에 적용 되는 특정 정책 조건도 볼 수 있습니다.

보낸 사람에 의해 표시 된 정책 팁의 예:

![보낸 사람에 대 한 정책 팁](./media/communication-compliance-warning-1.png)

보낸 사람에 게 표시 되는 정책 조건 알림의 예:

![보낸 사람에 대 한 정책 조건 정보](./media/communication-compliance-warning-2.png)

받는 사람이 본 정책 팁의 예:

![받는 사람에 대 한 정책 팁](./media/communication-compliance-warning-3.png)