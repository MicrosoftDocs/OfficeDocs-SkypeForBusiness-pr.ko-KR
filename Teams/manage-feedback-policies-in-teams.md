---
title: Microsoft 팀에서 피드백 정책 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: msedliak
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 조직의 팀 사용자가 Microsoft에 팀에 대 한 피드백을 제출할 수 있는지 여부를 제어 하는 데 피드백 정책을 사용 하는 방법을 알아봅니다.
ms.openlocfilehash: 3c9d05a3003906377447ee119b8cfc9bd137db81
ms.sourcegitcommit: f26bb86d38c3b45a82e6d77c5aa521360a81ee9b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2019
ms.locfileid: "36184682"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Microsoft 팀에서 피드백 정책 관리

[!INCLUDE [preview-feature](includes/preview-feature.md)]

팀 클라이언트에서 **** > **피드백을 제공** 하기 위해 사용자는 팀에 대 한 의견 및 제안을 Microsoft에 보낼 수 있습니다. 팀 경험을 지속적으로 개선 하 고 있으며,이 피드백을 사용 하 여 팀을 개선할 수 있습니다.

![팀의 피드백 제공 옵션 스크린샷](media/manage-feedback-policies-in-teams-give-feedback.png)

**의견 제공** 을 통해 전송 되는 데이터는 "고객 데이터" 또는 "개인 데이터"로 간주 되는 정보를 포함 하 여 Office 365 계약에 "지원 데이터"로 간주 됩니다.

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>사용자가 Microsoft에 팀에 대 한 피드백을 보낼 수 있는지 여부 설정

관리자는 조직의 사용자가 Microsoft에 팀에 대 한 피드백을 보낼 수 있는지 여부를 제어할 수 있습니다. 기본적으로 조직의 모든 사용자에 게 전역 (조직 전체 기본값) 정책이 자동으로 할당 되며 정책에서 해당 기능을 사용할 수 있습니다. 이 예외는 교사를 위해 기능을 사용 하도록 설정 하 고 학생에 게 사용할 수 없는 교육용 팀입니다.

전역 정책을 편집 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 사용자가 사용자 지정 정책을 할당 한 경우 해당 정책이 사용자에 게 적용 됩니다. 사용자가 사용자 지정 정책을 할당 하지 않으면 전역 정책이 사용자에 게 적용 됩니다. 전역 정책을 편집 하거나 정책을 할당 한 후 변경 내용이 적용 되는 데 최대 24 시간이 걸릴 수 있습니다.

예를 들어 조직의 모든 사용자가 교육의 새 고용를 제외 하 고 의견을 보낼 수 있도록 하려는 경우를 예로 들어 보겠습니다. 이 시나리오에서는 사용자 지정 정책을 만들어 기능을 끄고 새 고용에 할당 합니다. 조직의 다른 모든 사용자는 기능이 설정 된 전역 정책을 받습니다.  

**CsTeamsFeedbackPolicy** cmdlet을 사용 하 여 사용자 지정 정책 및 **허용-CsTeamsFeedbackPolicy** cmdlet을 만들어 보안 그룹 또는 메일 그룹과 같은 하나 이상의 사용자 또는 사용자 그룹에 할당 합니다. 

**UserInitiatedMode** 매개 변수를 **enabled** 로 설정 하면 정책에 할당 된 사용자가 피드백을 제공할 수 있습니다. 매개 변수를 **disabled** 로 설정 하면 기능이 해제 되 고 정책에 할당 된 사용자에 게 피드백을 제공 하는 옵션이 없습니다.

## <a name="create-a-custom-feedback-policy"></a>사용자 지정 피드백 정책 만들기

이 예제에서는 새 고용 피드백 정책 이라고 하는 피드백 정책을 만들고 피드백을 제공 하는 기능을 해제 합니다.

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a>사용자 지정 피드백 정책 지정

### <a name="assign-a-custom-feedback-policy-to-a-user"></a>사용자에 게 사용자 지정 피드백 정책 할당

이 예제에서는 user1 이라는 사용자에 게 새 채용 사용자 의견 정책 이라는 사용자 지정 정책을 할당 합니다.

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a>그룹의 사용자에 게 사용자 지정 피드백 정책 할당

이미 식별 한 여러 사용자에 게 사용자 지정 피드백 정책을 할당 하려고 할 수 있습니다. 예를 들어 보안 그룹의 모든 사용자에 게 정책을 할당 하려고 할 수 있습니다.

이 예제에서는 Contoso 새 고용 그룹의 모든 사용자에 게 새 채용 사용자 의견 정책 이라는 사용자 지정 피드백 정책을 할당 합니다.  

특정 그룹의 GroupObjectId를 가져옵니다.
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
지정 된 그룹의 구성원을 가져옵니다.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
그룹의 모든 사용자를 특정 피드백 정책에 할당 합니다. 이 예제에서는 새 채용에 대 한 의견 수집 정책입니다.
```
$members | ForEach-Object { Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
그룹의 구성원 수에 따라이 명령을 실행 하는 데 몇 분 정도 걸릴 수 있습니다.

## <a name="related-topics"></a>관련 항목

- [팀 PowerShell 개요](teams-powershell-overview.md)