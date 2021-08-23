---
title: 팀 대상 계층 구조 설정
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: 조직에서 팀 계층 구조를 설정하여 대규모 팀 집합에 콘텐츠를 게시하는 방법에 대해 자세히 알아보겠습니다.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c1a08bfe63db87332035dd51b93281cc8ac0f25
ms.sourcegitcommit: 9062b2c81c582ddc878c825ba1b22a6c23ca4b64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2021
ms.locfileid: "58398957"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>팀 대상 계층 구조 설정

팀 대상 계층 구조를 설정하면 조직에서 대규모 팀 집합에 콘텐츠를 게시할 수 있습니다. 팀 대상 계층 구조는 계층 구조의 모든 팀이 서로 관련되는 방법, 사용자가 작업을 게시할 수 있는 팀 및 게시할 권한이 있는 팀을 정의합니다. 조직에 대해 팀 대상 계층 구조가 설정되지 않는 한 모든 사용자에 대해 게시 기능을 사용할 수 없습니다. 팀 대상 계층 구조를 설정하려면 계층 구조를 정의하는 파일을 만든 다음 조직에 적용하기 위해 Teams 업로드해야 합니다. 스마마가 업로드된 후 해당 웹 Teams 사용할 수 있습니다.

> [!IMPORTANT]
> 초기 릴리스의 경우 작업 앱만 계층적 팀을 지원합니다.  조직에 팀 대상 계층 구조를 적용하면 작업 [앱에서](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) 태스크 게시가 활성화됩니다. 다른 영역의 팀 계층 구조가 Microsoft Teams.

다음은 계층 구조의 작업 앱에서 계층 구조를 나타내는 Teams. 작업 목록을 만든 후 게시 팀의 구성원은 받는 사람 팀을 선택하여 작업 목록을 보내(게시)할 수 있습니다. 팀을 선택할 때 게시 팀은 계층 구조, 특성 또는 둘 다의 조합을 통해 필터링할 수 있습니다.<br>

![작업을 게시하는 스크린샷](media/manage-tasks-app-publish.png)

## <a name="terminology"></a>용어

계층을 탐색할 때 다음 용어가 중요합니다. Teams 노드라고 **합니다.**

* **루트 노드는** 계층 구조에서 가장 상위 노드입니다. 이 예제에서 Retail Communications는 루트 노드입니다.
* **부모 노드** 및 **자식 노드는** 연결된 두 노드 간의 관계를 나타내는 용어입니다. 예제에서 01 지구는 영역 1의 자식 노드입니다.
* 여러 수준의 자식은 자식이라고 **합니다.** 지구 01, Store 01, Store 03, Store 07, District 02 및 District 03은 모두 지역 1의 후원자입니다.
* 자식이 없는 노드를 리프 **노드라고 합니다.** 계층 구조의 맨 아래에 있습니다.
* **받는 사람 팀은** 게시할 특정 콘텐츠 집합을 받기 위해 선택된 팀입니다. 리프 노드가 되어야 합니다.

## <a name="plan-your-hierarchy"></a>계층 구조 계획

계층 구조를 정의하는 도마를 만들기 전에 계획을 세우고 조직을 구성할 방법을 결정해야 합니다.  첫 번째 우선 순위 중 하나는 다른 그룹에 작업을 게시해야 하는 조직 그룹을 결정하는 것입니다. 계층 구조의 각 노드는 작업 그룹 또는 그룹 그룹을 나타냅니다.

### <a name="permissions-to-publish"></a>게시할 권한

게시 권한은 사용자가 계층 구조의 모든 팀의 구성원인지 여부와 해당 팀 또는 계층 구조의 다른 팀과의 관계에 따라 달라집니다.

> [!NOTE]
> 팀의 소유자에게 게시 권한도 부여됩니다.

* 사용자가 계층 구조에 자선이 있는 하나 이상의 팀의 구성원인 경우 해당 사용자는 게시하려는 모든 팀의 구성원이지 않고 해당 후속 팀에 게시할 수 있습니다.
* 사용자가 계층 구조에서 하나 이상의 팀의 구성원이지만 계층 구조에 있는 후속 팀의 구성원이 아닌 경우 해당 사용자는 조직에서 게시된 콘텐츠를 보고 받을 수 있습니다.
* 사용자가 계층 구조의 팀 구성원이 아닌 경우 해당 사용자는 게시 관련 기능을 볼 수 없습니다.

