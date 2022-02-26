---
title: 콘텐츠에 대한 eDiscovery 조사 수행
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: 법적 절차를 위해 전자적으로 저장된 모든 정보를 제출해야 하는 경우와 같이 eDiscovery를 수행해야 할 때 수행할 작업을 알아보습니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5a35afa53a8f94a5d0106e67d2f9f87eacfaca63
ms.sourcegitcommit: edf68b7ac4f1861259a0990157ee6ae84f68ca42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2022
ms.locfileid: "62974465"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>콘텐츠에 대한 eDiscovery 조사를 Microsoft Teams

대기업은 종종 ESI(전자적으로 저장된 모든 정보)의 제출을 요구하는 높은 위약금 소송에 노출됩니다. Microsoft Teams eDiscovery 조사 중에 콘텐츠를 검색하고 사용할 수 있습니다.

## <a name="overview"></a>개요

모든 Microsoft Teams 1:1 또는 그룹 채팅은 해당 사용자의 사서함에 저널로 기록됩니다. 모든 표준 채널 메시지는 팀을 나타내는 그룹 사서함으로 저널링됩니다. 표준 채널에 업로드된 파일은 온라인 및 SharePoint eDiscovery 기능에 비즈니스용 OneDrive.

개인 채널의 메시지 및 파일의 eDiscovery [](private-channels.md) 는 표준 채널과 다르게 작동합니다. 자세한 내용은 [개인 채널의 eDiscovery를 참조하세요](#ediscovery-of-private-channels).

모든 Teams eDiscoverable은 없습니다. 다음 표에는 Microsoft eDiscovery 도구를 사용하여 검색할 수 있는 콘텐츠 형식이 표시됩니다.

| 콘텐츠 형식 | eDiscoverable | 참고 |
|:--- | :--- |:--- |
|오디오 녹음 | 아니요 | |
|카드 콘텐츠|예|자세한 [내용은 카드 콘텐츠 검색](#search-for-card-content) 을 참조하세요.|
|채팅 링크 | 예 | |
|채팅 메시지 | 예 |여기에는 Teams 채널의 콘텐츠, 1:1 채팅, 1:N 그룹 채팅 및 게스트 사용자 참가자와의 채팅이 포함됩니다.  |
|코드 코드 코드 코드 | 아니요 | |
|편집된 메시지 | 예 | 사용자가 보류 중이면 편집된 이전 버전의 메시지도 유지됩니다. |
|이모지, GIF 및 스티커 | 예 | |
|피드 알림 | 아니요 | |
|인라인 이미지 | 예 | |
|루프 구성 요소| 예|루프 구성 요소의 콘텐츠는 루프 구성 요소를 보내는 사용자의 비즈니스용 OneDrive .fluid 파일에 저장됩니다. 즉, 루프 구성 요소에서 콘텐츠를 검색할 OneDrive 데이터 원본으로 데이터를 포함해야 합니다. |
|IM 대화 모임 | 예 | |
|모임 메타데이터<sup>1</sup> | 예 |  |
|채널 이름 | 예 | |
|개인 채널 메시지 | 예 | |
|따옴표 | 예 | 인용된 콘텐츠는 검색할 수 있습니다. 그러나 검색 결과는 콘텐츠가 인용된 것을 나타내지 않습니다. |
|반응(예: 좋아, 하트 및 기타 반응) | 아니요 | |
|제목 | 예 | |
|표 | 예 | |
||||

<sup>1</sup> 모임(및 호출) 메타데이터에는 다음이 포함됩니다.

- 모임 시작 및 종료 시간 및 기간
- 각 참가자에 대한 모임 참가 및 이벤트 남기기
- VOIP 조인/통화
- 익명 조인
- 페더리드 사용자 조인
- 게스트 사용자 조인

  이미지는 모임 메타데이터의 예제를 보여줍니다.

  > [!div class="mx-imgBorder"]
  > ![규정 준수 복사본의 모임 메타데이터입니다.](media/conversationOption3.png)

다음은 모임 중에 참가자 간의 IM 대화의 예입니다.

![참가자 간의 Teams.](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![eDiscovery 검색 결과의 참가자 간의 대화입니다.](media/MeetingImConversation2.png)

eDiscovery 조사 수행에 대한 자세한 내용은 [Core eDiscovery 시작을 참조하세요](/microsoft-365/compliance/get-started-core-ediscovery).

Microsoft Teams eDiscovery 내보내기 출력에 im 또는 Conversations로 Excel 표시됩니다. 파일을 내 `.pst` 보낼 Outlook 해당 메시지를 볼 수 있습니다.

팀의 .pst 파일을 볼 때 모든 대화는 대화 기록 아래에 있는 팀 채팅 폴더에 있습니다. 메시지 제목에는 팀 이름과 채널 이름이 포함되어 있습니다. 예를 들어 아래 이미지는 제조 사양 팀의 Project 7개 표준 채널에 메시지를 보낸 Bob의 메시지를 보여줍니다.

![사용자의 사서함에 있는 팀 채팅 폴더의 스크린샷을 Outlook.](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

사용자의 사서함에 있는 비공개 채팅은 대화 기록 아래 팀 채팅 폴더에 저장됩니다.

## <a name="ediscovery-of-private-channels"></a>개인 채널의 eDiscovery

비공개 채널로 전송된 메시지의 준수 복사본은 그룹 사서함이 아닌 모든 비공개 채널 구성원의 사서함으로 전달됩니다. 준수 복사본의 제목에는 전송된 비공개 채널에서 보냈다는 걸 나타내는 서식이 지정됩니다.

각 개인 채널에는 부모 팀 사이트와 SharePoint 자체 사이트가 있기 때문에 개인 채널의 파일은 부모 팀과 독립적으로 관리됩니다.

Teams 팀 내에서 단일 채널의 eDiscovery 검색을 지원하지 않습니다. 따라서 팀 전체를 검색해야 합니다. 개인 채널에서 콘텐츠의 eDiscovery 검색을 수행하려면 팀, 개인 채널과 연결된 사이트 모음(파일을 포함), 개인 채널 구성원의 사서함(메시지를 포함)을 검색합니다.

다음 단계를 사용하여 eDiscovery 검색에 포함할 개인 채널의 파일 및 메시지를 식별합니다.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>eDiscovery 검색에 개인 채널 파일 포함

이러한 단계를 수행하기 전에 온라인 SharePoint 셸을 설치하고 온라인 SharePoint [연결합니다](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

1. 다음을 실행하여 팀의 개인 채널과 SharePoint 모든 사이트 모음의 목록을 얻습니다.

    ```PowerShell
    Get-SPOSite
    ```

2. 다음 PowerShell 스크립트를 실행하여 팀의 SharePoint 및 부모 팀 그룹 ID와 연결된 모든 사이트 모음 URL의 목록을 얻습니다.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. 각 팀 또는 그룹 ID에 대해 다음 PowerShell `$groupID` 스크립트를 실행하여 팀의 그룹 ID인 모든 관련 개인 채널 사이트를 식별합니다.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```
> [!NOTE]
> SharePoint 2021년 6월 28일 이후에 만든 개인 채널의 사이트는 사용자 `teamchannel#1` 지정 템플릿 ID에 값을 사용하세요. 따라서 이 날짜 이후에 만든 개인 채널의 경우 이전 `teamchannel#1` 두 스크립트를 실행하는 경우 값을 사용하세요.

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>eDiscovery 검색에 개인 채널 메시지 포함

이러한 단계를 수행하기 전에 최신 버전의 [PowerShell 모듈](teams-powershell-overview.md)을 Teams 있는지 확인합니다.

1. 다음 명령을 실행하여 검색할 개인 채널이 포함된 팀의 그룹 ID를 얻습니다.

   ```powershell
   Get-Team -MailNickName <mail alias of the associated Office 365 Group>
   ```

   > [!TIP]
   > 매개 변수 없이 **Get-Team** cmdlet을 실행하여 조직의 모든 Teams 표시합니다. 목록에는 모든 팀에 대한 그룹 ID 및 MailNickName이 포함되어 있습니다.

2. 다음 명령을 실행하여 팀에서 개인 채널 목록을 얻습니다. 1단계에서 얻은 팀의 그룹 ID를 사용 합니다.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupId> -MembershipType Private
    ```

3. 다음 명령을 실행하여 개인 채널 소유자 및 멤버 목록을 얻습니다.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupId> -DisplayName "Engineering" 
    ```

4. [eDiscovery](/microsoft-365/compliance/search-for-content-in-core-ediscovery) 검색 쿼리의 일부로 팀의 각 개인 채널의 모든 소유자 및 구성원의 사서함을 포함합니다.

## <a name="search-for-content-for-guest-users"></a>게스트 사용자에 대한 콘텐츠 검색

eDiscovery 도구를 사용하여 조직의 게스트 사용자와 Teams 콘텐츠를 검색할 수 있습니다. Teams 사용자와 연결된 채팅 콘텐츠는 클라우드 기반 저장소 위치에 보존되고 eDiscovery를 사용하여 검색할 수 있습니다. 여기에는 게스트 사용자가 조직의 다른 사용자와 함께 참여하는 1:1 및 1:N 채팅 대화의 콘텐츠를 검색하는 것이 포함됩니다. 게스트 사용자가 참여하는 비공개 채널 메시지를 검색하고 게스트 *:* 게스트 채팅 대화에서 유일한 참가자가 게스트 사용자인 콘텐츠를 검색할 수도 있습니다.

게스트 사용자에 대한 콘텐츠를 검색하는 경우:

1. 커넥트 Ad PowerShell에 대해 설명합니다. 지침은 PowerShell을 커넥트 "Azure Active Directory PowerShell" 섹션을 커넥트 [Microsoft 365 참조하세요](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). 이전 항목에서 1단계 및 2단계를 완료해야 합니다.

2. Azure AD PowerShell에 성공적으로 연결한 후 다음 명령을 실행하여 조직의 모든 게스트 사용자에 대한 UPN(사용자 주체 이름)을 표시합니다. 4단계에서 검색을 만들 때 게스트 사용자의 UPN을 사용해야 합니다.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > 컴퓨터 화면에 사용자 주체 이름 목록을 표시하는 대신 명령의 출력을 텍스트 파일로 리디렉션할 수 있습니다. 이전 명령에 추가 `> filename.txt` 하여 이 작업을 할 수 있습니다. 사용자 주체 이름이 있는 텍스트 파일이 현재 폴더에 저장됩니다.

3. 다른 Windows PowerShell 창에서 Security & PowerShell에 연결합니다. 지침은 보안 커넥트 [준수 센터 PowerShell에 & 참조하세요](/powershell/exchange/connect-to-scc-powershell). 다단계 인증을 사용하지 않고도 연결할 수 있습니다.

4. 다음 명령을 실행하여 지정된 게스트 사용자가 참여한 모든 콘텐츠(예: 채팅 메시지 및 전자 메일 메시지)를 검색하는 콘텐츠 검색을 생성합니다.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   예를 들어 게스트 사용자 Sara Davis와 연결된 콘텐츠를 검색하기 위해 다음 명령을 실행합니다.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    PowerShell을 사용하여 콘텐츠 검색을 만드는 데 대한 자세한 내용은 [New-ComplianceSearch를 참조하세요](/powershell/module/exchange/new-compliancesearch).

5. 다음 명령을 실행하여 4단계에서 만든 콘텐츠 검색을 시작하세요.

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. 로 이동 [https://compliance.microsoft.com](https://compliance.microsoft.com) 한 다음 **모든** > **Content 검색 표시를 클릭합니다**.

7. 검색 목록에서 4단계에서 만든 검색을 선택하여 플라이아웃 페이지를 표시합니다.

8. 플라이아웃 페이지에서 다음 작업을 할 수 있습니다.

   - 결과 **보기를** 클릭하여 검색 결과를 보고 콘텐츠를 미리 볼 수 있습니다.

   - 쿼리 필드 **옆에** 있는 편집 **을 클릭하여 편집** 한 다음 검색을 다시 실행합니다. 예를 들어 검색 쿼리를 추가하여 결과를 좁힐 수 있습니다.

   - 결과 **내보내기 를** 클릭하여 검색 결과를 내보내고 다운로드합니다.

## <a name="search-for-card-content"></a>카드 콘텐츠 검색

여러 채널, 1:Teams 채팅 및 1xN 채팅의 앱에서 생성된 카드 콘텐츠는 사서함에 저장되고 검색할 수 있습니다. 카드 *는* 짧은 콘텐츠에 대한 UI 컨테이너입니다. 카드에는 여러 속성과 첨부 파일이 있을 수 있으며 카드 작업을 트리거할 수 있는 단추를 포함할 수 있습니다. 자세한 내용은 카드를 [참조하세요.](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

다른 Teams 콘텐츠와 마찬가지로 카드 콘텐츠가 저장되는 위치는 카드가 사용된 위치를 기반으로 합니다. 채널에 사용되는 카드의 Teams 그룹 사서함에 Teams 저장됩니다. 1:1 및 1xN 채팅에 대한 카드 콘텐츠는 채팅 참가자의 사서함에 저장됩니다.

카드 콘텐츠를 검색하기 위해 조건 또는 검색 `kind:microsoftteams` 을 사용할 `itemclass:IPM.SkypeTeams.Message` 수 있습니다. 검색 결과를 검토할 때 Teams 봇에 의해 생성된 카드 콘텐츠에는 보낸 사람 **/**`<appname>@teams.microsoft.com`작성자 전자 메일 속성이 있습니다. 여기서 `appname` 카드 콘텐츠를 생성한 앱의 이름입니다. 사용자가 카드 콘텐츠를 생성한 경우 **보낸 사람/작성자의 값이** 사용자를 식별합니다.

콘텐츠 검색 결과에서 카드 콘텐츠를 볼 때 콘텐츠가 메시지에 첨부 파일로 표시됩니다. 첨부 파일은 `appname.html`이라는 이름입니다. 여기서 `appname` 카드 콘텐츠를 생성한 앱의 이름입니다. 다음 스크린샷은 카드 콘텐츠(Asana라는 앱의 경우)가 검색 결과와 Teams 표시하는 방법을 보여 주며,

**카드 콘텐츠가 Teams**

![채널 메시지의 Teams 콘텐츠입니다.](media/CardContentTeams.png)

**검색 결과의 카드 콘텐츠**
  
![콘텐츠 검색 결과의 동일한 카드 콘텐츠입니다.](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> 현재 카드 콘텐츠의 이미지를 검색 결과에 표시하기 위해(예: https://teams.microsoft.com) 이전 스크린샷의 확인 표시)에 로그인해야 Teams 검색 결과를 보는 데 사용하는 동일한 브라우저 세션의 다른 탭에서 다른 탭에서 로그인해야 합니다. 그렇지 않으면 이미지 자리 표시자가 표시됩니다.

## <a name="related-topics"></a>관련 항목

- [Microsoft 365 eDiscovery 솔루션](/microsoft-365/compliance/ediscovery)
- [Core eDiscovery 시작](/microsoft-365/compliance/get-started-core-ediscovery)
- [Teams 워크플로에서 Advanced eDiscovery](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Teams PowerShell 개요](teams-powershell-overview.md)
