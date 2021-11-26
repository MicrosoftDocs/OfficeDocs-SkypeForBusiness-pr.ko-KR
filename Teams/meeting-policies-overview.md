---
title: 모임 정책 관리 Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- seo-marvel-apr2020
description: 모임에서 모임 정책 설정을 관리하고 Teams 모임 참가자가 예약한 모임에 사용할 수 있는 기능을 제어하는 방법을 학습합니다.
ms.openlocfilehash: ccfcb15cb5456a25b8bbad0383481f20d4c81e9b
ms.sourcegitcommit: 7cc7e237b0da270c9cf4a3e535db16dd113e4300
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2021
ms.locfileid: "61205538"
---
# <a name="manage-meeting-policies-in-microsoft-teams"></a>모임 정책 관리 Microsoft Teams

<a name="bkautomatically-admit-people"> </a>

<a name="bkallow-a-participant-to-give-or-request-control"> </a>

<a name="bkallow-transcription"> </a>

모임 정책은 조직에서 사용자가 예약한 모임 참가자가 사용할 수 있는 기능을 제어하는 데 사용됩니다. 자동 생성된 전역(조직 전체의 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어서 할당할 수 있습니다. Microsoft Teams 관리 센터에서 아니면 [PowerShell](teams-powershell-overview.md)을 사용하여 모임 정책을 관리합니다.

> [!NOTE]
> 역할을 사용하여 모임 발표자 및 참석자 권한 관리하기에 대한 자세한 내용은[ Teams 모임에서 역할](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)을 참조하세요.

다음 방법으로 정책을 구현하면 이 정책은 모임이 시작되기 전이나, 모임 도중이나 모임 후에 사용자의 모임 환경에 영향을 미칩니다.

|구현 유형  |설명  |
|---------|---------|
|모임 이끌이별    |이끌이별 정책을 구현하면 모임의 모든 참가자가 이끌이의 정책을 이어 받습니다. 예를 들어 **사용자를** 자동으로 지정하는 것은 조직 내 정책으로, 사용자가 모임에 직접 참가할지 아니면 정책이 할당된 사용자가 예약한 모임을 위해 로비에서 대기할지 여부를 제어합니다.          |
|사용자별    |사용자별 정책을 구현하는 경우 사용자별 정책이 적용되어 이끌이 및/또는 모임 참가자의 특정 기능을 제한합니다. 예를 들어 **채널에서 지금 만나는 것은** 사용자당 정책입니다.     |
|이끌이별 및 사용자별     |이끌이별 및 사용자별 정책 조합을 구현하는 경우 해당 정책 및 이끌이의 정책에 따라 모임 참가자의 특정 기능이 제한됩니다. 예를 들어 **클라우드 기록은** 이끌이 및 사용자당 정책입니다. 모임 이끌이 및 참가자가 녹음/녹화를 시작하고 중지할 수 있도록 이 설정을 켜 습니다.

전역 정책의 설정을 편집하거나 하나 이상의 사용자 지정 정책을 만들어 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당하지 않으면 사용자에게 전역 정책이 적용됩니다.

> [!NOTE]
> 사용자가 오디오 회의 라이선스를 사용하도록 설정하거나 사용자가 오디오 회의에 포함되어 있는 경우 모임 세부 정보 단추를 사용할 수 있습니다. 그렇지 않은 경우 모임 세부 정보를 사용할 수 없습니다.

## <a name="create-a-custom-meeting-policy"></a>사용자 지정 모임 정책 만들기

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **모임** > **모임 정책** 으로 이동합니다.
2. **추가** 를 클릭합니다.
3. 정책의 이름과 설명을 입력합니다. 이름에 특수 문자가 들어가거나 64자를 초과할 수 없습니다.
4. 원하는 설정을 선택합니다.
5. **저장** 을 클릭합니다.

예를 들어, 사용자 수가 많은데 모임에 필요한 대역폭의 양을 제한하려고 한다고 가정해 보겠습니다. "제한된 대역폭"이라는 새 사용자 지정 정책을 만들고 다음 설정을 사용하지 않도록 설정합니다.

**오디오 및 비디오** 에서:

- 클라우드 녹화를 해제합니다.
- IP 비디오를 끄기.

**콘텐츠 공유** 에서:

- 화면 공유 모드를 사용하지 않도록 설정합니다.
- 화이트보드를 끄기.
- 공유 노트를 해제합니다.

그 다음 사용자에게 정책을 할당합니다.

## <a name="edit-a-meeting-policy"></a>모임 정책 편집

전역 정책 및 직접 만든 사용자 지정 정책을 편집할 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **모임** > **모임 정책** 으로 이동합니다.
2. 정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 클릭합니다.
3. 여기서 원하는 내용을 변경합니다.
4. **저장** 을 클릭합니다.

> [!NOTE]
> 한 번에 한 개의 모임 정책만 사용자에게 할당됩니다.

## <a name="assign-a-meeting-policy-to-users"></a>사용자에게 모임 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> 사용자에게 할당된 정책을 삭제할 수 없습니다. 먼저 영향을 받는 모든 사용자에게 다른 정책을 할당한 후에 처음의 정책을 삭제할 수 있습니다.

## <a name="meeting-policy-settings"></a>모임 정책 설정

모임 정책 페이지에서 기존  정책을 선택하거나  추가를 선택하여 새 정책을 추가하면 다음에 대한 설정을 구성할 수 있습니다.

- [일반](meeting-policies-in-teams-general.md)
- [오디오 및 비디오](meeting-policies-audio-and-video.md)
- [기록 & 기록](meetings-policies-recording-and-transcription.md)
- [콘텐츠 공유](meeting-policies-content-sharing.md)
- [참가자 및 게스트](meeting-policies-participants-and-guests.md)

## <a name="related-topics"></a>관련 항목

- [Teams PowerShell 개요](teams-powershell-overview.md)
- [Teams에서 사용자에게 정책 할당](policy-assignment-overview.md)
- [사용자의 RestrictedAnonymousAccess Teams 모임 정책 삭제](meeting-policies-restricted-anonymous-access.md)
