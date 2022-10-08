---
title: Teams 관리 센터에서 팀 템플릿 시작하기
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: yinchang
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
description: Microsoft Teams 관리 센터에서 팀 템플릿 및 관리 방법에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fc4f5c88e123981ee5224a76c28996306e51ded
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046898"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>Teams 관리 센터에서 팀 템플릿 시작하기

**사용자 지정 템플릿을 만드는 기능은 아직 EDU 고객에게 지원되지 않습니다.**

> [!NOTE]
> - 개인 및 공유 채널은 현재 팀 템플릿에서 지원되지 않습니다. 프라이빗 및 공유 채널 만들기는 템플릿 정의에 포함되지 않습니다.
>
> - 민감도 레이블은 GCC 환경의 팀 템플릿에서 지원되지 않습니다. 템플릿 흐름에서 팀 만들기의 민감도 레이블 옵션은 팀에 적용되지 않습니다.

## <a name="overview"></a>개요

Microsoft Teams의 팀 템플릿은 비즈니스 요구 사항 또는 프로젝트를 중심으로 설계된 팀의 구조에 대한 정의입니다. 관리자는 템플릿을 사용하여 조직 전체에 일관된 팀을 쉽게 배포할 수 있습니다. 템플릿을 사용하면 사용자가 미리 정의된 설정, 채널 및 앱을 사용하여 풍부한 공동 작업 공간을 빠르게 만들 수 있습니다.

