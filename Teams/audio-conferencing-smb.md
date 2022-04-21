---
title: 중소 기업을 위한 오디오 회의 설정
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: '전화를 사용하여 모임에 전화해야 하는 사람들을 위해 중소기업에서 오디오 회의를 설정하는 방법을 알아봅니다. '
ms.openlocfilehash: 91db0bc151d48b2aa7e9557fff7157626ca4ef4f
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2022
ms.locfileid: "65016590"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>중소 기업을 위한 오디오 회의 설정

오디오 회의를 통해 사용자는 모바일 장치 또는 컴퓨터에서 Teams 앱을 사용하는 대신 전화를 사용하여 Teams 모임에 전화할 수 있습니다.  

최대 300명의 사용자가 있는 중소 규모의 비즈니스이며 현재 오디오 회의 라이선스가 없는 경우 1년 동안 오디오 회의를 무료로 받을 수 있습니다. 이 무료 제품은 2020년 10월 1일부터 사용할 수 있습니다.

오디오 회의 추가 기능 라이선스는 Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1 또는 Enterprise E3 라이선스가 있는 사용자에게 적용할 수 있습니다. 자세한 내용은 [Teams 추가 기능 라이선스를 참조하세요.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

> [!NOTE]
> E5 또는 Microsoft 365 Business Voice Enterprise 경우 이러한 라이선스에 이미 오디오 회의가 포함되어 있으므로 무료 오디오 회의 제품을 사용할 수 없습니다.

이 문서에서는 오디오 회의를 설정하는 방법을 안내합니다. 모임 일정을 계획하거나 주도하는 사용자들을 위해 오디오 회의를 설정하기만 하면 됩니다. 모임에 참가하는 모임 참석자는 라이선스 또는 기타 설정이 필요하지 않습니다. 자세한 내용은 [오디오 회의를 참조하세요](audio-conferencing-in-office-365.md).

## <a name="set-up-audio-conferencing"></a>오디오 회의 설정

오디오 회의를 설정하면 모임 초대에 사용할 수 있도록 전화 번호가 회의 브리지에 자동으로 할당됩니다. 회의 브리지의 기본 번호로 할당된 전화 번호는 조직의 국가 또는 지역에서 오는 전화 번호입니다. 이 전화 번호는 장거리 요금이 적용될 수 있는 통행료 번호입니다.

> [!NOTE]
> 몇 가지 추가 단계가 필요한 무료 전화 번호를 사용할 수도 있습니다. 회의 브리지의 전화 번호에 대한 자세한 내용은 이 문서의 뒷부분에 있는 [오디오 회의 전화 번호를](#audio-conferencing-phone-numbers) 참조하세요.

### <a name="step-1-get-audio-conferencing-licenses"></a>1단계: 오디오 회의 라이선스 가져오기

모임을 이끌 각 사용자에 대해 하나의 오디오 회의 라이선스를 받습니다. 이 작업을 수행하려면 Microsoft 365 관리 센터 사용합니다.

1. Microsoft 365 관리 센터 **BillingPurchase** >  **서비스** 로 이동한 다음 페이지 아래쪽에서 **추가** 기능을 선택합니다.
2. **Microsoft 365 오디오 회의 채택 프로모션을** >  선택한 **다음 지금** **가져오기** 를 선택합니다.
3. 모임 이끌이에게 필요한 라이선스 수를 입력한 다음 주문을 완료합니다.

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="오디오 회의 채택 프로모션 라이선스의 스크린샷.":::

    > [!NOTE]
    > 이 **라이선스가 없는 모든 사용자에게** 오디오 회의 라이선스를 자동으로 할당할지 여부에 따라 라이선스가 없는 모든 사용자에게 자동으로 할당을 선택 취소하거나 선택합니다.

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>2단계: 모임을 이끄는 사용자에게 오디오 회의 라이선스 할당

모임을 이끌 각 사용자에게 라이선스를 할당합니다. 이 작업을 수행하려면 Microsoft 365 관리 센터 사용합니다.

#### <a name="assign-a-license-to-one-user"></a>한 사용자에게 라이선스 할당

1. Microsoft 365 관리 센터 **UsersActive** >  사용자로 이동합니다.  
2. 라이선스를 할당할 사용자의 행을 선택한 다음 창에서 **라이선스 및 앱을** 선택합니다.
3. **Microsoft 365 오디오 회의** 확인란을 선택한 다음 **변경 내용 저장** 을 선택합니다.

#### <a name="assign-a-license-to-multiple-users"></a>여러 사용자에게 라이선스 할당

1. Microsoft 365 관리 센터 **UsersActive** >  사용자로 이동합니다.  
2. 라이선스를 할당할 사용자 옆에 있는 원을 선택한 다음 **제품 라이선스 관리를** 선택합니다.
3. **제품 라이선스 관리** 창에서 **추가 할당** 을 선택합니다.
4. **Microsoft 365 오디오 회의** 확인란을 선택한 다음 **변경 내용 저장** 을 선택합니다.  

## <a name="schedule-teams-meetings-in-outlook"></a>Outlook Teams 모임 예약

이제 모임 이끌이가 Outlook 모임을 예약할 수 있습니다. Outlook **일정** 으로 이동한 다음 새 **Teams 모임** 단추를 선택합니다. 모임 전화 접속 번호와 회의 ID는 모임 참석자에게 전송되는 모임 초대에 자동으로 추가됩니다. 자세한 내용은 [Outlook Teams 모임 예약을](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f) 참조하세요.

> [!NOTE]
> 원하는 경우 모임 초대를 사용자 지정하여 회사 로고, 지원 웹 사이트 링크 및 법적 고지 사항 및 텍스트 전용 바닥글을 추가할 수 있습니다. 자세한 내용은 [모임 초대 사용자 지정을 참조하세요](meeting-settings-in-teams.md#customize-meeting-invitations).

## <a name="audio-conferencing-phone-numbers"></a>오디오 회의 전화 번호

회의 브리지에 사용할 수 있는 두 가지 유형의 숫자가 있습니다. **공유 번호**(이 문서의 앞부분에 있는 [오디오 회의 설정](#set-up-audio-conferencing) 섹션에서와 같이) 또는 **전용 번호를** 사용할 수 있습니다. 각각에 대한 자세한 내용은 다음과 같습니다.

### <a name="shared-numbers"></a>공유 번호

공유 번호는 모든 조직에서 공유되는 숫자입니다. 공유 번호는 유료 번호이며 오디오 회의를 설정할 때 자동으로 할당됩니다.

회의 브리지에 할당된 기본 번호를 보려면 Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **MeetingsConference** >  브리지로 이동한 다음 가장 가까운 위치의 번호를 찾습니다.

### <a name="dedicated-numbers"></a>전용 번호

전용 번호는 사용자만 사용할 수 있는 숫자입니다. 전용 번호는 통행료 번호 또는 무료 번호일 수 있습니다. 전용 번호를 사용하려면 먼저 번호를 가져와서 회의 브리지에 할당한 다음 모임을 이끌 각 사람에게 번호를 할당해야 합니다.

전용 번호를 가져오는 몇 가지 방법이 있습니다. Microsoft에서 숫자를 얻거나 현재 서비스 공급자에서 Microsoft로 기존 번호를 전송(포트)할 수 있습니다. 이 작업을 수행하는 방법에 대한 자세한 내용은 [서비스 번호 가져오기를 참조하세요](getting-service-phone-numbers.md).

무료 번호를 사용하는 경우 먼저 모임을 이끌 각 사용자에게 통신 크레딧 라이선스를 할당해야 합니다. 자세한 내용은 [조직에 대한 통신 크레딧 설정을 참조하세요](set-up-communications-credits-for-your-organization.md).

번호가 있으면 전화 회의 브리지에 할당합니다. 이 작업을 수행하려면 Microsoft Teams 관리 센터를 사용합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **MeetingsConference** >  브리지로 이동합니다.
2. **추가** 를 선택한 다음 **, 통행료 번호** 또는 **무료 번호를** 선택합니다.
3. **전화 번호 추가** 창에서 번호를 선택한 다음 **적용** 을 선택합니다.

#### <a name="assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>모임을 이끄는 사용자의 전화 접속 전화 번호 할당

[Microsoft Teams 초대에 포함된 전화 번호 설정을](set-the-phone-numbers-included-on-invites-in-teams.md) 참조하세요.

> [!NOTE]
> *TeamsAudioconferencingpolicy* 에 전화 번호를 추가하고 사용자에게 정책을 할당하여 전화 번호를 설정할 수도 있습니다. 정책에 추가된 수신자 및 무료 전화 번호는 오디오 회의 설정 창을 통해 사용자에게 개별적으로 설정된 전화 번호보다 우선합니다. *Teamsaudioconferencingpolicy* 에 전화 번호가 추가되지 않으면 오디오 회의 설정 창을 통해 사용자에 대해 개별적으로 설정된 전화 번호가 Microsoft Teams 모임 요청에 표시됩니다. [유료 및 무료 번호에 대한 오디오 회의 정책 설정에는](audio-conferencing-toll-free-numbers-policy.md) 자세한 정보가 있습니다.

## <a name="related-topics"></a>관련 항목

- [오디오 회의](audio-conferencing-in-office-365.md)
- [Teams 대한 오디오 회의 설정](set-up-audio-conferencing-in-teams.md)
- [오디오 회의의 전화 번호](phone-numbers-for-audio-conferencing-in-teams.md)
- [오디오 회의 일반적인 질문](audio-conferencing-common-questions.md)
- [서비스 번호 가져오기](getting-service-phone-numbers.md)
- [추가 기능 라이선스 Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [사용자에게 라이선스 할당](/microsoft-365/admin/manage/assign-licenses-to-users)
