---
title: 클라우드 음성 사서함 설정 관리
author: crowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 사용자의 음성 메일 설정을 관리합니다.
ms.openlocfilehash: 80dad0b2088518c9d6f08ee005eba25cc1e10e2b
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494864"
---
# <a name="manage-cloud-voicemail-settings-for-users"></a>사용자에 대한 클라우드 음성 사서함 설정 관리

음성 메일 설정을 사용하면 개별 사용자에 대한 음성 메일 설정을 구성할 수 있습니다.

사용자에 대한 음성 메일 설정을 구성하기 전에 [클라우드 음성 사서함 설정을](set-up-phone-system-voicemail.md) 읽어야 합니다. 사용자 그룹에 대한 정책을 설정하는 방법에 대한 자세한 내용은 [음성 메일 정책 관리를](manage-voicemail-policies.md) 참조하세요.

클라우드 음성 사서함 대한 기본 설정은 다음과 같습니다.

- 음성 메일을 사용할 수 있습니다.
- 프롬프트 언어는 사용자의 기본 설정 언어로 설정됩니다.
- 외부 인사말은 사용할 수 없습니다.
- Outlook에서 자동 회신이 설정되면 부재 중 인사말이 비활성화됩니다.
- Outlook의 일정에 업무 외 인사말이 표시되면 외부 인사말이 비활성화됩니다.
- 학습 및 정확도 향상을 위해 서비스와 음성 메일 및 전사 데이터를 공유할 수 없습니다.
- 통화 응답 규칙은 일반 음성 메일로 설정됩니다.
- 기본 인사말 프롬프트 덮어쓰기가 설정되지 않았습니다.
- 기본 외부 인사말 프롬프트 덮어쓰기가 설정되지 않았습니다.
- 전송 대상이 설정되지 않았습니다.


사용자의 클라우드 음성 사서함 기능을 관리하려면 Teams 관리 센터 또는 PowerShell을 사용할 수 있습니다. 최종 사용자는 설정 **-> 통화 -> Voicemail 구성** 으로 이동하여 Teams 클라이언트에서 이러한 설정을 구성할 수도 있습니다.

## <a name="use-teams-admin-center"></a>Teams 관리 센터 사용

Teams 관리 센터에서 다음을 수행합니다.

1.  왼쪽 탐색 창에서 **사용자 > 사용자 관리** 로 이동하여 사용자를 선택합니다.

2.  사용자 세부 정보 페이지에서 **음성 메일** 탭으로 이동합니다.

3.  설정을 변경합니다.

4.  **저장** 을 선택합니다.


## <a name="use-powershell"></a>PowerShell 사용

PowerShell을 사용하여 다음과 같이 음성 메일 설정을 관리할 수도 있습니다.

- 개별 사용자에 대한 클라우드 음성 사서함 설정을 관리하려면 [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) cmdlet을 사용합니다. 

- 설정을 보려면 [Get-CsOnlineVoicemailUserSettings](/powershell/module/skype/get-csonlinevoicemailusersettings) cmdlet을 사용합니다.

- [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) cmdlet을 사용하고 VoicemailEnabled 매개 변수를 $false 설정하여 사용자에 대한 클라우드 음성 사서함 사용하지 않도록 설정할 수 있습니다. 

## <a name="voicemail-settings"></a>음성 메일 설정

- **음성 메일 사용** - 이 설정은 사용자에 대해 클라우드 음성 사서함 사용할 수 있는지 여부를 제어합니다. 설정이 false이면 클라우드 음성 사서함 서비스를 사용할 수 없으며 사용자의 음성 메일을 기록하지 않습니다.

- **프롬프트 언어** - 이 설정은 클라우드 음성 사서함 프롬프트에 사용되는 언어를 지정합니다. 자세한 내용은 [인사말 및 전자 메일의 기본 언어 변경을 참조하세요](change-the-default-language-for-greetings-and-emails.md).

- **인사말 설정** - 클라우드 음성 사서함 사용자가 사무실에 있을 때와 사용자가 사무실 외부에 있을 때 특정 인사말을 재생할 수 있습니다. 사용자가 두 인사말을 모두 기록하거나 텍스트 음성 변환 인사말을 사용할 수 있습니다.

  - **기본 인사말 프롬프트 덮어쓰기** - 사용자가 인사말을 기록하지 않은 경우 재생할 텍스트 음성 변환 인사말을 지정합니다.

  - **인사말 사용** - Outlook 설정에 관계없이 부재 중 인사말이 음성 메일 입금 시나리오에서 재생되는지 여부를 지정합니다.

  - **Oof Greeting Follow Automatic Replies Enabled** - 사용자가 Outlook에서 자동 회신을 설정할 때 음성 메일 입금 시나리오에서 부재 중 인사말을 재생할지 여부를 지정합니다.

  - **Oof Greeting Follow Calendar Enabled** - 사용자가 부재 중 일정을 설정할 때 음성 메일 입금 시나리오에서 부재 중 인사말을 재생할지 여부를 지정합니다.

  - **기본 Oof 인사말 프롬프트 덮어쓰기** - 사용자가 부재 중이고 부재 중 인사말을 기록하지 않은 경우 재생되는 텍스트 음성 변환 인사말을 지정합니다.

- **통화 응답 규칙** - 이 설정은 통화 응답 규칙을 지정합니다. 규칙은 다음과 같습니다.
  - 서비스는 메시지 없이 호출을 거부합니다.
  - 관련 인사말(일반 또는 외부)만 재생됩니다.
  - 관련 인사말(일반 또는 외부)이 재생되고 발신자가 지정된 사용자 또는 전화 번호로 전송됩니다.
  -  관련 인사말(일반 또는 외부)이 재생되고 발신자가 음성 메일을 남길 수 있습니다.
  - 관련 인사말(일반 또는 외부)이 재생되고, 발신자가 음성 메일을 남길 수 있으며, 0을 눌러 지정된 사용자 또는 전화 번호로 전송할 수 있습니다.

- **서비스 개선을 위한 데이터 공유** - 음성 메일 및 전사 데이터를 교육 및 정확도 향상을 위해 서비스와 공유되는지 여부를 지정합니다. false로 설정하면 사용자 선택에 관계없이 음성 메일 데이터가 공유되지 않습니다.

- **통화 전송** - 발신자가 전송되는 사용자 또는 전화 번호를 지정합니다.


