---
title: Microsoft Teams에서 피드백 정책 관리
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: 피드백 정책을 사용하여 조직의 Teams 사용자가 Teams에 대한 피드백을 Microsoft에 제출할 수 있는지 여부를 제어하는 방법을 알아봅니다.
ms.openlocfilehash: 933c6971058c107ab881cb48bb0f2a9dbd74900d
ms.sourcegitcommit: 44fd07d8e6e5fcbe5051de2300e180f295eaaad3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2022
ms.locfileid: "67339802"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>Microsoft Teams에서 피드백 정책 관리

조직의 사용자는 Microsoft Teams에 대한 피드백을 보내 Teams 데스크톱, 웹 클라이언트 및 모바일 내에서 직접 수행하는 방법을 알려줄 수 있습니다. Teams 환경을 지속적으로 개선하고 있으며 이 피드백을 사용하여 Teams를 개선합니다.

> [!NOTE]
> GCC, GCC High 또는 DOD 배포에서는 피드백 정책을 사용할 수 없습니다.

****피드백 제공** 기능**

사용자는 Teams 데스크톱 및 웹에서 **피드백을 제공하는** **데 도움을** >  주며 Teams에 대한 의견과 제안을 보낼 수 있습니다.


![Teams에서 피드백 옵션 제공](media/manage-feedback-policies-in-teams-give-feedback.png)

**설정** > **도움말 & 피드백을****보내 피드백을** 사용하여 모바일에 대한 피드백  >  에 액세스합니다.

![모바일의 Teams에서 피드백 옵션 제공](media/feedback3.jpg)

 **피드백 제공** 및 **피드백 보내기** 를 통해 전송된 데이터는 "고객 데이터" 또는 "개인 데이터"로 간주되는 정보를 포함하여 Microsoft 365 또는 Office 365 계약에 따라 "지원 데이터"로 간주됩니다.



**설문 조사**

또한 사용자는 Teams에 대한 경험을 평가하고 제공하는 등급에 대한 세부 정보를 보낼 수 있습니다. 이 팝업 설문 조사는 Teams에서 수시로 사용자에게 표시됩니다. 사용자가 알림에서 **피드백 제공** 을 선택하면 설문 조사가 완료되도록 표시됩니다.

![Teams의 설문 조사 알림 및 양식](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>사용자가 Teams에 대한 피드백을 Microsoft에 보낼 수 있는지 여부 설정

관리자는 조직의 사용자가 Teams에 대한 피드백을 Microsoft에 보낼 수 있는지 여부와 설문 조사를 받을지 여부를 제어할 수 있습니다. 기본적으로 조직의 모든 사용자에게 전역(조직 전체 기본값) 정책이 자동으로 할당되고 정책에서 피드백 기능 및 설문 조사가 사용하도록 설정됩니다. 예외는 교육용 Teams 있습니다. 여기서 기능은 교사에 대해 사용하도록 설정되고 학생은 사용하지 않도록 설정됩니다.

전역 정책을 편집하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 전역 정책을 편집하거나 사용자 지정 정책을 할당한 후 변경 내용이 적용되는 데 몇 시간이 걸릴 수 있습니다.

예를 들어 조직의 모든 사용자가 피드백을 보내고 교육에서 신입 사원을 제외한 설문 조사를 받을 수 있도록 허용하려고 합니다. 이 시나리오에서는 두 기능을 모두 끄고 신규 채용 담당자에게 할당하는 사용자 지정 정책을 만듭니다. 조직의 다른 모든 사용자는 기능이 켜져 있는 전역 정책을 받습니다.  

PowerShell을 사용하여 피드백 정책을 관리합니다. [**New-CsTeamsFeedbackPolicy** cmdlet](/powershell/module/skype/new-csteamsfeedbackpolicy)을 사용하여 사용자 지정 정책을 만듭니다. **Grant-CsTeamsFeedbackPolicy** cmdlet을 사용하여 보안 그룹 또는 메일 그룹과 같은 하나 이상의 사용자 또는 사용자 그룹에 할당합니다. **Set-CsTeamsFeedbackPolicy** 를 사용하여 특정 플래그를 설정합니다.

기능을 끄고 켜려면 다음 매개 변수를 설정합니다.

 - **피드백 제공**: 정책이 할당된 사용자가 피드백을 제공할 수 있도록 **userInitiatedMode** 매개 변수를 **사용하도록** 설정합니다. 매개 변수를 **사용하지 않도록** 설정하면 기능이 해제되고 정책이 할당된 사용자에게 피드백을 제공할 수 있는 옵션이 없습니다.

 - **설문 조사**: 정책이 할당된 사용자가 설문 조사를 받을 수 있도록 **receiveSurveysMode** 매개 변수를 **사용하도록** 설정합니다. 사용자가 설문 조사를 받고 옵트아웃하도록 허용하려면 매개 변수를 **enabledUserOverride** 로 설정합니다. Teams에서 사용자는 **설정** > **개인 정보 보호** 로 이동하여 설문 조사에 참여할지 여부를 선택할 수 있습니다. 매개 변수를 **사용하지 않도록** 설정하면 기능이 해제되고 정책이 할당된 사용자는 설문 조사를 받지 못합니다.

 - **스크린샷**: **AllowScreenshotCollection** 플래그를 사용하여 사용자에 대한 스크린샷 컬렉션 옵트인을 추가합니다.
 - **Email**: **AllowEmailCollection** 플래그를 사용하여 전자 메일 필드를 추가합니다.
 - **로그 컬렉션**: **AllowLogCollection** 플래그를 사용하여 사용자에 대한 로그 컬렉션 옵트인을 추가합니다. 로그 수집은 현재 모바일에서만 사용하도록 설정되어 있습니다. 로그를 통해 공유되는 데이터에 대한 자세한 내용은 [자세히 알아보세요](https://go.microsoft.com/fwlink/?linkid=2168178).

## <a name="create-a-custom-feedback-policy"></a>사용자 지정 피드백 정책 만들기

이 예제에서는 신입 사원 피드백 정책이라는 피드백 정책을 만들고 **피드백** 제공 및 설문 조사를 통해 피드백을 제공하는 기능을 해제합니다.

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>사용자에게 사용자 지정 피드백 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

이 예제에서는 user1이라는 사용자에게 New Hire 피드백 정책이라는 사용자 지정 정책을 할당합니다.

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>관련 주제

- [Teams PowerShell 개요](teams-powershell-overview.md)
- [Teams에서 사용자에게 정책 할당](policy-assignment-overview.md)
