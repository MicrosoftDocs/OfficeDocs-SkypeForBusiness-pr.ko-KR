---
title: 관리 콘솔에서 일반 팀 서식 파일 사용
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
description: 관리 콘솔을 사용 하 여 미리 정의 된 설정, 채널 및 사전 설치 앱을 제공 하 여 일반 팀 서식 파일을 사용 하 여 팀 구조를 만드는 방법을 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 39debd0b184109a55686977f27ba1262d5d65641
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216699"
---
# <a name="use-general-teams-templates-in-the-admin-console"></a>관리 콘솔에서 일반 팀 서식 파일 사용

[!INCLUDE [template](includes/preview-feature.md)]

팀 서식 파일을 사용 하면 미리 정의 된 서식 파일 (설정, 채널 및 사전 설치 된 앱)을 제공 하 여 빠르고 쉽게 팀을 만들 수 있습니다.

팀 템플릿에는 재무 요구에 따라 디자인 된 팀 구조 정의가 미리 작성 되어 있습니다. 팀 템플릿을 확장 하 여 특정 조직의 요구 사항에 맞게 조정 된 팀을 만들 수도 있습니다.

이 문서에서는 각 팀 서식 파일과이를 사용 하는 방법을 소개 합니다.

이 문서에서는 재무 조직에서 여러 팀을 계획, 배포 및 관리 하는 책임이 있습니다. 조직에 이미 팀 서비스를 배포 했다고 가정 합니다. 아직 팀을 롤아웃하기 않은 경우 먼저 [Microsoft 팀을 배포 하는 방법을](How-to-roll-out-teams.md)읽어 보세요.

일반적으로 팀 서식 파일에 대 한 자세한 내용은 [팀 서식 파일 시작](get-started-with-teams-templates-in-the-admin-console.md)을 참조 하세요.

## <a name="global-crisis-or-event"></a>전역 위기 또는 이벤트

비즈니스 단위에서 위기 팀을 위한 공동 작업을 수행 하 고, 비즈니스 연속성 계획을 만들고, 원격 작업 팁을 공유 하 고, 고객 통신을 추적 하 고, 모든 사용자에 게 공지 사항 및 뉴스를 유지 하는 데

| 기본 서식 파일 형식 |baseTemplateId | 이 기본 서식 파일에 포함 된 속성 |
| ------------------ |--|----------------------------------------------------- |
| 전역 위기 또는 이벤트에 대 한 공동 작업 |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |채널 <ul><li>일반<li>알림에서</li><li>월드 뉴스</li><li>비즈니스 연속성</li><li>원격 작업</li><li>내부 주석 s</li><li>외부 대화 s</li><li>고객 불만</li><li>보너스</li><li>임원 업데이트</li></ul>들 <ul><li>칭찬</li><li>키</li><li>웹 사이트</li></ul>|
||||

## <a name="adopt-office-365"></a>Office 365 도입

챔피언 커뮤니티 출시를 전파 하 고 새로운 기술로 동료를 지원 해 보세요.

| 기본 서식 파일 형식 |baseTemplateId | 이 기본 서식 파일에 포함 된 속성 |
| ------------------|-- |----------------------------------------------------- |
| Office 365 도입 | `com.microsoft.teams.template.AdoptOffice365` |  채널 <ul><li>일반</li> <li>알림에서</li> <li>챔피언 모서리</li> <li>팀 양식</li></ul> 들 <ul><li>키</li>  <li>일정</li> |li><li>기술 개발</li><li>대출 처리</li><li>고객 불만</li><li>보너스</li><li>재미 있는 내용</li><li>규정 준수</li></ul>|
||||

## <a name="manage-a-project"></a>프로젝트 관리

일반 프로젝트 관리를 위해이 서식 파일을 사용 하 여 작업 관리, 문서 공유, 프로젝트 모임 수행, 위험 및 의사 결정 문서화

| 기본 서식 파일 형식| baseTemplateId | 이 기본 서식 파일에 포함 된 속성 |
| ------------------|-- |----------------------------------------------------- |
| 프로젝트 관리| ManageAProject (c)  | 채널 <ul><li>일반</li> <li>알림에서</li> <li>리소스도</li> <li>계획</li></ul> 들<ul><li>키</li><li>만들어졌으므로</li></ul> |
||||

## <a name="manage-an-event"></a>이벤트 관리

멋진 이벤트를 제공 하는 데 필요한 모든 작업을 관리 하 고, 문서 및 공동 작업을 수행 합니다. 회사 내부와 외부에서 안전한 공동 작업을 할 수 있도록 게스트 사용자를 초대 합니다.

앱 사용 권한 정책에 따라 특정 앱에 대 한 액세스 권한이 없을 수 있습니다.

| 기본 서식 파일 형식 | baseTemplateId| 이 기본 서식 파일에 포함 된 속성 |
| ------------------ |--|----------------------------------------------------- |
| 이벤트 관리| `com.microsoft.teams.template.ManageAnEvent` | 채널 <ul><li>일반</li> <li>알림에서</li> <li>예산</li> <li>콘텐트가</li><li>물류</li> <li>계획</li> <li> 마케팅 및 홍보</li></ul> 들<ul><li>키</li><li>웹 사이트</li> <li>YouTube</li> <li>Planner</li> <li>만들어졌으므로</li></ul> |
||||

## <a name="onboard-employees"></a>내장 직원

리소스, 질문, 약간의 재미를 위해이 중앙 팀을 통해 사용자의 문화를 개선 하 고 직원의 온 보 딩을 간소화 하세요.

| 기본 서식 파일 형식 |baseTemplateId | 이 기본 서식 파일에 포함 된 속성 |
| ------------------|- |----------------------------------------------------- |
|내장 직원|`com.microsoft.teams.template.OnboardEmployees`  | 채널 <ul><li>일반</li> <li>알림에서</li> <li>직원 채팅</li> <li>교육</li></ul>들<ul><li>키</li><li>커뮤니티</li></ul>|
||||

## <a name="organize-a-help-desk"></a>지원 센터 구성

헬프데스크를 지 원하는 문서, 정책 및 프로세스를 공동으로 작업 합니다. 기존 티켓 시스템을 통합 하거나 서식 파일을 사용 하 여 요청을 관리 합니다.

| 기본 서식 파일 형식 | | 이 기본 서식 파일에 포함 된 속성 |
| ------------------|-- |----------------------------------------------------- |
|지원 센터 구성|`com.microsoft.teams.template.OrganizeHelpDesk`| 채널<ul><li>일반</li><li>알림에서</li><li>FAQ</li></ul>들<ul><li>키</li><li>만들어졌으므로</li></ul> |
||||
