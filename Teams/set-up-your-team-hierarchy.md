---
title: 팀 대상 계층 구조 설정
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
description: 대규모 팀 집합에 콘텐츠를 게시하기 위해 조직에서 팀 계층 구조를 설정하는 방법을 배워야 합니다.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cab89e7d3e1c2956c79a4013edd254167c990f9b
ms.sourcegitcommit: f122c078b6458754500f3cc68086d6ccfa62d183
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588311"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>팀 대상 계층 구조 설정

> **이 기능은 현재 비공개 미리 보기로 제공됩니다.**

조직에서 대규모 팀 집합에 콘텐츠를 게시하는 데 사용할 수 있는 팀 계층 구조를 만들하려면 팀 대상을 지정하는 팀을 설정해야 합니다. 이마트는 계층 구조의 모든 팀이 서로 관련되는 방식과 팀을 필터링하는 데 사용할 수 있는 특성을 정의합니다. 스마마를 만든 후 Teams에 업로드하면 계층 구조가 조직 전체에 적용됩니다. 스마마가 업로드된 후 Teams 클라이언트 내의 앱에서 사용할 수 있습니다. 

> [!IMPORTANT]
> 팀 또는 채널을 검색할 때 팀 계층 구조가 표시되지 않습니다. 팀의 계층 구조를 표시하려면 팀을 지원하는 앱을 사용해야 합니다. 초기 릴리스의 경우 작업 앱만 계층적 팀을 지원합니다. 이 문서의 나머지에서는 받는 사람 팀에 작업을 게시하는 컨텍스트에서 팀 계층 구조를 설정하는 데 대해 설명합니다. 팀 대상 계층 구조를 설정하기 전에 작업 게시에 대한 개요는 [Teams에서](manage-tasks-app.md) 조직의 작업 앱 관리를 참조하세요.

Teams의 작업 앱에서 계층 구조를 나타내는 방법의 예는 다음과 같습니다. 작업 목록을 만든 후 게시 팀의 구성원은 받는 사람 팀을 선택하여 작업 목록을 보내(게시)할 수 있습니다. 팀을 선택할 때 게시 팀은 계층 구조, 특성 또는 둘의 조합을 통해 필터링할 수 있습니다.<br>

![작업 게시 스크린샷](media/manage-tasks-app-publish.png)

## <a name="plan-your-hierarchy"></a>계층 구조 계획

계층 구조를 정의하는 스마마를 만들기 전에 몇 가지 계획을 세우고 조직을 구성할 방법을 결정해야 합니다. 여기에는 작업을 다른 그룹에 게시해야 하는 조직 그룹 결정이 포함됩니다. 계층 구조의 각 노드는 작업 그룹 또는 그룹 그룹을 나타냅니다. 계층 구조의 맨 아래에 있는 노드(자식이 없는 노드)는 작업을 받을 수 있는 팀인 반면 다른 노드(부모)는 작업을 아래쪽으로 게시할 수 있는 권한이 있는 조직 그룹입니다. 팀은 계층 구조에서 한 번만 표현할 수 있습니다.

예를 들어 다음 계층 구조에서 Recall, Retail Communications 및 HR은 계층 구조의 모든 아래쪽 노드(팀)에 작업을 게시할 수 있는 반면 북동부 영역은 뉴욕 스토어 및 보스턴 스토어 팀에만 작업을 게시할 수 있습니다. 이 계층 구조를 사용하면 회수, 소매 통신 및 HR 그룹에서 CEO의 혜택 정보 또는 메시지와 같이 회사 전체에 적용되는 작업을 게시할 수 있습니다. 북동부 영역은 직원 일기 예보, 날씨 정보 등의 작업을 뉴욕 스토어 및 보스턴 스토어 팀에만 게시할 수 있습니다.

![팀 계층적 예제](media/team-targeting-schema-example.png)

## <a name="create-your-hierarchy"></a>계층 구조 만들기

