---
title: 관리 센터에서 일반 팀 템플릿 사용
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
description: 관리 센터를 사용하여 미리 정의된 설정, 채널 및 미리 설치된 앱을 제공하여 일반 팀 템플릿을 사용하여 팀 구조를 만드는 방법에 대해 알아보습니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c68e3efd00e0f9204f507b4c63977837076bb3beb75a958a0629f1e5da64f69e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344031"
---
# <a name="use-general-team-templates-in-the-admin-center"></a>관리 센터에서 일반 팀 템플릿 사용

팀 템플릿을 사용하면 설정, 채널 및 미리 설치된 앱의 미리 정의된 템플릿을 제공하여 빠르고 쉽게 팀을 만들 수 있습니다.

팀 템플릿에는 재정적 요구 사항을 중심으로 설계된 팀 구조에 대한 미리 작성된 정의가 있습니다. 팀 템플릿을 확장하여 특정 조직 요구에 맞게 팀을 만들 수도 있습니다.

이 문서에서는 각 팀 템플릿을 소개하고 이를 사용하는 방법을 권장합니다.

이 문서는 조직 전체에서 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우를 위한 것입니다. 귀사는 이미 Teams 서비스를 구축했습니다. 롤아웃하지 않은 Teams 을 롤아웃하는 방법을 [Microsoft Teams.](./deploy-overview.md)

일반적으로 팀 템플릿에 대한 자세한 내용은 팀 템플릿 시작 을 [참조합니다.](get-started-with-teams-templates-in-the-admin-console.md)

## <a name="global-crisis-or-event"></a>글로벌 위기 또는 이벤트

비즈니스 단위에서 위기 팀에 대한 공동 작업을 중앙 집중화하고 비즈니스 연속성 계획을 만들고, 원격 작업 팁을 공유하고, 고객 통신을 추적하고, 공지 및 뉴스를 사용하여 모든 사람을 루프에 유지할 수 있습니다.

> [!div class="mx-tdBreakAll"]
> | 기본 서식 파일 형식 |baseTemplateId| 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
> | ------------------ |--|----------------------------------------------------------|
> | 글로벌 위기 또는 이벤트에 대한 공동 작업 |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` | 채널 <ul><li>일반<li>공지 사항</li><li>세계 뉴스</li><li>비즈니스 연속성</li><li>외부 커미스</li><li>승인 요청</li><li>원격 작업</li><li>내부 커미스</li><li>외부 커미스</li><li>고객 불만</li><li>Kudos</li><li>임원 업데이트</li></ul>앱: <ul><li>칭찬하기</li><li>Wiki</li><li>웹 사이트</li><li>Planner</li></ul>|
> ||||

## <a name="adopt-office-365"></a>Office 365

동료를 새로운 기술로 전도하고 지원하여 챔피언 커뮤니티 롤아웃을 빌드, 성장 및 유지해 돕습니다.

> [!div class="mx-tdBreakAll"]
> | 기본 서식 파일 형식 |baseTemplateId| 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
> | ------------------|--|-----------------------------------------------------------|
> | Office 365 | `com.microsoft.teams.template.AdoptOffice365` | 채널 <ul><li>일반</li> <li>공지 사항</li> <li>챔피언 코너</li> <li>팀 양식</li></ul> 앱: <ul><li>Wiki</li>  <li>일정</li><li>기술 개발</li><li>대출 처리</li><li>고객 불만</li><li>Kudos</li><li>재미있는 물건</li><li>규정 준수</li></ul>|
> ||||

## <a name="manage-a-project"></a>프로젝트 관리

일반 프로젝트 관리를 위해 이 템플릿을 사용하여 작업을 관리하고, 문서를 공유하고, 프로젝트 모임을 수행하고, 위험 및 결정을 문서화합니다.

> [!div class="mx-tdBreakAll"]
> | 기본 서식 파일 형식| baseTemplateId| 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
> | ------------------|--|-----------------------------------------------------------|
> | 프로젝트 관리| `com.microsoft.teams.template.ManageAProject`  | 채널 <ul><li>일반</li> <li>공지 사항</li> <li>리소스</li> <li>계획</li></ul> 앱:<ul><li>Wiki</li><li>OneNote</li><li>Planner</li><li>목록</li> </ul> |
> ||||

## <a name="manage-an-event"></a>이벤트 관리

뛰어난 이벤트를 제공하는 데 필요한 모든 작업에 대해 작업, 문서 및 공동 작업을 관리합니다. 게스트 사용자를 회사 안팎에서 안전하게 공동 작업할 수 있도록 초대합니다.

앱 사용 권한 정책에 따라 특정 앱에 액세스할 수 없습니다.

> [!div class="mx-tdBreakAll"]
> | 기본 서식 파일 형식 | baseTemplateId| 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
> | ------------------ |--|-----------------------------------------------------------|
> | 이벤트 관리| `com.microsoft.teams.template.ManageAnEvent` | 채널 <ul><li>일반</li> <li>공지 사항</li> <li>예산</li> <li>콘텐츠</li><li>물류</li> <li>계획</li> <li> 마케팅 및 PR</li></ul> 앱:<ul><li>Wiki</li><li>웹 사이트</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
> ||||

## <a name="onboard-employees"></a>직원 온보드

리소스, 질문 및 약간의 재미를 위해 이 중앙 팀을 통해 문화를 개선하고 직원 온보드를 간소화합니다.

> [!div class="mx-tdBreakAll"]
> | 기본 서식 파일 형식 |baseTemplateId| 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
> | ------------------|--|-----------------------------------------------------------|
> | 직원 온보드|`com.microsoft.teams.template.OnboardEmployees`  | 채널 <ul><li>일반</li> <li>공지 사항</li> <li>직원 채팅</li> <li>교육</li></ul>앱:<ul><li>Wiki</li><li>커뮤니티</li><li>Planner</li></ul>|
> ||||

## <a name="organize-a-help-desk"></a>지원 센터 구성

도움말 데스크를 지원하는 설명서, 정책 및 프로세스에 대해 공동 작업합니다. 기존 발권 시스템을 통합하거나 템플릿을 사용하여 요청을 관리합니다.

> [!div class="mx-tdBreakAll"]
> | 기본 서식 파일 형식 |baseTemplateId| 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
> | ------------------|--|------------------------------------------------------------|
> | 지원 센터 구성|`com.microsoft.teams.template.OrganizeHelpDesk`| 채널 <ul><li>일반</li><li>공지 사항</li><li>FAQ</li></ul>앱:<ul><li>Wiki</li><li>OneNote</li><li>Planner </li><li>칭찬하기 </li></ul> |
> ||||
