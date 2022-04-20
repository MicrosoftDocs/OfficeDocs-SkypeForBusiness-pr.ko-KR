---
title: Microsoft Teams 통신 규정 준수
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Microsoft Teams 관점에서 내부 위험 솔루션 집합의 일부인 커뮤니케이션 규정 준수에 대한 Learning(M365 통신 규정 준수 기능의 일부).
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 091fe5eba9d17cefc442978cb3090aaca87844d8
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922649"
---
# <a name="communication-compliance-with-microsoft-teams"></a>Microsoft Teams 통신 규정 준수

Microsoft Purview 커뮤니케이션 규정 준수는 조직에서 부적절한 메시지를 감지, 캡처 및 조치를 취함으로써 통신 위험을 최소화하는 데 도움이 되는 Microsoft 365 내부 위험 솔루션입니다.

Microsoft Teams 통신 규정 준수는 Teams 채널, 프라이빗 Teams 채널 또는 1:1 및 그룹 채팅에서 [다음과 같은 유형의](/microsoft-365/compliance/communication-compliance-feature-reference) 부적절한 콘텐츠를 식별하는 데 도움이 됩니다.

- 공격적, 불경한 언어 및 괴롭힘 언어
- 성인, 외설 및 피투성이 이미지
- 중요한 정보 공유

커뮤니케이션 규정 준수 및 조직에 대한 정책을 구성하는 방법에 대한 자세한 내용은 [커뮤니케이션 규정 준수에 대한 자세한 내용을 참조](/microsoft-365/compliance/communication-compliance)하세요.

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>Microsoft Teams 통신 규정 준수를 사용하는 방법

커뮤니케이션 규정 준수 및 Microsoft Teams 긴밀하게 통합되어 조직의 통신 위험을 최소화하는 데 도움이 될 수 있습니다. 첫 번째 통신 규정 준수 정책을 구성한 후에는 경고에 자동으로 플래그가 지정된 부적절한 Microsoft Teams 메시지 및 콘텐츠를 적극적으로 관리할 수 있습니다.

### <a name="getting-started"></a>시작

Microsoft Teams 커뮤니케이션 규정 준수를 시작하는 것은 Teams 채널 또는 1:1 및 그룹에서 부적절한 사용자 활동을 식별하는 미리 정의된 또는 사용자 지정 정책을 [계획하고](/microsoft-365/compliance/communication-compliance-plan) 만드는 것으로 시작합니다. 구성 프로세스의 일부로 일부 권한 및 기본 필수 구성 요소를 [구성](/microsoft-365/compliance/communication-compliance-configure) 해야 합니다.

Teams 관리자는 다음 수준에서 통신 준수 정책을 구성할 수 있습니다.

- **사용자 수준**: 이 수준의 정책은 개별 Teams 사용자에게 적용되거나 조직의 모든 Teams 사용자에게 적용될 수 있습니다. 이러한 정책은 이러한 사용자가 1:1 또는 그룹 채팅에서 보낼 수 있는 메시지를 다룹니다. 사용자에 대한 채팅 통신은 사용자가 구성원인 모든 Microsoft Teams 자동으로 모니터링됩니다.
- **Teams 수준**: 이 수준의 정책은 비공개 채널을 포함한 Microsoft Teams 채널에 적용됩니다. 이러한 정책은 Teams 채널에서 보낸 메시지만 다룹니다.

### <a name="report-a-concern-in-microsoft-teams"></a>Microsoft Teams 문제 보고

>[!NOTE]
>사용자가 보고한 메시지는 2022년 5월부터 [통신 규정 준수](/microsoft-365/compliance/communication-compliance-configure#subscriptions-and-licensing) 및 Microsoft Teams 사용이 허가된 조직에서 사용할 수 있게 됩니다. 이 기능은 2022년 8월 31일까지 사용이 허가된 모든 조직에서 사용할 수 있어야 합니다.

Teams 메시지의 *문제 보고* 옵션은 기본적으로 사용하도록 설정되며 Teams [관리 센터의](/microsoftteams/manage-teams-in-modern-portal) Teams 메시징 정책을 통해 제어할 수 있습니다. 이렇게 하면 조직의 사용자가 정책에 대한 커뮤니케이션 규정 준수 검토자가 검토할 부적절한 메시지를 제출할 수 있습니다. 통신 규정 준수에서 사용자가 보고한 메시지에 대한 자세한 내용은 [통신 준수 정책을](/microsoft-365/compliance/communication-compliance-policies#user-reported-messages-policy) 참조하세요.

![문제 메뉴를 보고합니다.](./media/communication-compliance-report-a-concern-full-menu.png)

검토를 위해 메시지를 제출한 후 사용자는 Microsoft Teams 제출에 대한 확인을 받습니다. 채팅의 다른 참가자는 이 알림을 볼 수 없습니다.

![우려 사항 확인을 보고합니다.](./media/communication-compliance-report-a-concern.png)

사용자 지정 정책을 만들고 할당하지 않는 한 조직의 사용자는 자동으로 전역 정책을 받습니다. 전역 정책에서 설정을 편집하거나 하나 이상의 사용자 지정 정책을 만들고 할당하여 이 기능을 켜거나 끕니다. 자세한 내용은 [Teams 메시징 정책 관리를](/microsoftteams/messaging-policies-in-teams) 참조하세요.

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>Microsoft Teams 부적절한 메시지에 대한 작업

정책을 구성하고 Microsoft Teams 메시지에 대한 통신 준수 경고를 받은 후에는 조직의 규정 준수 검토자가 이러한 메시지에 대해 작업해야 합니다. 조직에 대해 사용하도록 설정된 경우 사용자가 보고한 메시지도 포함됩니다. 검토자는 커뮤니케이션 규정 준수 경고를 검토하고 Microsoft Teams 보기에서 플래그가 지정된 메시지를 제거하여 조직을 보호할 수 있습니다.

![Teams 메시지를 제거합니다.](./media/communication-compliance-remove-teams-message.png)

제거된 메시지 및 콘텐츠는 메시지 또는 콘텐츠가 제거되었으며 제거에 적용할 수 있는 정책을 설명하는 뷰어 알림으로 대체됩니다. 제거된 메시지 또는 콘텐츠의 보낸 사람도 제거 상태에 대한 알림을 받고 제거와 관련된 컨텍스트에 대한 원본 메시지 콘텐츠가 제공됩니다. 발신자는 메시지 제거에 적용되는 특정 정책 조건을 볼 수도 있습니다.

보낸 사람에게 표시되는 정책 팁의 예:

![보낸 사람용 정책 팁입니다.](./media/communication-compliance-warning-1.png)

보낸 사람에게 표시되는 정책 알림의 예:

![보낸 사람 정책 조건 정보입니다.](./media/communication-compliance-warning-2.png)

받는 사람이 볼 수 있는 정책 팁의 예:

![받는 사람을 위한 정책 팁입니다.](./media/communication-compliance-warning-3.png)