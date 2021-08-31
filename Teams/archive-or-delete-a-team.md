---
title: Microsoft Teams에서 팀 보관 또는 삭제하기
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: 이 문서에서는 팀을 보관하거나 영구적으로 삭제하는 방법에 대해 Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f5743dda03b7495bc8f7c275fb955f83d7db6be2
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727207"
---
# <a name="archive-or-delete-a-team-in-microsoft-teams"></a>Microsoft Teams에서 팀 보관 또는 삭제하기

시간이 지남에 따라 Microsoft Teams에서 만든 팀이 사용되지 않거나 프로젝트가 끝날 때 팀을 보관하거나 삭제하려고 할 수 있습니다. Microsoft Teams 관리자인 경우 이 문서에 나와 있는 단계를 따라 더 이상 필요하지 않은 팀을 보관하거나 삭제하세요.

팀을 보관하면 해당 팀에 대한 모든 활동이 중단됩니다. 팀을 보관하면 팀의 개인 채널과 연결된 사이트 모음도 보관됩니다.  그러나 관리자가 계속해서 구성원을 추가 또는 제거하고 역할을 업데이트할 수 있으며, 표준 및 개인 채널, 파일 및 채팅에서 모든 팀 활동을 계속 볼 수 있습니다.

팀을 삭제하면 표준 및 개인 채널(및 연결된 사이트 모음)에서 팀 활동, 파일 및 채팅도 삭제됩니다.

> [!IMPORTANT]
> 보관된 팀은 다시 활성화될 수 있지만 삭제된 팀은 직접 복원할 수 없습니다. 먼저 팀을 보관하고 팀이 더 이상 필요하지 않을 때까지 삭제를 연기하는 것이 좋습니다.

## <a name="archive-a-team"></a>팀 보관하기

팀을 보관하려면 다음 단계를 따르세요. 이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다. 관리 역할 및 사용 권한 가져오기에 대한 내용은 [Teams 관리자 역할 사용](./using-admin-roles.md)을 참조하세요.

1. 관리 센터에서 를 **Teams.**
2. 팀 이름을 클릭하여 팀을 선택합니다.
3. **보관** 을 선택합니다. 다음 메시지가 표시됩니다.

    ![보관 Teams 스크린샷.](media/teams-archive-message.png)

4. 팀과 연결된 웹 사이트 및 SharePoint 위키 탭에서 콘텐츠를 편집하지 못하게하려면 팀 구성원에 SharePoint 사이트 읽기 전용으로 만들기를 **선택합니다.** (Teams 소유자는 여전히 이 콘텐츠를 편집할 수 있습니다.)
5. **보관** 을 선택하여 팀을 보관합니다. 팀의 상태가 **보관됨** 으로 변경됩니다.

## <a name="make-an-archived-team-active"></a>보관된 팀을 활성화하기

보관된 팀을 다시 활성화하려면 다음 단계를 따르세요.

1. 관리 센터에서 를 **Teams.**
2. 팀 이름을 클릭하여 팀을 선택합니다.
3. **보관 취소** 를 선택합니다. 팀의 상태가 **활성** 으로 변경됩니다.

## <a name="delete-a-team"></a>팀 삭제하기

나중에 팀이 필요하지 않은 경우에는 팀을 보관하지 않고 삭제할 수 있습니다. 팀을 삭제하려면 다음 단계를 따르세요.

1.  관리 센터에서 를 **Teams.**
2.  팀 이름을 클릭하여 팀을 선택합니다.
3.  **삭제** 를 선택합니다. 확인 메시지가 표시됩니다.
4.  팀을 영구적으로 삭제하려면 **삭제** 를 선택합니다.

## <a name="restore-a-deleted-team"></a>삭제된 작업 복원하기

다음 단계를 수행하여 팀과 연결된 Microsoft 365 복원하여 삭제된 팀을 복원합니다. 팀의 Microsoft 365 그룹 복원은 탭, 표준 채널 및 개인 채널 및 관련 사이트 모음을 비롯한 팀 콘텐츠를 복원합니다.

기본적으로 삭제된 Microsoft 365 그룹은 30일 동안 유지됩니다. 이 30일의 기간을 “일시 삭제”라고 하며 이 기간 동안 그룹을 복원할 수 있습니다. 자세한 내용은 삭제된 [그룹 복원을 참조합니다.](/microsoft-365/admin/create-groups/restore-deleted-group)

### <a name="install-the-azureadpreview-module"></a>AzureADPreview 모듈 설치하기

1. 관리자 권한으로 Windows PowerShell을 엽니다.
2. 이전 버전의 AzureADPreview 모듈 또는 AzureAD module이 설치되어 있는 경우 다음 중 하나를 실행하여 제거합니다.

    ```PowerShell
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. 다음을 실행하여 최신 버전의 AzureADPreview 모듈을 설치합니다.

    ```PowerShell
    Install-Module AzureADPreview
    ```

### <a name="restore-the-deleted-microsoft-365-group"></a>삭제된 그룹 Microsoft 365 복원

1. 다음을 실행하여 Azure AD에 연결합니다.
    ```PowerShell
    Connect-AzureAD
    ```
    메시지가 표시되면 관리자 계정 및 암호를 사용하여 로그인합니다.  
2. 다음을 실행하여 30일 보존 기간 내에 Microsoft 365 모든 소프트 삭제된 모든 그룹 목록을 표시합니다. 그룹이 많이 있는 경우 **-All $True** 매개 변수를 사용합니다.
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ```
3. 복원하려는 그룹을 찾은 다음 해당 Id를 기록해 둡니다.
4. 다음을 실행하여 해당 그룹을 복원합니다. 여기서 [Id]는 그룹 Id입니다.
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  다음을 실행하여 그룹이 성공적으로 복원되었는지 확인합니다. 여기서 [Id]는 그룹 Id입니다.
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    복원 프로세스가 완료되는 데 최대 24시간이 걸릴 수 있으며, 복원된 후에는 팀과 탭과 채널을 포함하는 팀과 연결된 콘텐츠가 팀에 표시됩니다.
    
## <a name="related-topics"></a>관련 항목

- [팀 보관 또는 복원](https://support.microsoft.com/office/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) 
