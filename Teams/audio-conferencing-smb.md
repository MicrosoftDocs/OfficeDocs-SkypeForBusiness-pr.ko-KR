---
title: 중소 기업을 위한 오디오 회의 설정
ms.author: v-cichur
author: cichur
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
description: '전화로 모임에 전화해야 하는 사용자에 대해 중소기업 또는 중소기업에서 오디오 회의를 설정하는 방법에 대해 자세히 알아보습니다. '
ms.openlocfilehash: d4624feb0ccacb7a5fd8ecf6d9ba06155950e90e
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728937"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>중소 기업을 위한 오디오 회의 설정

오디오 회의를 사용하여 모바일 디바이스 또는 컴퓨터에서 Teams 대신 휴대폰을 사용하여 Teams 모임에 전화를 걸 수 있습니다.  

사용자가 최대 300명인 중소기업이며 현재 오디오 회의 라이선스가 없는 경우 1년 동안 오디오 회의를 무료로 받을 수 있습니다. 이 무료 혜택은 2020년 10월 1일부터 제공됩니다.

오디오 회의 추가 기능 라이선스는 E3 라이선스를 Microsoft 365 Business Basic 비즈니스 표준, 비즈니스 Premium Enterprise E3 라이선스를 Enterprise 수 있습니다. 자세한 내용은 추가 [Teams 라이선스를 참조합니다.](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

> [!NOTE]
> E5 또는 Enterprise Microsoft 365 Business Voice 라이선스에 이미 오디오 회의가 포함되어 있기 때문에 무료 오디오 회의 제안을 사용할 수 없습니다.

이 문서에서는 오디오 회의를 설정하는 방법을 제공합니다. 모임 일정을 계획하거나 주도하는 사용자들을 위해 오디오 회의를 설정하기만 하면 됩니다. 모임에 참가하는 모임 참석자에는 라이선스 또는 기타 설정이 필요하지 않습니다. 자세한 내용은 오디오 회의 [를 참조합니다.](audio-conferencing-in-office-365.md)

## <a name="set-up-audio-conferencing"></a>오디오 회의 설정

오디오 회의를 설정할 때 전화 번호가 회의 브리지에 자동으로 할당되어 모임 초대에 사용할 수 있습니다. 회의 브리지의 기본 번호로 할당된 전화 번호는 조직의 국가 또는 지역의 전화 번호입니다. 이 전화 번호는 장거리 요금이 부과될 수 있는 요금 번호입니다.

> [!NOTE]
> 몇 가지 추가 단계가 필요한 무료 전화 번호를 사용할 수도 있습니다. 회의 브리지에 대한 전화 번호에 대한 자세한 내용은 이 문서 의 의 1부에서 [오디오](#audio-conferencing-phone-numbers) 회의 전화 번호를 참조하세요.

### <a name="step-1-get-audio-conferencing-licenses"></a>1단계: 오디오 회의 라이선스를 얻습니다.

모임을 이끌 각 사용자에 대해 하나의 오디오 회의 라이선스를 얻습니다. 이 Microsoft 365 관리 센터 를 사용하여 이 작업을 합니다.

1. Microsoft 365 관리 센터 구매 서비스로 이동한 다음 페이지 아래쪽에서 추가 기능을  >   **선택합니다.**
2. 오디오 **Microsoft 365** 채택 프로모션 세부 정보를 선택한 다음  >  지금 **을 선택합니다.**
3. 모임 이끌이에 필요한 라이선스 수를 입력한 다음 주문을 완료합니다.

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="오디오 회의 채택 프로모션 라이선스 스크린샷.":::

    > [!NOTE]
    > 이 라이선스가 없는 모든 사용자에게 오디오 회의 라이선스를 자동으로 할당할지 여부에 따라 라이선스가 없는 모든 사용자에게 자동으로 할당을 선택 취소하거나 선택합니다.

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>2단계: 모임을 주도하는 사용자에게 오디오 회의 라이선스 할당

모임을 이끌 각 사용자에게 라이선스를 할당합니다. 이 Microsoft 365 관리 센터 를 사용하여 이 작업을 합니다.

#### <a name="assign-a-license-to-one-user"></a>한 사용자에게 라이선스 할당

1. 이 Microsoft 365 관리 센터 사용자 활성 **사용자로**  >  **이동합니다.**  
2. 라이선스를 할당할 사용자의 행을 선택한 다음 창에서 라이선스 및 앱 **을 선택합니다.**
3. 오디오 **Microsoft 365** 확인란을 선택한 다음 변경 내용 **저장을 선택합니다.**

#### <a name="assign-a-license-to-multiple-users"></a>여러 사용자에게 라이선스 할당

1. 이 Microsoft 365 관리 센터 사용자 활성 **사용자로**  >  **이동합니다.**  
2. 라이선스를 할당할 사용자 옆에 있는 원을 선택한 다음 제품 라이선스 관리를 **선택합니다.**
3. 제품 라이선스 **관리 창에서** 더 **할당을 선택합니다.**
4. 오디오 **Microsoft 365** 확인란을 선택한 다음 변경 내용 **저장을 선택합니다.**  

## <a name="schedule-teams-meetings-in-outlook"></a>Teams 모임 예약Outlook

이제 모임 이끌이가 모임을 예약할 수 Outlook. Outlook 일정으로 이동한 다음 새 모임 Teams **선택합니다.** 모임 전화 접속 번호와 회의 ID는 모임 참석자에 전송되는 모임 초대에 자동으로 추가됩니다. 자세한 내용은 에서 Teams [모임 예약을 Outlook.](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)

> [!NOTE]
> 원하는 경우 모임 초대를 사용자 지정하여 회사 로고를 추가하고, 지원 웹 사이트 및 법적 고지 조항에 대한 링크 및 텍스트 전용 발판을 추가할 수 있습니다. 자세한 내용은 모임 초대 [사용자 지정 을 참조합니다.](meeting-settings-in-teams.md#customize-meeting-invitations)

## <a name="audio-conferencing-phone-numbers"></a>오디오 회의 전화 번호

회의 브리지에 사용할 수 있는 두 가지 유형의 숫자가 있습니다. 공유 번호(이  문서의 앞부분의 오디오 회의 설정 섹션에서와 같은) 또는 전용 번호를 **사용할 수 있습니다.** [](#set-up-audio-conferencing) 다음은 각 정보에 대한 자세한 정보입니다.

### <a name="shared-numbers"></a>공유 번호

공유 번호는 모든 조직에서 공유되는 숫자입니다. 공유 번호는 전화 번호로, 오디오 회의를 설정할 때 자동으로 할당됩니다.

회의 브리지에 할당된 기본 번호를 확인하려면 Microsoft Teams 관리 센터의 왼쪽 탐색에서 모임 회의 브리지로 이동한 다음 가장 가까운 위치에 대한 번호를   >  찾습니다.

### <a name="dedicated-numbers"></a>전용 번호

전용 번호는 사용자만 사용할 수 있는 숫자입니다. 전용 번호는 무료 전화 번호 또는 무료 번호일 수 있습니다. 전용 번호를 사용하시다가 먼저 번호를 얻게 하여 회의 브리지에 할당한 다음, 모임을 이끌 각 사용자에게 번호를 할당해야 합니다.

전용 번호를 얻을 수 있는 몇 가지 방법이 있습니다. Microsoft에서 번호를 얻거나 현재 서비스 공급자에서 Microsoft로 기존 번호를 전송(포트)할 수 있습니다. 이 작업을 하는 방법에 대한 자세한 내용은 서비스 번호 보기 [를 참조합니다.](getting-service-phone-numbers.md)

무료 전화 번호를 사용하는 경우 먼저 모임을 이끌 각 사용자에게 Communications 크레딧 라이선스를 할당해야 합니다. 자세한 내용은 조직의 통신 크레딧 [설정 을 참조합니다.](set-up-communications-credits-for-your-organization.md)

번호가 있는 경우 전화 회의 브리지에 할당합니다. 이 작업을 Microsoft Teams 관리 센터를 사용하세요.

1. 관리 센터의 왼쪽 Microsoft Teams 모임 브리지로   >  **이동하세요.**
2. 추가 **를** 선택한  다음, 전화 번호 또는 무료 전화 번호 **를 선택합니다.**
3. 전화 번호 **추가** 창에서 번호를 선택한 다음 적용을 **선택합니다.**

그런 다음 모임을 이끌 각 사용자에게 번호를 할당합니다. 이 작업을 Microsoft Teams 관리 센터를 사용하세요.

1. 관리 센터의 Microsoft Teams 탐색에서 사용자를 선택하고 **사용자의** 표시 이름을 클릭하고 **편집을 선택합니다.**
2. 오디오 **회의** 옆에 있는 편집을 선택한 다음  오디오 회의 창에서 전화 번호 또는 무료  전화 번호  목록에서 번호를 선택한 다음 적용을 **선택합니다.**

## <a name="related-topics"></a>관련 항목

- [오디오 회의](audio-conferencing-in-office-365.md)
- [오디오 회의 설정 Teams](set-up-audio-conferencing-in-teams.md)
- [오디오 회의의 전화 번호](phone-numbers-for-audio-conferencing-in-teams.md)
- [오디오 회의 일반적인 질문](audio-conferencing-common-questions.md)
- [서비스 번호 사용](getting-service-phone-numbers.md)
- [Teams 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [사용자에게 라이선스 할당](/microsoft-365/admin/manage/assign-licenses-to-users)