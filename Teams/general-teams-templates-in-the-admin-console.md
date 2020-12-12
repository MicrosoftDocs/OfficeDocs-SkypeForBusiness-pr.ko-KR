---
title: 관리 센터에서 일반 Teams 서식 파일 사용
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 관리 센터를 사용하여 미리 정의한 설정, 채널 및 미리 설치된 앱을 제공하여 일반 Teams 템플릿을 사용하여 팀 구조를 만드는 방법을 배워보아야 합니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: caef10a4e9b659ce18e05df65bf2a441248ec493
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662073"
---
# <a name="use-general-teams-templates-in-the-admin-center"></a>관리 센터에서 일반 Teams 서식 파일 사용

Teams 서식 파일을 사용하면 설정, 채널 및 미리 설치된 앱의 미리 정의된 서식 파일을 제공하여 빠르고 쉽게 팀을 만들 수 있습니다.

Teams 템플릿에는 재무 요구 사항을 중심으로 설계된 팀 구조에 대한 미리 작성된 정의가 있습니다. Teams 서식 파일을 확장하여 특정 조직 요구에 맞는 팀을 만들 수도 있습니다.

이 문서에서는 각 Teams 서식 파일을 소개하고 이를 사용하는 방법을 권장합니다.

이 문서는 재무 조직에서 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우를 위한 것입니다. 조직에 Teams 서비스를 이미 배포했습니다. Teams를 롤아웃하지 않은 경우 먼저 Microsoft Teams를 롤아웃하는 [방법을 읽어 읽습니다.](How-to-roll-out-teams.md)

일반적으로 팀 서식 파일에 대한 자세한 내용은 Teams 서식 파일 [시작을 참조합니다.](get-started-with-teams-templates-in-the-admin-console.md)

## <a name="global-crisis-or-event"></a>글로벌 위기 또는 이벤트

사업부 전반에 걸쳐 위기 팀에 대한 공동 작업을 중앙 집중화하고 비즈니스 연속성 계획을 만들고, 원격 작업 팁을 공유하고, 고객 통신을 추적하고, 공지와 뉴스를 통해 모든 사람을 계속 진행할 수 있습니다.

| 기본 템플릿 형식 |baseTemplateId| 이 기본 템플릿과 함께 사용할 속성 |
| ------------------ |--|----------------------------------------------------------|
| 글로벌 위기 또는 이벤트에 대한 공동 작업 |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |채널: <ul><li>일반<li>공지</li><li>세계 뉴스</li><li>비즈니스 연속성</li><li>외부 커미스</li><li>승인 요청</li><li>원격 작업</li><li>내부 COMM</li><li>외부 커미스</li><li>고객 불만</li><li>Kudos</li><li>경영진 업데이트</li></ul>앱: <ul><li>칭찬</li><li>Wiki</li><li>웹 사이트</li><li>Planner</li></ul>|
||||

## <a name="adopt-office-365"></a>Office 365 채택

동료를 새로운 기술로 전도하고 지원하여 챔피언 커뮤니티 롤아웃을 빌드하고, 성장하고, 유지하세요.

| 기본 템플릿 형식 |baseTemplateId| 이 기본 템플릿과 함께 사용할 속성 |
| ------------------|--|-----------------------------------------------------------|
| Office 365 채택 | `com.microsoft.teams.template.AdoptOffice365` |  채널: <ul><li>일반</li> <li>공지</li> <li>챔피언 코너</li> <li>팀 양식</li></ul> 앱: <ul><li>Wiki</li>  <li>일정</li><li>기술 개발</li><li>대출 처리</li><li>고객 불만</li><li>Kudos</li><li>재미있는 것</li><li>규정 준수</li></ul>|
||||

## <a name="manage-a-project"></a>프로젝트 관리

일반적인 프로젝트 관리를 위해 이 서식 파일을 사용하여 작업을 관리하고, 문서를 공유하고, 프로젝트 모임을 수행하고, 위험 및 결정을 문서화합니다.

| 기본 템플릿 형식| baseTemplateId| 이 기본 템플릿과 함께 사용할 속성 |
| ------------------|--|-----------------------------------------------------------|
| 프로젝트 관리| `com.microsoft.teams.template.ManageAProject`  | 채널: <ul><li>일반</li> <li>공지</li> <li>리소스</li> <li>계획</li></ul> 앱:<ul><li>Wiki</li><li>OneNote</li><li>Planner</li><li>목록</li> </ul> |
||||

## <a name="manage-an-event"></a>이벤트 관리

작업을 관리하고, 문서를 관리하고, 뛰어난 이벤트를 제공하는 데 필요한 모든 작업을 공동 작업합니다. 게스트 사용자를 회사 내부 및 외부에서 안전하게 공동 작업할 수 있도록 초대합니다.

앱 사용 권한 정책에 따라 특정 앱에 액세스할 수 없습니다.

| 기본 템플릿 형식 | baseTemplateId| 이 기본 템플릿과 함께 사용할 속성 |
| ------------------ |--|-----------------------------------------------------------|
| 이벤트 관리| `com.microsoft.teams.template.ManageAnEvent` | 채널: <ul><li>일반</li> <li>공지</li> <li>예산</li> <li>콘텐츠</li><li>물류</li> <li>계획</li> <li> 마케팅 및 PR</li></ul> 앱:<ul><li>Wiki</li><li>웹 사이트</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
||||

## <a name="onboard-employees"></a>직원 온보드

리소스, 질문 및 재미를 위해 이 중앙 팀과 함께 문화를 개선하고 직원 온보드를 간소화합니다.

| 기본 템플릿 형식 |baseTemplateId| 이 기본 템플릿과 함께 사용할 속성 |
| ------------------|--|-----------------------------------------------------------|
|직원 온보드|`com.microsoft.teams.template.OnboardEmployees`  | 채널: <ul><li>일반</li> <li>공지</li> <li>직원 채팅</li> <li>교육</li></ul>앱:<ul><li>Wiki</li><li>커뮤니티</li><li>Planner</li></ul>|
||||

## <a name="organize-a-help-desk"></a>지원 센터 구성

기술 지원 팀을 지원하는 설명서, 정책 및 프로세스에 대해 공동 작업합니다. 기존 티켓 시스템을 통합하거나 템플릿을 사용하여 요청을 관리합니다.

| 기본 템플릿 형식 |baseTemplateId| 이 기본 템플릿과 함께 사용할 속성 |
| ------------------|--|------------------------------------------------------------|
|지원 센터 구성|`com.microsoft.teams.template.OrganizeHelpDesk`| 채널:<ul><li>일반</li><li>공지</li><li>FAQ</li></ul>앱:<ul><li>Wiki</li><li>OneNote</li><li>Planner </li><li>칭찬 </li></ul> |
||||
