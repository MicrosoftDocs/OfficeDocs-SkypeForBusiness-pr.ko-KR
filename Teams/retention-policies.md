---
title: Microsoft 팀의 보존 정책
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: 보존 정책 및 팀에서이를 만들고 관리 하는 방법에 대해 알아봅니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86cbb37b46bca606e7225ce0267a49c709fc9619
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42160752"
---
# <a name="retention-policies-in-microsoft-teams"></a>Microsoft 팀의 보존 정책

보존 정책은 조직의 정보를 보다 효율적으로 관리 하는 데 도움이 됩니다. 보존 정책을 사용 하 여 조직의 내부 정책, 업계 규정 또는 법적 요구를 준수 하는 데 필요한 데이터를 유지 하 고, 책임으로 간주 되는 데이터를 삭제 하 고, 더 이상 유지 하지 않거나 법률 또는 비즈니스 가치를가지고 있지 않습니다.

기본적으로 팀 채팅, 채널 및 파일 데이터는 영구적으로 유지 됩니다. 관리자는 채팅 및 채널 메시지에 대 한 팀 보존 정책을 설정 하 고 데이터 유지, 삭제 또는 특정 기간 동안 보존 하도록 사전에 결정 하 고 삭제할 수 있습니다.

[Office 365 보안 & 준수 센터](https://protection.office.com/) 에서 또는 보안 & 준수 센터 PowerShell cmdlet을 사용 하 여 팀과 다른 작업에 대 한 보존 정책을 만들고 관리 합니다. 전체 조직 또는 특정 사용자 및 팀에 팀 보존 정책을 적용할 수 있습니다.

> [!NOTE]
> 아직 개인 채널 메시지 보존에 대 한 구성은 지원 하지 않습니다. 개인 채널에서 공유 된 파일을 보존 하는 기능이 지원 됩니다.

Office 365의 보존 정책에 대해 자세히 알아보려면 [보존 정책 개요](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)를 참조 하세요.

## <a name="what-are-retention-policies-for-teams"></a>팀에 대 한 보존 정책은 무엇입니까?

팀 또는 기타 작업 부하에 대 한 보존 정책을 설정할 때 다음으로 설정할 수 있습니다.

- **데이터 보존**: 보존 정책을 사용 하 여 사용자 앱에서 발생 하는 작업에 관계 없이 일정 기간 동안 데이터가 유지 되도록 합니다. 데이터는 규정 준수를 위해 유지 되며 보존 기간이 만료 될 때까지 eDiscovery에 사용할 수 있으며, 이후 정책에 아무 작업도 수행할지 아니면 삭제할지를 표시 합니다. 예를 들어 채널 메시지를 7 년 동안 유지 하기 위해 팀 보존 정책을 만드는 경우 사용자가 팀에서 메시지를 삭제 하더라도 해당 메시지는 eDiscovery에 대해 보관 됩니다 (7 년 동안).
- **데이터 삭제**: 보존 정책을 사용 하 여 데이터를 삭제 하 여 조직의 책임을 지지 않도록 합니다. 팀 보존 정책을 사용 하 여 데이터를 삭제 하면 팀 서비스의 모든 저장소 위치에서 영구적으로 삭제 됩니다.

팀에 대 한 보존 정책을 사용 하 여 다음을 수행할 수 있습니다.

- 팀 채팅 및/또는 채널 메시지를 지정 된 기간 동안 유지 한 다음 아무 작업도 수행 하지 않습니다.
- 팀 채팅 및/또는 채널 메시지를 지정 된 기간 동안 유지 한 다음 데이터를 삭제 합니다.
- 지정 된 기간 후 팀 채팅 및/또는 채널 메시지를 삭제 합니다.

> [!NOTE]
> 팀에서 사용자가 개인 채팅을 통해 공유 하는 파일은 파일을 공유한 사용자의 비즈니스용 OneDrive 계정에 저장 된다는 점에 유의 하세요. 팀 멤버가 채널 대화에 업로드 하는 파일은 팀의 SharePoint 사이트에 저장 됩니다. 따라서 팀에서 파일을 보존 하거나 삭제 하려면 비즈니스용 OneDrive 및 SharePoint Online에 적용 되는 보존 정책을 만듭니다.

데이터는 보존 정책의 영향을 받을 때 데이터는 원래 위치에 그대로 유지 되므로 사용자가 계속 작업할 수 있습니다. 사용자가 정책에 따라 데이터를 편집 하거나 삭제 한 경우에는 정책이 적용 되는 동안 보존 된 보안 위치에 복사본이 저장 됩니다.

보존 정책의 최소 라이선스 요구 사항은 Office 365 E3입니다. 라이선스에 대해 자세히 알아보려면 [팀에 대 한 Office 365 라이선스](Office-365-licensing.md)를 참조 하세요.

## <a name="how-teams-retention-policies-work"></a>팀 보존 정책이 작동 하는 방식

팀 채팅은 채팅에 있는 각 사용자의 사서함에 있는 숨겨진 하위 Strate보류가 있는 폴더에 저장 되며 팀 채널 메시지는 팀의 그룹 사서함에 숨겨진 SubstratesHolds 폴더에 저장 됩니다. 팀은이 데이터를 저장 하는 Azure 기반 채팅 서비스를 사용 하며 기본적으로이 서비스는 데이터를 영구적으로 저장 합니다. 팀 보존 정책을 사용 하면 데이터를 삭제할 때 Exchange 사서함과 기본 채팅 서비스에서 모두 영구적으로 삭제 됩니다.

보존 정책을 팀 채팅 및 채널 메시지에 적용 하는 경우 다음이 수행 됩니다.

- 보존 기간 중에 사용자가 채팅 또는 채널 메시지를 편집 하거나 삭제 한 경우 메시지가 복사 (편집 된 경우) 되거나 이동 (삭제 된 경우) 한 후 보존 기간이 만료 될 때까지이 폴더에 저장 됩니다. 보존 기간이 만료 될 때 데이터를 삭제 하도록 정책이 구성 된 경우 보존 기간이 만료 되는 날에 메시지가 영구적으로 삭제 됩니다.
- 보존 기간 동안 사용자가 채팅 또는 채널 메시지를 삭제 하지 않으면 보존 기간이 만료 된 후 1 일 내에 메시지가 하위 Strate보관 폴더로 이동 합니다. 보존 기간이 만료 될 때 데이터를 삭제 하도록 정책이 구성 된 경우 메시지가 폴더로 이동 된 후 하루에 영구적으로 삭제 됩니다.

> [!NOTE]
> 비즈니스용 Skype Online 및 팀 interop 채팅에도 동일한 흐름이 작동 합니다. 비즈니스용 Skype Online 채팅이 팀에 들어오면 팀 채팅 스레드에서 메시지가 되며 해당 사서함으로 ingested 됩니다. 팀 보존 정책은 팀 스레드에서 이러한 메시지를 삭제 합니다. 그러나 비즈니스용 Skype Online이 켜져 있고 비즈니스용 Skype Online 클라이언트측에서 대화 내용이 사서함에 저장 되어 있는 경우에는 해당 채팅 데이터가 팀 보존 정책에 따라 처리 되지 않습니다.

팀의 보존 정책은 채팅 또는 채널 메시지가 생성 되 고 소급 된 날짜를 기반으로 합니다. 즉, 90 일 보다 오래 된 데이터를 삭제 하는 보존 정책을 만들면 90 일이 지난 후에 만든 팀 데이터가 삭제 됩니다.

SharePoint Online 또는 비즈니스용 OneDrive에 적용 된 보존 정책이 해당 메시지가 삭제 되기 전에 팀 채팅 또는 채널 메시지에서 참조 되는 파일을 삭제할 수 있는 경우도 있습니다. 이 시나리오에서 파일은 팀 메시지에 계속 표시 되지만, 사용자가 파일을 클릭 하면 "파일을 찾을 수 없습니다." 오류가 발생 하 게 됩니다. 이 문제는 누군가가 SharePoint Online 또는 비즈니스용 OneDrive에서 파일을 수동으로 삭제 하는 경우에도 발생할 수 있습니다.

### <a name="considerations-and-limitations"></a>고려 사항 및 제한 사항

팀 보존 정책 사용 시 주의 해야 할 몇 가지 고려 사항 및 제한 사항은 다음과 같습니다.

- 팀에는 다른 작업 부하와 별도의 보존 정책이 필요 합니다. 즉, 팀 채팅 및/또는 채널 메시지에 대 한 특정 보존 정책을 만들어야 합니다. 이러한 이유로 조직 전체 보존 정책에 팀을 포함할 수 없습니다.

- 개인 채널 메시지는 지원 되지 않습니다. 현재, 팀의 보존 정책은 표준 채널 메시지에만 적용 됩니다.

- 팀은 키워드 또는 중요 한 정보가 포함 된 콘텐츠에 정책을 적용 하는 기능과 같은 고급 보존 설정을 지원 하지 않습니다. 현재, 팀의 보존 정책은 모든 채팅 및/또는 채널 메시지 컨텐트에 적용 됩니다.

- 팀에서 만료 된 메시지를 정리 하는 데 최대 3 일이 걸릴 수 있습니다. 팀 보존 정책은 보존 기간이 만료 되 면 채팅 및 채널 메시지를 삭제 합니다. 그러나이 메시지를 정리 하 고 영구적으로 삭제 하는 데 최대 3 일이 걸릴 수 있습니다. 또한 채팅 및 채널 메시지는 보존 기간이 만료 된 후와 메시지가 영구적으로 삭제 되는 시간 사이에 eDiscovery 도구를 사용 하 여 검색할 수 있습니다.

### <a name="multiple-retention-policies-and-the-principles-of-retention"></a>여러 보존 정책 및 보존 원칙

다양 한 기간을 사용 하 여 여러 팀 보존 정책을 설정 하는 경우 [보존 정책의 원칙이](https://docs.microsoft.com/microsoft-365/compliance/retention-policies#the-principles-of-retention-or-what-takes-precedence) 적용 됩니다. 우선 하는 항목에 대 한 개요는 다음과 같습니다.

- 보존을 통해 항상 우선 적용 됩니다.
- 가장 오래 유지 되는 기간이 항상 우선 적용 됩니다.
- 명시적 포함 wins는 위치 측면에서 암시적으로 포함 됩니다.
- 가장 짧은 삭제 기간 wins

## <a name="when-to-use-retention-policies-for-teams"></a>팀에 대 한 보존 정책을 사용 하는 경우

대부분의 경우 조직은 일반적으로 프로젝트 관련 대화에 대 한 채널 메시지 보다 더 많은 책임으로 개인 채팅 데이터를 고려 합니다.

개인 채팅 (1:1 또는 1: 다 수의 채팅) 및 채널 메시지에 대해 별도의 보존 정책을 설정할 수 있습니다. 조직의 특정 사용자 또는 팀에 적용 되는 고유한 정책을 구성할 수도 있습니다. 팀 채팅의 경우 정책이 적용 되는 사용자를 선택할 수 있습니다. 팀 채널 메시지의 경우 정책이 적용 되는 팀을 선택할 수 있습니다.

예를 들어 채널 메시지의 경우 조직의 특정 팀에 1 년 삭제 정책을 적용 하 고 다른 모든 팀에 3 년 삭제 정책을 적용할 수 있습니다.

## <a name="manage-retention-policies-for-teams"></a>팀의 보존 정책 관리

### <a name="using-the-security--compliance-center"></a>보안 & 준수 센터 사용

#### <a name="create-a-retention-policy"></a>보존 정책 만들기

팀 채팅 및 채널 메시지에 대 한 보존 정책을 만들려면 다음을 수행 합니다.

1. 보안 & 준수 센터의 왼쪽 탐색 모음에서 **정보 관리** > **보존**으로 이동 합니다.
2. **만들기**를 선택 합니다.
3. **정책 이름** 페이지에서 정책의 이름과 설명을 입력 하 고 **다음**을 클릭 합니다.
4. **설정** 페이지에서 데이터 보관 여부, 삭제 또는 보존 기간을 지정 하 고 **다음**을 클릭 합니다.
5. **위치 선택** 페이지에서 다음을 수행 하 **고 다음을 클릭 합니다**.

    - 채널 메시지에 정책을 적용 하려면 **팀 채널 메시지**를 켭니다.  조직의 특정 팀에 정책을 적용 하려는 경우 **팀 선택을**선택한 다음 원하는 팀을 선택 합니다.
    - 채팅에 정책을 적용 하려면 **팀 채팅**을 켭니다. 조직의 특정 사용자에 게 정책을 적용 하려면 **사용자 선택을**선택 하 고 원하는 사용자를 선택 합니다.
      > [!NOTE]
      > **팀 채널 메시지** 및/또는 **팀 채팅**을 켜면 다른 모든 위치가 자동으로 꺼집니다. 팀 보존 정책에는 팀 위치만 포함 될 수 있습니다.

        ![위치 선택 페이지의 팀 채널 메시지 및 팀 채팅 옵션 스크린샷](media/retention-policies-create.png)

      > [!IMPORTANT]
      > 팀 채팅 및 채널 메시지는 **Exchange 전자 메일** 또는 **Office 365 그룹** 위치의 사용자 또는 그룹 사서함에 적용 된 보존 정책의 영향을 받지 않습니다. 팀 채팅 및 채널 메시지는 Exchange에 저장 되지만, 팀 위치에 적용 된 보존 정책에 의해서만 영향을 받습니다.

6. 설정을 검토 하 고 준비가 되 면 **이 정책 만들기**를 선택 합니다.

#### <a name="edit-a-retention-policy"></a>보존 정책 편집

팀 보존 정책을 편집 하려면 다음을 수행 합니다.

1. 보안 & 준수 센터의 왼쪽 탐색 모음에서 **정보 관리** > **보존**으로 이동 합니다.
2. 보존 정책 목록에서 편집 하려는 보존 정책 옆에 있는 확인란을 선택 합니다.
3. 편집할 항목 옆에 있는 **편집** 을 선택 하 고 필요한 사항을 변경한 다음 **저장**을 클릭 하 고 **닫기를**클릭 합니다.

    ![위치 선택 페이지의 팀 채널 메시지 및 팀 채팅 옵션 스크린샷](media/retention-policies-edit.png)

#### <a name="delete-a-retention-policy"></a>보존 정책 삭제

팀 보존 정책을 삭제 하려면 다음을 수행 합니다.

1. 보안 & 준수 센터의 왼쪽 탐색 모음에서 **정보 관리** > **보존**으로 이동 합니다.
2. 보존 정책 목록에서 삭제 하려는 보존 정책 옆에 있는 확인란을 선택 합니다.
3. **정책 삭제**를 선택 합니다.

### <a name="using-powershell"></a>PowerShell 사용

PowerShell을 사용 하 여 팀 보존 정책을 만들고 관리 하려면 다음 cmdlet을 사용 합니다.

|Policy|노트|
|---|---|
|[새로운 TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [새로운 TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[제거-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [제거-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

## <a name="known-issues"></a>알려진 문제

다음은 추적 및 조사 중인 팀의 보존 정책에 대 한 알려진 문제점입니다.

- **팀 채널 메시지** 위치 행의 **팀 선택** 에서 팀이 아닌 Office 365 그룹이 표시 될 수 있습니다. 이 문제는 향후 해결 될 예정입니다.

- **팀 채팅** 위치 행의 **사용자 선택** 에서 게스트 및 사서함이 아닌 사용자가 표시 될 수 있습니다. 보존 정책은 게스트에 대해 설정 되지 않으며, 목록에서 제거 하는 데 사용 됩니다.

- ELC (Exchange 수명 주기 도우미)는 매일 실행 되지만 SLA는 7 일입니다. 따라서 팀 보존 정책에서 60 일 보다 오래 된 항목을 삭제 하는 경우 이러한 항목은 최대 67 일 동안 유지 될 수 있습니다. 이는 Exchange 모델을 따르는 새로운 상황이 아닙니다. 물론 대부분의 경우에는 지연이 없습니다.

## <a name="related-topics"></a>관련 주제

- [보존 정책 개요](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)
