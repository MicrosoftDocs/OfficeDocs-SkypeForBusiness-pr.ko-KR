---
title: 팀 대상 지정 계층 구조 설정
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
description: 대규모 팀 집합에 콘텐츠를 게시 하기 위해 조직의 팀 계층 구조를 설정 하는 방법에 대해 알아봅니다.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2bb8133733f7230715753ecea0118fc635af446b
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159005"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>팀 대상 지정 계층 구조 설정

> **이 기능은 현재 비공개 미리 보기 상태입니다.**

조직에서 콘텐츠를 대규모 팀 집합에 게시 하는 데 사용할 수 있는 팀의 계층 구조를 만들려면 팀 대상 지정 스키마를 설정 해야 합니다. 스키마는 계층 구조의 모든 팀과 팀을 필터링 하는 데 사용할 수 있는 특성을 정의 합니다. 스키마를 만든 후에는 팀에 업로드 하 고 조직 전체에 계층이 적용 됩니다. 스키마를 업로드 한 후에는 팀 클라이언트 내에서 앱을 사용할 수 있습니다. 

> [!IMPORTANT]
> 팀 또는 팀 내에서 채널을 검색 하는 경우에는 팀의 계층 구조가 표시 되지 않습니다. 팀의 계층 구조를 보려면이를 지 원하는 앱을 사용 해야 합니다. 초기 릴리스에서는 작업 앱만 계층적 팀을 지원 합니다. 이 문서의 나머지 부분에서는 받는 사람 팀에 작업을 게시 하는 컨텍스트에서 팀 계층을 설정 하는 방법에 대해 설명 합니다. 팀 대상 계층 구조를 설정 하려면 먼저 [팀에서 조직의 작업 앱 관리](manage-tasks-app.md) 를 참조 하 여 작업 게시에 대 한 개요를 확인 하세요.

팀의 Tasks 앱에서 계층이 표시 되는 방식에 대 한 예는 다음과 같습니다. 작업 목록을 만든 후 게시 팀의 구성원은 받는 사람 팀을 선택 하 여 작업 목록을 전송 (게시) 할 수 있습니다. 팀을 선택할 때 게시 팀은 계층 구조, 특성 또는 둘 다의 조합을 기준으로 필터링 할 수 있습니다.<br>

![작업 게시 스크린샷](media/manage-tasks-app-publish.png)

## <a name="plan-your-hierarchy"></a>계층 계획

계층 구조를 정의 하는 스키마를 만들기 전에 몇 가지 계획을 수행 하 고 조직의 모양을 결정할 수 있어야 합니다. 여기에는 다른 그룹에 작업을 게시 해야 하는 조직 그룹을 결정 하는 것이 포함 됩니다. 계층 구조의 각 노드는 작업 그룹 또는 그룹 그룹을 나타냅니다. 계층 구조의 맨 아래에 있는 노드 (자식이 없는)는 작업을 받을 수 있는 팀 이며, 다른 노드 (부모)는 작업을 아래쪽으로 게시할 권한이 있는 조직 그룹입니다. 팀은 계층 구조에서 한 번만 표현할 수 있습니다.

예를 들어 다음 계층, 일반 매장, HR에서 계층의 모든 하위 노드 (팀)에 작업을 게시할 수 있는 반면, 북미 영역은 뉴욕 저장소와 보스턴 상점 팀에만 작업을 게시할 수 있습니다. 이 계층 구조를 통해 회수, 소매 통신 및 HR 그룹은 회사 전체에 적용 되는 작업 (예: 혜택 정보 또는 CEO의 메시지)을 게시할 수 있습니다. 북미는 직원 예약, 날씨 정보 등의 작업을 뉴욕 상점 및 보스턴 상점 팀에 게시할 수 있습니다.

![팀 계층적 예제](media/team-targeting-schema-example.png)

## <a name="create-your-hierarchy"></a>계층 구조 만들기

계층 구조를 정의 하는 스키마는 CSV (쉼표로 구분 된 값) 파일을 기반으로 합니다. CSV 파일의 각 행은 팀의 계층 구조 내에 있는 하나의 노드에 해당 합니다. 각 행에는 계층 내에서 노드의 이름을 지정할 수 있고, 선택적으로 팀에 링크 하는 정보를 포함 하 고,이를 지 원하는 앱에서 팀을 필터링 하는 데 사용 되는 특성이 포함 되어 있습니다.

