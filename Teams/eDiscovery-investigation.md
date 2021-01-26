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
description: 법적 절차를 위해 전자적으로 저장된 모든 정보를 제출해야 하는 경우와 같이 eDiscovery를 수행해야 할 때 수행할 작업을 배워야 합니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: aa6b1212fda3983cc612885e41aa1131bb6f496d
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980462"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Microsoft Teams에서 콘텐츠에 대한 eDiscovery 조사 수행

대기업은 종종 모든 ESI(전자 저장 정보)의 제출을 요구하는 높은 페널티 법적 절차에 노출됩니다. Microsoft Teams 콘텐츠는 eDiscovery 조사 중에 검색하고 사용할 수 있습니다.

## <a name="overview"></a>개요

모든 Microsoft Teams 1:1 또는 그룹 채팅은 해당 사용자의 사서함에 기록됩니다. 모든 표준 채널 메시지는 팀을 나타내는 그룹 사서함으로 저널링됩니다. 표준 채널에 업로드된 파일은 SharePoint Online 및 비즈니스용 OneDrive에 대한 eDiscovery 기능에서 다루고 있습니다.

개인 채널의 메시지 및 파일의 [](private-channels.md) eDiscovery는 표준 채널과 다르게 작동합니다. 자세한 내용은 개인 [채널의 eDiscovery를 참조하세요.](#ediscovery-of-private-channels)

모든 Teams 콘텐츠는 eDiscoverable일 수 없습니다. 다음 표에서는 Microsoft eDiscovery 도구를 사용하여 검색할 수 있는 콘텐츠 형식을 보여줍니다.

| 콘텐츠 형식 | eDiscoverable | 참고 |
|:--- | :--- |:--- |
|오디오 녹음 | 아니요 | |
|카드 콘텐츠|예|자세한 [내용은 카드 콘텐츠 검색을](#search-for-card-content) 참조하세요.|
|채팅 링크 | 예 | |
|채팅 메시지 | 예 |여기에는 Teams 채널의 콘텐츠, 1:1 채팅, 1:N 그룹 채팅, 게스트 사용자 참가자와의 채팅이 포함됩니다.  |
|코드 코드시트 | 아니요 | |
|편집된 메시지 | 예 | 사용자가 보류 중이면 편집된 이전 버전의 메시지도 유지됩니다. |
|이모지, GIF 및 스티커 | 예 | |
|인라인 이미지 | 예 | |
|모임 IM 대화 | 예 | |
|모임 메타데이터<sup>1</sup> | 예 |  |
|채널 이름 | 아니요 | |
|개인 채널 메시지 | 예 | |
|따옴표 | 예 | 따옴표가 추가된 콘텐츠를 검색할 수 있습니다. 그러나 검색 결과에는 내용이 인용된 것으로 표시되지 않습니다. |
|반응(예: 좋아, 하트 및 기타 반응) | 아니요 | |
|제목 | 예 | |
|테이블 | 예 | |
|||

<sup>1개</sup> 모임(및 통화) 메타데이터에는 다음이 포함됩니다.

- 모임 시작 및 종료 시간 및 기간
- 각 참가자에 대한 모임 참가 및 이벤트 나가기
- VOIP 조인/호출
- 익명 조인
- 페더리된 사용자 조인
- 게스트 사용자 조인

  이 이미지는 모임 메타데이터의 예를 보여줍니다.

  > [!div class="mx-imgBorder"]
  > ![이미지는 CVR 레코드 모임 메타데이터입니다.](media/conversationOption3.png)

다음은 모임 중에 참가자 간의 IM 대화 예제입니다.

![Teams의 참가자 간 대화.](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![eDiscovery 검색 결과의 참가자 간 대화입니다.](media/MeetingImConversation2.png)

eDiscovery 조사 수행에 대한 자세한 내용은 [Core eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)시작을 참조하세요.

Microsoft Teams 데이터는 Excel eDiscovery 내보내기 출력에 IM 또는 대화로 표시됩니다. Outlook에서 파일을 열어 내보낼 때 해당 메시지를 `.pst` 볼 수 있습니다.

팀의 .pst 파일을 볼 때 모든 대화는 대화 기록 아래에 있는 팀 채팅 폴더에 보관됩니다. 메시지의 제목에는 팀 이름과 채널 이름이 포함되어 있습니다. 예를 들어 아래 이미지는 제조 사양 팀의 Project 7 표준 채널에 메시지를 보낸 Bob의 메시지를 보여줍니다.

![Outlook의 사용자 사서함에 있는 팀 채팅 폴더의 스크린샷](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

사용자의 사서함에 있는 비공개 채팅은 대화 기록 아래에 있는 팀 채팅 폴더에 저장됩니다.

## <a name="ediscovery-of-private-channels"></a>개인 채널의 eDiscovery

비공개 채널에 전송된 메시지 레코드는 그룹 사서함이 아닌 모든 비공개 채널 구성원의 사서함에 전달됩니다. 레코드 제목은 출처 비공개 채널을 표시하도록 형식이 지정됩니다.

각 개인 채널에는 상위 팀 사이트와 별개인 자체 SharePoint 사이트가 있기 때문에 비공개 채널의 파일은 상위 팀과 독립적으로 관리됩니다.

Teams는 팀 내에서 단일 채널의 eDiscovery 검색을 지원하지 않습니다. 따라서 팀 전체를 검색해야 합니다. 개인 채널에서 콘텐츠의 eDiscovery 검색을 수행하려면 팀, 개인 채널과 연결된 사이트 모음(파일 포함), 개인 채널 구성원의 사서함(메시지를 포함)을 검색합니다.

다음 단계를 사용하여 eDiscovery 검색에 포함할 개인 채널의 파일 및 메시지를 식별합니다.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>eDiscovery 검색에 개인 채널 파일 포함

이러한 단계를 수행하기 전에 SharePoint Online 관리 셸을 설치하고 [SharePoint Online에 연결합니다.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

1. 다음을 실행하여 팀의 비공개 채널과 연결된 모든 SharePoint 사이트 모음 목록을 얻습니다.

    ```PowerShell
    Get-SPOSite
    ```

2. 다음 PowerShell 스크립트를 실행하여 팀의 비공개 채널과 연결된 모든 SharePoint 사이트 모음 URL 및 부모 팀 그룹 ID 목록을 얻습니다.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. 각 팀 또는 그룹 ID에 대해 다음 PowerShell 스크립트를 실행하여 모든 관련 개인 채널 사이트를 식별합니다$groupID 팀의 그룹 ID입니다.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>eDiscovery 검색에 개인 채널 메시지 포함

이러한 단계를 수행하기 전에 최신 [버전의 Teams PowerShell](teams-powershell-overview.md) 모듈이 설치되어 있는지 확인합니다.

1. 다음 명령을 실행하여 팀의 비공개 채널 목록을 얻습니다.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. 다음 명령을 실행하여 개인 채널 멤버 목록을 얻습니다.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. [eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/search-for-content-in-core-ediscovery)검색 쿼리의 일부로 팀의 각 개인 채널에 있는 모든 구성원의 사서함을 포함합니다.

## <a name="search-for-content-for-guest-users"></a>게스트 사용자에 대한 콘텐츠 검색

eDiscovery 도구를 사용하여 조직의 게스트 사용자와 관련된 Teams 콘텐츠를 검색할 수 있습니다. 게스트 사용자와 연결된 Teams 채팅 콘텐츠는 클라우드 기반 저장소 위치에 유지되고 eDiscovery를 사용하여 검색할 수 있습니다. 여기에는 게스트 사용자가 조직의 다른 사용자와 참가자인 1:1 및 1:N 채팅 대화에서 콘텐츠를 검색하는 것이 포함됩니다. 게스트 사용자가 참가자인 개인 채널 메시지를 검색하고 게스트 사용자만이 게스트 사용자인 *게스트:게스트* 채팅 대화에서 콘텐츠를 검색할 수도 있습니다.

게스트 사용자에 대한 콘텐츠를 검색하는 경우:

1. Azure AD PowerShell에 연결합니다. 지침은 [PowerShell을 사용하여 Microsoft 365에](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)연결의 "Azure Active Directory PowerShell에 연결" 섹션을 참조하세요. 이전 항목의 1단계와 2단계를 완료해야 합니다.

2. Azure AD PowerShell에 성공적으로 연결한 후 다음 명령을 실행하여 조직의 모든 게스트 사용자에 대한 UPN(사용자 계정 이름)을 표시합니다. 4단계에서 검색을 만들 때 게스트 사용자의 UPN을 사용해야 합니다.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > 컴퓨터 화면에 사용자 계정 이름 목록을 표시하는 대신 명령의 출력을 텍스트 파일로 리디렉션할 수 있습니다. 이전 명령에 추가하여 이 `> filename.txt` 작업을 할 수 있습니다. 사용자 계정 이름이 있는 텍스트 파일이 현재 폴더에 저장됩니다.

3. 다른 Windows PowerShell Security & 준수 센터 PowerShell에 연결합니다. 지침은 Security & [준수 센터 PowerShell을 참조하세요.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 다단계 인증을 사용하여 연결하거나 사용하지 않고 연결할 수 있습니다.

4. 다음 명령을 실행하여 지정된 게스트 사용자가 참가자인 모든 콘텐츠(예: 채팅 메시지 및 전자 메일 메시지)를 검색하는 콘텐츠 검색을 만들 수 있습니다.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   예를 들어 게스트 사용자인 Sara Davis와 연결된 콘텐츠를 검색하기 위해 다음 명령을 실행합니다.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    PowerShell을 사용하여 콘텐츠 검색을 만드는 자세한 내용은 [New-ComplianceSearch를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

5. 다음 명령을 실행하여 4단계에서 만든 콘텐츠 검색을 시작하세요.

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. 이동한 다음 모든 콘텐츠 [https://compliance.microsoft.com](https://compliance.microsoft.com) 검색   >  **표시를 클릭합니다.**

7. 검색 목록에서 4단계에서 만든 검색을 선택하여 플라이아웃 페이지를 표시합니다.

8. 플라이아웃 페이지에서 다음을 할 수 있습니다.

   - 검색 **결과를 보고** 콘텐츠를 미리 보려면 결과 보기를 클릭합니다.

   - 쿼리 필드 **옆에 있는** **편집을** 클릭하여 편집한 다음 검색을 다시 실행합니다. 예를 들어 검색 쿼리를 추가하여 결과 범위를 좁힐 수 있습니다.

   - 내보내기 **결과를 클릭하여** 검색 결과를 내보내고 다운로드합니다.

## <a name="search-for-card-content"></a>카드 콘텐츠 검색

Teams 채널의 앱에서 생성한 카드 콘텐츠, 1:1 채팅 및 1xN 채팅은 사서함에 저장되고 검색할 수 있습니다. *카드는* 짧은 콘텐츠의 UI 컨테이너입니다. 카드에는 여러 속성과 첨부 파일이 있을 수 있으며 카드 작업을 트리거할 수 있는 단추를 포함할 수 있습니다. 자세한 내용은 카드를 [참조하세요.](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards)

다른 Teams 콘텐츠와 마찬가지로 카드 콘텐츠가 저장되는 위치는 카드가 사용된 위치를 기반으로 합니다. Teams 채널에 사용되는 카드의 콘텐츠는 Teams 그룹 사서함에 저장됩니다. 1:1 및 1xN 채팅의 카드 콘텐츠는 채팅 참가자의 사서함에 저장됩니다.

카드 콘텐츠를 검색하기 위해 조건 또는 검색 `kind:microsoftteams` 조건을 `itemclass:IPM.SkypeTeams.Message` 사용할 수 있습니다. 검색 결과를 검토할 때 Teams 채널의 봇에서 생성된 카드 콘텐츠에는 보낸 **사람/작성자** 전자 메일 속성이 있습니다. 여기서 카드 콘텐츠를 생성한 앱의 `<appname>@teams.microsoft.com` `appname` 이름입니다. 사용자가 카드 콘텐츠를 생성한 경우 보낸 **사람/작성자의 값이** 사용자를 식별합니다.

콘텐츠 검색 결과에서 카드 콘텐츠를 볼 때 콘텐츠는 메시지에 첨부 파일로 표시됩니다. 첨부 파일 이름은 카드 콘텐츠를 생성한 앱의 `appname.html` `appname` 이름입니다. 다음 스크린샷은 Teams 및 검색 결과에 카드 콘텐츠(Asana라는 앱의 경우)가 나타나는 방법을 보여 주며,

**Teams의 카드 콘텐츠**

![Teams 채널 메시지의 카드 콘텐츠](media/CardContentTeams.png)

**검색 결과의 카드 콘텐츠**
  
![콘텐츠 검색 결과의 동일한 카드 콘텐츠](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> 현재 카드 콘텐츠의 이미지를 검색 결과에 표시(예: 이전 스크린샷의 확인 표시)에 표시하기 위해 검색 결과를 보는 데 사용하는 동일한 브라우저 세션의 다른 탭에 있는 Teams에 https://teams.microsoft.com) 로그인해야 합니다. 그렇지 않으면 이미지 자리 표시자도 표시됩니다.

## <a name="advanced-ediscovery"></a>고급 eDiscovery

고급 [eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)워크플로를 사용하여 일부 Microsoft Teams 콘텐츠를 검색하고 보존할 수도 있습니다. eDiscovery는 다양한 검색, 보류 및 내보내기 기능을 제공하는 반면 고급 eDiscovery는 규정 준수 관리자에게 데이터 원본을 식별하고 해당 콘텐츠를 분석하는 더 많은 도구를 제공합니다.

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>Teams 콘텐츠에 대한 고급 eDiscovery 관리 워크플로

관할권은 다양한 팀의 구성원일 수 있습니다. 이러한 양도인과 관련된 Teams 콘텐츠를 캡처할 수 있습니다. 관리인 워크플로에 대한 지침은 [고급 eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)사례에 관리인 추가를 참조하세요.

양도인을 추가한 후 다음  단추를 클릭한 다음 추가 **단추를** 클릭합니다. 그러면 추가 위치를 선택하라는 메시지가 표시되는 창이 표시됩니다. 그러면 해당 데이터에 대한 모든 유관자 구성원과 해당 SharePoint 사이트 위치가 표시됩니다. 이러한 모든 데이터 원본 및 팀에서 eDiscovery에 사용할 콘텐츠를 선택한 다음 해당 사용자와 식별된 모든 데이터 원본을 보류하도록 할 수 있습니다.

Exchange 콘텐츠, OneDrive 콘텐츠 또는 둘 다를 포함할지 여부를 선택할 수 있습니다. Exchange 콘텐츠에는 전자 메일, 사서함에 저장된 Teams 콘텐츠 등 사용자의 사서함에 있는 모든 응용 프로그램 콘텐츠가 포함됩니다. OneDrive 콘텐츠에는 사용자의 콘텐츠뿐만 아니라 OneDrive에 저장된 모든 Teams 콘텐츠(예: 1:1 채팅, 1:N 채팅, 채팅에서 공유된 파일)가 포함됩니다.

또한 채널 채팅 메시지 및 권한이 있는 파일을 포함하기 위해 양도관이 구성원인 팀을 연결하는 옵션도 있습니다. 또한 다른 모든 팀은 양도인과 연결될 수 있습니다.

> [!NOTE]
> 개인 채널의 메시지 및 파일의 [](private-channels.md) eDiscovery는 표준 채널과 다르게 작동합니다. 자세한 내용은 개인 [채널의 eDiscovery를 참조하세요.](#ediscovery-of-private-channels)

### <a name="placing-a-data-source-on-hold"></a>데이터 원본 보류

보유자로 지정하는 특정 사용자가 없는 경우 전체 데이터 원본을 보류할 수 있습니다. 보류에 대한 자세한 내용은 [고급 eDiscovery의](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)보류 관리를 참조하세요.

Teams 콘텐츠에 대한 보류를 만들 때 보류에 포함할 위치를 모두 선택할 수 있습니다. 사용자가 콘텐츠를 삭제하거나 변경하는 경우에도 보류는 해당 콘텐츠의 모든 이전 버전 복사본을 유지 관리합니다.

선택적 쿼리를 사용하여 키워드, 날짜 범위, 작성자 및 기타 여러 조건에 따라 보류에 대한 조건을 설정할 수도 있습니다. 키워드를 지정하지 않으면 해당 데이터 원본의 모든 키워드가 보류됩니다.

### <a name="advanced-ediscovery-searches"></a>고급 eDiscovery 검색

Teams 콘텐츠를 검색할 수도 있습니다. 검색에 대한 자세한 내용은 [고급 eDiscovery의](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery)사례에 대한 데이터 수집을 참조하세요. 하나의 메시지가 검색 쿼리와 일치하는 경우 검색은 전체 대화를 반환합니다.

검색 쿼리를 만들 때 이미 선택한 모든 원본을 검색할 수 있도록 보육자 선택할 수 있습니다. 사용자에게 매핑되지 않은 Teams 사이트와 같은 비지원 출처를 검색할 수도 있습니다. 선택적 쿼리를 사용하여 Teams 콘텐츠 내에서 검색 범위를 좁힐 수도 있습니다.

검색을 만들어 선택한 후 선택한 검색에서 수행할 수 있는 추가 세부 정보 및 작업이 있는 창이 표시됩니다. 통계 단추를  클릭하면 위치 유형, 콘텐츠의 원본, 콘텐츠가 그룹 사서함, 개별 사용자 사서함 또는 SharePoint 사이트에 있는지 여부에 따라 분석 결과를 포함하여 검색에 대한 통계를 볼 수 있습니다. 따라서 검색 결과에 기여하는 원본의 분석 결과를 볼 수 있습니다. 또한 쿼리 **보기를** 사용할 수 있으므로 결과에 기여하는 개별 키워드를 볼 수 있습니다.

검색을 마무리한 후 결과 추가를 클릭하여 집합 단추를 검토하고 검토 집합에 추가할 수 있습니다.  검토 집합에 대한 자세한 내용은 이 문서의 후반부에 있는 [고급 eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) 및 [검토](#review-sets-workflow) 집합 워크플로에서 검토 집합 관리를 참조하세요.

#### <a name="normal-review-sets-and-conversation-review-sets"></a>일반 검토 집합 및 대화 검토 집합

검토 집합에 검색을 추가할 때 일반 검토 집합 또는 대화 검토 집합에서 선택할 수 있습니다.

일반 검토 집합은 내보내기와 유사합니다. Teams 콘텐츠에 대한 개별 파일을 제공하며 기본 보기로 콘텐츠를 `.msg` 제공합니다. 일반적으로 다른 소프트웨어 도구를 사용하여 나중에 파일을 다시 처리하려면 일반 검토 집합을 사용합니다.

대화 검토 집합은 대화를 보다 직관적이고 스레드된 보기로 제공합니다. 관련 메시지를 적절한 순서로 함께 표시됩니다.

> [!div class="mx-imgBorder"]
> ![대화 검토 집합의 스크린샷](media/conversationOptions2.png)

재배포와 같은 기능은 두 가지 유형의 검토 집합에서 사용할 수 있습니다. 검토 집합에 대한 자세한 내용은 고급 [eDiscovery의 대화 검토를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)

#### <a name="collection-options"></a>컬렉션 옵션

검토 집합에 추가할 때 대화 검색 옵션 및 Teams  대화를 포함하여 창의  컬렉션 옵션 섹션 아래에 확인란으로 사용할 수 있는 몇 가지 옵션이 **있습니다.** 이러한 옵션을 사용하도록 설정하면 검토 집합의 일부인 개별 Teams 메시지도 컨텍스트에 따라 추가 메시지와 함께 표시됩니다. 예를 들어 쿼리가 구체적이고 하나의 메시지만 결과로 반환되는 경우 이러한 옵션을 사용하도록 설정하면 쿼리와 일치하는 메시지까지 이어지는 여러 메시지가 반환됩니다.

많은 논리 조건은 추가 메시지가 쿼리와 일치하는 메시지에 컨텍스트를 제공하는지 여부를 결정하는 데 사용됩니다. 예를 들어 Teams 콘텐츠의 경우 이러한 옵션을 사용하도록 설정하면 메시지가 스레드되는 방식 때문에 부모 메시지와 모든 자식 메시지를 검색합니다.

메시지 타임스탬프도 선택됩니다. 메시지가 쿼리와 일치하는 경우 4시간 범위 내에서 앞에 오거나 4시간 범위 내에 인접한 메시지는 대화의 일부로 간주되는 것으로 간주하고 결과에도 포함됩니다.

검색 쿼리와 일치하는 컨텍스트 메시지가 반환될지 확실해야 하는 경우 이러한 옵션을 사용할 필요가 없습니다. 모든 콘텐츠를 수집하거나 쿼리의 결과로 더 많은 메시지가 반환될 수 있도록 검색의 날짜 범위를 넓히면 됩니다.

### <a name="review-sets-workflow"></a>검토 집합 워크플로

검토 집합 탭을 클릭하여 기존 검토 집합을 보거나 새 검토 집합을 **만들 수** 있습니다. 검토 집합에 대한 자세한 내용은 [고급 eDiscovery에서](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)검토 집합 관리를 참조하세요.

문서 외에도 전자 메일, Teams 메시지, Yammer 및 기타 콘텐츠를 검토 집합에 추가할 수 있습니다. 검토 집합 내에서 콘텐츠 검색 및 사용자 지정 쿼리 만들기와 같은 다른 컨텍스트에서 수행할 수 있는 동일한 많은 작업을 수행할 수도 있습니다. 이러한 작업은 검토 집합에 추가된 항목에만 적용됩니다.

검토 **집합 관리 단추는** 분석, 요약 보고, 추가된 부하 집합 수 등의 추가 옵션을 제공합니다.

데이터의 시각화 및 차트에 액세스하려면 오른쪽 위에 있는 **개별 결과** 검색 프로필 \>  보기를 클릭합니다. 이러한 차트에서 에지를 클릭하여 대화형으로 쿼리할 콘텐츠 유형을 선택할 수 있습니다. 예를 들어 Teams 콘텐츠만 쿼리할 수 있습니다. 수동으로 작성하는 쿼리를 저장하는 것만큼 이러한 쿼리를 저장할 수도 있습니다.

#### <a name="summary-view-text-view-and-annotate-view"></a>요약 보기, 텍스트 보기 및 주석 추가 보기

검토 집합에서 Teams 대화를 클릭하면 전체 Teams 대화를 개별적으로 상호 작용할 수 있는 메시지 목록으로 표시하는 요약 보기가 표시됩니다. 메시지 오른쪽의 아래쪽 화살표를 클릭하여 메시지 세부 정보를 보거나 개별 파일을 다운로드할 수 있는 상황에 맞는 메뉴를 `.msg` 표시합니다. 메시지 세부 정보를 클릭하면 메타데이터 요약 또는 메시지의 전체 메타데이터가 표시됩니다.

PDF를 다운로드하려면 요약 보기의 오른쪽 위에 있는 다운로드 단추를 클릭합니다.

텍스트 보기 **탭을 클릭하여** Teams 대화의 추출된 텍스트에 대한 일반 텍스트 보기를 표시합니다. 이 일반 텍스트 콘텐츠는 내보내기에 적합하며 다른 소프트웨어 도구를 사용하여 쉽게 작업할 수 있습니다.

주석 보기 **탭을 클릭하여** 주석 기능에 액세스합니다. 이 탭에는 Teams 대화와 같은 형식으로 콘텐츠가 표시되지만 편집을 위한 추가 옵션도 있습니다. 연필 도구를 사용하여 노트를 작성하거나, 메시지에 그리거나, 세분화하여 스크래치할 수 있습니다. 영역을 검은색으로 표시하고 "Redacted"로 표시하는 직사각형을 그리는 데 사용할 수 있는 영역 재배치 도구도 있습니다. 

다음은 사용자 간의 스레드 대화에 대한 시정된 파일의 예입니다.

> [!div class="mx-imgBorder"]
> ![변경된 파일의 스크린샷](media/RedactedFileExample.png)

주석 추가 **보기** 탭의 아래쪽에는  태그 지정 패널을 표시하는 문서 태그 단추가 있습니다. 이 패널 내에서 Teams 대화 내의 모든 메시지에 태그를 적용할 수 있습니다. 대화에 "흥미로운 항목"이 포함되어 있는지 여부, 내보내기에 포함해야 하는지 여부, 추가 검토가 필요한지 여부 등 응답 응답 또는 응답하지 않는 대화, 권한 있는 대화로 레이블을 지정할 수 있습니다. 사용자 지정 가능한 다른 태그를 관리하고 적용할 수도 있습니다.

#### <a name="action-menu"></a>작업 메뉴

검토 집합 창에서 작업 내보내기 를 클릭하여 콘텐츠를 **내보낼 수** \> **있습니다.** 내보낼 때 사용할 수 있는 다양한 옵션이 있습니다.

모든 Teams 메시지에 대한 모든 메타데이터가 포함된 파일을 내보내려면 파일 로드 확인란을 **클릭하여** 선택합니다. 파일에 콘텐츠에 적용한 태그를 포함하려면 태그 확인란을  클릭하여 선택합니다.

**네이티브 파일 옵션을 사용하여** 기본 형식으로 파일을 내보낼 수 있습니다. 대화를 하나의 파일로 내보내거나 개별 채팅 메시지를 모두 별도의 파일로 내보낼 수 있습니다.

텍스트 **파일 옵션을** 사용하면 일반 텍스트 버전의 콘텐츠를 저장할 수 있습니다. 검토 집합에서 Teams 대화의 일반 텍스트 보기를 얻는 방법에 대한 자세한 내용은 위의 요약 보기, 텍스트 보기 및 주석 [추가 보기를 참조하세요.](#summary-view-text-view-and-annotate-view)

위 요약 [보기,](#summary-view-text-view-and-annotate-view) 텍스트 보기 및 주석 추가 보기 섹션에 설명된 대로 콘텐츠에 편집을 적용한 경우 편집된 네이티브를 변환된 **PDF로** 바꾸기 옵션을 선택하여 네이티브 파일을 PDF의 변환된 복사본으로 바꿀 수 있습니다.

Microsoft에서 제공한 Azure Blob Storage 컨테이너로 내보내거나 사용자 자신의 Azure Blob Storage 컨테이너를 제공할 수 있습니다.

내보내기 프로세스를 시작할 준비가 되면 내보내기 **단추를** 클릭합니다. Azure [Blob Storage](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) 컨테이너에 액세스하고 내보내기 완료 후 내보낼 콘텐츠를 다운로드하는 방법에 대한 자세한 내용은 내보내기 작업 다운로드를 참조하세요.

> [!NOTE]
> 내보내는 데 시간이 연장될 수 있습니다. 내보내기 프로세스의 상태를 추적하려면 검토 집합 탭을 **종료하고** 내보내기 **탭을** 클릭합니다.

## <a name="related-topics"></a>관련 항목

- [Microsoft 365의 eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [Teams PowerShell 개요](teams-powershell-overview.md)
