---
title: Microsoft 팀의 콘텐츠 eDiscovery 조사 수행
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
description: 법률 소송 절차에 대해 전자적으로 저장 된 모든 정보를 제출 해야 하는 경우와 같이 eDiscovery를 preform 해야 할 경우 수행할 작업에 대해 알아보세요.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e645085130b65283a1841661c4e2885e5ea9cba4
ms.sourcegitcommit: ddb4eaf634476680494025a3aa1c91d15fb58413
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231119"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Microsoft 팀의 콘텐츠 eDiscovery 조사 수행
============================

대규모 기업은 모든 ESI (전자적 저장 정보) 제출을 요구 하는 높은 벌칙 법률 소송 절차에 게 노출 되는 경우가 많습니다.

모든 팀 1:1 또는 그룹 채팅은 각 사용자의 사서함으로 저널링 되며, 모든 표준 채널 메시지가 팀을 나타내는 그룹 사서함으로 저널링 됩니다. 표준 채널로 업로드 되는 파일은 SharePoint Online 및 비즈니스용 OneDrive의 eDiscovery 기능에서 다룹니다.

> [!NOTE]
> [개인 채널](private-channels.md) 의 메시지 및 파일 eDiscovery은 표준 채널과 다르게 작동 합니다. 자세히 알아보려면 [개인 채널 eDiscovery](#ediscovery-of-private-channels)를 참조 하세요.

1.  Microsoft 팀 콘텐츠를 사용 하 여 eDiscovery 조사를 수행 하려면 [이](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) 링크의 1 단계를 검토 합니다.

2.  Microsoft 팀 데이터가 Excel eDiscovery 내보내기 출력에 IM 또는 대화로 표시 되며,을 탑재할 수 있습니다. PST에서 해당 메시지를 보려면 내보내기를 게시 합니다.

    를 탑재 하는 경우. PST 팀의 경우 대화 내용 아래의 팀 채팅 폴더에 모든 대화가 보관 되어 있는지 확인 합니다. 메시지 제목은 팀 및 채널에 맞춰 정렬 됩니다. 아래 이미지를 검토 하 여 제조 사양 팀의 프로젝트 7 표준 채널을 messaged 하는 Bob 으로부터이 메시지를 확인할 수 있습니다.

    ![Outlook의 사용자 사서함에 있는 팀 채팅 폴더 스크린샷](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  사용자의 사서함에서 개인 채팅을 보려면 대화 내용 아래의 팀 채팅 폴더에도 포함 되어 있습니다.

## <a name="ediscovery-of-guest-to-guest-chats"></a>게스트 대 게스트 채팅 eDiscovery

사서함이 없으면 게스트 간 채팅 (가정용 테 넌 트 사용자가 없는 1xN 채팅)이 인덱싱되지 않으며 결과적으로 eDiscovery에 포함 되지 않습니다. 게스트 대 게스트 채팅에 eDiscovery 기능을 활용 하기 위해 클라우드 기반 사서함 (또는 팬텀 사서함)을 만들어 1xN 데이터를 저장 합니다. 팀 채팅 데이터는 클라우드 기반 사서함에 저장 된 후 eDiscovery 및 준수 콘텐츠 검색을 위해 인덱싱됩니다.

다음 그림은 사서함이 없는 게스트 대 게스트 채팅에 대해 eDiscovery가 작동 하는 방식을 보여 줍니다.

![비-게스트-사서함이 포함 된 채팅](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)

## <a name="ediscovery-of-private-channels"></a>개인 채널 eDiscovery

개인 채널로 전송 된 메시지의 레코드는 그룹 사서함이 아닌 모든 비공개 채널 구성원의 사서함으로 전달 됩니다. 레코드의 제목은 전송 된 개인 채널을 나타내도록 서식이 지정 됩니다.

각 개인 채널은 상위 팀 사이트와 별도의 고유한 SharePoint 사이트 모음을 포함 하므로 개인 채널의 파일은 상위 팀과 독립적으로 관리 됩니다.

팀은 단일 채널의 eDiscovery 기능을 지원 하지 않으므로 전체 팀을 검색 해야 합니다. 개인 채널에서 콘텐츠를 eDiscovery 검색 하려면 팀에서 검색 하 고, 개인 채널과 연결 된 사이트 모음 (파일 포함)과 개인 채널 구성원의 사서함 (메시지 포함)을 사용 합니다.

EDiscovery 검색에 포함할 개인 채널의 파일 및 메시지를 식별 하려면 다음 단계를 사용 합니다.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>EDiscovery 검색에 개인 채널 파일 포함

이 단계를 수행 하기 전에 [Sharepoint Online 관리 셸을 설치 하 고 Sharepoint online에 연결](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)합니다.

1. 팀의 개인 채널과 연결 된 모든 SharePoint 사이트 모음 목록을 가져오려면 다음을 실행 합니다.

    ```
    Get-SPOSite
    ```
2. 다음 PowerShell 스크립트를 실행 하 여 팀의 개인 채널과 해당 상위 팀 그룹 ID와 연결 된 모든 SharePoint 사이트 모음 Url 목록을 가져옵니다.

    ```
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. 각 팀 또는 그룹 ID에 대해 다음 PowerShell 스크립트를 실행 하 여 해당 팀의 그룹 ID 인 모든 관련 개인 채널 사이트를 식별 $groupID 합니다.

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>EDiscovery 검색에 개인 채널 메시지 포함

이 단계를 수행 하기 전에 [최신 버전의 팀 PowerShell 모듈이](teams-powershell-overview.md) 설치 되어 있는지 확인 합니다.

1. 다음을 실행 하 여 팀의 비공개 채널 목록을 가져옵니다.

    ```
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. 다음을 실행 하 여 개인 채널 구성원 목록을 가져옵니다.

    ```
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. EDiscovery 검색 쿼리의 일부로 팀의 각 개인 채널에 있는 모든 구성원의 사서함을 포함 합니다.

## <a name="related-topics"></a>관련 항목

- [팀 PowerShell 개요](teams-powershell-overview.md)