---
title: Microsoft Teams에서 피드백 정책 관리
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: msedliak
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
localization_priority: Normal
search.appverid: MET150
description: 피드백 정책을 사용하여 조직의 Teams 사용자가 Teams에 대한 피드백을 Microsoft에 제출할 수 있는지 여부를 제어하는 방법을 알아보습니다.
ms.openlocfilehash: bc925320959c55b2fa06c8480f1011aab81aae9c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094268"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Microsoft Teams에서 피드백 정책 관리

[!INCLUDE [preview-feature](includes/preview-feature.md)]

조직의 사용자는 Teams 데스크톱 및 웹 클라이언트 내에서 직접 Teams에 대한 피드백을 Microsoft에 보낼 수 있습니다. Teams 환경을 지속적으로 개선하고 있으며 이 피드백을 사용하여 Teams를 개선합니다.

> [!NOTE]
> 피드백 정책은 GCC, GCC High 또는 DOD 배포에서 사용할 수 없습니다.

**피드백 제공 기능**

사용자는 Teams에서 피드백을 제공하면 Teams에 대한 의견과 제안을 보낼  >   수 있습니다. 피드백 **제공을** 통해 전송된 데이터는 Microsoft 365 또는 Office 365 계약에 따라 "고객 데이터" 또는 "개인 데이터"로 간주되는 정보를 포함하여 "지원 데이터"로 간주됩니다.

![Teams에서 피드백 제공 옵션 스크린샷](media/manage-feedback-policies-in-teams-give-feedback.png)

**설문 조사**

또한 사용자는 Teams에 대한 경험을 평가하고 제공한 등급에 대한 세부 정보를 보낼 수 있습니다. 이 팝업 설문 조사는 Teams에서 수시로 사용자에게 표시됩니다. 사용자가 알림에서  피드백 제공을 클릭하면 설문 조사가 완료될 수 있습니다.

![Teams의 설문 조사 알림 및 양식 스크린샷](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>사용자가 Teams에 대한 피드백을 Microsoft로 보낼 수 있는지 여부를 설정합니다.

관리자는 조직의 사용자가 피드백 제공을 통해 Teams에 대한 피드백을  Microsoft에 보낼 수 있는지 여부와 설문 조사를 받을지 여부를 제어할 수 있습니다. 기본적으로 조직의 모든 사용자에게 전역(조직 전체 기본값) 정책이 자동으로 할당되고 피드백 제공 기능 및 설문 조사가 정책에서 활성화됩니다.  예외는 교육용 Teams입니다. 여기서는 교사가 기능을 사용하도록 설정하고 학생들을 위해 사용하지 않도록 설정됩니다.

전역 정책을 편집하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 전역 정책을 편집하거나 사용자 지정 정책을 할당한 후 변경 내용이 적용될 수 있는 데 몇 시간이 걸릴 수 있습니다.

예를 들어 조직의 모든 사용자가 피드백 제공을 통해 피드백을 보내고 교육에서 신규 고용을 제외한 설문 조사를 받을 수 있도록 허용하려는 경우를 예로 들 수 있습니다.  이 시나리오에서는 두 기능을 모두 해제하고 새 고용에 할당하는 사용자 지정 정책을 만들 수 있습니다. 조직의 다른 모든 사용자는 기능이 켜져 있는 전역 정책을 얻습니다.  

PowerShell을 사용하여 피드백 정책을 관리합니다. 여기서 찾을 수 있는 **New-CsTeamsFeedbackPolicy** cmdlet을 사용하여 사용자 지정 정책 및 **Grant-CsTeamsFeedbackPolicy** cmdlet을 만들어 하나 이상의 사용자 또는 사용자 그룹에 할당합니다(예: 보안 그룹 또는 메일 그룹). *[](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*

기능을 끄고 켜기 위해 다음 매개 변수를 설정합니다.

 - **피드백 제공:** 정책을 할당한 사용자가 피드백을  제공하도록 허용하도록 **userInitiatedMode** 매개 변수를 사용하도록 설정합니다. 매개 변수를 사용하지 않도록 **설정하면** 기능이 해제되어 정책에 할당된 사용자에게 피드백을 줄 수 있는 옵션이 없습니다.
 - **설문 조사**: 정책에 할당된 사용자가 설문  조사를 받을 수 있도록 **하도록 receiveSurveysMode** 매개 변수를 사용하도록 설정합니다. 사용자가 설문 조사를 수신하고 옵트아웃할 수 있도록 설정하기 위해 매개 변수를 **enabledUserOverride로 설정합니다.** 그런 다음 Teams에서 사용자는 설정 개인 정보로 이동하여 설문 조사에 참여할지  >   여부를 선택할 수 있습니다. 매개 변수를 사용하지 않도록 **설정하면** 기능이 해제되어 정책이 할당된 사용자는 설문 조사를 받지 않습니다.

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

## <a name="related-topics"></a>관련 항목

- [Teams PowerShell 개요](teams-powershell-overview.md)
- [Teams에서 사용자에게 정책 할당](assign-policies.md)