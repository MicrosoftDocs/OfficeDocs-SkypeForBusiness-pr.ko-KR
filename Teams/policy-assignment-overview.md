---
title: Teams 정책 할당
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams 사용자 및 그룹에 정책 및 정책 패키지를 할당하는 다양한 방법을 알아봅니다.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 48d0e771f50379c548cc801d4f6a3c38bcc81f5e
ms.sourcegitcommit: 9968ef7d58c526e35cb58174db3535fd6b2bd1db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/09/2022
ms.locfileid: "65284093"
---
# <a name="assign-policies-in-teams--getting-started"></a>Teams 정책 할당 – 시작

관리자는 정책을 사용하여 조직의 사용자가 사용할 수 있는 Teams 기능을 제어합니다. 예를 들어 몇 가지 이름을 지정하는 통화 정책, 모임 정책 및 메시징 정책이 있습니다.

조직에는 고유한 요구 사항이 있는 다양한 유형의 사용자가 있습니다. 만들고 할당하는 사용자 지정 정책을 사용하면 이러한 요구 사항에 따라 다양한 사용자 집합에 정책 설정을 조정할 수 있습니다.

조직에서 정책을 쉽게 관리하기 위해 Teams 사용자에게 정책을 할당하는 여러 가지 방법을 제공합니다. 일괄 할당을 통해 개별적으로 또는 대규모로 또는 사용자가 구성원인 그룹에 직접 정책을 할당합니다. 정책 패키지를 사용하여 비슷한 역할을 가진 조직의 사용자에게 미리 설정된 정책 컬렉션을 할당할 수도 있습니다. 선택하는 옵션은 관리하는 정책 수와 정책을 할당하는 사용자 수에 따라 달라집니다. 전역(조직 전체 기본값) 정책은 조직에서 가장 많은 수의 사용자에게 적용됩니다. 특수한 정책이 필요한 사용자에게만 정책을 할당해야 합니다.

이 문서에서는 사용자에게 정책을 할당할 수 있는 다양한 방법과 사용 시기에 권장되는 시나리오에 대해 설명합니다.

**사용자 및 그룹에 정책을 할당하는** 방법에 대한 자세한 내용은 [사용자 및 그룹에 정책 할당을 참조하세요](assign-policies-users-and-groups.md). **정책 패키지를 할당** 하는 방법에 대한 자세한 내용은 [정책 패키지 할당을 참조하세요](assign-policy-packages.md).

## <a name="which-policy-takes-precedence"></a>어떤 정책이 우선적으로 적용되는가?

사용자에게는 각 정책 유형에 대해 하나의 효과적인 정책이 있습니다. 사용자에게 정책이 직접 할당되고 동일한 유형의 정책이 할당된 하나 이상의 그룹의 구성원일 수도 있습니다. 이러한 종류의 시나리오에서 어떤 정책이 우선적으로 적용되는가? 사용자의 유효 정책은 다음과 같이 우선 순위 규칙에 따라 결정됩니다.

사용자에게 정책이 직접 할당된 경우(개별적으로 또는 일괄 처리 할당을 통해) 해당 정책이 우선적으로 적용됩니다. 다음 시각적 예제에서 사용자의 유효 정책은 사용자에게 직접 할당되는 링컨 스퀘어 모임 정책입니다.

![직접 할당된 정책이 우선하는 방법을 보여 주는 다이어그램](media/assign-policies-example-directly-assigned.png)