또한 게시 팀에서 관련 콘텐츠를 쉽게 보고 정렬 하 고 초점을 구분할 수 있도록 사용자가 받는 사람 팀에 보낸 콘텐츠를 구성 하는 데 사용할 수 있는 버킷을 정의할 수도 있습니다.

### <a name="add-required-columns"></a>필수 열 추가

CSV 파일에는 다음 순서 대로 첫 번째 열부터 다음 세 개의 열이 포함 되어야 합니다. 작업을 수신 하려면 노드가 팀에 연결 되어 있어야 합니다. 개인 미리 보기에서 500 노드를 지원 합니다. 시작 시에는 기본적으로 최소 2000 노드를 지원 해야 합니다. 대규모 조직의 경우 고객과 협력 하 여이 한도를 높일 계획입니다.

| 열 이름   | 필수 | 설명   |
----------------|----------|---------------|
| TargetName    | 예      | 노드의 이름입니다. 이름은 최대 100 자를 입력할 수 있으며 A-z, a-z 및 0-9 문자만 포함 합니다. 노드 이름은 고유 해야 합니다. |
| ParentName    | 예       | 부모 노드의 이름입니다. 여기서 지정한 값은 부모 노드의 TargetName 필드 값과 정확히 일치 해야 합니다. 둘 이상의 상위 노드를 추가 하려는 경우 각 상위 노드 이름을 세미콜론 (;)로 구분 합니다. 상위 노드는 최대 25 개까지 추가할 수 있으며 각 부모 노드 이름은 최대 2500 자를 가질 수 있습니다. 부모 노드가 루트 노드인 경우에만 노드에 여러 부모 노드가 있을 수 있습니다.   <br><br>**중요** 계층 구조에서 상위 노드가 계층 구조의 하위 노드를 참조 하는 루프를 만들지 않도록 주의 합니다. 이는 지원 되지 않습니다. |
| 팀 Id        | 예, 팀이 상위 노드에서 작업을 게시 하거나 작업을 수신 하는 경우       | 여기에는 노드를 연결할 팀의 ID가 포함 됩니다. 노드는 계층 맨 아래에 있고, 사용자가 해당 노드에서 게시할 수 있도록 하려는 경우 또는 사용자가 해당 노드 및 해당 노드의 하위 항목에 대 한 보고를 볼 수 있도록 하려면 팀에 연결 되어 있어야 합니다. 예를 들어, 서쪽 지역 사무소의 관리자가 해당 지역에 속하는 노드에 대 한 작업 완료 보고를 표시 하려고 합니다.<br><br>계층 구조에서 다른 노드를 그룹화 하는 목적 으로만 노드를 추가 하려는 경우 해당 노드를 팀에 연결 하 고이 필드를 비워 둘 수 있습니다. 각 노드를 한 팀에만 연결할 수 있습니다.<br>노드를 연결 하려는 팀의 ID를 가져오려면 다음 PowerShell 명령을 실행 `Get-Team | Export-Csv TeamList.csv`합니다. 조직의 팀이 나열 되 고 각 팀의 이름 및 ID가 포함 됩니다. 연결 하려는 팀의 이름을 찾은 다음이 필드에 해당 ID를 복사 합니다.|

### <a name="add-attribute-columns"></a>특성 열 추가

세 개의 필수 열을 추가한 후 선택적 특성 열을 추가할 수 있습니다. 이러한 특성은 작업을 게시할 수 있도록 노드를 필터링 하는 데 사용할 수 있습니다. 특성 값을 두 가지 방법으로 정의할 수 있습니다.

