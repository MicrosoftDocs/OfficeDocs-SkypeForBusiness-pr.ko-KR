---
title: 사용자의 오디오 회의 설정 관리
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Microsoft 365 또는 Office 365 관리자는 사용자의 공급자, 기본 요금 또는 무료 전화 번호, 전화 회의 ID 또는 PIN을 포함하여 Teams 오디오 회의 설정을 편집할 수 있습니다.
ms.openlocfilehash: 13e44c9f7d8d983325c5f4cf3bb88237a9ad1fb9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269693"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-microsoft-teams"></a>Microsoft Teams에서 사용자의 오디오 회의 설정 관리

Microsoft 365 또는 Office 365 관리자는 조직의 개별 사용자에 대한 오디오 회의 설정(예: 공급자, 기본 요금 또는 무료 전화 번호, 전화 회의 ID 또는 PIN)을 편집할 수 있습니다. 조직의 설정을 편집하려면 조직의 [오디오 회의 설정 관리를 참조하세요](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 왼쪽 탐색 영역에서 **사용자를** 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. **편집** 을 클릭합니다.

3. **오디오 회의** 아래에서 다음 중 어느 것을 수정합니다.

|**설정**|**설명**|
|:-----|:-----|
|**오디오 회의**|사용자에 대한 오디오 회의를 켜거나 끄려면 **오디오 회의** 옆의 **편집** 을 클릭한 다음 **오디오 회의** 창에서 **오디오 회의를** 켜거나 끕니다.|
|**전자 메일로 회의 정보 보내기**  |전화 회의 ID 및 전화 번호가 포함된 전자 메일을 사용자에게 즉시 보내려는 경우에만 이 링크를 클릭합니다. (이 전자 메일에는 PIN이 포함되지 않습니다.) [오디오 회의 정보를 사용하여 사용자에게 전자 메일 보내기를](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) 참조하세요.  |
|**회의 ID**  |사용자의 **전화 회의 ID** 를 다시 설정해야 하는 경우 전화 회의 ID 재설정을 클릭합니다. 자세한 내용은 [사용자의 전화 회의 ID 재설정을 참조하세요](reset-a-conference-id-for-a-user-in-teams.md).  |
|**핀** |사용자의 **PIN** 을 다시 설정해야 하는 경우 PIN 재설정을 클릭합니다. 자세한 내용은 [오디오 회의 PIN 다시 설정을](reset-the-audio-conferencing-pin-in-teams.md) 참조하세요. |
|**기본 회의 유료 전화 번호** (필수) |오디오 회의 브리지에 설정된 숫자입니다. 비즈니스용 Skype 및 Microsoft Teams 모임 요청에 표시할 번호의 서식을 지정합니다. 기본 통행료를 변경하려면 **오디오 회의** 옆의 **편집** 을 클릭하고 **오디오 회의** 창에서 **통행료 번호** 아래에서 숫자를 선택합니다. TeamsAudioConferencingPolicy에 전화 번호를 추가하고 사용자에게 정책을 할당하여 전화 번호를 설정할 수도 있습니다. 정책에 추가된 전화 번호는 **기본 회의 유료 전화 번호를 사용하여 설정된 전화 번호** 보다 우선합니다. TeamsAudioConferencingPolicy에 전화 번호가 추가되지 않으면 **기본 회의 수신자 전화 번호를 사용하여 설정된 전화 번호** 가 Microsoft Teams 모임 요청에 표시됩니다. |
|**이 사용자의 초대에는 무료 번호가 포함될 수 있습니다.**|이 설정은 TeamsAudioconferecningPolicy를 사용하여만 변경할 수 있습니다. |
|**인증되지 않은 사용자가 모임의 첫 번째 사용자가 될 수 있습니다.**|이 설정을 변경하려면 인증되지 않은 사용자 토글이 모임 켜기 또는 끄 **기에서 첫 번째 사용자가 될 수 있습니다** .
|**전화 접속 권한**|이 설정을 변경하려면 **오디오 회의** 옆의 **편집** 을 클릭하고 **오디오 회의** 창 **에서 모임의 전화 접속** 아래에서 옵션을 선택합니다.|

![사용자의 오디오 회의 설정을 표시합니다.](media/teams-manage-audio-conferencing-settings-for-a-user-image1.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>관련 항목

[조직의 오디오 회의 설정 관리](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)

[오디오 회의 일반적인 질문](audio-conferencing-common-questions.md)