Microsoft Teams 관리 센터에서 또는 PowerShell을 사용하여 팀 템플릿을 관리할 수 있습니다. Microsoft에서 제공하는 미리 빌드된 템플릿을 사용할 수 있으며 [사용자 지정 템플릿을 직접 만들 수도 있습니다](#create-your-own-team-templates). [템플릿 정책을 적용](#apply-team-template-policies)하여 Teams에서 사용자가 사용할 수 있는 템플릿을 제어할 수도 있습니다.

이 문서에서는 Teams 관리 센터에서 팀 템플릿 작업에 대한 개요를 제공합니다. 템플릿에서 지원되는 속성, 제공하는 미리 빌드된 템플릿, 템플릿 크기 제한, 템플릿을 만들고 관리하는 방법 등에 대해 알아봅니다.

> [!NOTE]
> 사용자는 Teams 앱 [에서 미리 빌드된 팀 또는 사용자 지정 팀 템플릿에서 팀을 만들 수 있습니다](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) . 개발자는 Microsoft Graph를 사용하여 미리 빌드되거나 사용자 지정 팀 템플릿에서 프로그래밍 방식으로 팀을 만들 수도 있습니다. 자세한 내용은 [Microsoft Graph를 사용하여 팀 템플릿 시작](get-started-with-teams-templates.md) 방법을 참조하세요.

## <a name="team-template-capabilities"></a>팀 템플릿 기능

팀의 대부분의 속성은 팀 템플릿에서 포함 및 지원됩니다. 그러나 현재 지원되지 않는 몇 가지 속성과 기능이 있습니다. 다음은 포함된 항목과 팀 템플릿에 포함되지 않은 항목에 대한 요약입니다.

| **팀 템플릿에서 지원하는 팀 속성** | **팀 템플릿에서 아직 지원되지 않는 팀 속성** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 서식 파일 유형 | 팀 구성원 |
| 팀 이름 | 팀 사진 |
| 팀 설명 | 채널 설정 |
| 팀 가시성(퍼블릭 또는 프라이빗) | 커넥터 |
| 팀 설정(예: 멤버, 게스트, @ 멘션) | 파일 및 내용 |
| Autofavorite 채널 | |
| 앱 설치됨 | |
| 고정된 탭 | |

> [!NOTE]
> Microsoft Teams의 향후 릴리스에서 더 많은 템플릿 기능을 추가할 예정이므로 지원되는 속성에 대한 최신 정보를 다시 확인하세요.

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>Teams 관리 센터에서 미리 빌드된 팀 템플릿

Teams 관리 센터에서 사용할 수 있는 미리 빌드된 팀 템플릿은 다음과 같습니다. 미리 빌드된 템플릿은 특정 산업을 위해 만든 템플릿입니다. 이러한 템플릿을 보려면 Teams 관리 센터의 왼쪽 탐색 영역에서 **Teams** > **팀 템플릿** 으로 이동합니다.

미리 빌드된 템플릿을 복제할 수 있지만 편집할 수는 없습니다. 미리 빌드된 템플릿의 속성을 변경하려면 기존 템플릿에서 새 템플릿을 만든 다음 원하는 속성을 추가하거나 제거할 수 있습니다. 일부 템플릿의 특정 속성은 변경할 수 없습니다.

> [!NOTE]
> 별표(*)는 템플릿이 *Microsoft 365 연결된 템플릿* 임을 나타냅니다. 사용자가 템플릿을 사용하여 팀을 만들면 연결된 SharePoint 템플릿이 사이트 및 팀에 적용됩니다. 페이지, 목록 및 Power Platform 통합과 같은 SharePoint 구성 요소는 자동으로 추가되고 팀의 일반 채널에 탭으로 고정됩니다. 사용자는 Teams 내에서 바로 이러한 페이지와 목록을 편집할 수 있습니다.
>
> SharePoint 템플릿에 대한 자세한 내용은 [SharePoint 사이트 서식 파일 적용 및 사용자 지정을 참조하세요](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

>[!div class="mx-tdBreakAll"]
>| 서식 파일 유형 | TemplateId | 이 템플릿과 함께 제공되는 속성 |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| 프로젝트 관리* |`com.microsoft.teams.template.ManageAProject`| 채널 <ul><li>일반</li> <li>공지 사항</li> <li>리소스</li> <li>계획</li></ul> 앱:<ul><li>승인</li><li>게시판</li><li>목록<ul><li>프로젝트 추적기</li><li>문제 추적기</li></ul></li><li>이정표</li><li>OneNote</li><li>Power Automate</li><li>SharePoint Pages<ul><li>당사 사이트</li></ul></li><li>Planner 및 할 일별 작업</li><li>Wiki</li></ul> |
| 이벤트 관리*|`com.microsoft.teams.template.ManageAnEvent` | 채널 <ul><li>일반</li> <li>공지 사항</li> <li>예산</li> <li>콘텐츠</li><li>물류</li> <li>계획</li> <li> 마케팅 및 PR</li></ul> 앱:<ul><li>승인</li><li>게시판</li> <li>직원 아이디어</li><li>목록<ul><li>콘텐츠 스케줄러</li></ul></li><li>이정표</li> <li>OneNote</li> <li>Power Automate</li> <li>SharePoint Pages<ul><li>당사 사이트</li><li>이벤트 정보</li></ul><li>Planner 및 할 일별 작업</li><li>Wiki</li> |
|직원 온보딩*|`com.microsoft.teams.template.OnboardEmployees` | 채널 <ul><li>일반</li> <li>공지 사항</li> <li>직원 채팅</li> <li>교육</li></ul>앱:<ul><li>게시판</li><li>직원 아이디어</li><li>목록<ul><li>온보딩 검사 목록</li></ul></li><li>이정표</li><li>Power Automate</li> <li>SharePoint Pages<ul><li>시작하기</li><li>교육</li></ul><li>Planner 및 할 일별 작업</li><li>Viva Engage</li><li>Wiki</li></ul>|
| Office 365 채택 |`com.microsoft.teams.template.AdoptOffice365`|  채널 <ul><li>일반</li> <li>공지 사항</li> <li>챔피언 코너</li> <li>Team Forms</li><li>일정</li></ul> 앱: <ul><li>Wiki</li>  <li>채널 일정</li> <li>이정표</li><li>게시판</li></ul>
|지원 센터 구성*| `com.microsoft.teams.template.OrganizeHelpDesk`|채널<ul><li>일반</li><li>공지 사항</li><li>FAQ</li></ul>앱:<ul><li>문제 보고</li><li>목록<ul><li>장치</li><li>티켓</li></ul></li><li>OneNote</li><li>Power Automate</li><li>SharePoint Pages<ul><li>당사 사이트</li><li>FAQ</li></ul></li><li>Planner 및 할 일별 작업</li><li>Wiki</li></ul> |
|인시던트 대응| `com.microsoft.teams.template.CoordinateIncidentResponse`|채널 <ul><li>일반<li>공지 사항</li><li>물류</li><li>계획</li><li>복구</li><li>긴급</li></ul> 앱: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>작업</li> <li>승인</li> <li>검사</li> <li>Power Automate</li><li>게시판</li><li>이정표</li></ul>|
| 위기 통신* |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| 채널 <ul><li>일반<li>공지 사항</li><li>임원 업데이트</li><li>계획</li><li>물류</li></ul>앱: <ul><li>승인</li><li>문제 보고</li><li>목록<ul><li>콘텐츠 스케줄러</li><li>프로젝트 계획</li></ul></li><li>OneNote</li><li>Power Automate</li><li>SharePoint Pages<ul><li>당사 사이트</li><li>최신 업데이트</li></ul><li>Planner 및 할 일별 작업</li>|
| 스토어 관리*| `com.microsoft.teams.template.retailStore` |채널 <ul><li>일반<li>Shift Handoff</li><li>스토어 준비 상태</li><li>학습</li></ul> 앱: <ul><li>승인</li><li>검사</li><li>목록<ul><li>인벤토리 목록</li></ul></li><li>SharePoint Pages<ul><li>Microsoft Store</li></ul></li><li>교대 근무</li><li>Planner 및 할 일별 작업</li><li>Wiki</li></ul>|
|은행 지점| `com.microsoft.teams.template.CollaborateWithinABankBranch`|채널 <ul><li>일반<li>공지 사항</li><li>장애 요소</li><li>고객 모임</li><li>승인 요청 </li><li>코칭</li><li>기술 개발</li><li>대출 처리</li><li>고객 불만 사항</li><li>쿠도스</li><li>재미있는 물건</li><li>규정 준수</li></ul>앱:<ul><li>칭찬 </li><li>문제 보고자</li><li>Wiki</li><li>일정</li><li>승인</li><li>게시판</li><li>아이디어</li></ul>|
| 환자 관리| `com.microsoft.teams.template.healthcareWard`| 채널<ul><li>일반</li><li>공지 사항</li><li>장애 요소</li><li>라운드</li><li>직원</li><li>교육</li></ul> 앱: <ul><li>Wiki</li><li>목록  </li><li>승인</li><li>게시판</li><li>검사</li></ul>|
|병원| `com.microsoft.teams.template.healthcareHospital` |채널 <ul><li>일반</li><li>공지 사항</li><li>규정 준수</li><li>보호</li><li>인적 리소스</li><li>약국</li></ul> 앱: <ul><li>Wiki</li><li>목록</li><li>작업</li><li>승인</li><li>교대 근무</li><li>게시판</li><li>검사</li><li>아이디어</li></ul>|
|품질 및 안전 |`com.microsoft.teams.template.QualitySafety`|채널 <ul><li>일반<li>공지 사항</li><li>리더십</li><li>유지 관리</li><li>프로덕션 라인 1</li><li>프로덕션 라인 2</li><li>프로덕션 라인 3</li><li>건강 및 안전</li><li>교육</li><li>재미있는 물건</li></ul> 앱: <ul><li>Wiki</li><li>작업</li> <li>문제 보고자</li> <li>검사</li> </ul>|
|관리자용 소매*| `com.microsoft.teams.template.retailManagerCollaboration` |채널 <ul><li>일반<li>작업</li><li>학습</li></ul> 앱: <ul><li>승인</li><li>검사</li><li>SharePoint Pages<ul><li>Microsoft Store</li></ul></li><li>Planner 및 할 일별 작업</li><li>Wiki</li></ul>|
|자원 봉사자 관리| `com.microsoft.teams.template.ManageVolunteers` |채널 <ul><li>일반<li>공지 사항</li><li>보고</li><li>자원 봉사자 관리</li><li>참여 기회</li><li>자원 봉사자 온보딩</li></ul> 앱: <ul><li>웹 사이트</li><li>YouTube</li><li>Power BI</li><li>Power Apps</li><li>작업</li><li>SharePoint</li><li>OneNote</li></ul>|

### <a name="team-templates-by-category-and-industry"></a>범주 및 산업별 팀 템플릿

업계에서 미리 빌드된 템플릿을 사용하는 방법에 대한 자세한 내용은 다음을 참조하세요.

- [일반 팀 템플릿](general-teams-templates-in-the-admin-console.md)
- [재무 팀 템플릿](financial-teams-templates-in-the-admin-console.md)
- [정부 팀 템플릿](government-teams-templates-in-the-admin-console.md)
- [의료 팀 템플릿](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [제조 팀 템플릿](manufacturing-teams-templates-in-the-admin-console.md)
- [비영리 팀 템플릿](team-templates-nonprofit.md)
- [소매 팀 템플릿](get-started-with-retail-teams-templates.md)

## <a name="team-template-size-limits"></a>팀 템플릿 크기 제한

템플릿은 특정 수의 채널, 탭 및 앱으로 제한됩니다.

 > [!Note]
 > 템플릿에서 만든 후 팀에 채널, 탭 및 앱을 더 추가할 수 있습니다.

|기능 | 제한|
|-|-|
|템플릿당 채널 수 | 15 |
|템플릿의 채널당 탭 | 20 |
|템플릿당 앱 | 50|

자세한 내용은 [Teams의 제한 및 사양을 참조하세요](limits-specifications-teams.md).

## <a name="manage-team-templates"></a>팀 템플릿 관리

### <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 관리 센터에서 팀 템플릿 관리

#### <a name="view-team-templates"></a>팀 템플릿 보기

팀 템플릿을 보려면 Teams 관리 센터의 왼쪽 탐색 영역에서 **Teams** > **팀 템플릿** 으로 이동합니다. 포함된 채널 및 앱을 포함하여 자세한 내용을 보려면 템플릿을 선택합니다.

#### <a name="create-your-own-team-templates"></a>고유한 팀 템플릿 만들기

사용자 지정 템플릿을 처음부터, 기존 팀 및 기존 템플릿에서 만들 수 있습니다. 자세한 내용은 다음을 참조하세요.

- [사용자 지정 팀 템플릿 만들기](create-a-team-template.md)
- [기존 팀에서 템플릿 만들기](create-template-from-existing-team.md)
- [기존 팀 템플릿에서 팀 템플릿 만들기](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>팀 템플릿 정책 적용

[Teams에서 팀을 만들기](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b) 위해 표시되는 템플릿을 제어하려면 템플릿 정책을 설정하고 조직의 사용자 및 그룹에 할당할 수 있습니다. 자세한 내용은 [Teams 관리 센터에서 팀 템플릿 관리를](templates-policies.md) 참조하세요.

### <a name="manage-team-templates-using-powershell"></a>PowerShell을 사용하여 팀 템플릿 관리

다음 cmdlet을 사용하여 PowerShell에서 템플릿을 관리합니다.

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate)
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist)
- [New-CsTeamTemplate](/powershell/module/teams/new-csteamtemplate)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate)
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate)

## <a name="related-articles"></a>관련 기사

- [템플릿으로 팀 만들기](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Microsoft Graph를 사용하여 팀 템플릿 시작하기](get-started-with-teams-templates.md)
- [팀 복제](/graph/api/team-clone)
- [Teams 및 SharePoint 통합 개요](/sharepoint/teams-connected-sites)