사용자에게 지정된 형식의 정책이 직접 할당되지 않은 경우 사용자가 멤버인 그룹에 할당된 정책이 우선적으로 적용됩니다. 사용자가 여러 그룹의 구성원인 경우 지정된 정책 유형에 대해 가장 높은([그룹 할당 순위](assign-policies-users-and-groups.md#group-assignment-ranking))를 가진 정책이 우선적으로 적용됩니다.

이 시각적 예제에서 사용자의 유효 정책은 Exec Teams 및 HD 정책입니다. 이 정책은 사용자가 멤버이고 동일한 정책 유형의 정책이 할당된 다른 그룹에 비해 할당 순위가 가장 높습니다.  

![그룹에서 상속된 정책이 우선하는 방법을 보여 주는 다이어그램](media/assign-policies-example-group.png)

사용자에게 정책이 직접 할당되지 않았거나 정책이 할당된 그룹의 구성원이 아닌 경우 사용자는 해당 정책 유형에 대한 전역(조직 전체 기본값) 정책을 가져옵니다. 시각적 예제는 다음과 같습니다.

![전역 정책의 우선 순위를 보여 주는 다이어그램](media/assign-policies-example-global.png)

자세한 내용은 ([우선 순위 규칙](assign-policies-users-and-groups.md#precedence-rules))을 참조하세요.

## <a name="ways-to-assign-policies"></a>정책을 할당하는 방법

다음은 사용자에게 정책을 할당할 수 있는 방법과 각 사용자에게 권장되는 시나리오에 대한 개요입니다. 자세한 내용을 보려면 링크를 선택합니다.

개별 사용자 또는 그룹에 정책을 할당하기 전에 먼저 조직에서 가장 많은 수의 사용자에게 적용되도록 [전역(조직 전체 기본값) 정책을 설정합니다](#set-the-global-policies) .  전역 정책이 설정되면 특수화된 정책이 필요한 사용자에게만 정책을 할당해야 합니다.

|이 작업을 수행합니다.  |경우...  | 사용...
|---------|---------|----|
|[개별 사용자에게 정책 할당](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | Teams 시작하거나 소수의 사용자에게 하나 또는 몇 개의 정책만 할당하면 됩니다. |Teams PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet
|[그룹에 정책 할당](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |사용자의 그룹 멤버 자격에 따라 정책을 할당합니다. 예를 들어 보안 그룹 또는 배포 목록의 모든 사용자에게 정책을 할당합니다.| Teams PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet|
|[사용자 일괄 처리에 정책 할당](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | 대규모 사용자 집합에 정책을 할당합니다. 예를 들어 조직의 수백 또는 수천 명의 사용자에게 한 번에 정책을 할당합니다. |Teams PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet|
|[사용자에게 정책 패키지 할당](assign-policy-packages.md#assign-a-policy-package-to-users)  |동일하거나 유사한 역할을 가진 조직의 특정 사용자 집합에 여러 정책을 할당합니다. 예를 들어 학교의 교사에게 교육(교사) 정책 패키지를 할당하여 채팅, 통화 및 모임에 대한 모든 권한을 부여합니다. 교육(중등학생) 정책 패키지를 중등학생에게 할당하여 개인 통화와 같은 특정 기능을 제한합니다.  |Teams PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet|
|[그룹에 정책 패키지 할당](assign-policy-packages.md#assign-a-policy-package-to-a-group)  |동일하거나 유사한 역할을 가진 조직의 사용자 그룹에 여러 정책을 할당합니다. 예를 들어 보안 그룹 또는 배포 목록의 모든 사용자에게 정책 패키지를 할당합니다. |Teams PowerShell 모듈의 Microsoft Teams 관리 센터(출시 예정) 또는 PowerShell cmdlet|
|[사용자 일괄 처리에 정책 패키지 할당](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|동일하거나 유사한 역할을 가진 조직의 사용자 일괄 처리에 여러 정책을 할당합니다. 예를 들어 일괄 할당을 사용하여 학교의 모든 교사에게 교육(교사) 정책 패키지를 할당하여 채팅, 통화 및 모임에 대한 모든 권한을 부여합니다. 교육(중등학생) 정책 패키지를 중등학생 일괄 처리에 할당하여 개인 통화와 같은 특정 기능을 제한합니다.|Teams PowerShell 모듈의 PowerShell cmdlet|

## <a name="set-the-global-policies"></a>전역 정책 설정

각 정책 유형에 대한 전역(조직 전체 기본값) 정책을 설정하려면 다음 단계를 수행합니다.

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 업데이트하려는 정책 유형에 대한 정책 페이지로 이동합니다. 예를 들어 **Teams** >  **Teams 정책**, **MeetingsMeetings** >  정책, **메시징 정책** 또는 **VoiceCalling** >  정책입니다.
2. **전역(조직 전체 기본값)** 정책을 선택하여 현재 설정을 봅니다.
3. 필요에 따라 정책을 업데이트한 다음 적용 **을 선택합니다.**

![Teams 관리 센터에서 전역 정책을 업데이트합니다.](media/assign-globalpolicy.png)

### <a name="using-powershell"></a>PowerShell 사용

PowerShell을 사용하여 전역 정책을 설정하려면 전역 식별자를 사용합니다.  먼저 현재 전역 정책을 검토하여 변경할 설정을 결정합니다.

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

다음으로, 필요에 따라 전역 정책을 업데이트합니다.  변경하려는 설정의 값만 지정하면 됩니다.

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="view-your-policy-assignments-in-the-activity-log"></a>활동 로그에서 정책 할당 보기

Microsoft Teams 관리 센터의 사용자에게 정책을 할당할 때 [활동 로그](https://admin.teams.microsoft.com/activitylog)에서 해당 정책 할당의 상태를 볼 수 있습니다. 활동 로그에는 네트워크 레코드 업로드 정보, Teams 관리 센터 및 PowerShell의 그룹 정책 작업 및 지난 30일 동안 Teams 관리 센터의 일괄 처리 정책 작업(20명 이상의 사용자용)이 표시됩니다.

![활동 로그 페이지의 스크린샷.](media/Activity_Log.png)

활동 로그에서 정책 작업을 보려면 다음을 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **대시보드** 로 이동한 다음 **활동 로그** 아래에서 **세부 정보 보기를** 선택합니다.
2. 각 정책 작업에 대한 다음 정보가 표시됩니다.
    - **작업**: 정책 작업의 이름입니다. 예: **그룹 정책 할당**
    - **그룹 이름**: 정책 작업이 완료된 그룹의 이름입니다.
    - **정책 유형**: 정책 유형입니다.
    - **정책 이름**: 정책 작업의 이름입니다. 일괄 처리 정책 할당의 경우 링크를 선택하여 자세한 내용을 볼 수 있습니다. 여기에는 정책이 할당된 사용자 수와 완료된 할당 수, 진행 중 및 시작되지 않은 할당 수가 포함됩니다. 일괄 처리의 사용자 목록과 각 사용자의 상태 및 결과도 표시됩니다.
    - **제출자**: 정책 작업을 제출한 사용자의 이름입니다.
    - **제출 날짜**: 정책 작업이 제출된 날짜 및 시간입니다.
    - **완료 날짜**: 정책 작업이 완료된 날짜 및 시간입니다.
    - **영향**: 일괄 처리 또는 그룹의 사용자 수입니다.
    - **전체 상태**: 정책 작업의 상태입니다. 정책에는 다음 상태 중 하나가 있을 수 있습니다.
        - **시작되지 않음**: 관리자가 정책 작업을 제출했습니다.
        - **진행 중**: 정책 작업이 처리를 시작했습니다.
        - **사용자에게 배포**: 시스템이 사용자에게 정책 업데이트를 적용하기 시작했습니다.
        - **완료됨**: 정책 업데이트가 모든 사용자에게 적용되었습니다.
        - **'x' 오류로 완료** 됨: 정책 작업이 완료되었지만 오류가 있습니다.

> [!NOTE]
> **사용자** 페이지에서 활동 로그로 가져올 수도 있습니다. **적용** 을 선택하여 대량 정책 할당을 제출하면 페이지 맨 위에 배너가 표시됩니다. 배너에서 **활동 로그** 링크를 선택합니다.

## <a name="related-topics"></a>관련 항목

- [사용자 및 그룹에 정책 할당](assign-policies-users-and-groups.md)
- [사용자 및 그룹에 정책 패키지 할당](assign-policy-packages.md)
- [정책을 사용하여 Teams 관리](manage-teams-with-policies.md)
- [Teams PowerShell 개요](teams-powershell-overview.md)