|특성을 추가 하는 방법|설명 |예  |
|---|---------|---------|
|특성 값이 함께 사용할 수 없는 경우에는 사용자가 지정 하는 열 이름이 특성의 이름이 됩니다.|각 행에는 해당 특성에 대해 하나의 값이 포함 될 수 있으며 각 값에는 최대 100 자를 사용할 수 있습니다. 특성 열에 지정 하는 특성 값 집합은 계층 구조를 사용 하는 팀 앱에서 해당 특성에 대해 사용 가능한 필터 값으로 표시 됩니다. 각 특성 열에는 최대 50 고유 값이 포함 될 수 있습니다. |사용자가 레이아웃을 기준으로 저장소를 필터링 할 수 있도록 하려는 경우 이 특성 값은 저장소에 하나의 레이아웃만 포함할 수 있으므로 상호 배타적이 지 않습니다. <br><br>레이아웃을 기준으로 저장소를 필터링 하는 특성을 추가 하려면 Stores 레이아웃 이라는 열을 추가 합니다. 이 예제에서는 Store layout 특성에 대 한 값이 Compact, Standard 및 Large입니다.
|특성에 대해 여러 값을 표시 해야 하는 경우 해당 값이 상호 배타적이 지 않으면 열 이름에 **AttributeName: UniqueValue** 형식을 사용 합니다. |콜론 앞의 텍스트 문자열 (:) 특성 이름이 됩니다. 콜론 앞에 같은 텍스트 문자열을 포함 하는 모든 열 (:) 필터링 메뉴의 섹션으로 그룹화 됩니다. 콜론 뒤의 각 문자열은 해당 섹션의 값이 됩니다.<br><br>각 행의 값은 해당 특성에 대해 0 또는 1이 될 수 있습니다. 값 0은 특성이 노드에 적용 되지 않고 값이 1 이라는 것을 의미 하며,이는 특성이 해당 노드에 적용 됨을 의미 합니다.|사용자가 부서별로 스토어를 필터링 할 수 있습니다. 저장소에는 여러 부서가 있을 수 있으므로이 특성의 값은 상호 배타적이 지 않습니다.<br><br>이 예제에서는 옷, 부서: 전자, 부서: 음식의, 부서: 집 및 정원, 부서: 특성 열로 서의 부서를 추가 합니다. 부서는 특성 이름이 되며 사용자는 옷, 전자, 음식의, 집 및 정원, 스포츠 상품 부서로 필터링 할 수 있습니다.|

특성 열을 추가 하는 경우 다음 사항에 유의 하세요.

- 사용자가 지정 하는 열 이름 또는 콜론 앞에 지정 하는 열 이름 (:) 특성 이름이 됩니다. 이 값은 계층을 사용 하는 팀 앱에 표시 됩니다.
- 열 이름은 최대 100 자를 입력할 수 있으며, A-z, a-z 및 0-9 및 공백만 포함 하는 문자는 포함할 수 있습니다. 열 이름은 고유 해야 합니다.
- 시작 시 50 특성 열을 허용 하도록 계획 합니다.

### <a name="add-bucket-columns"></a>버킷 열 추가

버킷 열을 추가 하 여 작업을 구성할 수 있는 그룹화 인 버킷을 만들 수 있습니다. 각 버킷은 CSV 파일에 고유한 열을 가져옵니다. 만든 버킷은 게시 팀에서 사용할 수 있게 됩니다. 그런 다음 게시 팀은 이러한 버킷을 사용 하 여 받는 사람 팀의 작업을 분류할 수 있습니다. 팀에 버킷이 아직 없는 경우 작업을 게시할 때 버킷이 필요에 따라 만들어집니다.

작업을 중앙에서 한 번 분류 하 여 게시 팀은 작업 목록을 받는 모든 수십, 수백 또는 수천 명의 받는 사람 팀에 대해 작업 목록을 미리 구성할 수 있습니다. 그러면 받는 사람 팀은 버킷에 따라 작업을 정렬 하 고 필터링 하 여 해당 작업에 가장 적합 한 영역에 집중할 수 있습니다.

버킷 열을 추가 하는 경우 다음을 참조 하세요.

