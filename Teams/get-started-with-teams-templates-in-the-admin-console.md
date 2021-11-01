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
description: 팀 템플릿 및 관리 센터에서 팀 템플릿을 관리하는 Microsoft Teams 대해 자세히 알아보습니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: a22ced459a9e014b92a7141a224ea20d5f7022d2
ms.sourcegitcommit: 813f1e44bd094bd997dd7423cda7e685ff61498f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2021
ms.locfileid: "60633514"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>Teams 관리 센터에서 팀 템플릿 시작하기

**사용자 지정 템플릿을 만드는 능력은 아직 EDU 고객에게 지원되지 않습니다.**

> [!NOTE]
> 개인 채널 및 민감도 레이블은 현재 팀 템플릿에서 지원되지 않습니다. 개인 채널 만들기는 템플릿 정의에 포함되지 않습니다. 템플릿 흐름에서 팀  만들기의 민감도 레이블 옵션은 팀에 적용되지 않습니다.

## <a name="overview"></a>개요

팀 템플릿은 Microsoft Teams 필요 또는 프로젝트를 중심으로 디자인된 팀 구조의 정의입니다. 관리자는 템플릿을 사용하여 조직 전체에 일관된 팀을 쉽게 배포할 수 있습니다. 템플릿을 사용하면 사용자가 미리 정의한 설정, 채널 및 앱을 사용하여 풍부한 공동 작업 공간을 빠르게 만들 수 있습니다.

