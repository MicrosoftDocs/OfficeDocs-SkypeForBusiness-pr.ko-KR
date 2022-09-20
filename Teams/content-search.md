---
title: Microsoft Teams에서 콘텐츠 검색 사용
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Microsoft Purview 규정 준수 포털 콘텐츠 검색을 사용하여 Exchange Online, SharePoint Online, 비즈니스용 OneDrive 및 OneNote에 저장된 Microsoft Teams 콘텐츠를 검색하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: b976c5e3c6467a6c71bb51eb1ff3ef720813584b
ms.sourcegitcommit: 6754f2d11da0afff067f0872acf778a83fd1595e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2022
ms.locfileid: "67808239"
---
# <a name="use-content-search-in-microsoft-teams"></a>Microsoft Teams에서 콘텐츠 검색 사용

> [!NOTE]
> [개인 채널](private-channels.md)에서 메시지 및 파일의 콘텐츠 검색은 표준 채널과 다르게 작동합니다. 자세한 내용은 [비공개 채널의 콘텐츠 검색을 참조하세요](#content-search-of-private-channels).

콘텐츠 검색은 Exchange, SharePoint Online 및 비즈니스용 OneDrive 걸쳐 Microsoft Teams 정보를 쿼리하는 방법을 제공합니다.

자세한 내용은 [Microsoft 365의 콘텐츠 검색을](/microsoft-365/compliance/content-search) 참조하세요.

예를 들어 제조 사양 사서함 및 제조 사양 SharePoint 사이트에 대해 **콘텐츠 검색** 을 사용하면 Exchange의 Teams 표준 채널 대화, SharePoint Online의 파일 업로드 및 수정 내용 및 OneNote 변경 내용을 검색할 수 있습니다.

**콘텐츠 검색** 에 쿼리 조건을 추가하여 반환된 결과의 범위를 좁힐 수도 있습니다. 위의 예제에서는 "**새 팩터리 사양"** 키워드가 사용된 콘텐츠를 찾을 수 있습니다.

> [!TIP]
> 검색 조건을 추가한 후 분석을 위해 보고서 또는 실제 콘텐츠를 컴퓨터로 내보낼 수 있습니다.

## <a name="content-search-of-private-channels"></a>비공개 채널의 콘텐츠 검색

비공개 채널에 전송된 메시지 레코드는 그룹 사서함이 아닌 모든 비공개 채널 구성원의 사서함에 전달됩니다. 레코드 제목은 출처 비공개 채널을 표시하도록 형식이 지정됩니다.

각 개인 채널에는 부모 팀 사이트와 별개인 자체 SharePoint 사이트 모음이 있으므로 비공개 채널의 파일은 부모 팀과 독립적으로 관리됩니다.

Teams는 단일 채널의 콘텐츠 검색을 지원하지 않으므로 전체 팀을 검색해야 합니다. 비공개 채널의 콘텐츠 검색을 수행하려면 팀 전체, 개인 채널과 연결된 사이트 모음(파일 포함) 및 비공개 채널 구성원의 사서함(메시지 포함)을 검색합니다.

다음 단계를 사용하여 콘텐츠 검색에 포함할 개인 채널의 파일 및 메시지를 식별합니다.

### <a name="include-private-channel-files-in-a-content-search"></a>콘텐츠 검색에 개인 채널 파일 포함

이러한 단계를 수행하기 전에 [SharePoint Online 관리 셸을 설치하고 SharePoint Online에 연결](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)합니다.

1. 다음을 실행하여 팀의 개인 채널과 연결된 모든 SharePoint 사이트 모음 목록을 가져옵니다.

    ```PowerShell
    Get-SPOSite
    ```
2. 다음 PowerShell 스크립트를 실행하여 팀의 개인 채널 및 부모 팀 그룹 ID와 연결된 모든 SharePoint 사이트 모음 URL 목록을 가져옵니다.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. 각 팀 또는 그룹 ID에 대해 다음 PowerShell 스크립트를 실행하여 모든 관련 개인 채널 사이트를 식별합니다.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a>콘텐츠 검색에 개인 채널 메시지 포함

이러한 단계를 수행하기 전에 [최신 버전의 Teams PowerShell 모듈이](teams-powershell-overview.md) 설치되어 있는지 확인합니다.

1. 다음을 실행하여 팀의 비공개 채널 목록을 가져옵니다.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. 다음을 실행하여 프라이빗 채널 멤버 목록을 가져옵니다.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. 콘텐츠 검색 쿼리의 일부로 팀의 각 개인 채널에 있는 모든 멤버의 사서함을 포함합니다.

## <a name="related-topics"></a>관련 주제

- [Microsoft Purview 규정 준수 포털 eDiscovery 사례](/Office365/SecurityCompliance/ediscovery-cases)