### <a name="guidelines"></a>지침

* 조직당 하나의 계층 구조 파일만 적용할 수 있습니다. 그러나 조직의 여러 부분을 하나의 파일 내에 노드의 고유한 계층으로 함께 포함할 수 있습니다. 예를 들어 Contoso Pharmaceuticals에는 약국 루트 노드와 소매 루트 노드가 있습니다. 두 루트 노드에는 여러 행의 후원 행이 있으며 둘 사이에는 겹치지 않습니다.
* 리프 노드만 발행물의 받는 사람일 수 있습니다. 계층 구조의 다른 노드는 발행물의 받는 사람을 선택하는 데 유용합니다.
* 팀은 계층 구조에서 한 번만 표현할 수 있습니다.
* 계층 구조에는 최대 15,000개 노드가 포함될 수 있습니다. 대규모 조직에 대해 이 한도를 높이기 위해 고객과 협력할 계획입니다.

### <a name="example-hierarchy"></a>예제 계층 구조

예를 들어 다음 계층 구조에서 리콜, 통신 및 HR은 계층 구조의 모든 아래쪽 노드(팀)에 작업을 게시할 수 있지만 북동부 영역은 뉴욕 스토어 및 보스턴 스토어 팀에만 작업을 게시할 수 있습니다. 예제 계층 구조를 사용하면 회수, 통신 및 HR 그룹이 CEO의 혜택 정보 또는 메시지와 같은 회사 전체에 적용되는 작업을 게시할 수 있습니다. Northeast Zone은 직원의 일과 같은 작업을 뉴욕 스토어 및 보스턴 스토어 팀에만 게시할 수 있습니다.

![팀 계층적 예제](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a>계층 구조 만들기

> [!NOTE]
> 이 문서의 나머지부분에서는 받는 사람 팀에 작업을 게시하는 컨텍스트에서 팀 계층 구조 설정에 대해 설명합니다. 작업 [게시를](./manage-tasks-app.md) 사용하도록 설정한 경우 작업 Teams 개요는 조직의 작업 앱 관리를 참조하세요.

계층 구조를 정의하는척도는 CSV(콤마로 구분된 값) 파일을 기반으로 합니다. 파일은 UTF-8 형식으로 있어야 합니다. CSV 파일의 각 행은 팀 계층 구조 내의 하나의 노드에 해당합니다. 각 행에는 계층 구조 내에서 노드의 이름을 입력하고, 선택적으로 팀에 연결하며, 이를 지원하는 앱의 팀을 필터링하는 데 사용할 수 있는 특성을 포함합니다.

또한 게시 팀에서 받는 사람 팀에 보낸 콘텐츠를 구성하는 데 사용할 수 있는 범주인 버킷을 정의하여 관련 콘텐츠를 보다 쉽게 보고 정렬하고 집중할 수 있습니다.

### <a name="add-required-columns"></a>필요한 열 추가

CSV 파일에는 첫 번째 열부터 다음 세 개의 열이 다음 순서로 포함되어야 합니다. 태스크를 수신하려면 노드를 팀에 연결해야 합니다.

| 열 이름   | 필수 | 설명   |
----------------|----------|---------------|
| DisplayName    | 예      | 이 필드는 노드의 이름입니다. 이름은 최대 100자까지 길고 A-Z, a-z 및 0-9 문자만 포함할 수 있습니다. 노드 이름은 고유해야 합니다. |
| ParentName    | 예       | 부모 노드의 이름입니다. 여기서 지정한 값은 부모 노드의 **DisplayName** 필드의 값과 정확히 일치해야 합니다. 두 개 이상의 상위 노드를 추가하려는 경우 세미코론(세미코론)으로 각 부모 노드 이름을 ;). 최대 25개 부모 노드를 추가할 수 있으며 각 상위 노드 이름은 최대 2500자까지 사용할 수 있습니다. 노드는 상위 노드가 루트 노드인 경우 여러 개의 상위 노드를 사용할 수 있습니다.   <br><br>**중요** 계층 구조에서 상위 상위에 있는 부모가 계층 구조의 하위 하위 노드를 참조하는 루프를 만들지 않도록 주의하세요. 지원되지 않습니다. |
| TeamId        | 예. 팀에서 작업을 게시하거나 부모 노드에서 작업을 수신하는 경우       | 여기에는 노드를 연결하려는 팀의 ID가 포함되어 있습니다. 각 노드는 고유한 팀을 참조해야 있으므로 각 TeamId 값은 계층 구조 파일에 한 번만 나타날 수 있습니다. 노드를 연결하려는 팀의 ID를 얻으면 다음 PowerShell 명령을 `Get-Team | Export-Csv TeamList.csv` 실행합니다. 이 명령은 조직의 팀을 나열하고 각 팀의 이름 및 ID를 포함합니다. 연결하려는 팀의 이름을 찾은 다음 이 필드에 ID를 복사합니다.|