계층 구조를 정의하는 스마마는 CSV(콤마로 구분된 값) 파일을 기반으로 합니다. CSV 파일의 각 행은 팀 계층 구조 내의 한 노드에 해당합니다. 각 행에는 계층 구조 내의 노드 이름을 입력하고, 선택적으로 팀에 연결하며, 이를 지원하는 앱에서 팀을 필터링하는 데 사용할 수 있는 특성이 포함되어 있습니다.

또한 게시 팀이 받는 사람 팀에 전송된 콘텐츠를 구성하는 데 사용할 수 있는 범주인 버킷을 정의하여 관련 콘텐츠를 더 쉽게 보고, 정렬하고, 집중할 수 있습니다.

### <a name="add-required-columns"></a>필요한 열 추가

CSV 파일에는 첫 번째 열부터 다음 세 개의 열이 다음 순서로 포함되어야 합니다. 태스크를 수신하려면 노드를 팀에 연결해야 합니다. 비공개 미리 보기 중에는 2,000개 노드가 지원됩니다. 시작 시 기본적으로 15,000개 이상의 노드를 지원할 것으로 예상됩니다. 더 큰 조직에 대해 이 제한을 높이기 위해 고객과 협력할 계획입니다.

| 열 이름   | 필수 | 설명   |
----------------|----------|---------------|
| TargetName    | 예      | 노드의 이름입니다. 이름은 최대 100자까지 사용할 수 있으며 A-Z, a-z 및 0-9 문자만 포함할 수 있습니다. 노드 이름은 고유해야 합니다. |
| ParentName    | 예       | 부모 노드의 이름입니다. 여기서 지정한 값은 부모 노드의 TargetName 필드 값과 정확히 일치해야 합니다. 두 개 이상의 부모 노드를 추가하려는 경우 각 부모 노드 이름을 세미코론(;). 최대 25개 부모 노드를 추가할 수 있으며 각 부모 노드 이름은 최대 2500자까지 입력할 수 있습니다. 노드는 부모 노드가 루트 노드인 경우 여러 부모 노드를 사용할 수 있습니다.   <br><br>**중요** 계층 구조에서 상위 부모가 계층 구조의 하위 노드를 참조하는 루프를 만들지 않도록 주의하세요. 지원되지 않습니다. |
| TeamId        | 예, 팀이 태스크를 게시하거나 부모 노드에서 작업을 수신하는 경우       | 여기에는 노드를 연결하려는 팀의 ID가 포함되어 있습니다. 계층 구조의 맨 아래에 있는 경우, 사용자가 해당 노드에서 게시할 수 있도록 하려는 경우 또는 사용자가 해당 노드 및 해당 자산에 대한 보고를 볼 수 있도록 하려는 경우 노드가 팀에 연결되어야 합니다. 예를 들어 서부 지역 Office의 관리자가 해당 지역에 속한 노드에 대한 작업 완료 보고를 확인하려는 경우입니다.<br><br>계층 구조에서 다른 노드를 그룹화하기 위해 노드를 추가하려는 경우 해당 노드를 팀에 연결하지 필요가 없습니다. 이 필드는 비워 두면 됩니다. 각 노드를 하나의 팀에만 연결하면 됩니다.<br>노드를 연결하려는 팀의 ID를 얻으면 다음 PowerShell 명령을 `Get-Team | Export-Csv TeamList.csv` 실행합니다. 조직의 팀을 나열하고 각 팀의 이름과 ID를 포함합니다. 연결하려는 팀의 이름을 찾은 다음 이 필드에 ID를 복사합니다.|

### <a name="add-attribute-columns"></a>특성 열 추가

세 개의 필수 열을 추가한 후 선택적 특성 열을 추가할 수 있습니다. 이러한 특성은 태스크를 게시하려는 특성을 보다 쉽게 선택할 수 있도록 노드를 필터링하는 데 사용할 수 있습니다. 해당 특성의 값이 상호 배타적인지 여부에 따라 특성을 정의하는 두 가지 방법이 있습니다.

