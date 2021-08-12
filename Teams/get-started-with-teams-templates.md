---
title: Microsoft Graph
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: phlouie
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft에서 팀 템플릿을 Graph 다른 토픽에 대한 채널을 사용하여 공동 작업 공간을 만들고 콘텐츠 및 서비스를 제공하기 위해 앱을 미리 설치하는 방법에 대해 알아보겠습니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8bee4379eb82d577104d2d69ff2e11c168f2de62d3e903fcff196d45293c2365
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322560"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Microsoft Graph

> [!NOTE]
> 팀 템플릿은 현재 개인 채널 만들기를 지원하지 않습니다. 개인 채널 만들기는 템플릿 정의에 포함되지 않습니다.

팀 템플릿은 비즈니스 필요 또는 프로젝트를 중심으로 디자인된 팀 구조의 미리 작성된 정의입니다. 관리 콘솔에서 사용자만의 [템플릿을 만들 수 있습니다.](get-started-with-teams-templates-in-the-admin-console.md) Microsoft Graph 템플릿을 사용할 수 있습니다. 팀 템플릿을 사용하여 다양한 토픽에 대한 채널을 사용하여 풍부한 공동 작업 공간을 빠르게 만들고, 앱을 미리 설치하여 중요한 콘텐츠 및 서비스를 끌어오면 됩니다. 팀 템플릿은 조직 전체에서 일관된 팀을 쉽게 만들 수 있도록 미리 정의된 팀 구조를 제공합니다.

이 문서에서는 템플릿에서 정의할 수 있는 속성, 기본 템플릿 유형 및 몇 가지 샘플 요청을 사용하여 템플릿에서 팀을 만드는 방법을 설명합니다.

이 문서는 다음을 위한 것입니다.

- 조직 전체에서 여러 팀을 계획, 배포 및 관리하는 책임<br>
- 프로그래밍식으로 미리 정의된 채널 및 앱을 사용하여 팀을 만들고자 하는 개발자

## <a name="team-template-capabilities"></a>팀 템플릿 기능

팀의 대부분의 속성은 템플릿에 의해 포함 및 지원됩니다. 그러나 현재 지원되지 않는 몇 가지 속성 및 기능이 있습니다. 다음 표에서는 포함된 내용과 팀 템플릿에 포함되지 않은 내용에 대한 간소한 요약을 제공합니다.

| **팀 템플릿에서 지원하는 팀 속성** | **팀 템플릿에서 아직 지원되지 않는 팀 속성** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 기본 서식 파일 형식 | 팀 구성원 |
| 팀 이름 | 팀 사진 |
| 팀 설명 | 채널 설정 |
| 팀 가시성(공개 또는 비공개) | 커넥터 |
| 팀 설정(예: 멤버, 게스트, @ 언급) | 파일 및 내용 |
| 자동 즐겨찾기 채널 | |
| 설치된 앱 | |
| 고정된 탭 | |

> [!NOTE]
> 지원되는 속성에 대한 최신 정보를 확인하여 향후 Microsoft Teams 서식 파일 기능을 추가할 예정입니다.

## <a name="what-are-base-template-types"></a>기본 템플릿 형식은 무엇일지

기본 템플릿 형식은 Microsoft가 특정 산업에 대해 만든 특수 템플릿입니다. 이러한 기본 템플릿에는 저장소에서 사용할 수 없는 독점 앱이 포함되어 있는 경우가 종종 있습니다. 또한 기본 템플릿에는 팀 템플릿에서 개별적으로 지원되지 않는 팀 속성이 포함되어 있는 경우가 종종 있습니다. Microsoft에서 팀 템플릿을 사용하는 [방법을 Graph.](get-started-with-teams-templates.md)

기본 템플릿 형식이 정의된 후 지정할 추가 속성으로 이러한 특수 템플릿을 확장하거나 다시 정의할 수 있습니다. 일부 기본 템플릿 유형에는재정할 수 없는 속성이 포함되어 있습니다.

기본적으로 기본 템플릿은 추가 독점 앱 또는 특수 속성을 포함하지 않는 표준으로 설정됩니다. 다음은 사용 가능한 기본 템플릿 형식의 현재 목록입니다.

| 기본 서식 파일 형식 | baseTemplateId | 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 표준 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | 추가 앱 및 속성 없음 |
| 교육 -<br>수업 팀 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | 앱:<ul><li>OneNote 수업용 전자 필기장(일반 탭에 **고정)** </li><li>할당 앱(일반 탭에 **고정)**</li></ul> 팀 속성:<ul><li>Team 가시성을 **HiddenMembership으로** 설정(다시 설정할 수 없습니다)</li></ul> |
| 교육 -<br>직원 팀 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | 앱:<ul><li>OneNote 직원 전자 필기장(일반 탭에 **고정)**</li></ul> |
|교육 -<br>PLC 팀 |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | 앱:<ul><li>OneNote PLC 전자 필기장(일반 탭에 **고정)**</ul></li>|
| 소매 -<br>Microsoft Store | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('retailStore')` | 채널<ul><li>교대 근무 전달</li><li>학습</li></ul>팀 속성<ul><li>팀 표시 유형이 공개로 설정됨</li></ul>구성원 권한<ul><li>구성원이 채널을 만들거나 업데이트하거나 제거하지 못하게 합니다.</li><li>구성원이 앱을 추가하거나 제거하지 못하게 합니다.</li><li>구성원이 커넥터를 만들거나 업데이트하거나 제거하지 못하게 합니다.</li></ul> |
| 소매 -<br>관리자 공동 작업 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('retailManagerCollaboration')` | 채널<ul><li>학습</li><li>운영</li></ul>팀 속성:<ul><li>비공개로 설정된 팀 표시 유형</li></ul>멤버 권한:<ul><li>구성원이 채널을 만들거나 업데이트하거나 제거하지 못하게 합니다.</li><li>구성원이 앱을 추가하거나 제거하지 못하게 합니다.</li><li>구성원이 커넥터를 만들거나 업데이트하거나 제거하지 못하게 합니다.</li></ul>|
| 의료 -<br>와드 |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('healthcareWard')` |채널 <ul><li>공지 사항\*</li><li>장애 요소\*</li><li>라운드</li><li>직원\*</li><li>교육\*</li></ul>\*자동 즐겨찾기 채널 |
|의료 -<br>병원 | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('healthcareHospital')` |채널<ul><li>공지 사항\*</li><li>규정 준수\*</li><li>보호</li><li>인적 리소스</li></li><li>약국</li></ul>\*자동 즐겨찾기 채널|
|||


