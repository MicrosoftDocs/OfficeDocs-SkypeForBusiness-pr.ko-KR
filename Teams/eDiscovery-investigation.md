---
title: eDiscovery 콘텐츠 조사
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
description: 법률 절차에 대한 모든 전자 저장 정보를 제출해야 하는 경우와 같이 eDiscovery를 수행해야 하는 경우 수행할 작업에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4679d8ed59ab8eec0fb856961f646d1f20049ff3
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814114"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Microsoft Teams에서 콘텐츠에 대한 eDiscovery 조사 조사

대기업은 종종 ESI(전자 저장 정보)를 제출하는 합리적인 법률 의문 사항으로 되어 있습니다. eDiscovery 조사 중에 Microsoft Teams 콘텐츠를 검색하고 사용할 수 있습니다.

## <a name="overview"></a>개요

모든 Microsoft Teams 1:1 또는 그룹 채팅은 해당 사용자의 사서함을 통해 업무를 수행합니다. 모든 표준 채널 메시지는 팀을 나타내는 그룹 사서함으로 이동합니다. 표준 채널에서 업로드한 파일은 SharePoint Online 및 비즈니스용 OneDrive의 eDiscovery 기능에 대해 다됩니다.

비공개 채널에서 메시지와 [파일을 보낸 후에는 표준](private-channels.md) 채널에서와 다르게 작동합니다. 자세한 내용은 [비공개 채널e의 eDiscovery를 참조하세요.](#ediscovery-of-private-channels)

모든 Teams 콘텐츠를 Discover로 기능할 수 있는 것은 아닌 경우. 다음 표에서는 eDiscovery를 통해 찾을 수 있는 콘텐츠 형식을 보여 주는 예제입니다.

| 콘텐츠 형식 | eDiscoverable | 참고 |
|:--- | --- |:--- |
| Teams 채팅 메시지 | 예 |  |
| 비공개 채널 메시지 | 예 | |
| 채널 이름 | 아니요 | |
| 모임 메신저 대화 | 예 | |
| 모임 메타데이터<sup>1</sup> | 예 |  |
| 편집된 메시지 | 예 | 사용자가 보류 중인 경우 이전 버전의 편집된 메시지는 보존됩니다. |
| 이모지, GMO, 스티커 | 예 | |
| 코드 조각 | 아니요 | |
| 채팅 링크 | 예 | |
| 다시 작음(예: 듣기, 하트 등) | 아니요 | |
| 인라인 이미지 | 예 | |
| 테이블 | 예 | |
| 제목 | 예 | |
| 시/따옴표 | 예 | 인용된 콘텐츠를 검색할 수 있습니다. 그러나 검색 결과로는 콘텐츠가 할당되었음을 나타내지는 않습니다. |
| 오디오 녹음 | 아니요 | |

<sup>모임</sup> 메타데이터에는 다음이 포함됩니다.

- 모임 또는 통화 시작 시간 및 종료 시간 및 기간
- 각 참가자에 대한 통화/모임 참가 및 종료
- VOIP 참가/호출
- 익명 참가
- 페더레이스 사용자 참가
- 게스트 사용자 참가

이미지는 메타데이터 예제를 보여 주는 이미지입니다.

![이미지는 CVR 레코드 모임 메타데이터입니다.](media/conversationOption3.png)

다음은 모임 중에 참가자 간의 메신저 대화의 예입니다.

![이미지는 참가자들 간의 대화입니다.](media/MeetingIMConversations.png)

![이미지는 참가자들 간의 대화입니다.](media/MeetingImConversation2.png)

Microsoft Teams 콘텐츠에 대한 eDiscovery 조사를 수행하려면 [Core eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery)시작에서 1단계를 검토하세요.

Microsoft Teams 데이터는 Excel eDiscovery 내보내기 출력에서 메신저 대화 또는 대화로 나타납니다. Outlook에서 파일을 `.pst` 열어 내보낸 후에 해당 메시지를 볼 수 있습니다.

팀에 대한 .pst 파일을 보고 있는 경우 모든 대화가 팀 채팅 폴더의 대화 내용 아래에 저장됩니다. 메시지 제목에는 팀 이름과 채널 이름이 포함되어 있습니다. 예를 들어 아래 이미지는 제조 사양 팀의 Project 7 표준 채널을 메시지를 받는 부동소의 메시지를 보여주고 있습니다.

![Outlook 사용자 사서함에 있는 팀 채팅 폴더 스크린샷](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

사용자의 사서함에 있는 비공개 채팅은 팀 채팅 폴더 아래에 대화 내용 아래에 저장됩니다.

## <a name="ediscovery-of-private-channels"></a>eDiscovery of pvate Channels

비공개 채널에 전송된 메시지 레코드는 그룹 사서함이 아닌 모든 비공개 채널 구성원의 사서함에 전달됩니다. 레코드 제목은 출처 비공개 채널을 표시하도록 형식이 지정됩니다.

각 비공개 채널에는 상위 팀 사이트와 별도로 별도의 SharePoint 사이트 모음이 있으므로 비공개 채널의 파일은 상위 팀과 개별적으로 관리됩니다.

Teams는 팀 내의 단일 채널에 대한 eDiscovery 검색을 지원하지 않으므로 전체 팀이 검색해야 합니다. 비공개 채널에서 콘텐츠를 eDiscovery 콘텐츠를 검색하려면 팀 전반에서 검색하고(파일 포함) 및 비공개 채널 구성원의 사서함(메시지를 포함하기 위한) 개인 채널 구성원의 사서함을 검색합니다.

다음 단계에 따라 eDiscovery 검색에 포함할 개인 채널에서 파일 및 메시지를 식별합니다.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>eDiscovery 검색에 개인 채널 파일 포함

이러한 단계를 수행하기 전에 [SharePoint Online 관리 셸을 설치하고 SharePoint Online에 연결합니다.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

1. 다음을 실행하여 팀의 비공개 채널과 연결된 모든 SharePoint 사이트 모음 목록을 가져올 수 있습니다.

    ```PowerShell
    Get-SPOSite
    ```

2. 다음 PowerShell 스크립트를 실행하여 팀의 비공개 채널과 연결된 모든 SharePoint 사이트 모음 URL 목록과 상위 팀 ID의 목록을 가져올 수 있습니다.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. 각 팀 또는 그룹 ID에 대해 다음 PowerShell 스크립트를 실행하여 모든 적정 비공개 채널 사이트를 식별합니다. 여기에서 $groupID 팀의 그룹 ID입니다.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>eDiscovery 검색에 개인 채널 메시지 포함

이러한 단계를 수행하기 전에 최신 [버전의 Teams PowerShell 모듈이 설치되어 있는지 확인합니다.](teams-powershell-overview.md)

1. 다음을 실행하여 팀의 비공개 채널 목록을 확인합니다.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. 다음을 실행하여 비공개 채널 구성원 목록을 확인합니다.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. eDiscovery 검색 쿼리의 일부로 팀에 있는 각 비공개 채널의 모든 구성원에 대한 사서함을 포함합니다.

## <a name="advanced-ediscovery"></a>고급 eDiscovery

일부 Microsoft Teams 콘텐츠는 고급 [eDiscovery 워크플로를 사용하여 검색하고 보관할 수 있습니다.](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) eDiscovery는 단일 검색, 보관 및 내보내기 기능으로 이어지는 여러 사용자만 고급 eDiscovery는 데이터 원본을 식별하고 해당 콘텐츠를 분석하는 데 더 많은 도구를 제공합니다.

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>Teams 콘텐츠에 대한 고급 eDiscovery 중요 도우미 워크플로

오토토마의는 다양한 팀의 구성원일 수 있습니다. 이러한 대중어와 연관된 Teams 콘텐츠를 캡처할 수 있습니다. 구현워자 워크플로의 배경 및 지침은 [고급 eDiscovery 워크플로를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)

에버디아어를 추가한 후에 다음 단추를 **클릭하고** 추가 단추를 **클릭합니다.** 그런 다음 추가 위치를 선택하라는 창에 55개의 추가 위치를 선택하면 해당 보유자의 구성원 자격과 해당 데이터에 해당하는 SharePoint 사이트 위치가 표시됩니다. 이러한 모든 데이터 원본과 팀에서 eDiscovery에 사용할 콘텐츠를 선택한 다음 해당 사용자와 보류로 식별한 모든 데이터 원본을 보관할 수 있습니다.

Exchange 콘텐츠, OneDrive 콘텐츠 또는 둘 다를 포함할지 여부를 선택할 수 있습니다. Exchange 콘텐츠에는 사용자의 사서함에 포함된 모든 응용 프로그램 콘텐츠(예: 전자 메일, 해당 사서함에 저장된 Teams 콘텐츠 등)가 포함됩니다. OneDrive 콘텐츠에는 사용자의 콘텐츠를 포함할 수 있지만 1:1 채팅, 1:N 채팅, 채팅과 같은 OneDrive에 저장된 모든 Teams 콘텐츠도 포함되어 있습니다.

또한 대리인 팀을 연결할 수 있는 옵션이 있으므로 채널 채팅 메시지와 보상자에 액세스하는 사람이 액세스할 수 있게 됩니다. 또한 다른 팀은 또한 인보자와 연결할 수 있습니다. 자세한 내용은 [고급 eDiscovery 사례에 오고항목 추가를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)

> [!NOTE]
> 비공개 채널에서 메시지와 [파일을 보낸 후에는 표준](private-channels.md) 채널에서와 다르게 작동합니다. 자세한 내용은 [비공개 채널e의 eDiscovery를 참조하세요.](#ediscovery-of-private-channels)

### <a name="placing-a-data-source-on-hold"></a>데이터 원본 보류

보유자로 지정할 특정 사용자가 없는 경우 전체 데이터 원본을 보류할 수 있습니다. 보류에 대한 자세한 내용은 [고급 eDiscovery에서 보류 관리를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)

Teams 콘텐츠를 보류하려면 보류에 포함할 위치를 모두 선택할 수 있습니다. 사용자가 콘텐츠를 삭제하거나 변경하더라도 보류에 포함한 콘텐츠의 사본이 보류됩니다.

키워드, 날짜 범위, 만든 이, 기타 여러 조건을 기준으로 보류 조건을 설정하기 위한 선택 쿼리를 사용할 수도 있습니다. 키워드를 지정하지 하면 해당 데이터 원본의 모든 항목이 보존되는 데 사용됩니다.

### <a name="advanced-ediscovery-searches"></a>고급 eDiscovery 검색

Teams 콘텐츠를 검색할 수 있습니다. 검색에 대한 자세한 내용은 [고급 eDiscovery에서 사례에 대한 데이터수집을 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery) 검색 쿼리와 일치하는 메시지가 없더라도 전체 대화가 반환됩니다.

검색 쿼리를 만들 때 에대한자를 선택하여 이미 선택한 모든 출처를 검색하도록 할 수 있습니다. 사용자에게 매핑되지 않은 Teams 사이트와 같은 바시처리스트 원본을 검색할 수도 있습니다. 선택적 쿼리를 Teams 콘텐츠 내에서 검색 범위를 좁용할 수도 있습니다.

검색을 만들어 선택하고 나면 선택한 검색에 대해 수행할 수 있는 추가 세부 정보와 작업이 나열된 창이 표시됩니다. **통계 단추를** 클릭하면 위치 유형에 맞는 분석, 콘텐츠의 원래 소스, 그룹 사서함의 콘텐츠 위치, 개별 사용자 사서함 또는 SharePoint 사이트 등 검색에 대한 통계를 볼 수 있습니다. 따라서 검색 결과에 어떤 출처가 적으로 어떤 원인이 있는지 분석 결과를 볼 수 있습니다. 또한 쿼리 **보기도 사용할** 수 있도록 쿼리 보기라고 표시되어 있어 결과에 어떤 개별 키워드가 있는지 확인할 수 있습니다.

검색을 완료하고 나면 결과 추가를 클릭하여 결과를 **검토하며** 검토 집합에 추가할 수 있습니다. 검토 집합에 대한 자세한 내용은 이 문서의 [뒷부분에 나오는 고급 eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) 및 [리뷰 설정 워크플로에서](#review-sets-workflow) 검토 설정 관리를 참조하세요.

#### <a name="normal-review-sets-and-conversation-review-sets"></a>일반 검토 집합 및 대화 검토 집합

검토 집합에 검색을 추가할 때 정상 검토 집합 또는 대화 검토 집합 중에서 선택할 수 있습니다.

일반적인 검토 집합은 내보내기와 비사유합니다. Teams 콘텐츠에 대한 `.msg` 개별 파일을 제공하고 기본 보기에 콘텐츠를 제공합니다. 다른 소프트웨어 도구를 사용하여 나중에 파일을 다시 처리하려는 경우 일반적인 검토 설정을 사용합니다.

대화 검토 목록은 대화에 더욱 관부분적이고 시각적인 보기를 제공합니다. 관련 메시지를 올바된 순서로 함께 표시합니다.

![대화 검토 집합 스크린샷](media/conversationOptions2.png)

다시 알림과 같은 기능은 두 유형의 검토 집합에서 사용할 수 있습니다. 검토 설정에 대한 자세한 내용은 [고급 eDiscovery에서의 대화를 검토하세요.](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)

#### <a name="collection-options"></a>컬렉션 옵션

검토 설정에 추가하면 대화 검색 옵션 및 Teams 대화를 비롯하여 창의 컬렉션 **Conversation Retrieval Options** 옵션 섹션에서 여러 옵션을 사용할 **수 있습니다.** **Collection Options** 이러한 옵션을 활성화하면 검토 설정에 포함된 모든 개별 Teams 메시지에 주위의 텍스트수정 메시지도 표시됩니다. 예를 들어 쿼리가 매우 특정이며 한 메시지만 결과값으로 반환되는 경우 이러한 옵션을 사용하도록 설정하면 여러 메시지가 쿼리와 일치하는 메시지를 전달하고 후바로 팔로우할 수 있습니다.

많은 논리 조건을 사용하여 메시지가 쿼리와 일치하는 메시지에 특정 인식을 제공하는지 여부를 확인하는 데 사용됩니다. 예를 들어 Teams 콘텐츠의 경우 이러한 옵션을 사용하도록 설정하면 메시지가 스레드되는 방식으로 인해 상위 메시지와 모든 자식 메시지를 검색할 수 있습니다.

메시지 타임스탬프도 선택되어 있습니다. 메시지가 쿼리와 일치하는 경우, 4시간 이내에 또는 4시간 이내에 이어지는 메시지는 대화에 포함되며 결과에 포함됩니다.

검색 쿼리와 일치하는 상황별 메시지가 반환될 특정 메시지가 검색 쿼리에 반환될지를 특정게 하는 경우 이러한 옵션을 사용할 필요가 없습니다. 모든 콘텐츠를 수집하거나 더 많은 메시지가 쿼리 결과로 반환되도록 검색 범위의 날짜 범위를 넓히거나 검색 범위의 범위를 넓히게 할 수 있습니다.

### <a name="review-sets-workflow"></a>설정 워크플로 검토

검토 설정 탭을 클릭하면 기존 검토 집합을 보거나 새 목록을 **만들 수** 있습니다. 검토 집합에 대한 자세한 내용은 [고급 eDiscovery에서 리뷰 설정 관리를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)

문서 외에도 검토를 설정할 전자 메일, Teams 메시지 Yammer, 기타 콘텐츠를 추가할 수 있습니다. 검토 집합 내에서 콘텐츠 검색 및 사용자 지정 쿼리 작성 등과 같이 다른 상황에서 수행할 수 있는 것은 다수의 동일한 작업을 수행할 수 있습니다. 이러한 작업은 검토 집합에 추가된 항목에만 적용됩니다.

검토 **설정 관리 단추는** 분석, 요약 보고, 추가된 로드 집합 수 등의 추가 옵션을 제공합니다.

데이터의 시각화 및 차트에 액세스하려면 오른쪽 **위에서** \> **개별 결과 검색 프로필** 보기를 클릭합니다. 이 차트의 방사를 클릭하여 쿼리하려는 콘텐츠의 형식을 대화형으로 선택할 수 있습니다. 예를 들어 Teams 콘텐츠만 쿼리하라고 선택할 수 있습니다. 이러한 쿼리를 수동으로 작성하는 것과 마찬가지로 저장할 수도 있습니다.

#### <a name="summary-view-text-view-and-annotate-view"></a>요약 보기, 텍스트 보기 및 주의 주기 탭

검토 설정에서 Teams 대화를 클릭하면 Teams 대화가 **Summary view**전체 Teams 대화가 개별적으로 조작할 수 있는 메시지 목록으로 표시됩니다. 메시지의 오른쪽에 있는 아래쪽 화살표를 클릭하여 메시지 세부 정보를 보거나 개별 파일을 다운로드할 수 있는 상황에 맞는 메뉴를 `.msg` 표시합니다. 메시지 세부 정보를 클릭하면 메타데이터 또는 메시지의 전체 메타데이터에 대한 요약이 표시됩니다.

PDF를 다운로드하려면 요약 보기 오른쪽 위에 있는 다운로드 단추를 클릭합니다.

텍스트 **보기 탭을** 클릭하여 Teams 대화와 추출된 텍스트의 일반 텍스트 보기를 표시합니다. 이 일반 텍스트 콘텐츠는 내보내기에 적제하고 다른 소프트웨어 도구를 사용하여 쉽게 작업할 수 있습니다.

주제 **기능에 액세스하려면 주제 탭을** 클릭합니다. 이 탭은 Teams 대화와 비합하되만 편집할 수 있는 추가 옵션이 있는 형식의 콘텐츠를 표시합니다. 노트를 작성하거나, 메시지에 그리거나, 정제로 명의하기 쉽게 작성하는 데 사용할 수 있는 연필 도구가 있습니다. 영역의 **정확도를** 사용하여 해당 영역을 이사각형으로 그리고 "Redacted"로 표시하는 사각형을 그릴 수 있습니다.

다음은 사용자 들 사이에 스레드된 대화에 대한 실제로 해당 파일의 예입니다.

![복구된 파일 스크린샷](media/RedactedFileExample.png)

주석 **번역 탭 하단에는** **태그 패널이** 표시되는 태그 문서 단추가 있습니다. 이 패널 내에서 Teams 대화 내의 모든 메시지에 태그를 적용할 수 있습니다. 대화에 응답 또는 응답성 없이, 사용 여부와 상관없이 부여되거나 여부에 상관없이 내보내기에 포함할지 여부, 검토가 필요한지 여부 등으로 텍스트에 레이블을 지정할 수 있습니다. 또한 기타 사용자 지정 가능한 태그를 관리하고 적용할 수 있습니다.

#### <a name="action-menu"></a>작업 메뉴

검토 집합 내에서 작업 내보내기를 클릭하여 콘텐츠를 내보낼 **수** \> **있습니다.** 내보낼 때 사용할 수 있는 다양한 옵션이 있습니다.

모든 Teams 메시지에 대한 모든 메타데이터를 포함하는 파일을 내보내려면 파일 로드 **확인란을 클릭하여** 선택합니다. 파일에 적용한 모든 태그를 파일에 포함하려면 태그 **확인란을 클릭하여 선택합니다.**

기본 **파일 옵션을 사용하여 파일을** 기본 형식으로 내보냅니다. 대화를 하나의 파일로 내보내거나 별도의 파일에 있는 모든 개별 채팅 메시지로 내보낼 수 있습니다.

텍스트 **파일 옵션을** 사용하면 콘텐츠의 일반 텍스트 버전을 저장할 수 있습니다. 검토 집합에서 Teams 대화의 일반 텍스트 보기를 구하는 방법에 대한 자세한 내용은 요약 보기, [텍스트 보기, 위의](#summary-view-text-view-and-annotate-view) 주의 표시를 참조하세요.

위의 요약 [보기,](#summary-view-text-view-and-annotate-view) 텍스트 보기 및 주석 보기 섹션에 설명된 대로 콘텐츠에 대한 수정사항을 적용한 경우 다시 **적용된 원리를** 선택하고 변환된 PDF 로그를 PDF의 변환된 복사본으로 대체하는 옵션을 선택할 수 있습니다.

Microsoft가 제공하는 Azure blob 저장소 컨테이너로 내보내거나 자체 Azure Blob 저장소 컨테이너를 제공할 수 있습니다.

내보내기 프로세스를 시작할 준비가 되면 내보내기 단추를 **클릭합니다.** Azure blob [저장소 컨테이너에](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) 액세스하고 내보내기가 완료된 후 내보낸 콘텐츠를 다운로드하는 방법에 대한 자세한 내용은 내보내기 작업을 참조하세요.

> [!NOTE]
> 내보내기에는 오프라인 시간이 걸릴 수 있습니다. 내보내기 프로세스의 상태를 추적하려면 검토 설정 **탭을 종료하고 내보내기** **탭을 클릭합니다.**

## <a name="related-topics"></a>관련 항목

- [Microsoft 365의 eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [Teams PowerShell 개요](teams-powershell-overview.md)
