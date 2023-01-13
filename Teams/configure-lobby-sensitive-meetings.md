---
title: 중요한 모임에 대한 Microsoft Teams 모임 로비 구성
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: 관리자 정책, 민감도 레이블 및 모임 템플릿을 사용하여 중요한 모임에 대한 보안을 강화하도록 Teams 모임 로비를 구성하는 방법을 알아봅니다.
ms.openlocfilehash: 1905bc337f0260e86b2351da5015b8e1ba641bf4
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800155"
---
# <a name="configure-the-microsoft-teams-meeting-lobby-for-sensitive-meetings"></a>중요한 모임에 대한 Microsoft Teams 모임 로비 구성

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

모임 로비는 부적절한 사용자가 모임에 입장할 수 없도록 하는 데 사용할 수 있는 도구입니다. 다양한 유형의 참가자를 로비에서 개최함으로써 모임 주최자는 참가자를 검사하고 모임에 참석하는 것이 적절한지 확인할 수 있습니다.

기본적으로 조직의 사용자와 [게스트](guest-access.md) 는 모임에 직접 참가할 수 있으며 신뢰할 수 있는 도메인 및 익명 참가자의 참가자는 로비에서 모임 이끌이가 입장할 때까지 기다려야 합니다. 모임 이끌이는 만든 각 모임에 대해 이 기본 설정을 변경할 수 있습니다.

로비 및 기타 관련 설정은 Teams 관리자가 모임 정책, 모임 템플릿 및 민감도 레이블을 사용하여 다양한 사용자 및 다양한 유형의 모임에 대한 환경을 사용자 지정하여 제어할 수 있습니다.

다음 표에는 조직의 로비 환경 및 구성 위치를 관리하는 데 사용할 수 있는 기능이 나와 있습니다.

|설정|관리 정책|민감도 레이블|템플릿|모임 이끌이|
|:------|:----------:|:---------------:|:------:|:---------------:|
|전화 접속 발신자가 참가하거나 나갈 때 알림|아니요|아니요|예|예|
|익명 사용자 및 전화 접속 발신자가 모임을 시작할 수 있습니다.|예|아니요|아니요|아니요|
|익명 사용자가 모임에 참가할 수 있습니다.|예|아니요|아니요|아니요|
|사람 전화 접속은 로비를 우회할 수 있습니다.|예|예|예|예|
|로비를 우회할 수 있는 사용자|예|예|예|예|

템플릿 및 민감도 레이블을 사용하여 모임 설정을 구성하는 방법에 대한 자세한 내용은 [Microsoft Teams의 사용자 지정 모임 템플릿 개요](custom-meeting-templates-overview.md) 및 [민감도 레이블을 사용하여 일정 항목, Teams 모임 및 채팅을 보호합니다](/microsoft-365/compliance/sensitivity-labels-meetings).

> [!Note]
> 민감도 레이블 및 사용자 지정 모임 템플릿의 모임 설정에는 Teams Premium 필요합니다.

## <a name="lobby-settings-for-different-types-of-meetings"></a>다양한 유형의 모임에 대한 로비 설정

로비를 우회할 수 있는 사용자를 위해 다음 설정을 사용할 수 있습니다.

- 모든 사용자
- 내 조직의 사용자, 신뢰할 수 있는 조직 및 게스트
- 내 조직의 사용자 및 게스트
- 내 조직의 사용자
- 초대받은 사람
- 이끌이 및 공동 이끌이

모임 이끌이는 일반적으로 각 모임에 사용할 설정을 선택하지만 모임 템플릿 또는 민감도 레이블을 사용하여 특정 설정을 적용할 수 있습니다.

조직에서 조직 외부 사용자가 특정 유형의 모임에 참석하지 않도록 요구하는 경우 조직의 사용자만 로비를 우회할 수 있는 모임 템플릿을 고려합니다. 이렇게 하면 실수로 초대되거나 모임 링크를 보낸 조직 외부의 사용자가 모임에 직접 참가할 수 없습니다.

조직에 매우 중요한 정보가 공유되는 모임이 있고 특정 사용자만 참석해야 하는 경우 모임 이끌이만 로비를 우회할 수 있도록 하는 모임 템플릿 또는 민감도 레이블을 사용하는 것이 좋습니다. 이렇게 하면 이끌이가 들어오는 각 참가자를 검사하여 모임에 참석해야 하는지 확인할 수 있습니다. 이렇게 하면 이끌이가 참가할 때까지 모임이 시작되지 않습니다.

일반적으로 중요한 모임의 경우 **초대된 사람** 옵션을 사용하는 것이 좋습니다. 이렇게 하면 모임 초대(전달된 초대 포함)가 없는 사용자가 로비를 통과할 수 있습니다. 모임 이끌이는 모임을 만들 때 전달을 방지할 수도 있습니다.

모임 템플릿 및 민감도 레이블을 함께 사용하는 방법에 대한 자세한 내용은 [Teams 모임 템플릿, 민감도 레이블 및 관리 정책을 함께 사용하여 중요한 모임을 참조하세요](meeting-templates-sensitivity-labels-policies.md).

### <a name="attendees-calling-in-by-phone"></a>전화로 통화하는 참석자

기본적으로 전화로 전화를 걸고 있는 참석자는 로비를 통과합니다. 관리자는 **전화 접속 사용자가 로비 관리자 모임 정책을 무시할 수 있으므로** 이 기본값을 변경할 수 있습니다. 이 설정을 켜거나 끄려면 모임 템플릿 또는 민감도 레이블을 사용해야 합니다.

발신자가 로비를 우회할 수 있도록 허용하려는 경우 모임 이끌이가 이 설정을 제어하거나 모임 템플릿 또는 민감도 레이블을 통해 적용할 수 있습니다.

#### <a name="join-and-leave-notifications"></a>알림 가입 및 나가기

모임 이끌이는 모임에 참가하거나 나갈 때 참석자가 전화로 전화를 걸도록 할 수 있습니다. 전화 참석자가 특정 유형의 모임에 대해 발표되도록 하려면 모임 템플릿을 사용하여 이 설정을 적용할 수 있습니다.

## <a name="meeting-with-anonymous-participants"></a>익명 참가자와의 모임

모든 사용자가 로비를 우회하도록 허용하지 않는 한 익명의 참가자는 모임에 참석하기 위해 로비를 통과해야 합니다. 그런 다음 모임 이끌이는 이러한 참가자를 입학할지 여부를 결정할 수 있습니다.

조직에서 익명 참가자의 모임 참가를 전혀 허용하지 않는 경우 Teams 관리 센터에서 **익명 사용자가 모임에 참가할 수** 있는 설정을 해제할 수 있습니다. 자세한 내용은 [Microsoft Teams에서 모임 설정 관리를 참조하세요](/microsoftteams/meeting-settings-in-teams).

조직에서 익명 참가자 및 다른 사용자(예: 연구)와 함께 모임을 구성해야 하는 마케팅과 같은 특정 그룹이 있는 경우 Teams 모임 정책을 사용하여 다른 그룹에 대한 익명 모임 참가를 구성할 수 있습니다. (이 작업을 수행하려면 **익명 사용자가 위에서 언급한 모임에 참가할 수 있도록** 설정해야 합니다.) 자세한 내용은 [모임 정책 설정 - 참가자 & 게스트를 참조하세요](/microsoftteams/meeting-policies-participants-and-guests).

## <a name="related-topics"></a>관련 주제

[세 가지 보호 계층으로 Teams 모임 구성](configure-meetings-three-tiers-protection.md)

[Microsoft Teams에서 외부 모임 및 채팅 관리](/microsoftteams/manage-external-access)
