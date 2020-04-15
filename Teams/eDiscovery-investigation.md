---
title: 콘텐츠의 eDiscovery 조사 수행
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
f1.keywords:
- NOCSH
description: 법률 소송 절차에 대해 전자적으로 저장 된 모든 정보를 제출 해야 하는 경우와 같이 eDiscovery을 수행 해야 하는 경우 수행할 작업에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 75098323afa8aef9e80223cbc1883e9c12cb53c6
ms.sourcegitcommit: 477aac9e14fced139ee7dd827942ce35b9769b63
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2020
ms.locfileid: "43510697"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Microsoft 팀의 콘텐츠 eDiscovery 조사 수행

대규모 기업은 모든 ESI (전자적 저장 정보) 제출을 요구 하는 높은 벌칙 법률 소송 절차에 게 노출 되는 경우가 많습니다. EDiscovery 조사 중에 Microsoft 팀 콘텐츠를 검색 하 고 사용할 수 있습니다.

## <a name="overview"></a>개요

모든 팀 1:1 또는 그룹 채팅은 각 사용자의 사서함으로 저널링 됩니다. 모든 표준 채널 메시지가 팀을 나타내는 그룹 사서함으로 저널링 됩니다. 표준 채널로 업로드 되는 파일은 SharePoint Online 및 비즈니스용 OneDrive의 eDiscovery 기능에서 다룹니다.

