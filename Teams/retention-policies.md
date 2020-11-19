---
title: Microsoft Teams의 보존 정책
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 이 문서에서는 보존 정책 및 Microsoft 팀에서이를 만들고 관리 하는 방법에 대해 설명 합니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3b7854af353b9619a1e668006c4e143ac8d37e77
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130659"
---
# <a name="retention-policies-in-microsoft-teams"></a>Microsoft Teams의 보존 정책

보존 정책은 조직에서 정보를 더 효과적으로 관리하는 데 도움이 됩니다. 보존 정책을 사용하여 조직의 내부 정책, 업계 규제 또는 법적 요구 사항을 준수하는 데 필요한 데이터를 유지하고, 책임으로 간주되거나, 더 이상 유지할 필요가 없거나 또는 법적 혹은 비즈니스적 가치가 없는 데이터를 삭제합니다.

보존 정책, 사용자 삭제, 관리자 삭제 등을 통해 콘텐츠를 삭제 하려고 하지 않는 한 기본적으로 팀 채팅, 채널 및 파일 데이터는 무기한 유지 됩니다. 관리자는 채팅 및 채널 메시지에 대 한 팀 보존 정책을 설정 하 고 데이터 유지, 삭제 또는 특정 기간 동안 보존 하도록 사전에 결정 하 고 삭제할 수 있습니다.