- 열 이름이 버킷 이름으로 변환 됩니다. 지정 하는 각 버킷은 계층을 사용 하는 팀 앱의 버킷 목록에 표시 됩니다. 버킷 이름에 중요 한 정보를 포함 하지 않는 것이 좋습니다. 현재, 게시 팀은 게시를 만든 후에는 버킷을 제거할 수 없습니다.
- 열 이름 앞에는 해시 태그 (#)가와 야 합니다. 최대 100 자까지 사용할 수 있으며 a-z, a-z 및 0-9 문자만 포함 합니다. 예를 들어 #Operations 및 #Frozen 상품입니다.
- 시작 시에 25 개의 버킷 열을 지원할 예정입니다. 대규모 조직에 대해 고객과 협력 하 여이 한도를 높일 계획입니다.

### <a name="example"></a>예

다음은 위의 이미지에 표시 된 계층 구조를 지원 하기 위해 생성 되는 스키마 CSV 파일의 예입니다. 이 스키마에는 다음이 포함 됩니다.

- 라는 `TargetName`세 개의 필수 열 `ParentName`, 및`TeamID`
- 이라는 `Store layout` `Departments:Clothing`세 개의 특성 열과`Departments:Foods`
- 세 개의 버킷 열 `Fresh Foods`, `Frozen Foods`및`Womenswear`

`Store layout` 특성에는, 및 `Large`를 `Compact`포함 `Standard`하는 값이 있습니다. 특성 `Departments` 열은 값 `0` (0) 또는 `1`으로 설정할 수 있습니다. `Store` 레이아웃 및 `Departments` 특성이 위의 이미지에 표시 되지 않습니다. 노드 항목에 특성을 추가 하는 방법을 보여 주기 위해 여기에 추가 됩니다. 이는 세 개의 버킷 열에도 적용 됩니다.


| TargetName             | ParentName                      | 팀 Id                       | 스토어 레이아웃|부서: 옷|부서: 음식의|#Fresh 음식의|#Frozen 음식의|#Womenswear|
|------------------------|-------------------------|--------------------------------------|-------------|---|---|---|---|---|
| 리콜                 |                         | db23e6ba-04a6-412a-95e8-49e5b01943ba |||||||
| 커뮤니케이션         |                         | 145399ce-a761-4843-a110-3077249037fc |||||||
| HR                     |                         | b8f7db91-201c-4cf9-9f7e-90a4894ed8e4 |||||||
| 동부 지역 사무소   |                         |                                      |||||||
| 서쪽 지역 사무소   |                         |                                      |||||||
| 북미 영역        | 동부 지역 사무소    |                                      |||||||
| 동남 동 존        | 동부 지역 사무소    |                                      |||||||
| 뉴욕 상점         | 북미 영역         | e2ba65f6-25e7-488b-b8f0-b8562d5de60a |대형|1|1||||
| 보스턴 스토어           | 북미 영역         | 0454f08a-0507-437c-969a-682eb2fae7fc |표준이|1|1||||
| 마이애미 상점            | 동남 동 존         | 619d6e4e-5f68-4b36-8e1f-16c98d7396c1 |Cf|0|1||||
| 새 뉴올리언스 스토어      | 동남 동 존         | 6be960b8-72af-4561-a343-9ac4711874eb |Cf|0|1||||
| 시애틀 상점          | 서쪽 지역 사무소    | 487c0d20-4e55-4dc2-8187-a24c826e0fee |표준이|1|1||||
| 로스앤젤레스 상점      | 서쪽 지역 사무소    | 204a1287-2efb-4a8a-88e0-56fbaf5a2389 |대형|1|1||||

## <a name="apply-your-hierarchy"></a>계층 구조 적용

> [!IMPORTANT]
> 이 단계를 수행 하려면 PowerShell 테스트 갤러리에서 최신 버전의 팀 PowerShell 모듈을 설치 하 고 사용 해야 합니다. 이 작업을 수행 하는 방법에 대 한 단계는 [Powershell 테스트 갤러리에서 최신 팀 PowerShell 모듈 설치](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery)를 참조 하세요.

스키마 CSV 파일에서 계층 구조를 정의 하 고 나면 팀에 업로드할 수 있습니다. 이렇게 하려면 다음 명령을 실행 합니다. 이 단계를 수행 하려면 전역 관리자 또는 팀 서비스 관리자 여야 합니다.

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

## <a name="remove-your-hierarchy"></a>계층 구조 제거

> [!IMPORTANT]
> 이 단계를 수행 하려면 PowerShell 테스트 갤러리에서 최신 버전의 팀 PowerShell 모듈을 설치 하 고 사용 해야 합니다. 이 작업을 수행 하는 방법에 대 한 단계는 [Powershell 테스트 갤러리에서 최신 팀 PowerShell 모듈 설치](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery)를 참조 하세요.

조직의 모든 사용자에 대해 게시 된 **목록** 탭을 즉시 사용 하지 않도록 설정 하려는 경우 계층 구조를 제거할 수 있습니다. 사용자는 **게시 된 목록** 탭 또는 탭의 기능에 액세스할 수 없습니다.  여기에는 게시, 액세스 초안 목록, 게시, 게시 취소 및 중복 목록에 대 한 새 작업 목록을 만드는 기능과 보고서 보기가 포함 됩니다. 계층을 제거 해도 이전에 게시 한 작업은 게시 취소 되지 않습니다. 이러한 작업은 받는 사람 팀이 완료 될 때까지 계속 사용할 수 있습니다. 

계층 구조를 제거 하려면 다음 명령을 실행 합니다. 이 단계를 수행 하려면 관리자 여야 합니다. 

```powershell
Remove-TeamTargetingHierarchy
```

### <a name="teams-powershell-module"></a>팀 Powershell 모듈

#### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a>PowerShell 테스트 갤러리에서 최신 팀 PowerShell 모듈 설치

최근에 공개적으로 사용할 수 있는 팀 PowerShell 모듈 버전 (현재 [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5))은 팀 계층 관리를 지원 하지 않습니다. 이 단계를 사용 하 여 PowerShell 테스트 갤러리에서 팀 계층 구조 지원과 함께 팀 PowerShell 모듈의 최신 버전을 설치 합니다.

> [!NOTE]
> PowerShell 테스트 갤러리에서 팀 PowerShell 모듈을 공용 PowerShell 갤러리의 모듈 버전과 나란히 설치 하지 마세요. 이 단계에 따라 먼저 공용 PowerShell 갤러리에서 팀 PowerShell 모듈을 제거 하 고 PowerShell 테스트 갤러리에서 최신 버전의 모듈을 설치 합니다.

1. 모든 기존 PowerShell 세션을 닫습니다.
2. Windows PowerShell 모듈의 새 인스턴스를 시작 합니다.
3. 공용 PowerShell 갤러리에서 팀 PowerShell 모듈을 제거 하려면 다음을 실행 합니다.

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. 모든 기존 PowerShell 세션을 닫습니다.
5. Windows PowerShell 모듈을 다시 시작 하 고 다음을 실행 하 여 PowerShell 테스트 갤러리를 신뢰할 수 있는 원본으로 등록 합니다.

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. PowerShell 테스트 갤러리에서 최신 팀 PowerShell 모듈을 설치 하려면 다음을 실행 합니다.

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. 다음을 실행 하 여 PowerShell 테스트 갤러리에서 최신 버전의 팀 PowerShell 모듈이 성공적으로 설치 되었는지 확인 합니다.

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>PowerShell 테스트 갤러리에서 최신 버전의 팀 PowerShell 모듈로 업데이트

PowerShell 테스트 갤러리에서 팀 PowerShell 모듈을 이미 설치한 경우 다음 단계를 사용 하 여 최신 버전으로 업데이트 합니다.

1. 모든 기존 PowerShell 세션을 닫습니다.
2. Windows PowerShell 모듈의 새 인스턴스를 시작 합니다.
3. 다음을 실행 하 여 PowerShell 테스트 갤러리에서 현재 설치 된 버전의 팀 PowerShell 모듈을 업데이트 합니다.

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. 다음을 실행 하 여 PowerShell 테스트 갤러리에서 최신 버전의 팀 PowerShell 모듈이 성공적으로 설치 되었는지 확인 합니다.

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="troubleshooting"></a>문제 해결

### <a name="you-receive-an-error-message-when-you-upload-your-schema-file"></a>스키마 파일을 업로드 하면 오류 메시지가 나타남

스키마를 업로드할 수 없는 이유를 나타내기 위해 문제 해결 정보를 포함 해야 한다는 오류 메시지에 유의 하세요. 오류 메시지의 정보를 기준으로 스키마 CSV 파일을 검토 하 고 편집한 다음 다시 시도 합니다.

## <a name="related-topics"></a>관련 항목

- [팀에서 조직의 작업 앱 관리](manage-tasks-app.md)