관리 센터 또는 PowerShell을 사용하여 Microsoft Teams 팀 템플릿을 관리할 수 있습니다. 제공한 미리 작성된 템플릿을 사용할 수 있으며 사용자 지정 템플릿을 직접 만들 [수도 있습니다.](#create-your-own-team-templates) 템플릿 정책을 [적용하여](#apply-team-template-policies) 사용자가 사용할 수 있는 템플릿을 제어할 수도 Teams.

이 문서에서는 관리 센터에서 팀 템플릿을 사용하는 Teams 제공합니다. 템플릿에서 지원되는 속성, 우리가 제공하는 미리 작성된 템플릿, 템플릿 크기 제한, 템플릿을 만들고 관리하는 방법 등입니다.

> [!NOTE]
> 사용자는 [미리](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) 작성된 또는 사용자 지정 팀 템플릿에서 팀을 만들 수 Teams 있습니다. 개발자는 Microsoft Graph. 자세한 내용은 [Microsoft](get-started-with-teams-templates.md)Graph.

## <a name="team-template-capabilities"></a>팀 템플릿 기능

팀의 대부분의 속성은 팀 템플릿에서 포함 및 지원됩니다. 그러나 현재 지원되지 않는 몇 가지 속성 및 기능이 있습니다. 여기에 포함된 내용과 팀 템플릿에 포함되지 않은 내용에 대한 요약이 있습니다.

| **팀 템플릿에서 지원하는 팀 속성** | **팀 템플릿에서 아직 지원되지 않는 팀 속성** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 서식 파일 유형 | 팀 구성원 |
| 팀 이름 | 팀 사진 |
| 팀 설명 | 채널 설정 |
| 팀 가시성(공개 또는 비공개) | 커넥터 |
| 팀 설정(예: 멤버, 게스트, @ 언급) | 파일 및 내용 |
| Autofavorite 채널 | |
| 설치된 앱 | |
| 고정된 탭 | |

> [!NOTE]
> 지원되는 속성에 대한 최신 정보를 확인하여 향후 Microsoft Teams 서식 파일 기능을 추가할 예정입니다.

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>관리 센터에 미리 Teams 팀 템플릿

다음은 관리 센터에서 사용할 수 있는 미리 작성된 팀 Teams 있습니다. 미리 작성된 템플릿은 특정 산업에 대해 만든 템플릿입니다. 이러한 템플릿을 보시고 관리 센터의 왼쪽 Teams 팀 **템플릿으로** Teams  >  **으로 이동하세요.**

미리 작성된 템플릿을 복제할 수 있지만 편집할 수 없습니다. 미리 작성된 템플릿에서 속성을 변경하려면 기존 템플릿에서 새 템플릿을 만든 다음 원하는 속성을 추가하거나 제거할 수 있습니다. 일부 템플릿의 특정 속성을 변경할 수 없습니다.

| 서식 파일 유형 | TemplateId | 이 템플릿과 함께 제공되는 속성 |
| ------------------ | -------------- | ----------------------------------------------------- |
| Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  채널 <ul><li>일반</li> <li>공지 사항</li> <li>챔피언 코너</li> <li>팀 양식</li><li>일정</li></ul> 앱: <ul><li>Wiki</li>  <li>채널 일정</li> <li>중요 시점</li><li>게시판</li></ul>|
| 프로젝트 관리 |`com.microsoft.teams.template.ManageAProject`| 채널 <ul><li>일반</li> <li>공지 사항</li> <li>리소스</li> <li>계획</li></ul> 앱:<ul><li>Wiki</li><li>OneNote</li><li>작업</li><li>목록</li><li>Power Automate</li></ul> |
| 이벤트 관리|`com.microsoft.teams.template.ManageAnEvent` | 채널 <ul><li>일반</li> <li>공지 사항</li> <li>예산</li> <li>콘텐츠</li><li>물류</li> <li>계획</li> <li> 마케팅 및 PR</li></ul> 앱:<ul><li>Wiki</li><li>웹 사이트</li> <li>YouTube</li> <li>작업</li> <li>OneNote</li> <li>직원 아이디어</li> <li>문제 보고자</li><li>Power Automate</li><li>게시판</li><li>중요 시점</li></ul> |
|직원 온보드|`com.microsoft.teams.template.OnboardEmployees` | 채널 <ul><li>일반</li> <li>공지 사항</li> <li>직원 채팅</li> <li>교육</li></ul>앱:<ul><li>Wiki</li><li>커뮤니티</li><li>작업</li><li>직원 아이디어</li><li>Power Automate</li><li>게시판</li><li>중요 시점</li></ul>|
|지원 센터 구성| `com.microsoft.teams.template.OrganizeHelpDesk`|채널<ul><li>일반</li><li>공지 사항</li><li>FAQ</li></ul>앱:<ul><li>Wiki</li><li>OneNote</li><li>작업 </li><li>칭찬</li><li>문제 보고자</li><li>Power Automate</li><li>게시판</li></ul> |
| 환자 간호| `com.microsoft.teams.template.healthcareWard`| 채널<ul><li>일반</li><li>공지 사항</li><li>장애 요소</li><li>라운드</li><li>직원</li><li>교육</li></ul> 앱: <ul><li>Wiki</li><li>목록  </li><li>승인</li><li>게시판</li><li>검사</li></ul>|
| 위기 통신 |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| 채널 <ul><li>일반<li>공지 사항</li><li>세계 뉴스</li><li>내부 커미스</li><li>외부 커미스</li><li>승인 요청</li><li>고객 에스컬레이터</li><li>임원 업데이트</li><li>계획</li><li>물류</li></ul>앱: <ul><li>웹 사이트</li><li>작업</li><li>문제 보고자</li><li>승인</li><li>게시판</li><li>OneNote</li><li>Power Automate</li><li>SharePoint</li></ul>|
|은행 지점| `com.microsoft.teams.template.CollaborateWithinABankBranch`|채널 <ul><li>일반<li>공지 사항</li><li>장애 요소</li><li>고객 모임</li><li>승인 요청 </li><li>코칭</li><li>기술 개발</li><li>대출 처리</li><li>고객 불만 사항</li><li>쿠도스</li><li>재미있는 내용</li><li>규정 준수</li></ul>앱:<ul><li>칭찬 </li><li>문제 보고자</li><li>Wiki</li><li>일정</li><li>승인</li><li>게시판</li><li>아이디어</li></ul>|
|인시던트 응답| `com.microsoft.teams.template.CoordinateIncidentResponse`|채널 <ul><li>일반<li>공지 사항</li><li>물류</li><li>계획</li><li>복구</li><li>긴급</li></ul> 앱: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>작업</li> <li>승인</li> <li>검사</li> <li>Power Automate</li><li>게시판</li><li>중요 시점</li></ul>|
|병원| `com.microsoft.teams.template.healthcareHospital` |채널 <ul><li>일반</li><li>공지 사항</li><li>규정 준수</li><li>보호</li><li>인적 리소스</li><li>약국</li></ul> 앱: <ul><li>Wiki</li><li>목록</li><li>작업</li><li>승인</li><li>교대 근무</li><li>게시판</li><li>검사</li><li>아이디어</li></ul>|
|스토어 구성| `com.microsoft.teams.template.retailStore` |채널 <ul><li>일반<li>교대 근무 전달</li><li>매장 준비 상태</li><li>학습</li></ul> 앱: <ul><li>Wiki</li><li>작업</li><li>교대 근무</li><li>검사</li></ul>|
|관리자용 소매| `com.microsoft.teams.template.retailManagerCollaboration` |채널 <ul><li>일반<li>작업</li><li>학습</li></ul> 앱: <ul><li>Wiki</li><li>작업</li><li>검사</li></ul>|
|품질 및 안전 |`com.microsoft.teams.template.QualitySafety`|채널 <ul><li>일반<li>공지 사항</li><li>리더십</li><li>유지 관리</li><li>프로덕션 라인 1</li><li>프로덕션 라인 2</li><li>프로덕션 라인 3</li><li>보건 및 안전</li><li>교육</li><li>재미있는 내용</li></ul> 앱: <ul><li>Wiki</li><li>작업</li> <li>문제 보고자</li> <li>검사</li> </ul>|
|자원봉사자 관리| `com.microsoft.teams.template.ManageVolunteers` |채널 <ul><li>일반<li>공지 사항</li><li>보고</li><li>자원봉사자 관리</li><li>참여 기회</li><li>자원봉사자 온보더링</li></ul> 앱: <ul><li>웹 사이트</li><li>YouTube</li><li>Power BI</li><li>Power Apps</li><li>작업</li><li>SharePoint</li><li>OneNote</li></ul>|
||||

&sup1;앱이 탭으로 채널에 추가되었습니다.


### <a name="team-templates-by-category-and-industry"></a>범주 및 산업별 팀 템플릿

업계에서 미리 작성된 템플릿을 사용하는 방법에 대한 자세한 내용은 다음을 참조하세요.

- [재무 팀 템플릿](financial-teams-templates-in-the-admin-console.md)
- [일반 팀 템플릿](general-teams-templates-in-the-admin-console.md)
- [정부 팀 템플릿](government-teams-templates-in-the-admin-console.md)
- [의료 팀 템플릿](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [제조 팀 템플릿](manufacturing-teams-templates-in-the-admin-console.md)
- [비영리 팀 템플릿](team-templates-nonprofit.md)
- [소매 팀 템플릿](retail-teams-templates-in-the-admin-console.md)

## <a name="team-template-size-limits"></a>팀 템플릿 크기 제한

템플릿은 특정 수의 채널, 탭 및 앱으로 제한됩니다.

 > [!Note]
 > 템플릿에서 만든 후 팀에 더 많은 채널, 탭 및 앱을 추가할 수 있습니다.

|기능 | 제한|
|-|-|
|템플릿당 채널 | 15 |
|템플릿의 채널당 탭 | 20 |
|템플릿당 앱 | 50|
|||

자세한 내용은 의 제한 및 [사양을 Teams.](limits-specifications-teams.md)

## <a name="manage-team-templates"></a>팀 템플릿 관리

### <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 관리 센터에서 팀 템플릿 관리

#### <a name="view-team-templates"></a>팀 템플릿 보기

팀 템플릿을 보시고 관리 센터의 왼쪽 Teams 팀 **템플릿으로** Teams  >  **로 이동하세요.** 포함된 채널 및 앱을 포함하여 자세한 내용을 확인하려면 템플릿을 선택합니다.

#### <a name="create-your-own-team-templates"></a>사용자만의 팀 템플릿 만들기

처음부터 기존 팀 및 기존 템플릿에서 사용자 지정 템플릿을 만들 수 있습니다. 자세한 내용은 다음을 참조하세요.

- [사용자 지정 팀 템플릿 만들기](create-a-team-template.md)
- [기존 팀에서 템플릿 만들기](create-template-from-existing-team.md)
- [기존 팀 템플릿에서 팀 템플릿 만들기](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>팀 템플릿 정책 적용

사용자가 팀을 만들기 위해 Teams 서식 파일을 제어하기 위해 [템플릿](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)정책을 설정하고 조직의 사용자 및 그룹에 할당할 수 있습니다. 자세한 내용은 관리 센터의 팀 [템플릿 Teams 참조하세요.](templates-policies.md)

### <a name="manage-team-templates-using-powershell"></a>PowerShell을 사용하여 팀 템플릿 관리

다음 cmdlet을 사용하여 PowerShell에서 템플릿을 관리합니다.

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate?view=teams-ps)
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist?view=teams-ps)
- [New-CsTeamTemplate](/powershell/module/teams/new-csteamtemplate?view=teams-ps)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate?view=teams-ps)
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate?view=teams-ps)

## <a name="related-articles"></a>관련 기사

- [템플릿으로 팀 만들기](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Microsoft Graph를 사용하여 팀 템플릿 시작하기](get-started-with-teams-templates.md)
- [팀 복제](/graph/api/team-clone?view=graph-rest-1.0&tabs=http)