|특성을 추가하는 방법|설명 |예제  |
|---|---------|---------|
|특성 값이 상호 배타적이면 지정한 열 이름이 특성의 이름이 됩니다.|각 행은 해당 특성에 대해 하나의 값을 포함할 수 있으며, 각 값은 최대 100자까지 사용할 수 있습니다. 특성 열에 지정한 특성 값 집합은 계층 구조를 사용하는 Teams 앱에서 해당 특성에 대해 사용 가능한 필터 값으로 표시됩니다. 각 특성 열에는 최대 50개 고유 값이 있습니다. |사용자가 레이아웃을 통해 저장소를 필터링할 수 있도록 하려는 경우 저장소에 레이아웃이 하나만 있기 때문에 이 특성의 값은 상호 배타적입니다. <br><br>레이아웃을 통해 저장소를 필터링하는 특성을 추가하기 위해 스토어 레이아웃이라는 열을 추가합니다. 이 예제에서 스토어 레이아웃 특성의 값은 Compact, Standard 및 Large입니다.
|특성에 대해 여러 값을 나타내야 하지만 값이 상호 배타적이지 않은 경우 열 이름에 **대해 AttributeName:UniqueValue** 형식을 사용합니다. |콜론 앞의 텍스트 문자열(:) 특성의 이름이 됩니다. 콜론 앞에 동일한 텍스트 문자열이 포함된 모든 열(:) 필터링 메뉴의 섹션으로 그룹화됩니다. 콜론 뒤의 각 문자열은 이 섹션의 값이 됩니다.<br><br>각 행의 값은 해당 특성에 대해 0 또는 1일 수 있습니다. 값이 0이면 특성이 노드에 적용되지 않는 것이고 값 1은 특성이 해당 노드에 적용된다는 의미입니다.|사용자가 부서를 통해 저장소를 필터링할 수 있도록 하려는 경우 저장소에는 여러 부서가 있을 수 있으므로 이 특성의 값은 상호 배타적이지 않습니다.<br><br>이 예제에서는 Departments:의류, Departments:Electronics, Departments:Foods, Departments:Home and Garden, Departments:Sporting 상품을 특성 열로 추가합니다. 부서는 특성 이름이 됐고 사용자는 의류, 전자, 음식, 집 및 정원 및 스포츠 상품 부서를 통해 필터링할 수 있습니다.|

특성 열을 추가할 때 다음에 유의해야 합니다.

- 지정한 열 이름 또는 콜론 앞에 지정한 열 이름(:) 특성의 이름이 됩니다. 이 값은 계층 구조를 사용하는 Teams 앱에 표시됩니다.
- 열 이름은 최대 100자까지 사용할 수 있으며 문자 A-Z, a-z 및 0-9 및 공백만 포함할 수 있습니다. 열 이름은 고유해야 합니다.
- 시작 시 50개 특성 열을 허용할 계획입니다.

### <a name="add-bucket-columns"></a>버킷 열 추가

버킷 열을 추가하여 작업을 구성할 수 있는 그룹화인 버킷을 만들 수 있습니다. 각 버킷은 CSV 파일에서 자체 열을 얻습니다. 만든 버킷은 게시 팀에서 사용할 수 있습니다. 게시 팀은 이러한 버킷을 사용하여 받는 사람 팀에 대한 작업을 분류할 수 있습니다. 팀에 버킷이 아직 없는 경우 작업이 게시될 때 필요한 경우 버킷이 만들어집니다.

게시 팀은 작업을 한 번 중앙에서 분류하여 작업 목록을 받는 수십, 수백 또는 수천 명의 받는 사람 팀에 대해 작업 목록을 미리 구성할 수 있습니다. 그런 다음 받는 사람 팀은 버킷별로 작업을 정렬하고 필터링하여 업무와 가장 관련성이 높은 영역에 집중할 수 있습니다.

