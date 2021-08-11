---
title: 콘텐츠 검색을 Microsoft Teams
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: 콘텐츠 검색을 사용하여 Microsoft 365 규정 준수 센터, Microsoft Teams, Exchange Online, SharePoint, 비즈니스용 OneDrive 및 OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6810355304371564a2a305c82290df7667f5efd41889e598021636cc9ccd11d4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278216"
---
# <a name="use-content-search-in-microsoft-teams"></a>콘텐츠 검색을 Microsoft Teams

> [!NOTE]
> 개인 채널에서 메시지 및 [](private-channels.md) 파일의 콘텐츠 검색은 표준 채널과 다르게 작동합니다. 자세한 내용은 개인 [채널의 콘텐츠 검색을 참조하세요.](#content-search-of-private-channels)

콘텐츠 검색은 Microsoft Teams, Exchange 온라인 및 SharePoint 정보를 쿼리하는 비즈니스용 OneDrive.

자세한 내용은 에서 콘텐츠 [검색을 Microsoft 365.](/microsoft-365/compliance/content-search)

예를 들어,  제조 사양 사서함 및 제조 사양 SharePoint 사이트에 대해 콘텐츠 검색을 사용하여 Teams 온라인에서 표준 채널 Exchange 파일 업로드 및 수정을 검색하고 변경 내용을 SharePoint OneNote 수 있습니다.

콘텐츠 검색에 쿼리 조건을  추가하여 반환된 결과를 좁힐 수도 있습니다. 위의 예제에서는 "새 팩터리 **사양"을** 키워드로 사용한 콘텐츠를 검색할 수 있습니다.

> [!TIP]
> 검색 조건을 추가한 후 분석하기 위해 보고서 또는 실제 콘텐츠를 컴퓨터에 내보낼 수 있습니다.

## <a name="content-search-of-private-channels"></a>개인 채널의 콘텐츠 검색

비공개 채널에 전송된 메시지 레코드는 그룹 사서함이 아닌 모든 비공개 채널 구성원의 사서함에 전달됩니다. 레코드 제목은 출처 비공개 채널을 표시하도록 형식이 지정됩니다.

각 개인 채널에는 부모 SharePoint 별도의 자체 사이트 모음이 있기 때문에 개인 채널의 파일은 부모 팀과 독립적으로 관리됩니다.

Teams 채널의 콘텐츠 검색을 지원하지 않습니다. 따라서 팀 전체를 검색해야 합니다. 개인 채널의 콘텐츠 검색을 수행하려면 팀, 개인 채널과 연결된 사이트 모음(파일 포함), 개인 채널 구성원의 사서함(메시지를 포함)을 검색합니다.

다음 단계를 사용하여 콘텐츠 검색에 포함할 개인 채널의 파일 및 메시지를 식별합니다.

### <a name="include-private-channel-files-in-a-content-search"></a>콘텐츠 검색에 개인 채널 파일 포함

이러한 단계를 수행하기 전에 SharePoint 온라인 관리 셸을 설치하고 SharePoint [에 연결합니다.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

1. 다음을 실행하여 팀의 개인 채널과 SharePoint 모든 사이트 모음의 목록을 얻습니다.

    ```PowerShell
    Get-SPOSite
    ```
2. 다음 PowerShell 스크립트를 실행하여 팀의 SharePoint 및 부모 팀 그룹 ID와 연결된 모든 사이트 모음 URL의 목록을 얻습니다.

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

이러한 단계를 수행하기 전에 최신 버전의 [PowerShell 모듈이](teams-powershell-overview.md) 설치되어 Teams 확인합니다.

1. 다음을 실행하여 팀에서 개인 채널 목록을 얻습니다.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. 다음을 실행하여 개인 채널 구성원 목록을 얻습니다.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. 콘텐츠 검색 쿼리의 일부로 팀의 각 개인 채널의 모든 구성원의 사서함을 포함합니다.

## <a name="related-topics"></a>관련 항목

- [Microsoft 365 준수 센터의 eDiscovery 사례](/Office365/SecurityCompliance/ediscovery-cases)