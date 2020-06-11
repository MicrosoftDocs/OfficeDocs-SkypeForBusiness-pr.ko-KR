---
title: Microsoft 팀에서 콘텐츠 검색 사용
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Microsoft 팀에서 콘텐츠 검색을 사용 하 여 Exchange, SharePoint Online, 비즈니스용 OneDrive, OneNote에서 Microsoft 팀 정보를 쿼리 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45da4a0f4acf66cb8caafcd8d2bc2287c1176c94
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690444"
---
<a name="use-content-search-in-microsoft-teams"></a>Microsoft 팀에서 콘텐츠 검색 사용
=====================================

> [!NOTE]
> [개인 채널](private-channels.md) 의 메시지 및 파일의 콘텐츠 검색은 표준 채널과 다르게 작동 합니다. 자세히 알아보려면 [개인 채널의 콘텐츠 검색](#content-search-of-private-channels)을 참조 하세요.

콘텐츠 검색은 Exchange, SharePoint Online, 비즈니스용 OneDrive에 걸친 Microsoft 팀 정보를 쿼리 하는 방법을 제공 합니다.

자세한 내용은 [Microsoft 365 또는 Office 365의 콘텐츠 검색](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)을 참고 하세요.

예를 들어 제조 스펙 사서함 및 제조 사양 SharePoint 사이트에 대 한 **콘텐츠 검색** 을 사용 하 여 Exchange에서 팀 표준 채널 대화, sharepoint Online의 파일 업로드 및 수정, OneNote 변경 내용을 검색할 수 있습니다.

또한 **콘텐츠 검색** 에 쿼리 조건을 추가 하 여 반환 되는 결과의 범위를 좁힐 수 있습니다. 위의 예제에서는 "**New Factory 스펙"** 키워드를 사용한 콘텐츠를 찾을 수 있습니다.

> [!TIP]
> 검색 조건을 추가 하 고 나면 분석을 위해 보고서 또는 데이터를 컴퓨터로 내보낼 수 있습니다.

## <a name="content-search-of-private-channels"></a>개인 채널의 콘텐츠 검색

비공개 채널에 전송된 메시지 레코드는 그룹 사서함이 아닌 모든 비공개 채널 구성원의 사서함에 전달됩니다. 레코드 제목은 출처 비공개 채널을 표시하도록 형식이 지정됩니다.

각 개인 채널은 상위 팀 사이트와 별도의 고유한 SharePoint 사이트 모음을 포함 하므로 개인 채널의 파일은 상위 팀과 독립적으로 관리 됩니다.

팀은 단일 채널의 콘텐츠 검색을 지원 하지 않으므로 전체 팀을 검색 해야 합니다. 개인 채널의 콘텐츠 검색을 수행 하려면 팀, 개인 채널에 연결 된 사이트 모음 (파일 포함) 및 개인 채널 구성원의 사서함 (메시지 포함)에서 검색 합니다.

콘텐츠 검색에 포함할 개인 채널의 파일 및 메시지를 식별 하려면 다음 단계를 사용 합니다.

### <a name="include-private-channel-files-in-a-content-search"></a>콘텐츠 검색에 개인 채널 파일 포함

이 단계를 수행 하기 전에 [Sharepoint Online 관리 셸을 설치 하 고 Sharepoint online에 연결](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)합니다.

1. 팀의 개인 채널과 연결 된 모든 SharePoint 사이트 모음 목록을 가져오려면 다음을 실행 합니다.

    ```PowerShell
    Get-SPOSite
    ```
2. 다음 PowerShell 스크립트를 실행 하 여 팀의 개인 채널과 해당 상위 팀 그룹 ID와 연결 된 모든 SharePoint 사이트 모음 Url 목록을 가져옵니다.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. 각 팀 또는 그룹 ID에 대해 다음 PowerShell 스크립트를 실행 하 여 모든 관련 개인 채널 사이트를 식별 합니다.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>콘텐츠 검색에 개인 채널 메시지 포함

이 단계를 수행 하기 전에 [최신 버전의 팀 PowerShell 모듈이](teams-powershell-overview.md) 설치 되어 있는지 확인 합니다.

1. 다음을 실행 하 여 팀의 비공개 채널 목록을 가져옵니다.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. 다음을 실행 하 여 개인 채널 구성원 목록을 가져옵니다.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. 콘텐츠 검색 쿼리의 일부로 팀의 각 개인 채널에 있는 모든 구성원의 사서함을 포함 합니다.

## <a name="related-topics"></a>관련 항목

- [Microsoft 365 준수 센터의 eDiscovery 사례](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 