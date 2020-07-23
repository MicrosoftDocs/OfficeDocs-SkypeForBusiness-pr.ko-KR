---
title: 초대에 포함할 전화 번호 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 다음 단계에 따라 호출자가 Microsoft 팀 모임에 참가 하는 데 사용할 기본 전화 번호를 만듭니다.
ms.openlocfilehash: 7dd59950403543074d8428d35270ab963ca824e3
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372187"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Microsoft 팀의 초대에 포함 된 전화 번호 설정

Microsoft 365 및 Office 365의 오디오 회의를 통해 조직의 사용자가 Microsoft 팀 모임을 만든 다음 사용자가 휴대폰을 사용 하 여 해당 모임에 전화를 걸 수 있습니다.
  
회의 브리지는 조직의 전화 접속 전화 번호 집합을 제공 합니다. 이 모든 항목은 모임 이끌이가 만든 모임에 참가 하는 데 사용할 수 있지만 모임 초대에 포함 될 모임을 선택할 수 있습니다.
  
> [!NOTE]
> 모임 주최자에 대 한 모임 초대에는 최대 1 명의 유료 전화 번호와 한 명 이상의 무료 전화번호가 있을 수 있지만, 모임 참가에 사용할 수 있는 모든 전화 접속 전화 번호의 전체 목록을 여는 링크가 각 모임 초대의 맨 아래에 있는 링크 이기도 합니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>새 사용자를 위해 모임 초대에 포함 된 전화 번호의 초기 할당

오디오 회의에 사용 하도록 설정 된 사용자의 모임 초대에 포함 되는 전화 번호는 기본 회의 유료 전화 번호 및 기본 회의 무료 전화 번호 사용자 설정에 따라 정의 됩니다. 각 설정은 지정 된 사용자의 모임 초대에 포함 될 유료 및 무료 번호를 지정 합니다. 위에서 언급 한 것 처럼 각 모임 초대에는 하나의 유료 번호와 추가 무료 번호, 그리고 특정 모임에 참가 하는 데 사용할 수 있는 모든 전화 접속 전화 번호의 전체 목록을 여는 링크가 포함 되어 있습니다.

새 사용자의 경우 기본 회의 유료 전화 번호는 사용자가 오디오 회의 서비스를 사용할 수 있는 경우 사용자의 Microsoft 365 관리 센터에 설정 된 사용 위치에 따라 지정 됩니다. 사용자의 국가와 일치 하는 유료 전화 번호가 있는 경우 해당 번호는 사용자의 기본 유료 번호로 자동으로 할당 됩니다. 전화 회의 브리지의 기본 유료 번호로 정의 된 번호가 사용자의 기본 유료 번호로 할당 되지 않는 경우에 사용 됩니다.  

사용자가 오디오 회의 서비스를 사용할 수 있게 되 면 사용자의 기본 유료 및 무료 전화 번호를 언제 든 지 초기 값으로 테 넌 트 관리자가 변경할 수 있습니다.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>모임 이끌이 또는 사용자의 기본 오디오 회의 전화 번호 설정 또는 변경

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

이러한 변경 작업을 수행 하려면 팀 서비스 관리자 여야 합니다. 팀 [관리 역할을 사용](https://docs.microsoft.com/microsoftteams/using-admin-roles) 하 여 관리자 역할 및 사용 권한 얻기에 대 한 정보를 읽어 보세요 .를 참조 하세요.

1. Microsoft 팀 관리 센터에 로그인 합니다.

2. 왼쪽 탐색 창에서 **사용자**를 클릭 합니다.

    ![Microsoft 팀 관리 센터에서 사용자 선택을 표시 합니다.](media/Admin-users.png)

3. 사용 가능한 사용자 목록에서 사용자 이름을 클릭 합니다.

4. **오디오 회의**옆에 있는 **편집**을 클릭 합니다.

    ![오디오 회의 옆에 있는 편집 클릭](media/teams-set-phone-numbers-on-invites-image3.png)

5. **유료** 번호 또는 **수신자 부담 번호** 필드를 사용 하 여 사용자의 번호를 입력 합니다.

> [!IMPORTANT]
> 사용자의 오디오 회의 설정을 변경 하는 경우에는 되풀이 및 향후 Microsoft 팀 모임을 업데이트 하 고 참석자에 게 보내야 합니다.

## <a name="want-to-use-windows-powershell"></a>Windows PowerShell을 사용 하려는 경우

Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.

- [Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)

- [Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법](https://go.microsoft.com/fwlink/?LinkId=525142)

Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.
  
## <a name="related-topics"></a>관련 항목

[Microsoft 365 또는 Office 365에서 오디오 회의 체험 또는 구매](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[오디오 회의 브리지에서 전화 번호 변경](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