다음 템플릿을 사용하여 Microsoft Teams 클라이언트에서 팀을 Graph.


| 기본 서식 파일 형식 | baseTemplateId | 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
| ------------------ | -------------- | ----------------------------------------------------- |
| Office 365 |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  채널 <ul><li>일반</li> <li>공지 사항</li> <li>챔피언 코너</li> <li>팀 양식</li></ul> 앱: <ul><li>Wiki</li>  <li>일정</li> |
| 프로젝트 관리 |`com.microsoft.teams.template.`<br>`ManageAProject`| 채널 <ul><li>일반</li> <li>공지 사항</li> <li>리소스</li> <li>계획</li></ul> 앱:<ul><li>Wiki</li><li>OneNote</li></ul> |
| 이벤트 관리|`com.microsoft.teams.template.`<br>`ManageAnEvent` | 채널 <ul><li>일반</li> <li>공지 사항</li> <li>예산</li> <li>콘텐츠</li><li>물류</li> <li>계획</li> <li> 마케팅 및 PR</li></ul> 앱:<ul><li>Wiki</li><li>웹 사이트</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|직원 온보드|`com.microsoft.teams.template.`<br>`OnboardEmployees` | 채널 <ul><li>일반</li> <li>공지 사항</li> <li>직원 채팅</li> <li>교육</li></ul>앱:<ul><li>Wiki</li><li>커뮤니티</li></ul>|
|지원 센터 구성| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|채널<ul><li>일반</li><li>공지 사항</li><li>FAQ</li></ul>앱:<ul><li>Wiki</li><li>OneNote</li></ul> |
| 환자 관리 공동 작업| `healthcareWard `| 채널<ul><li>일반</li><li>공지 사항</li><li>장애 요소</li><li>라운드</li><li>직원</li><li>교육</li></ul> 앱: <ul><li>Wiki</li>|
| 글로벌 위기 또는 이벤트에 대한 공동 작업 |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| 채널 <ul><li>일반<li>공지 사항</li><li>세계 뉴스</li><li>비즈니스 연속성</li><li>원격 작업</li><li>내부 커미스</li><li>외부 커미스</li><li>고객 불만</li><li>Kudos</li><li>임원 업데이트</li></ul>앱: <ul><li>칭찬하기</li><li>Wiki</li><li>웹 사이트</li></ul>|
|은행 지점 내에서 공동 작업| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|채널 <ul><li>일반<li>공지 사항</li><li>장애 요소</li><li>고객 모임</li><li>코칭</li><li>기술 개발</li><li>대출 처리</li><li>고객 불만</li><li>Kudos</li><li>재미있는 물건</li><li>규정 준수</li></ul>|
|인시던트 응답 조정| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|채널 <ul><li>일반<li>공지 사항</li><li>물류</li><li>계획</li><li>복구</li><li>긴급</li></ul> 앱: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|병원| `healthcareHospita`l |채널 <ul><li>일반<li>공지 사항</li><li>규정 준수</li><li>보호</li><li>인적 리소스</li><li>약국</li></ul> 앱: <ul><li>Wiki</li></ul>|
|스토어 구성| `retailStore` |채널 <ul><li>일반<li>교대 근무 전달</li><li>학습</li></ul> 앱: <ul><li>Wiki</li></ul>|
|품질 및 안전 |`com.microsoft.teams.`<br>`template.QualitySafety`|채널 <ul><li>일반<li>공지 사항</li><li>1줄</li><li>2줄</li><li>3줄</li><li>안전</li><li>교육</li><li>유지 관리</li><li>재미있는 물건</li></ul> 앱: <ul><li>Wiki</li></ul>|
|소매 - 관리자 공동 작업| `retailManagerCollaboration` |채널 <ul><li>일반<li>작업</li><li>학습</li></ul> 앱: <ul><li>Wiki</li></ul>|
||||

자세한 [내용은](get-started-with-teams-templates-in-the-admin-console.md) 관리 센터에서 팀 템플릿 시작을 참조하세요.

## <a name="related-topics"></a>관련 항목

- [관리 콘솔에서 팀 템플릿 시작](get-started-with-teams-templates-in-the-admin-console.md)
- [팀 만들기(미리](/graph/api/team-post?view=graph-rest-beta) 보기)
- [New-Team](/powershell/module/teams/New-Team?view=teams-ps)
- [사용자에 대한 관리자 Microsoft Teams](itadmin-readiness.md)
