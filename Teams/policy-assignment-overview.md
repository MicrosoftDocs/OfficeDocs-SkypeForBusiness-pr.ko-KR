---
title: 정책 할당 Teams
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
description: 정책 및 정책 패키지를 사용자 및 그룹에 할당하는 다양한 방법을 Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: fb85ae05925a44db75ed63ada899c6fca92cbceb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621990"
---
# <a name="assign-policies-in-teams--getting-started"></a>Teams 정책 할당 - 시작

관리자는 정책을 사용하여 조직의 Teams 사용할 수 있는 기능을 제어합니다. 예를 들어 몇 가지 이름을 지정하는 호출 정책, 모임 정책 및 메시징 정책이 있습니다.

조직에는 고유한 요구 사항을 가지는 다양한 유형의 사용자가 있습니다. 만들고 할당하는 사용자 지정 정책을 사용하면 이러한 요구에 따라 다양한 사용자 집합에 정책 설정을 조정할 수 있습니다.

조직의 정책을 쉽게 관리하기 위해 Teams 여러 가지 방법으로 정책을 할당할 수 있습니다. 일괄 처리 할당을 통해 개별적으로 또는 규모에 따라 사용자에게 직접 정책을 할당하거나 사용자가 구성원인 그룹에 할당합니다. 정책 패키지를 사용하여 유사한 역할이 있는 조직의 사용자에게 미리 설정한 정책 컬렉션을 할당할 수도 있습니다. 선택하는 옵션은 관리하는 정책의 수와 정책을 할당하는 사용자 수에 따라 달라 습니다. 전역(조직 전체 기본값) 정책은 조직의 가장 많은 사용자 수에 적용됩니다. 특수한 정책이 필요한 사용자에게만 정책을 할당해야 합니다.

이 문서에서는 사용자에게 정책을 할당할 수 있는 다양한 방법과 이를 사용할 때 권장되는 시나리오에 대해 설명합니다.

사용자 및 그룹에 정책을 할당하는 방법에 대한 자세한 내용은 **사용자** 및 그룹에 정책 [할당을 참조합니다.](assign-policies-users-and-groups.md) 정책 패키지를 할당하는 방법에 대한 자세한 내용은 **정책** 패키지 [할당을 참조합니다.](assign-policy-packages.md)

## <a name="which-policy-takes-precedence"></a>우선 순위는 어떤 정책인가요?

사용자에게는 각 정책 유형에 대해 하나의 효과적인 정책이 있습니다. 사용자가 정책을 직접 할당하고 동일한 유형의 정책을 할당한 하나 이상의 그룹의 구성원일 수도 있습니다. 이러한 종류의 시나리오에서 어떤 정책이 우선인가요? 사용자의 유효 정책은 다음과 같이 우선 순위 규칙에 따라 결정됩니다.

사용자가 정책(개별적으로 또는 일괄 처리 할당을 통해)을 직접 할당하는 경우 해당 정책이 우선합니다. 다음 시각적 예제에서 사용자의 효과적인 정책은 사용자에게 직접 할당되는 Lincoln Square 모임 정책입니다.

![직접 할당된 정책이 우선하는 방법을 보여주는 다이어그램](media/assign-policies-example-directly-assigned.png)

