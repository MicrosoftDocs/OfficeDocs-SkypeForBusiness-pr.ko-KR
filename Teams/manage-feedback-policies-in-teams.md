---
title: 사용자 의견 정책 관리 Microsoft Teams
author: serdarsoysal
ms.author: serdars
manager: serdars
ms.reviewer: heprecel
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 피드백 정책을 사용하여 조직의 사용자가 Microsoft에 Teams 피드백을 제출할 수 있는지 여부를 Teams 방법을 알아보습니다.
ms.openlocfilehash: 582c5e39fca8dc37cefe8b480b2ff886779f6fa0
ms.sourcegitcommit: 84706d0b3b93c1bc72baac830fefd3f0a87c5ad1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2021
ms.locfileid: "59942103"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>사용자 의견 정책 관리 Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

조직의 사용자는 사용자에 대한 피드백을 Microsoft Teams 데스크톱, 웹 클라이언트 및 모바일 내에서 직접 Teams 알 수 있습니다. 이 피드백을 사용하여 더 나은 Teams 환경을 지속적으로 개선하고 Teams 있습니다.

> [!NOTE]
> 피드백 정책은 고가 또는 DOD GCC GCC 사용할 수 없습니다.

**피드백 **제공** 기능**

사용자는 데스크톱 및 웹에서 피드백을 Teams 도움말로 Teams 수  >   있습니다.


![사용자 의견 옵션을 Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

피드백 보내기 설정 도움말을 &  >  **모바일의**  >  **피드백에 액세스합니다.**

![모바일에서 Teams 피드백 옵션 제공](media/feedback3.jpg)

 피드백 제공  및  피드백 보내기를 통해 전송된 데이터는 "고객 데이터" 또는 "개인 데이터"로 간주되는 Microsoft 365 Office 365 계약에 따라 "지원 데이터"로 간주됩니다.


**설문 조사**

또한 사용자는 사용자 경험에 대한 평가를 Teams 등급에 대한 세부 정보를 보낼 수 있습니다. 이 팝업 설문 조사는 사용자에 대해 수시로 표시됩니다Teams. 사용자가 알림에서  피드백 제공을 선택하면 설문 조사가 완료될 수 있습니다.

![설문 조사 알림 및 Teams.](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>사용자가 Microsoft에 대한 피드백을 보낼 수 Teams 설정

관리자는 조직의 사용자가 Microsoft에 대한 피드백을 보낼 수 Teams 여부를 제어할 수 있습니다. 기본적으로 조직의 모든 사용자에게 전역(조직 전체 기본값) 정책이 자동으로 할당되고, 피드백 기능 및 설문 조사가 정책에서 활성화됩니다. 예외는 교육용 Teams 기능을 사용하도록 설정하고 학생을 위해 사용하지 않도록 설정되어 있습니다.

전역 정책을 편집하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 전역 정책을 편집하거나 사용자 지정 정책을 할당한 후 변경 내용이 적용될 수 있는 데 몇 시간이 걸릴 수 있습니다.

예를 들어 조직의 모든 사용자가 교육에서 신규 고용을 제외하고 피드백을 보내고 설문 조사를 받을 수 있도록 허용하려는 경우를 예로 들 수 있습니다. 이 시나리오에서는 두 기능을 모두 해제하고 새 고용에 할당하는 사용자 지정 정책을 만들 수 있습니다. 조직의 다른 모든 사용자는 기능이 켜져 있는 전역 정책을 얻습니다.  

PowerShell을 사용하여 피드백 정책을 관리합니다. [ **New-CsTeamsFeedbackPolicy** cmdlet을](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) 사용하여 사용자 지정 정책을 만들 수 있습니다. **Grant-CsTeamsFeedbackPolicy** cmdlet을 사용하여 보안 그룹 또는 메일 그룹과 같은 하나 이상의 사용자 또는 사용자 그룹에 할당합니다. **Set-CsTeamsFeedbackPolicy를** 사용하여 특정 플래그를 설정합니다.

기능을 끄고 켜기 위해 다음 매개 변수를 설정합니다.

 - **피드백 제공:** 정책을 할당한 사용자가 피드백을  제공하도록 허용하도록 **userInitiatedMode** 매개 변수를 사용하도록 설정합니다. 매개 변수를 사용하지 않도록 **설정하면** 기능이 해제되어 정책에 할당된 사용자에게 피드백을 줄 수 있는 옵션이 없습니다.
 - **설문 조사**: 정책에 할당된 사용자가 설문  조사를 받을 수 있도록 **하도록 receiveSurveysMode** 매개 변수를 사용하도록 설정합니다. 사용자가 설문 조사를 수신하고 옵트아웃할 수 있도록 설정하기 위해 매개 변수를 **enabledUserOverride로 설정합니다.** 이 Teams 사용자는 개인 정보 보호 설정 이동하여 설문 조사에 참여할지  >   여부를 선택할 수 있습니다. 매개 변수를 사용하지 않도록 **설정하면** 기능이 해제되어 정책이 할당된 사용자는 설문 조사를 받지 않습니다.
 - **전자 메일**: **AllowEmailCollection** 플래그를 사용하여 전자 메일 필드를 추가합니다.
 - **로그 컬렉션**: **AllowLogCollection** 플래그를 사용하여 사용자에 대한 로그 컬렉션 옵트인을 추가합니다. 로그 컬렉션은 현재 모바일에서만 사용하도록 설정되어 있습니다. 로그를 통해 공유되는 데이터에 대한 자세한 내용은 를 [참조합니다.](https://go.microsoft.com/fwlink/?linkid=2168178)

## <a name="create-a-custom-feedback-policy"></a>사용자 지정 피드백 정책 만들기

이 예제에서는 신규 고용 피드백 정책이라는 피드백 정책을 만들고 피드백 제공 및  설문 조사를 통해 피드백을 주는 기능을 해제합니다.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>사용자에게 사용자 지정 피드백 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

이 예제에서는 user1이라는 사용자에게 새 고용 피드백 정책이라는 사용자 지정 정책을 할당합니다.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>관련 주제

- [Teams PowerShell 개요](teams-powershell-overview.md)
- [Teams에서 사용자에게 정책 할당](assign-policies.md)