> [!NOTE]
> 노드가 루트 노드 또는 리프 노드가 아니고 게시 및 보고에 해당하는 권한을 부여하기 위해 팀 멤버 자격이 필요하지 않은 경우 TeamId를 비워 두면 됩니다. 이 메서드는 받는 사람 팀을 선택할 때 또는 해당 팀이 없는 완료 보고서를 볼 때 더 세분성을 추가하는 데 사용할 수 있습니다.

### <a name="add-attribute-columns"></a>특성 열 추가

필요한 세 열을 추가한 후 선택적 특성 열을 추가할 수 있습니다. 이러한 특성은 작업을 게시할 속성을 보다 쉽게 선택할 수 있도록 노드를 필터링하는 데 사용할 수 있습니다. 해당 특성에 대한 값이 상호 배타적인지 여부에 따라 특성을 정의하는 두 가지 방법이 있습니다.

|특성을 추가하는 방법|설명 |예제  |
|---|---------|---------|
|특성의 값이 상호 배타적이면 지정한 열 이름이 특성의 이름이 됩니다.|각 행은 해당 특성에 대한 하나의 값을 포함할 수 있으며, 각 특성 열에는 최대 50개 고유 값이 있을 수 있습니다. 각 값은 최대 100자까지 길 수 있습니다. 특성 열에 지정한 특성 값 집합은 팀 대상 계층 구조를 사용하여 받는 사람 팀을 선택할 때 해당 특성에 대한 필터 값으로 표시됩니다.|사용자가 레이아웃으로 저장소를 필터링할 수 있도록 합니다. 저장소에 레이아웃이 하나만 있기 때문에 이 특성의 값은 상호 배타적입니다. <br><br>레이아웃에 따라 저장소를 필터링하는 특성을 추가하기 위해 저장소 레이아웃이라는 열을 추가합니다. 이 예제에서는 Store 레이아웃 특성에 대한 값이 Compact, Standard 및 Large입니다.
|특성에 대해 여러 값을 표시해야 하는 경우 값이 상호 배타적이지 않은 경우 열 이름에 **대해 AttributeName:UniqueValue** 형식을 사용합니다. <br><br>**중요** 영어 전용 콜론(:) 유니코드는 특성 열분리자로 지원되지 않습니다. |콜론 앞에 있는 텍스트 문자열(:) 는 특성의 이름이 됩니다. 콜론 앞에 동일한 텍스트 문자열이 포함된 모든 열(:) 필터링 메뉴의 섹션으로 그룹화됩니다. 콜론 다음의 각 문자열은 이 섹션의 값이 됩니다.<br><br>각 행에는 해당 특성에 대한 값이 0(0) 또는 1일 수 있습니다. 값이 0이면 특성이 노드에 적용되지 않습니다. 1 값은 특성이 해당 노드에 적용됩니다.|사용자가 부서에 따라 저장소를 필터링할 수 있도록 합니다. 저장소에 여러 부서가 있을 수 있으므로 이 특성의 값은 상호 배타적이지 않습니다.<br><br>이 예제에서는 Departments:Clothing, Departments:Electronics, Departments:Foods, Departments:Home and Garden, Departments:Sporting goods를 특성 열로 추가합니다. 부서는 특성 이름이 며 사용자는 의류, 전자 제품, 식품, 가정 및 정원 및 스포츠 제품 부서를 통해 필터링할 수 있습니다.|

특성 열을 추가할 때 다음을 염두에 두어야 합니다.