사용자가 지정된 유형의 정책을 직접 할당하지 않은 경우 사용자가 구성원인 그룹에 할당된 정책이 우선합니다. 사용자가 여러 그룹의 구성원인 경우 지정한 정책 유형에 대해 가장 높은(그룹 할당 순위)를 가지는 정책이 우선합니다.[](assign-policies-users-and-groups.md#group-assignment-ranking)

이 시각적 예제에서 사용자의 효과적인 정책은 Exec Teams HD 정책으로, 이 정책은 사용자가 구성원으로 있는 다른 그룹에 비해 가장 높은 할당 순위를 가지며 동일한 정책 유형의 정책도 할당됩니다.  

![그룹에서 상속된 정책이 우선하는 방법을 보여주는 다이어그램](media/assign-policies-example-group.png)

사용자가 정책을 직접 할당하지 않은 경우 또는 정책이 할당된 그룹의 구성원이 아닌 경우 사용자는 해당 정책 유형에 대한 전역(Org-wide default) 정책을 얻습니다. 다음은 시각적 예제입니다.

![전역 정책의 우선 순위를 보여주는 다이어그램](media/assign-policies-example-global.png)

자세한 내용은[(우선 순위 규칙)를 참조합니다.](assign-policies-users-and-groups.md#precedence-rules)

## <a name="ways-to-assign-policies"></a>정책을 할당하는 방법

사용자에게 정책을 할당할 수 있는 방법과 각 시나리오에 대해 권장되는 시나리오에 대한 개요는 다음과 같습니다. 자세한 내용은 링크를 선택합니다.

개별 사용자 또는 그룹에 정책을 할당하기 전에 먼저 조직에서 가장 많은 사용자 수에 적용할 수 있도록 전역(조직 전체 [기본값)](#set-the-global-policies) 정책을 설정해야 합니다.  전역 정책을 설정하면 특수한 정책이 필요한 사용자에게만 정책을 할당해야 합니다.

|이 작업을  |경우...  | 사용 중...
|---------|---------|----|
|[개별 사용자에게 정책 할당](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | 새로운 사용자 Teams 시작하거나 소수의 사용자에게 정책 하나 또는 두 개만 할당하면 됩니다. |PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet Teams
|[그룹에 정책 할당](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |사용자의 그룹 구성원 자격에 따라 정책을 할당합니다. 예를 들어 보안 그룹 또는 메일 그룹의 모든 사용자에게 정책을 할당합니다.| PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet Teams|
|[사용자 일괄 처리에 정책 할당](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | 대규모 사용자 집합에 정책을 할당합니다. 예를 들어 조직에서 수백 또는 수천 명의 사용자에게 정책을 할당합니다. |PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet Teams|
|[사용자에게 정책 패키지 할당](assign-policy-packages.md#assign-a-policy-package-to-users)  |동일한 역할 또는 유사한 역할이 있는 조직의 특정 사용자 집합에 여러 정책을 할당합니다. 예를 들어 학교의 교사에게 교육(교사) 정책 패키지를 할당하여 채팅, 통화 및 모임에 대한 모든 액세스 권한을 부여합니다. 중등 학생에게 교육(중등 학생) 정책 패키지를 할당하여 개인 통화와 같은 특정 기능을 제한합니다.  |PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet Teams|
|[그룹에 정책 패키지](assign-policy-packages.md#assign-a-policy-package-to-a-group) 할당(비공개 미리 보기에서)   |동일한 역할 또는 유사한 역할이 있는 조직의 사용자 그룹에 여러 정책을 할당합니다. 예를 들어 보안 그룹 또는 메일 그룹의 모든 사용자에게 정책 패키지를 할당합니다. |PowerShell Microsoft Teams 관리 센터 또는 PowerShell Teams cmdlet|
|[사용자 일괄 처리에 정책 패키지 할당](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|동일한 역할 또는 유사한 역할이 있는 조직의 사용자 일괄 처리에 여러 정책을 할당합니다. 예를 들어 일괄 처리 과제를 사용하여 학교의 모든 교사에게 교육(교사) 정책 패키지를 할당하여 채팅, 통화 및 모임에 대한 모든 액세스 권한을 부여합니다. 사설 통화와 같은 특정 기능을 제한하기 위해 중등 학생 일괄 처리에 교육(중등 학생) 정책 패키지를 할당합니다.|PowerShell 모듈의 PowerShell Teams cmdlet|

## <a name="set-the-global-policies"></a>전역 정책 설정

다음 단계를 수행하여 각 정책 유형에 대해 전역(Org-wide default) 정책을 설정합니다.

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 관리 센터의 왼쪽 Microsoft Teams 업데이트할 정책 유형에 대한 정책 페이지로 이동합니다. 예를 들어 Teams **Teams** 모임 정책, 메시징 정책 또는 음성 통화 정책 을  >  사용할   >  수    >  **있습니다.**
2. **전역(Org-wide 기본값)** 정책을 선택하여 현재 설정을 확인합니다.
3. 필요한 경우 정책을 업데이트한 다음 적용을 **선택합니다.**

![관리 센터에서 전역 Teams 업데이트](media/assign-globalpolicy.png)

### <a name="using-powershell"></a>PowerShell 사용

PowerShell을 사용하여 전역 정책을 설정하기 위해 전역 식별자를 사용 합니다.  먼저 현재 전역 정책을 검토하여 변경할 설정을 파악합니다.

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

다음으로, 필요한 경우 전역 정책을 업데이트합니다.  변경할 설정의 값만 지정하면 됩니다.

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="view-your-policy-assignments-in-the-activity-log"></a>활동 로그에서 정책 할당 보기

관리 센터의 사용자에게 정책을 Microsoft Teams 경우 활동 로그에서 해당 정책 할당의 상태를 볼 수 있습니다. 활동 로그는 지난 30일 동안 관리 센터를 통해 20명 Microsoft Teams 일괄 처리에 대한 정책 할당을 보여줍니다. 활동 로그는 PowerShell을 통해 정책 패키지 할당, 20명 미만의 사용자 일괄 처리에 대한 정책 할당을 Microsoft Teams 없습니다.

![활동 로그 페이지의 스크린샷](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>활동 로그에서 정책 할당 활동 보기

활동 로그에서 정책 할당을 확인하려면 다음을 수행합니다.

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams 대시보드로 이동한 다음 활동 로그에서 **세부** **정보 보기를 선택합니다.**
2. 모든 정책 할당을 보거나 상태를 통해 목록을 필터링하여 시작되지 않은  **과제,** 진행 중 또는 완료된 과제만 **표시할 수 있습니다.** 각 과제에 대한 다음 정보가 표시됩니다.
    - **이름**: 정책 할당의 이름입니다. 링크를 클릭하여 자세한 내용을 볼 수 있습니다. 여기에는 정책이 할당된 사용자 수와 완료된 과제 수가 포함되고 진행 중입니다. 또한 일괄 처리의 사용자 목록과 각 사용자의 상태 및 결과가 표시됩니다. 다음은 예제입니다.

        ![스크린샷](media/activity-log-policy-assignment-detail.png)

    - **제출**: 정책 할당이 제출된 날짜 및 시간입니다.
    - **완료 시간**: 정책 할당이 완료된 날짜 및 시간입니다.
    - **영향**: 일괄 처리의 사용자 수입니다.
    - **전체 상태**: 정책 할당의 상태입니다.

> [!NOTE]
> 사용자 페이지에서 활동 로그에 **얻을** 수도 있습니다. 적용을  클릭하여 대량 정책 할당을 제출하면 페이지 맨 위에 배너가 표시됩니다. **배너에서 활동 로그** 링크를 클릭합니다.

## <a name="related-topics"></a>관련 주제

- [사용자 및 그룹에 정책 할당](assign-policies-users-and-groups.md)
- [사용자 및 그룹에 정책 패키지 할당](assign-policy-packages.md)
- [정책으로 Teams 관리](manage-teams-with-policies.md)
- [Teams PowerShell 개요](teams-powershell-overview.md)