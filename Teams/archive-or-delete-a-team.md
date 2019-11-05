---
title: Microsoft 팀에서 팀 보관 또는 삭제
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: 팀을 보관 하거나 영구적으로 삭제 하는 방법에 대해 알아봅니다.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ceb699ff4c8d7ba2cf10e1b8e94ca33f60eb9b8d
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968269"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a>Microsoft 팀에서 팀 보관 또는 삭제
===========================================

시간이 지남에 따라 Microsoft 팀에서 만든 팀이 사용 되지 않거나 프로젝트의 마지막에 팀을 보관 하거나 삭제할 수 있습니다. Microsoft 팀 관리자 인 경우이 문서에 나와 있는 단계를 따라 더 이상 필요 하지 않은 팀을 보관 하거나 삭제할 수 있습니다.

팀을 보관 하면 해당 팀의 모든 활동이 중단 됩니다. 팀 보관은 팀 및 연결 된 사이트 모음에도 개인 채널을 보관 합니다.  그러나 여전히 구성원을 추가 또는 제거 하 고 역할을 업데이트할 수 있으며, 표준 및 개인 채널, 파일 및 채팅에서 모든 팀 활동을 계속 볼 수 있습니다.

팀을 삭제 하면 표준 및 개인 채널의 팀 활동 (및 연결 된 사이트 모음), 파일 및 채팅도 삭제 됩니다.

> [!IMPORTANT]
> 보관 된 팀은 다시 활성화할 수 있지만 삭제 된 팀은 직접 삭제 취소할 수 없습니다. 팀을 먼저 보관 하 고 더 이상 팀이 필요 하지 않을 때까지 삭제를 연기 하세요.

## <a name="archive-a-team"></a>팀 보관

팀을 보관 하려면 다음 단계를 따르세요.

1. Microsoft 팀 관리 센터에서 **팀**을 선택 합니다.
2. 팀 이름을 클릭 하 여 팀을 선택 합니다.
3. **보관**을 선택 합니다. 다음 메시지가 표시 됩니다.

    ![팀 보관 메시지의 스크린샷](media/teams-archive-message.png)

4. 팀의 SharePoint 사이트를 읽기 전용으로 설정 하려면 확인란을 선택 합니다.
5. **보관** 을 선택 하 여 팀을 보관 합니다. 팀의 상태가 **보관**됨으로 변경 됩니다.

## <a name="make-an-archived-team-active"></a>보관 된 팀을 활성 상태로 만들기

보관 된 팀이 다시 활성화 되도록 하려면 다음 단계를 따르세요.

1. Microsoft 팀 관리 센터에서 **팀**을 선택 합니다.
2. 팀 이름을 클릭 하 여 팀을 선택 합니다.
3. **보관**해제를 선택 합니다. 팀의 상태가 **활성**으로 변경 됩니다.

## <a name="delete-a-team"></a>팀 삭제

나중에 팀이 필요 하지 않은 경우에는 보관 하는 대신 삭제할 수 있습니다. 팀을 삭제 하려면 다음 단계를 따르세요.

1.  Microsoft 팀 관리 센터에서 **팀**을 선택 합니다.
2.  팀 이름을 클릭 하 여 팀을 선택 합니다.
3.  **삭제**를 선택 합니다. 확인 메시지가 표시 됩니다.
4.  **삭제** 를 선택 하 여 팀을 영구적으로 삭제 합니다.

## <a name="restore-a-deleted-team"></a>삭제 된 팀 복원

팀과 연결 된 Office 365 그룹을 복원 하 여 삭제 된 팀을 복원 하려면 다음 단계를 따르세요. 팀에 대 한 Office 365 그룹 복원 탭, 표준 채널, 개인 채널 및 연결 된 사이트 모음을 비롯 한 팀 콘텐츠를 복원 합니다.

기본적으로 삭제 된 Office 365 그룹은 30 일 동안 보존 됩니다. 그룹을 복원할 수 있으므로이 30 일의 기간이 "일시 삭제" 라고 합니다. 자세히 알아보려면 [삭제 된 Office 365 그룹 복원을](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group)참조 하세요.

### <a name="install-the-azureadpreview-module"></a>AzureADPreview 모듈 설치

1. 관리자 권한으로 Windows PowerShell을 엽니다.
2. 이전 버전의 AzureADPreview 모듈이 설치 되어 있거나 AzureAD 모듈이 설치 되어 있는 경우 다음 중 하나를 실행 하 여 제거 합니다.

    ``` 
    Uninstall-Module AzureADPreview
    ```

    ```
    Uninstall-Module AzureAD
    ```
3. 다음을 실행 하 여 최신 버전의 AzureADPreview 모듈을 설치 합니다.

    ```
    Install-Module AzureADPreview
    ```    

### <a name="restore-the-deleted-office-365-group"></a>삭제 된 Office 365 그룹 복원

1. Azure AD에 연결 하려면 다음을 실행 합니다.
    ```
    Connect-AzureAD
    ```
    메시지가 표시 되 면 관리자 계정 및 암호를 사용 하 여 로그인 합니다.  
2. 다음을 실행 하 여 30 일 보존 기간 내에 그대로 남아 있는 모든 소프트 삭제 된 Office 365 그룹의 목록을 표시 합니다. 그룹이 많은 경우 **-All $True** 매개 변수를 사용 합니다.
    ```
    Get-AzureADMSDeletedGroup
    ``` 
3. 복원 하려는 그룹을 찾은 다음 Id를 기록해 둡니다.
4. 그룹을 복원 하려면 다음을 실행 합니다. 여기서 [Id]는 그룹 Id입니다.
    ```
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  다음을 실행 하 여 그룹이 성공적으로 복원 되었는지 확인 하 고 여기서 [Id]는 그룹 Id입니다.
    ```
    Get-AzureADGroup -ObjectId [Id]
    ```

    복원 프로세스가 완료 되는 데 최대 24 시간이 소요 될 수 있으며 그 이후에는 팀과 관련 된 팀 및 콘텐츠 (탭 및 채널 포함)가 팀에 표시 됩니다.