* 지정한 열 이름 또는 콜론 앞에 지정한 열 이름(:) 는 특성의 이름이 됩니다. 이 값은 계층 구조를 사용하는 Teams 앱에 표시됩니다.
* 계층 구조에 최대 50개 특성 열을 사용할 수 있습니다.
* 열 이름은 최대 100자까지 사용할 수 있으며 A-Z, a-z 및 0-9 및 공백만 포함할 수 있습니다. 열 이름은 고유해야 합니다.

### <a name="add-bucket-columns"></a>버킷 열 추가

버킷 열을 추가하여 작업을 구성할 수 있는 그룹화인 버킷을 만들 수 있습니다. 각 버킷은 CSV 파일에서 자체 열을 얻습니다. 만든 버킷은 게시 팀에서 사용할 수 있습니다. 그런 다음 게시 팀은 이러한 버킷을 사용하여 받는 사람 팀에 대한 작업을 분류할 수 있습니다. 팀에 버킷이 아직 없는 경우 태스크가 게시될 때 버킷이 수요에 따라 생성됩니다.

작업 항목을 한 번씩 중앙에서 분류하여 게시 팀은 작업 목록을 받는 수십, 수백 또는 수천 명의 받는 사람 팀에 대해 작업 목록을 미리 구성할 수 있습니다. 그런 다음 받는 사람 팀은 작업과 가장 관련된 영역에 집중하기 위해 버킷으로 작업을 정렬하고 필터링할 수 있습니다.

버킷 열을 추가할 때 다음을 유의합니다.