[개인 채널](private-channels.md) 의 메시지 및 파일 eDiscovery은 표준 채널과 다르게 작동 합니다. 자세히 알아보려면 [개인 채널 eDiscovery](#ediscovery-of-private-channels)를 참조 하세요.

일부 팀 콘텐츠는 eDiscoverable 수 없습니다. 다음 표에서는 eDiscovery를 통해 찾을 수 있는 콘텐츠 형식을 보여 줍니다.

| 콘텐츠 형식 | eDiscoverable 가능 | 상속자 |
|:--- | --- |:--- |
| 팀 채팅 메시지 | 예 | 게스트 사용자가 1:1 또는 1의 유일한 참가자 인 채팅의 채팅 메시지: N 채팅은 eDiscoverable 수 없습니다. |
| 오디오 녹음 | 아니요 | |
| 각 사용자가 메시지를 읽었을 때 표시 하는 타임 스탬프 | 아니요 | |
| 오디오 녹음 | 아니요 | |
| 개인 채널 메시지 | 아니요 | |
| Emojis, Gif, 스티커 | 아니요 | |
| 코드 조각 | 아니요 | |
| 채팅 링크 | 아니요 | |
| 반응과 (좋아요, 하트 등) | 아니요 | |
| 편집 된 메시지 | 예 | 사용자가 보류 중인 경우에는 이전 버전의 편집 된 메시지가 보존 됩니다. |
| 인라인 이미지 | 아니요 | |
| 목차 | 아니요 | |
| 제목 | 아니요 | |
| 부호가 | 예 | 인용 부호로 묶은 콘텐츠를 검색할 수 있습니다. 그러나 검색 결과에는 콘텐츠가 인용 부호로 표시 되지 않습니다. |
| 채널 이름 | 아니요 | |

- Microsoft 팀 콘텐츠를 사용 하 여 eDiscovery 조사를 수행 하려면 [보안 & 준수 센터 링크에서 ediscovery 사례 관리](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) 의 1 단계를 검토 합니다.

- Microsoft 팀 데이터가 Excel eDiscovery 내보내기 출력에 IM 또는 대화로 표시 됩니다. Outlook에서 파일을 `.pst` 열어 내보낸 후 해당 메시지를 볼 수 있습니다.

    팀에 대 `.pst` 한 파일을 볼 때 모든 대화가 대화 내용 아래의 팀 채팅 폴더에 보관 되어 있는지 확인 합니다. 메시지 제목은 팀 이름 및 채널 이름을 포함 합니다. 예를 들어 아래 이미지는 제조 사양 팀의 Project 7 표준 채널을 messaged 하는 Bob의 메시지를 보여줍니다.

    ![Outlook의 사용자 사서함에 있는 팀 채팅 폴더 스크린샷](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

- 사용자의 사서함에 있는 개인 채팅은 대화 내용 아래의 팀 채팅 폴더에 저장 됩니다.

## <a name="ediscovery-of-private-channels"></a>개인 채널 eDiscovery

비공개 채널에 전송된 메시지 레코드는 그룹 사서함이 아닌 모든 비공개 채널 구성원의 사서함에 전달됩니다. 레코드 제목은 출처 비공개 채널을 표시하도록 형식이 지정됩니다.

각 개인 채널은 상위 팀 사이트와 별도의 고유한 SharePoint 사이트 모음을 포함 하므로 개인 채널의 파일은 상위 팀과 독립적으로 관리 됩니다.

팀은 팀 내 단일 채널의 eDiscovery 검색을 지원 하지 않으므로 전체 팀을 검색 해야 합니다. 개인 채널에서 콘텐츠를 eDiscovery 검색 하려면 팀에서 검색 하 고, 개인 채널과 연결 된 사이트 모음 (파일 포함)과 개인 채널 구성원의 사서함 (메시지 포함)을 사용 합니다.

EDiscovery 검색에 포함할 개인 채널의 파일 및 메시지를 식별 하려면 다음 단계를 사용 합니다.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>EDiscovery 검색에 개인 채널 파일 포함

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

3. 각 팀 또는 그룹 ID에 대해 다음 PowerShell 스크립트를 실행 하 여 해당 팀의 그룹 ID 인 모든 관련 개인 채널 사이트를 식별 $groupID 합니다.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>EDiscovery 검색에 개인 채널 메시지 포함

이 단계를 수행 하기 전에 [최신 버전의 팀 PowerShell 모듈이](teams-powershell-overview.md) 설치 되어 있는지 확인 합니다.

1. 다음을 실행 하 여 팀의 비공개 채널 목록을 가져옵니다.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. 다음을 실행 하 여 개인 채널 구성원 목록을 가져옵니다.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. EDiscovery 검색 쿼리의 일부로 팀의 각 개인 채널에 있는 모든 구성원의 사서함을 포함 합니다.

## <a name="advanced-ediscovery"></a>고급 eDiscovery

일부 Microsoft 팀 콘텐츠는 [고급 eDiscovery 워크플로](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)를 사용 하 여 검색 하 고 유지할 수도 있습니다. EDiscovery는 다양 한 검색, 유지, 내보내기 기능을 제공 하며, 고급 eDiscovery에서는 규정 준수 관리자가 데이터 원본을 식별 하 고 해당 콘텐츠를 분석 하는 데 더 많은 도구를 제공 합니다.

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>팀 콘텐츠에 대 한 고급 eDiscovery custodian 워크플로

Custodians는 다양 한 팀의 구성원 일 수 있습니다. 이러한 custodians 관련 된 팀 콘텐츠를 캡처할 수 있습니다. Custodian 워크플로에 대 한 배경 및 지침은 [고급 eDiscovery 워크플로](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)를 참조 하세요.

Custodian를 추가한 후에 **다음** 단추를 클릭 한 다음 **추가** 단추를 클릭 합니다. 그런 다음 추가 위치를 선택 하 라는 메시지가 표시 되 고 해당 데이터에 대 한 모든 custodian의 멤버 자격과 해당 하는 SharePoint 사이트 위치가 표시 됩니다. 이러한 모든 데이터 원본과 팀에서 eDiscovery에 사용할 콘텐츠를 선택한 다음 해당 사용자와 보류를 위해 확인 한 모든 데이터 원본을 배치할 수 있습니다.

Exchange 콘텐츠, 해당 OneDrive 콘텐츠 또는 두 가지 모두 포함 여부를 선택할 수 있습니다. Exchange 콘텐츠에는 전자 메일, 사서함에 저장 된 팀 콘텐츠 등의 사용자 사서함에 있는 모든 응용 프로그램 콘텐츠가 포함 됩니다. OneDrive 콘텐츠에는 사용자의 콘텐츠 뿐만 아니라 OneDrive에 저장 된 모든 팀 콘텐츠 (예: 1:1 채팅, 1: N 채팅, 채팅에 공유 되는 파일)도 포함 됩니다.

또한 custodian가 구성원 인 모든 팀을 연결 하는 옵션을 사용 하 여 custodian에서 액세스할 수 있는 채널 채팅 메시지 및 파일을 포함 시킬 수 있습니다. 또한 다른 팀은 custodian와 연결 될 수 있습니다. 자세한 내용은 [고급 eDiscovery 사례에 Custodians 추가](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case)를 참조 하세요.

> [!NOTE]
> [개인 채널](private-channels.md) 의 메시지 및 파일 eDiscovery은 표준 채널과 다르게 작동 합니다. 자세히 알아보려면 [개인 채널 eDiscovery](#ediscovery-of-private-channels)를 참조 하세요.

### <a name="placing-a-data-source-on-hold"></a>데이터 원본을 대기 상태로 두기

Custodian로 지정할 특정 사용자가 없는 경우 전체 데이터 원본을 보류에 배치할 수 있습니다. 보류에 대 한 자세한 내용은 [고급 eDiscovery에서 보류 관리](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)를 참조 하세요.

팀 콘텐츠에 대 한 보류를 만들 때 보류에 포함할 위치를 모두 선택할 수 있습니다. 사용자가 콘텐츠를 삭제 하거나 변경 해도 보류에는 해당 콘텐츠의 모든 이전 버전의 복사본이 유지 됩니다.

또한 선택적 쿼리를 사용 하 여 키워드, 날짜 범위, 저자 및 기타 다양 한 조건을 기준으로 보류 조건을 설정할 수 있습니다. 키워드를 지정 하지 않으면 해당 데이터 원본의 모든 내용에 보류가 적용 됩니다.

### <a name="advanced-ediscovery-searches"></a>고급 eDiscovery 검색

팀 콘텐츠를 검색할 수도 있습니다. 검색에 대 한 자세한 내용은 [고급 eDiscovery에서 서비스 케이스에 대 한 데이터 수집](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery)을 참조 하세요. 검색 쿼리와 일치 하는 메시지가 하나라도 있으면 검색에서 전체 대화를 반환 합니다.

검색 쿼리를 만들 때 이미 선택한 모든 원본이 검색 되도록 custodians을 선택할 수 있습니다. 사용자에 게 매핑되지 않은 팀 사이트와 같은 비 custodial 출처를 검색할 수도 있습니다. 선택 쿼리를 사용 하 여 팀 콘텐츠 내에서 검색 범위를 좁힐 수도 있습니다.

검색을 만들고 선택한 후 선택한 검색에 대해 수행할 수 있는 추가 세부 정보 및 작업이 창에 표시 됩니다. **통계** 단추를 클릭 하면 위치 형식, 콘텐츠의 원본 원본, 콘텐츠를 그룹 사서함, 개별 사용자 사서함 또는 SharePoint 사이트에 배치할지 여부를 포함 하 여 검색에 대 한 통계를 볼 수 분석. 이렇게 하면 검색 결과에 기여 하는 원본에 대해 분석을 확인할 수 있습니다. 또한 **쿼리** 보기를 사용 하 여 결과에 참여 하는 개별 키워드를 확인할 수 있습니다.

검색을 완료 한 후 **에 결과 추가** 단추를 클릭 하 여 집합을 검토 하 고 검토 집합에 추가할 수 있습니다. 검토 집합에 대 한 자세한 내용은이 문서의 뒷부분에 나오는 [고급 eDiscovery에서 검토 집합 관리](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) 및 [설정 워크플로](#review-sets-workflow) 를 참조 하세요.

#### <a name="normal-review-sets-and-conversation-review-sets"></a>일반 검토 집합 및 대화 검토 집합

검색을 검토 집합에 추가 하는 경우 일반 검토 집합 또는 대화 검토 집합에서 선택할 수 있습니다.

일반 검토 집합은 내보내기와 유사 합니다. 팀 콘텐츠의 개별 `.msg` 파일을 제공 하 고 기본 보기에 콘텐츠를 표시 합니다. 나중에 다른 소프트웨어 도구를 사용 하 여 파일을 다시 처리 하려는 경우 일반적으로 일반 검토 설정을 사용 합니다.

대화 검토 집합을 통해 보다 직관적인 스레드된 대화를 볼 수가 있습니다. 적절 한 순서 대로 관련 메시지를 함께 표시 합니다.

교정 등의 기능을 두 가지 유형의 검토 집합에서 사용할 수 있습니다.

검토 집합에 대 한 자세한 내용은 [고급 eDiscovery에서 대화 검토](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets) 를 참조 하세요.

#### <a name="collection-options"></a>모음 옵션

검토 집합에 추가 하는 경우 창의 **모음 옵션** 섹션에서 **대화 검색 옵션** 및 **팀 대화**를 포함 하 여 여러 옵션을 checkbox로 사용할 수 있습니다. 이러한 옵션을 사용 하도록 설정 하면 검토 집합에 포함 된 개별 팀 메시지에도 컨텍스트에 대 한 추가 메시지가 표시 됩니다. 예를 들어 쿼리가 매우 구체적이 고 결과로 하나의 메시지만 반환 되는 경우 이러한 옵션을 사용 하도록 설정 하면 해당 쿼리와 일치 하는 메시지에 대 한 몇 개의 메시지가 앞으로도 반환 됩니다.

여러 논리 조건을 사용 하 여 추가 메시지가 쿼리와 일치 하는 메시지에 컨텍스트를 제공 하는지 여부를 결정 합니다. 예를 들어 팀 콘텐츠의 경우 이러한 옵션을 사용 하도록 설정 하면 메시지가 스레드 되는 방식 때문에 부모 메시지와 모든 자식 메시지가 검색 됩니다.

메시지 타임 스탬프도 검사 합니다. 쿼리와 일치 하는 메시지가 있는 경우 4 시간 범위 내에서 그 앞에 오는 인접 한 메시지는 대화의 일부로 간주 되며 결과에도 포함 됩니다.

검색 쿼리와 일치 하는 항목으로 반환 되는 컨텍스트 메시지에 대해 확실히 알고 있어야 하는 경우에는 이러한 옵션을 사용할 필요가 없습니다. 모든 콘텐츠를 수집 하거나 검색 범위의 날짜 범위를 확장 하 여 쿼리 결과로 반환 되는 메시지를 더 많이 반환할 수 있습니다.

### <a name="review-sets-workflow"></a>집합 워크플로 검토

**집합 검토** 탭을 클릭 하 여 기존 검토 집합을 보거나 새로 만들 수 있습니다. 검토 집합에 대 한 자세한 내용은 [고급 eDiscovery에서 검토 집합 관리](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets)를 참조 하세요.

문서 외에도 전자 메일, 팀 메시지, Yammer 메시지 및 기타 콘텐츠를 검토 집합에 추가할 수 있습니다. 검토 집합 내에서 다른 컨텍스트에서 수행할 수 있는 여러 작업 (예: 콘텐츠 검색 및 사용자 지정 쿼리 만들기)을 수행할 수도 있습니다. 이러한 작업은 검토 집합에 추가 된 항목에만 적용 됩니다.

**검토 집합 관리** 단추는 분석, 요약 보고, 추가 된 부하 집합 수 등의 추가 옵션을 제공 합니다.

데이터의 시각화 및 차트에 액세스 하려면 오른쪽 위에 있는 **개별 결과** \> **검색 프로필 보기** 를 클릭 합니다. 이러한 차트에서 파이 아웃을 클릭 하면 쿼리 하려는 콘텐츠 유형을 대화형으로 선택할 수 있습니다. 예를 들어 팀 콘텐츠만 쿼리 하도록 선택할 수 있습니다. 직접 작성 한 쿼리를 저장 하는 것 처럼 이러한 쿼리를 저장할 수도 있습니다.

#### <a name="summary-view-text-view-and-annotate-view"></a>요약 보기, 텍스트 보기 및 주석 달기 보기

검토 집합에서 팀 대화를 클릭 하면 전체 팀 대화를 개별적으로 상호 작용할 수 있는 메시지 목록으로 표시 하는 **요약 보기가**표시 됩니다. 메시지 오른쪽에 있는 아래쪽 화살표를 클릭 하 여 메시지 세부 정보를 보거나 개별 `.msg` 파일을 다운로드할 수 있는 상황에 맞는 메뉴를 표시 합니다. 메시지 정보를 클릭 하면 해당 메시지의 전체 메타 데이터 또는 메타 데이터 요약이 표시 됩니다.

PDF를 다운로드 하려면 요약 보기의 오른쪽 위에 있는 다운로드 단추를 클릭 합니다.

**텍스트 보기** 탭을 클릭 하 여 팀 대화에서 추출 된 텍스트의 일반 텍스트 보기를 표시 합니다. 이는 내보내기에 적합 하며, 다른 소프트웨어 도구를 사용 하 여 추출 된 텍스트로 쉽게 작업할 수 있습니다.

주석 기능에 액세스 하려면 **주석 달기 보기** 탭을 클릭 합니다. 이 탭에는 팀 대화와 유사한 형식의 콘텐츠가 표시 되지만 편집을 위한 추가 옵션도 있습니다. 메모를 작성 하거나, 메시지에 그림을 그리거나, 교정 하기 위해 세밀 하 게 scratching 아웃 하는 데 사용할 수 있는 연필 도구가 있습니다. 영역을 축소 하 고 "Redacted"로 표시 하는 사각형을 그리는 데 사용할 수 있는 **영역 교정** 도구도 있습니다.

**주석 달기 보기** 탭의 맨 아래에는 태그 지정 패널이 표시 된 **태그 문서** 단추가 있습니다. 이 패널에서 팀 대화 내의 모든 메시지에 태그를 적용할 수 있습니다. 응답 하거나 응답 하지 않는 것으로 대화에 레이블을 지정할 수 있으며, "관심 있는 항목"이 있는지, 내보내기에 포함 해야 하는지 여부, 추가 검토가 필요한 지 여부 다른 사용자 지정 가능 태그를 관리 하 고 적용할 수도 있습니다.

#### <a name="action-menu"></a>동작 메뉴

집합 검토 창에서 **작업** \> **내보내기를**클릭 하 여 콘텐츠를 내보낼 수 있습니다. 내보낼 때 사용할 수 있는 여러 가지 옵션이 있습니다.

모든 팀 메시지에 대 한 모든 메타 데이터가 포함 된 파일을 내보내려면 **파일 로드** 확인란을 클릭 하 여 선택 합니다. 콘텐츠에 적용 한 태그를 파일에 포함 하려면 **태그** 확인란을 클릭 하 여 선택 합니다.

네이티브 **파일** 옵션을 사용 하 여 파일을 네이티브 형식으로 내보냅니다. 대화를 별도의 파일에 있는 하나의 파일 또는 모든 개별 채팅 메시지로 내보내도록 선택할 수 있습니다.

**텍스트 파일** 옵션을 사용 하 여 일반 텍스트 버전의 콘텐츠를 저장할 수 있습니다. 검토 집합에서 팀 대화의 일반 텍스트 보기를 가져오는 방법에 대 한 자세한 내용은 위의 [요약 뷰, 텍스트 뷰 및 주석 달기 보기](#summary-view-text-view-and-annotate-view) 를 참조 하세요.

위의 [요약 보기, 텍스트 보기 및 주석 보기](#summary-view-text-view-and-annotate-view) 섹션에 설명 된 대로 콘텐츠에 redactions를 적용 한 경우 **변환 된 pdf로 redacted natives 바꾸기** 옵션을 선택 하 여 원시 파일을 PDF의 변환 된 복사본으로 바꿀 수 있습니다.

Microsoft에서 제공 하는 Azure blob 저장소 컨테이너로 내보내기를 선택 하거나 고유한 Azure Blob 저장소 컨테이너를 제공할 수 있습니다.

내보내기 프로세스를 시작할 준비가 되 면 **내보내기** 단추를 클릭 합니다. 내보내기가 완료 되 면 Azure blob 저장소 컨테이너에 액세스 하 여 내보낸 콘텐츠를 다운로드 하는 방법에 대 한 자세한 내용은 [내보내기 작업 다운로드](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) 를 참조 하세요.

> [!NOTE]
> 내보내기에 오랜 시간이 걸릴 수 있습니다. 내보내기 프로세스의 상태를 추적 하려면 **검토 집합** 탭을 종료 하 고 **내보내기** 탭을 클릭 합니다.

## <a name="related-topics"></a>관련 항목

- [Microsoft 365의 eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [팀 PowerShell 개요](teams-powershell-overview.md)
