---
title: Microsoft Graph를 사용 하 여 팀 서식 파일 시작
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
description: Microsoft Graph에서 팀 서식 파일을 사용 하 여 여러 주제에 대 한 채널과 함께 공동 작업 공간을 만들고 콘텐츠 및 서비스를 제공 하는 앱을 사전 설치 하는 방법을 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 484b3ac3fd3545ce306dcb6e3d833bb523df5a86
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772199"
---
# <a name="get-started-with-teams-templates-using-microsoft-graph"></a>Microsoft Graph를 사용 하 여 팀 서식 파일 시작

> [!NOTE]
> 팀 템플릿은 현재 개인 채널 만들기를 지원 하지 않습니다. 개인 채널 만들기는 서식 파일 정의에 포함 되지 않습니다.

팀 템플릿은 비즈니스 요구 또는 프로젝트를 기준으로 설계 된 팀의 구조에 대 한 미리 작성 된 정의입니다. [관리 콘솔에서 고유한 서식 파일을 만들](get-started-with-teams-templates-in-the-admin-console.md)수 있습니다. Microsoft Graph에서는 미리 작성 된 서식 파일을 사용 합니다. 팀 서식 파일을 사용 하 여 다양 한 주제 및 사전 설치 앱에 대 한 채널을 사용 하 여 업무에 중요 한 콘텐츠 및 서비스에 대 한 공동 작업 공간을 빠르게 만들 수 있습니다. 팀 서식 파일은 조직에서 일관 된 팀을 쉽게 만들 수 있도록 미리 정의 된 팀 구조를 제공 합니다.

이 문서에서는 템플릿에서 정의할 수 있는 속성, 기본 템플릿 형식, 몇 가지 샘플 요청을 사용 하 여 템플릿에서 팀을 만드는 방법에 대해 설명 합니다.

이 문서는 다음과 같은 경우에 적합 합니다.

- 조직에서 여러 팀을 계획, 배포 및 관리 하는 책임이 있습니다.<br>
- 미리 정의 된 채널 및 앱을 사용 하 여 프로그래밍 방식으로 팀을 만드는 개발자

## <a name="teams-template-capabilities"></a>팀 템플릿 기능

팀의 대부분의 속성은 서식 파일에 포함 되 고 지원 됩니다. 그러나 현재 지원 되지 않는 몇 가지 속성과 기능이 있습니다. 다음 표에서는 포함 된 항목과 팀 템플릿에 포함 되지 않은 항목에 대 한 간략 한 요약을 제공 합니다.

| **팀 템플릿에서 지원 되는 팀 속성** | **팀 템플릿에서 아직 지원 되지 않는 팀 속성** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 기본 서식 파일 형식 | 팀 구성원 |
| 팀 이름 | 팀 사진 |
| 팀 설명 | 채널 설정 |
| 팀 표시 유형 (공개 또는 비공개) | 기가 |
| 팀 설정 (예: 회원, 게스트, @ 멘 션) | 파일 및 내용 |
| 자동 즐겨찾기 채널 | |
| 설치 된 앱 | |
| 고정 된 탭 | |

> [!NOTE]
> Microsoft 팀의 향후 릴리스에서 서식 파일 기능을 추가 하면 지원 되는 속성에 대 한 최신 정보를 다시 확인 하세요.

## <a name="what-are-base-template-types"></a>기본 서식 파일 형식

기본 서식 파일 형식은 Microsoft에서 특정 산업에 대해 만든 특수 서식 파일입니다. 이러한 기본 서식 파일에는 주로 스토어에서 사용할 수 없는 독점 앱이 포함 되어 있습니다. 또한 기본 템플릿에는 아직 팀 템플릿에서 개별적으로 지원 되지 않는 팀 속성이 포함 되는 경우가 많습니다. [Microsoft Graph에서 팀 서식 파일](get-started-with-teams-templates.md)을 사용 하는 방법에 대해 알아봅니다.

기본 서식 파일 형식을 정의한 후에는 지정 하려는 추가 속성을 사용 하 여 이러한 특수 템플릿을 확장 하거나 재정의할 수 있습니다. 일부 기본 서식 파일 형식에 재정의할 수 없는 속성이 포함 되어 있습니다.

기본적으로 기본 서식 파일은 **표준** 으로 설정 되어 있으며, 여기에는 추가 독점 앱 또는 특수 속성이 포함 되지 않습니다. 다음은 사용 가능한 기본 서식 파일 형식의 현재 목록입니다.

| 기본 서식 파일 형식 | baseTemplateId | 이 기본 서식 파일에 포함 된 속성 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 표준이 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | 추가 앱 및 속성 없음 |
| Education<br>수업 팀 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | 들<ul><li>OneNote 수업용 전자 필기장 ( **일반** 탭에 고정) </li><li>할당 앱 ( **일반** 탭에 고정 됨)</li></ul> 팀 속성:<ul><li>팀 가시성을 **HiddenMembership** 로 설정 (재정의할 수 없음)</li></ul> |
| Education<br>교직원 팀 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | 들<ul><li>OneNote 교직원 용 전자 필기장 ( **일반** 탭에 고정)</li></ul> |
|Education<br>PLC 팀 |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | 들<ul><li>OneNote PLC 전자 필기장 ( **일반** 탭에 고정)</ul></li>|
| Retail<br>스토어 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | 채널<ul><li>교대 이송</li><li>배웁니다</li></ul>팀 속성<ul><li>팀 가시성을 공개로 설정</li></ul>회원 사용 권한<ul><li>구성원이 채널을 만들거나 업데이트 하거나 제거 하지 못하도록 방지</li><li>구성원이 앱을 추가 하거나 제거 하지 못하도록 방지</li><li>구성원이 커넥터를 만들거나 업데이트 하거나 제거 하지 못하도록 방지</li></ul> |
| Retail<br>관리자 공동 작업 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | 채널<ul><li>배웁니다</li><li>운영</li></ul>팀 속성:<ul><li>팀 표시 유형을 비공개로 설정</li></ul>회원 권한:<ul><li>구성원이 채널을 만들거나 업데이트 하거나 제거 하지 못하도록 방지</li><li>구성원이 앱을 추가 하거나 제거 하지 못하도록 방지</li><li>구성원이 커넥터를 만들거나 업데이트 하거나 제거 하지 못하도록 방지</li></ul>|
| 의료<br>I |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |채널 <ul><li>알림에서\*</li><li>Huddles\*</li><li>소수</li><li>자원\*</li><li>교육\*</li></ul>\*자동 즐겨찾기에 채널 |
|의료<br>병원 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |채널<ul><li>알림에서\*</li><li>규정 준수\*</li><li>Custodial</li><li>인적 자원</li></li><li>Pharmacy</li></ul>\*자동 즐겨찾기에 채널|
|||