* 열 이름은 버킷의 이름이 됩니다. 지정한 각 버킷은 계층 구조를 사용하는 Teams 버킷 목록에 표시됩니다.
* 중요한 정보는 버킷 이름에 포함하지 않는 것이 좋습니다. 현재 게시 팀은 게시를 통해 버킷을 제거할 수 없습니다.
* 열 이름은 해시태그(#) 앞에 있어야 합니다. 최대 100자까지 길고 A-Z, a-z 및 0-9 문자만 포함할 수 있습니다. 예를 들어 #Operations #Frozen 수 있습니다.
* 계층 구조에는 최대 25개 버킷 열이 포함될 수 있습니다. 대규모 조직에 대한 이 제한을 높이기 위해 고객과 협력할 계획입니다.

### <a name="example"></a>예제

이전 이미지에 표시된 계층 구조를 지원하기 위해 만들어질 Schema CSV 파일의 예는 다음과 같습니다. 이 계획에는 다음이 포함되어 있습니다.

* 이라는 세 개의 필수 열 `TargetName` `ParentName` 및 `TeamId`
* 이라는 3개의 특성 `Store layout` `Departments:Clothing` 열 및 `Departments:Foods`
* 이라는 세 개의 버킷 열 `Fresh Foods` `Frozen Foods` 및 `Women's Wear`

특성에는 `Store layout` , 및 를 포함 하는 `Compact` 값이 `Standard` `Large` 있습니다. 특성 `Departments` 열은 (0) 또는 의 값으로 설정할 `0` 수 `1` 있습니다. 레이아웃 및 특성은 위의 `Store` `Departments` 이미지에 표시되지 않습니다. 노드 항목에 특성을 추가할 수 있는 방법을 보여 주기 위해 여기에 추가됩니다. 세 개의 버킷 열도 마찬가지입니다.

```CSV
TargetName,ParentName,TeamId,Store layout,Departments:Clothing,Departments:Foods,#Fresh Foods,#Frozen Foods,#Women's Wear
Recall,,db23e6ba-04a6-412a-95e8-49e5b01943ba,,,,,,
Communications,,145399ce-a761-4843-a110-3077249037fc,,,,,,
HR,,125399ce-a761-4983-a125-3abc249037fc,,,,,,
East Regional Office,HR;Communications;Recall,,,,,,,
West Regional Office,HR;Communications;Recall,,,,,,,
Northeast Zone,East Regional Office,,,,,,,
Southeast Zone,East Regional Office,,,,,,,
New York Store,Northeast Zone,e2ba65f6-25e7-488b-b8f0-b8562d5de60a,Large,1,1,,,
Boston Store,Northeast Zone,0454f08a-0507-437c-969a-682eb2fae7fc,Standard,1,1,,,
Miami Store,Southeast Zone,619d6e4e-5f68-4b36-8e1f-16c98d7396c1,Compact,0,1,,,
New Orleans Store,Southeast Zone,6be960b8-72af-4561-a343-9ac4711874eb,Compact,0,1,,,
Seattle Store,West Regional Zone,487c0d20-4e55-4dc2-8187-a24c826e0fee,Standard,1,1,,,
Los Angeles Store,West Regional Zone,204a1287-2efb-4a8a-88e0-56fbaf5a2389,Large,1,1,,,
```

## <a name="apply-your-hierarchy"></a>계층 구조 적용

> [!NOTE] 
> 이 단계를 수행하려면 PowerShell 갤러리에서 Teams PowerShell 공개 미리 보기 모듈을 설치하고 사용해야 합니다. 모듈을 설치하는 방법에 대한 단계는 PowerShell 설치를 Teams 참조하세요.

> [!NOTE]
> 정부 커뮤니티 클라우드(GCC) 고객은 cmdlet 미리 보기 버전 [2.4.0 미리](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.0-preview) 보기 이상을 사용하여 데이터가 공용 클라우드 환경이 아닌 GCC 환경으로 라우팅되도록 해야 합니다.

Schema CSV 파일에서 계층 구조를 정의한 후 해당 계층 구조를 업로드할 준비가 Teams. 이렇게 하여 다음 명령을 실행합니다. 이 단계를 위해 전역 관리자 또는 Teams 관리자 되어야 합니다.

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a>계층 구조 업데이트

위와 동일한 PowerShell 명령을 사용하여 이전 계층 구조를 대체하기 위해 새 계층 구조를 업로드할 수 있습니다. 새 계층 구조를 업로드할 때마다 이전 계층 구조가 대체됩니다.

### <a name="check-the-status-of-your-hierarchy"></a>계층 구조 상태 확인

다음 명령을 실행하여 계층 구조 업로드 상태를 확인할 수 있습니다.

```powershell
Get-TeamTargetingHierarchyStatus
```

명령은 다음 필드를 반환합니다.

필드|설명
-----|------------
ID | 업로드에 대한 고유 ID입니다.
상태 | 업로드 상태입니다. 값에는 **시작,** **유효성 검사,** **성공** 및 **실패가 포함됩니다.**
ErrorDetails | 업로드 오류가 있는 경우 세부 정보입니다. 오류 세부 정보에 대한 자세한 내용은 문제 해결 섹션을 참조하세요. 오류가 없는 경우 이 필드는 비어 있습니다.
LastUpdatedAt | 타임스탬프 및 파일이 마지막으로 업데이트된 날짜입니다.
LastModifiedBy | 파일을 수정한 마지막 사용자의 ID입니다.
FileName | CSV의 파일 이름입니다.

## <a name="remove-your-hierarchy"></a>계층 구조 제거

조직의 모든 사용자에  대해 게시된 목록 탭을 즉시 사용하지 않도록 설정하려면 계층 구조를 제거할 수 있습니다. 사용자는 게시된 목록 탭  또는 탭의 기능에 액세스할 수 없습니다.  여기에는 게시, 초안 목록에 액세스, 게시, 게시, 게시 및 중복 목록 및 보고를 볼 수 있는 새 작업 목록을 만드는 기능을 포함합니다. 계층 구조를 제거해도 이전에 게시된 작업이 게시되지 않습니다. 이러한 작업은 받는 사람 팀이 완료할 수 있도록 계속 사용할 수 있습니다.

계층 구조를 제거하려면 다음 명령을 실행합니다. 이 단계를 수행하려면 관리자가 되어야 합니다.

```powershell
Remove-TeamTargetingHierarchy
```

삭제를 확인할 때 상태 메시지는 여전히 이전의 도마가 표시되고, 다시 삭제하려고 하면 개체가 null인 오류가 반환됩니다.

## <a name="create-a-sample-hierarchy"></a>샘플 계층 구조 만들기

### <a name="install-the-teams-powershell-module"></a>PowerShell Teams 설치

> [!IMPORTANT]
> 이 단계를 수행하려면 PowerShell 갤러리에서 Teams PowerShell 공개 미리 보기 모듈을 설치하고 [사용해야 합니다.](https://www.powershellgallery.com/packages/MicrosoftTeams/) 모듈을 설치하는 방법에 대한 단계는 [PowerShell Teams 참조하세요.](teams-powershell-install.md)

### <a name="sample-script"></a>샘플 스크립트

다음 스크립트를 사용하여 팀을 만들고 .csv 테넌트에 Microsoft Teams 수 있습니다. 기존 계층 구조가 있는 경우 이 스크립트가 대체됩니다.

#### <a name="create-teams-for-a-simple-hierarchy"></a>간단한 계층 구조에 대한 팀 만들기

```powershell
$tm1 = New-Team -DisplayName "HQ"
$tm2 = New-Team -DisplayName "North"
$tm3 = New-Team -DisplayName "Store 1"
$tm4 = New-Team -DisplayName "Store 2"
$tm5 = New-Team -DisplayName "South"
$tm6 = New-Team -DisplayName "Store 3"
$tm7 = New-Team -DisplayName "Store 4"
```

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a>팀 데이터를 사용하여 콤마로 구분된 출력을 만들 수 있습니다(DisplayName, ParentName, TeamId)

```powershell
$csvOutput = "DisplayName" + "," + "ParentName" + "," + "TeamId" + "`n"
$csvOutput = $csvOutput + $tm1.DisplayName + "," + "," + $tm1.GroupID + "`n"
$csvOutput = $csvOutput + $tm2.DisplayName + "," + $tm1.DisplayName + "," + $tm2.GroupID + "`n"
$csvOutput = $csvOutput + $tm3.DisplayName + "," + $tm2.DisplayName + "," + $tm3.GroupID + "`n"
$csvOutput = $csvOutput + $tm4.DisplayName + "," + $tm2.DisplayName + "," + $tm4.GroupID + "`n"
$csvOutput = $csvOutput + $tm5.DisplayName + "," + $tm1.DisplayName + "," + $tm5.GroupID + "`n"
$csvOutput = $csvOutput + $tm6.DisplayName + "," + $tm5.DisplayName + "," + $tm6.GroupID + "`n"
$csvOutput = $csvOutput + $tm7.DisplayName + "," + $tm5.DisplayName + "," + $tm7.GroupID 
```

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a>다운로드 폴더에 .csv 파일에 출력 **저장**

```powershell
$csvOutputPath = $env:USERPROFILE + "\downloads\testhierarchy-" + (Get-Date -Format "yyyy-MM-dd-hhmmss") + ".csv" 
$csvOutput | Out-File $csvOutputPath
```

#### <a name="upload-the-hierarchy"></a>업로드 계층 구조

```powershell
Set-TeamTargetingHierarchy -FilePath $csvOutputPath
Get-TeamTargetingHierarchyStatus
```

## <a name="troubleshooting"></a>문제 해결

### <a name="how-to-view-error-details"></a>오류 세부 정보를 보는 방법

다음 명령을 실행하여 오류의 원인을 이해하고 오류 세부 정보를 반환할 수 있습니다.

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>Schema CSV 파일을 업로드할 때 오류 메시지가 표시됩니다.

오류 메시지에 문제 해결 정보가 포함되어야 하여, 왜 스마마를 업로드할 수 없는지 나타냅니다. 오류 메시지의 정보를 기반으로 Schema CSV 파일을 검토하고 편집한 다음 다시 시도합니다.

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>Schema CSV 파일을 업로드할 때 "Error: InvalidTeamId" 오류 메시지가 표시됩니다.

Schema CSV 파일을 업로드하려고 할 때 다음과 같은 오류 메시지가 표시됩니다.

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

Schema CSV 파일에서 팀에 대해 올바른 TeamId를 사용하고 있는지 확인합니다. TeamId는 팀을 백업하는 Microsoft 365 그룹의 그룹 ID와 동일해야 합니다. 관리 센터에서 팀의 그룹 ID를 Microsoft Teams 있습니다.

1. 관리 센터의 [왼쪽 탐색에서](https://admin.teams.microsoft.com/)Microsoft Teams 관리 **Teams**  >  **로 이동하세요.**
2. 그룹 **ID** 열이 표에 표시되지 않는  경우 표의 오른쪽 위 모서리에 있는 열 편집을 선택한 다음 그룹 **ID 를 를 켜면 됩니다.**
3. 목록에서 팀을 찾은 다음 그룹 ID를 찾습니다.

Schema CSV 파일의 TeamId가 관리 센터에 표시되는 그룹 ID와 Microsoft Teams 합니다.

## <a name="related-topics"></a>관련 항목

* [조직의 작업 앱 관리 Teams](manage-tasks-app.md)
* [Teams PowerShell 개요](teams-powershell-overview.md)