버킷 열을 추가할 때 다음에 유의합니다.

- 열 이름은 버킷의 이름이 됩니다. 지정한 각 버킷은 계층 구조를 사용하는 Teams 앱의 버킷 목록에 표시됩니다. 버킷 이름에 중요한 정보를 포함하지 않는 것이 좋습니다. 현재 게시 팀은 버킷을 만든 후 게시를 통해 버킷을 제거할 수 없습니다.
- 열 이름 앞에 해시태그(#)가 있어야 합니다. 최대 100자까지 사용할 수 있으며 A-Z, a-z 및 0-9 문자만 포함할 수 있습니다. 예를 들어 #Operations #Frozen 수 있습니다.
- 시작 시 25개 버킷 열을 지원할 것으로 예상됩니다. 더 큰 조직에 대해 이 제한을 늘리기 위해 고객과 협력할 계획입니다.

### <a name="example"></a>예제

다음은 위의 이미지에 표시된 계층 구조를 지원하기 위해 만들어질 Schema CSV 파일의 예입니다. 이 schema에는 다음이 포함되어 있습니다.

- 3개의 필수 열 `TargetName` `ParentName` , 및 `TeamId`
- 3개의 특성 `Store layout` 열, `Departments:Clothing` 및 `Departments:Foods`
- 3개의 버킷 열 `Fresh Foods` `Frozen Foods` , 및 `Womenswear`

특성에는 `Store layout` `Compact` , 및 `Standard` .를 포함 하는 값이 `Large` 있습니다. 특성 `Departments` 열은 값(0) 또는 `0` 0으로 설정할 수 `1` 있습니다. 레이아웃 `Store` 및 `Departments` 특성은 위의 이미지에 나와 있지 않습니다. 노드 항목에 특성을 추가하는 방법을 보여 주기 위해 여기에 추가됩니다. 세 개의 버킷 열도 마찬가지입니다.


| TargetName             | ParentName                      | TeamId                       | 스토어 레이아웃|Departments:의류|Departments:Foods|#Fresh 음식|#Frozen 음식|#Womenswear|
|------------------------|-------------------------|--------------------------------------|-------------|---|---|---|---|---|
| 회수                 |                         | db23e6ba-04a6-412a-95e8-49e5b01943ba |||||||
| 커뮤니케이션         |                         | 145399ce-a761-4843-a110-3077249037fc |||||||
| HR                     |                         | b8f7db91-201c-4cf9-9f7e-90a4894ed8e4 |||||||
| 동부 지역 사무실   |                         |                                      |||||||
| 서부 지역 사무실   |                         |                                      |||||||
| 북동 영역        | 동부 지역 사무실    |                                      |||||||
| 동남 영역        | 동부 지역 사무실    |                                      |||||||
| 뉴욕 스토어         | 북동 영역         | e2ba65f6-25e7-488b-b8f0-b8562d5de60a |대형|1|1||||
| 보스턴 스토어           | 북동 영역         | 0454f08a-0507-437c-969a-682eb2fae7fc |표준|1|1||||
| 마이애미 스토어            | 동남 영역         | 619d6e4e-5f68-4b36-8e1f-16c98d7396c1 |압축|0|1||||
| New Orleans 스토어      | 동남 영역         | 6be960b8-72af-4561-a343-9ac4711874eb |압축|0|1||||
| 시애틀 스토어          | 서부 지역 사무실    | 487c0d20-4e55-4dc2-8187-a24c826e0fee |표준|1|1||||
| 로스앤젤레스 스토어      | 서부 지역 사무실    | 204a1287-2efb-4a8a-88e0-56fbaf5a2389 |대형|1|1||||

## <a name="apply-your-hierarchy"></a>계층 구조 적용

> [!IMPORTANT]
> 이 단계를 수행하려면 PowerShell 갤러리에서 Teams PowerShell 공개 미리 보기 모듈을 [설치하고 사용해야 합니다.](https://www.powershellgallery.com/packages/MicrosoftTeams/) 모듈을 설치하는 방법에 대한 단계는 [Teams PowerShell 설치를 참조하세요.](teams-powershell-install.md)

Schema CSV 파일에서 계층 구조를 정의한 후 Teams에 업로드할 준비가 된 것입니다. 이렇게 하여 다음 명령을 실행합니다. 이 단계를 수행하려면 전역 관리자 또는 Teams 서비스 관리자 되어야 합니다.

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

## <a name="remove-your-hierarchy"></a>계층 구조 제거

> [!IMPORTANT]
> 이 단계를 수행하려면 PowerShell 갤러리에서 Teams PowerShell 공개 미리 보기 모듈을 [설치하고 사용해야 합니다.](https://www.powershellgallery.com/packages/MicrosoftTeams/) 모듈을 설치하는 방법에 대한 단계는 [Teams PowerShell 설치를 참조하세요.](teams-powershell-install.md)

조직의 모든 사용자에 **Published lists** 대해 게시된 목록 탭을 즉시 사용하지 않도록 설정하려면 계층 구조를 제거할 수 있습니다. 사용자는 게시된 목록 탭 **Published lists** 또는 탭의 기능에 액세스할 수 없습니다.  여기에는 새 작업 목록을 만들어 게시, 초안 목록에 액세스, 게시, 게시, 게시 및 중복 목록을 보고하는 기능을 포함합니다. 계층 구조를 제거해도 이전에 게시된 작업이 게시되지 않습니다. 이러한 작업은 받는 사람 팀이 완료할 수 있도록 유지됩니다. 

계층 구조를 제거하려면 다음 명령을 실행합니다. 이 단계를 수행하려면 관리자 되어야 합니다. 

```powershell
Remove-TeamTargetingHierarchy
```

## <a name="troubleshooting"></a>문제 해결

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>Schema CSV 파일을 업로드할 때 오류 메시지가 표시됩니다.

문제 해결 정보를 포함해야 하여 이 오류 메시지를 메모해 두어, 이 문제를 해결할 수 없는 이유를 나타냅니다. 오류 메시지의 정보를 기반으로 SCHEMA CSV 파일을 검토하고 편집한 다음 다시 시도합니다.

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>Schema CSV 파일을 업로드할 때 "오류: InvalidTeamId" 오류 메시지가 표시됩니다.

Schema CSV 파일을 업로드하려고 할 때 다음과 같은 오류 메시지가 표시됩니다.

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

Schema CSV 파일에서 팀에 대해 올바른 TeamId를 사용하고 있는지 확인합니다. TeamId는 팀을 지원하는 Microsoft 365 그룹의 그룹 ID와 동일해야 합니다. Microsoft Teams 관리 센터에서 팀의 그룹 ID를 찾아 볼 수 있습니다. 

1. [Microsoft Teams](https://admin.teams.microsoft.com/)관리 센터의 왼쪽 탐색 모음에서 Teams **관리**  >  **팀으로 이동하세요.**
2. 테이블에 그룹 **ID** 열이 표시되지 않는 **Edit columns** 경우 테이블의 오른쪽 위 모서리에 있는 열 편집을 선택한 다음 그룹 **ID를 켜면 됩니다.**
3. 목록에서 팀을 찾은 다음 그룹 ID를 찾습니다.

Schema CSV 파일의 TeamId가 Microsoft Teams 관리 센터에 표시되는 그룹 ID와 일치하는지 확인 

## <a name="related-topics"></a>관련 항목

- [Teams에서 조직의 작업 앱 관리](manage-tasks-app.md)
- [Teams PowerShell 개요](teams-powershell-overview.md)