팀 클라이언트와 Microsoft Graph 모두에서 팀을 만들려면 다음 서식 파일을 사용 합니다.


| 기본 서식 파일 형식 | baseTemplateId | 이 기본 서식 파일에 포함 된 속성 |
| ------------------ | -------------- | ----------------------------------------------------- |
| Office 365 도입 |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  채널 <ul><li>일반</li> <li>알림에서</li> <li>챔피언 모서리</li> <li>팀 양식</li></ul> 들 <ul><li>키</li>  <li>일정</li> |
| 프로젝트 관리 |`com.microsoft.teams.template.`<br>`ManageAProject`| 채널 <ul><li>일반</li> <li>알림에서</li> <li>리소스도</li> <li>계획</li></ul> 들<ul><li>키</li><li>만들어졌으므로</li></ul> |
| 이벤트 관리|`com.microsoft.teams.template.`<br>`ManageAnEvent` | 채널 <ul><li>일반</li> <li>알림에서</li> <li>예산</li> <li>콘텐트가</li><li>물류</li> <li>계획</li> <li> 마케팅 및 홍보</li></ul> 들<ul><li>키</li><li>웹 사이트</li> <li>YouTube</li> <li>Planner</li> <li>만들어졌으므로</li></ul> |
|내장 직원|`com.microsoft.teams.template.`<br>`OnboardEmployees` | 채널 <ul><li>일반</li> <li>알림에서</li> <li>직원 채팅</li> <li>교육</li></ul>들<ul><li>키</li><li>커뮤니티</li></ul>|
|지원 센터 구성| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|채널<ul><li>일반</li><li>알림에서</li><li>FAQ</li></ul>들<ul><li>키</li><li>만들어졌으므로</li></ul> |
| 환자 관리에 대 한 공동 작업| `healthcareWard `| 채널<ul><li>일반</li><li>알림에서</li><li>Huddles</li><li>소수</li><li>자원</li><li>교육</li></ul> 들 <ul><li>키</li>|
| 전역 위기 또는 이벤트에 대 한 공동 작업 |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| 채널 <ul><li>일반<li>알림에서</li><li>월드 뉴스</li><li>비즈니스 연속성</li><li>원격 작업</li><li>내부 주석 s</li><li>외부 대화 s</li><li>고객 불만</li><li>보너스</li><li>임원 업데이트</li></ul>들 <ul><li>칭찬</li><li>키</li><li>웹 사이트</li></ul>|
|은행 지사 내에서 공동 작업| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|채널 <ul><li>일반<li>알림에서</li><li>Huddles</li><li>고객 모임</li><li>코칭</li><li>기술 개발</li><li>대출 처리</li><li>고객 불만</li><li>보너스</li><li>재미 있는 내용</li><li>규정 준수</li></ul>|
|조정 사고 대응| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|채널 <ul><li>일반<li>알림에서</li><li>물류</li><li>계획</li><li>복구</li><li>받기</li></ul> 들 <ul><li>키</li><li>0:excel}</li><li>만들어졌으므로</li><li>SharePoint</li><li>Planner</li></ul>|
|병원| `healthcareHospita`l-p |채널 <ul><li>일반<li>알림에서</li><li>규정 준수</li><li>Custodial</li><li>인적 자원</li><li>Pharmacy</li></ul> 들 <ul><li>키</li></ul>|
|스토어 구성| `retailStore` |채널 <ul><li>일반<li>교대 이송</li><li>배웁니다</li></ul> 들 <ul><li>키</li></ul>|
|품질 및 안전 |`com.microsoft.teams.`<br>`template.QualitySafety`|채널 <ul><li>일반<li>알림에서</li><li>줄 1</li><li>선 2</li><li>선 3</li><li>안전</li><li>교육</li><li>관리할</li><li>재미 있는 내용</li></ul> 들 <ul><li>키</li></ul>|
|소매 관리자 공동 작업| `retailManagerCollaboration` |채널 <ul><li>일반<li>운영</li><li>배웁니다</li></ul> 들 <ul><li>키</li></ul>|
||||

자세한 내용은 [관리 센터에서 팀 템플릿 시작](get-started-with-teams-templates-in-the-admin-console.md) 을 참조 하세요.

## <a name="related-topics"></a>관련 항목

- [관리 콘솔에서 팀 서식 파일 시작](get-started-with-teams-templates-in-the-admin-console.md)
- [팀 만들기](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (미리 보기)
- [신규-팀](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Microsoft 팀의 관리 교육](itadmin-readiness.md)