[Microsoft 365 준수 센터](https://protection.office.com/) 에서 팀과 기타 작업 부하에 대 한 보존 정책을 만들고 관리 하거나 보안 & 준수 센터 PowerShell cmdlet을 사용 합니다. Teams 보존 정책을 전체 조직 또는 특정 사용자 및 팀에 적용할 수 있습니다.

> [!NOTE]
> 아직 개인 채널 메시지 보존에 대 한 구성은 지원 하지 않습니다. 비공개 채널에서 공유된 파일의 보존이 지원됩니다.

Microsoft 365 또는 Office 365의 보존 정책에 대해 자세히 알아보려면 [보존 정책 개요](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)를 참조 하세요.

## <a name="what-are-retention-policies-for-teams"></a>팀의 보존 정책

Teams 또는 다른 작업에 대한 보존 정책을 설정할 때 다음과 같이 설정할 수 있습니다.

- **데이터 보존**: 사용자 앱에서 일어나는 일과 관계없이 보존 정책을 사용하여 일정 기간 데이터를 보존합니다. 데이터는 규정 준수를 위해 보존되며 보존 기간이 만료될 때까지 eDiscovery에서 사용할 수 있으며, 이후 정책에 따라 아무런 작업도 수행하지 않을지 또는 데이터를 삭제할 것인지가 표시됩니다. 예를 들어, 채널 메시지를 7년간 보존하는 Teams 보존 정책을 만드는 경우 사용자가 Teams에서 메시지를 삭제하더라도 7년 동안 eDiscovery를 위해 메시지가 보존됩니다.
- **데이터 삭제**: 보존 정책을 사용하여 데이터를 삭제하고, 조직의 책임을 해소합니다. Teams 보존 정책을 통해 데이터를 삭제하면 Teams 서비스의 모든 저장 위치에서 영구적으로 삭제됩니다.

Teams 보존 정책을 통해 다음을 수행할 수 있습니다.

- Teams 채팅 및/또는 채널 메시지를 일정 기간 유지하고 아무런 작업도 수행하지 않습니다.
- Teams 채팅 및/또는 채널 메시지를 일정 기간 유지하고 데이터를 삭제합니다.
- Teams 채팅 및/또는 채널 메시지를 일정 기간 유지하고 아무런 작업도 수행하지 않습니다.

> [!NOTE]
> Teams에서 사용자가 비공개 채팅에서 공유하는 파일은 파일을 공유한 사용자의 비즈니스용 OneDrive 계정에 저장됩니다. 또한 팀 구성원이 채널 대화에 업로드하는 파일은 팀의 SharePoint 사이트에 저장됩니다. 따라서 Teams에서 파일을 보존하거나 삭제하려면 비즈니스용 OneDrive 및 SharePoint Online에 적용되는 보존 정책을 만듭니다.

데이터에 보존 정책이 적용되는 경우 데이터가 원래 위치에 그대로 유지되므로 사용자는 계속해서 작업할 수 있습니다. 사용자가 정책의 대상이 되는 데이터를 편집하거나 삭제하는 경우 정책이 적용되는 동안 보존되는 안전한 위치에 사본이 저장됩니다.

보존 정책에 대한 최소 라이선스 요구 사항은 Office 365 E3입니다. 라이선스에 대해 자세히 알아보려면 [Microsoft 팀 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)참조 하세요.

## <a name="how-teams-retention-policies-work"></a>Teams 보존 정책 작동 방식

팀 채팅은 채팅에 있는 각 사용자의 사서함에 숨겨진 폴더 (Teamschat)에 저장 되며, 팀 채널 메시지는 그룹 사서함의 숨겨진 폴더 (Teamschat)에 저장 됩니다. Teams가 사용하는 Azure 기반 채팅 서비스에서도 이 데이터를 저장하고 기본적으로 이 서비스는 데이터를 영구적으로 저장합니다. Teams 보존 정책을 사용하여 데이터를 삭제하면 Exchange 사서함과 기본 채팅 서비스 모두에서 데이터가 영구적으로 삭제됩니다.

팀 대화방 또는 채널 메시지에 **보존** 정책을 적용 하면 다음과 같은 현상이 발생 합니다.

- 보존 기간 동안 사용자가 채팅 또는 채널 메시지를 편집 하거나 삭제 한 경우에는 메시지가 복사 (편집 된 경우) 되거나 이동 (삭제 된 경우) 하 고 보존 기간이 만료 될 때까지이 폴더에 저장 됩니다. 보존 기간이 만료될 때 데이터를 삭제하도록 정책을 구성하면 메시지는 보존 기간이 만료되는 날에 영구적으로 삭제됩니다.
- **보존** 기간 동안 사용자가 채팅 또는 채널 메시지를 삭제 하지 않으면 보존 기간이 만료 된 후 1 일 내에 메시지가 하위 Strate보류가 포함 된 폴더로 이동 합니다. 보존 기간이 만료될 때 데이터를 삭제하도록 정책을 구성하면 메시지가 폴더로 이동된 후 하루가 지나면 메시지가 영구적으로 삭제됩니다.

팀 대화방 및 채널 메시지에 **보존-삭제** 정책을 적용 하면 다음과 같은 현상이 발생 합니다.

- 채팅 또는 채널 메시지가 만료 되는 경우 (예: **보존-삭제** 정책, 백 엔드 서비스)가 만료 된 메시지를 식별 하 고 백엔드 저장소 (사용자 또는 그룹 사서함)에서 삭제를 시작 하는 메시지의 보관 기간
- 백 엔드 저장소에서 메시지가 삭제 되 면 프로세스가 트리거되어 Azure가 제공 하는 채팅 서비스와 사용자의 팀 앱에서 같은 메시지를 삭제 합니다. 팀 앱에서 메시지를 삭제 하려면 앱이 인터넷에 연결 되어 있고 유휴 상태 (사용자 활동 없음)에 있어야 삭제 프로세스가 사용자 환경을 방해 하지 않습니다. 사용자에 게 여러 장치가 있을 수 있으며, 다른 상태에 있을 수 있으므로 보존 삭제가 동시에 해당 장치와 동기화 되지 않습니다.
- 백 엔드 저장소에서 메시지 삭제가 완료 되 면 eDiscovery와 같은 준수 검색 보고서에 표시 되는 메시지가 중지 됩니다.

> [!NOTE]
> 비즈니스용 Skype Online 및 Teams interop 채팅에도 동일한 흐름이 적용됩니다. 비즈니스용 Skype Online 채팅이 Teams로 이동하는 경우 해당 채팅은 Teams 채팅 스레드에서 메시지가 되고 해당 사서함에 수집됩니다. Teams 보존 정책은 이러한 메시지를 Teams 스레드에서 삭제합니다. 그러나 비즈니스용 Skype Online 및 비즈니스용 Skype Online 클라이언트 쪽에서 대화 기록을 켜는 경우, 채팅 데이터는 사서함에 저장되고 Teams 보존 정책에 의해 처리되지 않습니다.

> [!NOTE]
> 메시지 삭제는 영구적 이며 되돌릴 수 없습니다.

Teams의 보존 정책은 채팅 또는 채널 메시지가 생성된 날짜를 기준으로 하며 소급 적용됩니다. 즉, 90일보다 오래된 데이터를 삭제하는 보존 정책을 만드는 경우 90일 전에 생성된 Teams 데이터가 삭제됩니다.

SharePoint Online 또는 비즈니스 용 OneDrive에 적용되는 보존 정책은 해당 메시지가 삭제되기 전에 Teams 채팅 또는 채널 메시지에서 참조되는 파일을 삭제할 수 있습니다. 이 시나리오에서는 파일이 Teams 메시지에 여전히 표시되지만, 사용자가 파일을 클릭하면 "파일을 찾을 수 없음" 오류가 발생합니다. 정책이 없을 때 누군가가 SharePoint Online 또는 비즈니스용 OneDrive에서 파일을 수동으로 삭제하는 경우에도 해당 문제가 발생할 수 있습니다.

### <a name="considerations-and-limitations"></a>고려 사항 및 제한 사항

다음은 Teams 보존 정책을 사용할 때 알아야 할 몇 가지 고려 사항과 제한 사항입니다.

- Teams에는 다른 작업과는 별도의 보존 정책이 필요합니다. 즉, Teams 채팅 및/또는 채널 메시지에 대한 특정 보존 정책을 만들어야 합니다. 따라서 조직 전체 보존 정책에 Teams를 포함할 수 없습니다.

- 비공개 채널 메시지는 지원되지 않습니다. 현재 Teams의 보존 정책은 표준 채널 메시지에만 적용됩니다.

- Teams는 키워드 또는 민감한 정보를 포함하는 콘텐츠에 정책을 적용하는 기능과 같은 고급 보존 설정을 지원하지 않습니다. 현재 Teams의 보존 정책은 모든 채팅 및/또는 채널 메시지 콘텐츠에 적용됩니다.

- 팀 보존 정책은 메시지 생성 날짜에 따라 해당 메시지가 만료 되는 경우 채팅 및 채널 메시지를 삭제 하는 프로세스를 트리거합니다. 그러나 서비스 로드에 따라 백엔드 저장소 및 팀 앱에서 이러한 메시지를 영구적으로 삭제 하는 데 최대 7 일이 걸릴 수 있습니다. 또한 이러한 메시지는 사용자가 백엔드 저장소에서 영구적으로 삭제 될 때까지 준수 도구 (eDiscovery, 최종 사용자 검색)를 사용 하 여 검색할 수 있습니다.

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a>복수의 보존 정책 및 보존 원칙

기간이 다른 Teams 보존 정책을 여러 개 설정하는 경우 [보존 정책 원칙](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence)이 적용됩니다. 우선 순위에 대한 개요는 다음과 같습니다.

- 보존은 항상 삭제보다 우선합니다.
- 가장 긴 보존 기간이 항상 우선합니다.
- 명시적 포함은 위치 측면에서 암시적 포함보다 우선합니다.
- 가장 짧은 삭제 기간이 우선합니다.

## <a name="when-to-use-retention-policies-for-teams"></a>Teams에 보존 정책을 사용하는 시기

대부분의 경우 조직은 비공개 채팅 데이터를 일반적으로 프로젝트 관련 대화가 주를 이루는 채널 메시지보다 더 많은 책임으로 간주합니다.

비공개 채팅(1:1 또는 1:다수 채팅) 및 채널 메시지에 대해 별도의 보존 정책을 설정할 수 있습니다. 조직의 특정 사용자 또는 팀에 적용되는 고유한 정책을 구성할 수도 있습니다. Teams 채팅의 경우 정책을 적용할 사용자를 선택할 수 있습니다. Teams 채널 메시지의 경우 정책을 적용할 팀을 선택할 수 있습니다.

예를 들어 채널 메시지의 경우 조직의 특정 팀에는 1년 삭제 정책을 적용하고 다른 모든 팀에는 3년 삭제 정책을 적용할 수 있습니다.

## <a name="manage-retention-policies-for-teams"></a>Teams의 보존 정책 관리

### <a name="using-the-security--compliance-center"></a>보안 및 준수 센터 사용

#### <a name="create-a-retention-policy"></a>보존 정책 만들기

Teams 채팅 및 채널 메시지에 대한 보존 정책을 만들려면 다음을 수행합니다.

1. 보안 및 준수 센터의 왼쪽 탐색에서 **정보 거버넌스** > **보존** 으로 이동합니다.
2. **만들기** 를 선택합니다.
3. **정책 이름 설정** 페이지에서 정책의 이름과 설명을 입력하고 **다음** 을 클릭합니다.
4. **설정** 페이지에서 데이터의 보존, 삭제 또는 둘 다 수행을 지정하고 보존 기간을 선택한 후 **다음** 을 클릭합니다.
5. **위치 선택** 페이지에서 다음을 수행한 후 **다음** 을 클릭합니다.

    - 채널 메시지에 정책을 적용하려면 **Teams 채널 메시지** 를 켭니다.  조직의 특정 팀에 정책을 적용하려면 **팀 선택** 을 선택하고 원하는 팀을 선택합니다.
    - 채팅에 정책을 적용하려면 **Teams 채팅** 을 켭니다. 조직의 특정 사용자에게 정책을 적용하려면 **사용자 선택** 을 선택하고 원하는 사용자를 선택합니다.
      > [!NOTE]
      > **Teams 채널 메시지** 및/또는 **Teams 채팅** 을 켜면 다른 모든 위치는 자동으로 꺼집니다. Teams 보존 정책에는 Teams 위치만 포함될 수 있습니다.

        ![위치 선택 페이지의 Teams 채널 메시지 및 Teams 채팅 옵션 스크린 샷](media/retention-policies-create.png)

      > [!IMPORTANT]
      > 팀 채팅 및 채널 메시지는 **Exchange 전자 메일** 또는 **Microsoft 365 그룹** 위치에서 사용자 또는 그룹 사서함에 적용 된 보존 정책의 영향을 받지 않습니다. Teams 채팅 및 채널 메시지가 Exchange에 저장되더라도 Teams 채팅 및 채널 메시지는 Teams 위치에 적용된 보존 정책의 영향만 받습니다.

6. 설정을 검토한 후 준비가 되면 **이 정책 만들기** 를 선택합니다.

#### <a name="edit-a-retention-policy"></a>보존 정책 편집

Teams 보존 정책을 편집하려면 다음을 수행합니다.

1. 보안 및 준수 센터의 왼쪽 탐색에서 **정보 거버넌스** > **보존** 으로 이동합니다.
2. 보존 정책 목록에서 편집하려는 보존 정책 옆의 확인란을 선택합니다.
3. 편집하려는 항목 옆에 있는 **편집** 을 선택하고 변경한 다음 **저장** 을 클릭하고 **닫기** 를 클릭합니다.

    ![위치 선택 페이지의 Teams 채널 메시지 및 Teams 채팅 옵션 스크린 샷](media/retention-policies-edit.png)

> [!WARNING]
> 팀 채널 메시지 또는 팀 채팅을 포함 하도록 특정 팀 또는 특정 사용자를 구성한 경우 해당 위치에 대 한 마지막 **항목을 제거** 하도록 해당 위치에 대 한 구성이 되돌립니다. 정책을 저장 하기 전에 의도 했던 구성 인지 확인 합니다.
> 
> 예를 들어 데이터를 삭제 하도록 구성 된 보존 정책에 포함할 팀 채팅 사용자를 지정 하 고 정책을 편집 하 여이 사용자를 제거 하면 기본적으로 모든 사용자는 팀 채팅 메시지를 영구적으로 삭제 하는 보존 정책에 적용 됩니다. 팀 채널 메시지에도 마찬가지 사항이 적용 됩니다.
> 
> 이 시나리오에서는 팀 채널 메시지 또는 팀 채팅 메시지에 대 한 **모든** 설정이 보존 정책에 적용 되는 것을 원하지 않는 경우 위치를 해제 합니다. 또는 정책에서 제외할 경우 exclude를 지정 합니다.


#### <a name="delete-a-retention-policy"></a>보존 정책 삭제

Teams 보존 정책을 삭제하려면 다음을 수행합니다.

1. 보안 및 준수 센터의 왼쪽 탐색에서 **정보 거버넌스** > **보존** 으로 이동합니다.
2. 보존 정책 목록에서 삭제하려는 보존 정책 옆의 확인란을 선택합니다.
3. **정책 삭제** 를 선택합니다.

### <a name="end-user-experience"></a>최종 사용자 환경

개인 채팅 (1:1 채팅) 또는 그룹 채팅의 경우, 최종 사용자는 보존 정책 구성 보다 오래 된 채팅을 삭제 하 고 "조직의 보존 정책에 따라 오래 된 메시지를 삭제 했습니다." 라는 제어 메시지가 아직 삭제 되지 않은 메시지의 맨 위에 표시 되는 것을 볼 수 있습니다.
:::image type="content" source="media/retention-policies-image1.png" alt-text="채팅 보존 스크린샷":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="그룹 채팅 보존 스크린샷":::

채널 메시지의 경우 최종 사용자 (채널 구성원)가 삭제 된 메시지를 보기에서 사라지고 메시지가 만료 된 것 처럼 표시 합니다. 삭제 된 메시지가 스레드 대화의 상위 메시지 이면 상위 메시지 대신 "이 메시지가 보존 정책으로 인해 삭제 되었습니다." 라는 메시지가 표시 됩니다.

:::image type="content" source="media/retention-policies-image3.png" alt-text="보존 전의 채널 스크린샷":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="보존 후 채널의 스크린샷":::

> [!NOTE]
> 최종 사용자 메시지는 현재 사용자 또는 관리자가 수정할 수 없습니다.


### <a name="using-powershell"></a>PowerShell 사용

[보안 & 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)을 사용 하 여 팀 보존 정책을 만들고 관리 하려면 다음 cmdlet을 사용 합니다.

|정책|규칙|
|---|---|
|[새로운 RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy?view=exchange-ps)| [새로운 RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule?view=exchange-ps)|
|[Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy?view=exchange-ps)| [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps)|
|[Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy?view=exchange-ps)| [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule?view=exchange-ps)|
|[제거-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy?view=exchange-ps)| [제거-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a>알려진 문제

현재 추적 및 조사 중인 Teams의 보존 정책에 대한 알려진 문제는 다음과 같습니다.

- **팀 채널 메시지** 위치 행의 **팀 선택** 에서 팀이 아닌 Microsoft 365 그룹이 표시 될 수 있습니다. 이 문제는 앞으로 해결될 예정입니다.

- **Teams 채팅** 위치 행의 **사용자 선택** 에서 게스트 및 비사서함 사용자가 표시될 수 있습니다. 보존 정책은 게스트에 대한 설정이 아니며 목록에서 제거하기 위해 해결 중에 있습니다.

- 보존 처리 작업은 매일 실행 되지만, 경우에 따라 7 일이 지난 후에 대기 시간이 발생 하는 것으로 알려져 있습니다. 따라서 60일보다 오래된 항목을 삭제하는 Teams 보존 정책이 있는 경우 이러한 항목은 최대 67일 동안 보존될 수 있습니다. 이것은 새로운 상황이 아니며 Exchange 모델을 따릅니다. 물론 대부분의 경우 지연되지 않습니다.

## <a name="related-topics"></a>관련 항목

- [보존 정책 개요](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)
