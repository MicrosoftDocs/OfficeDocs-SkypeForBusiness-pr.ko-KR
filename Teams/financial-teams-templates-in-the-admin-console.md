---
title: 관리 센터를 사용하여 재무 팀 템플릿 시작
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
description: 관리 센터를 사용하여 Teams 미리 정의된 설정, 채널 및 미리 설치된 앱을 제공하여 재무 요구에 따라 설계된 팀 구조를 만드는 방법에 대해 알아보습니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 749fa9a3a4264f5e4231082dcf097151377fff069bf5b123afa6b1abc5ba017b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349470"
---
# <a name="use-financial-team-templates-in-the-admin-center"></a>관리 센터에서 재무 팀 템플릿 사용

팀 템플릿을 사용하면 설정, 채널 및 미리 설치된 앱의 미리 정의된 템플릿을 제공하여 빠르고 쉽게 팀을 만들 수 있습니다.

팀 템플릿에는 재정적 요구 사항을 중심으로 설계된 팀 구조에 대한 미리 작성된 정의가 있습니다. 팀 템플릿을 확장하여 특정 조직 요구에 맞게 팀을 만들 수도 있습니다.

이 문서에서는 각 팀 템플릿을 소개하고 이를 사용하는 방법을 권장합니다.

이 문서는 재무 조직 전반에 걸쳐 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우를 위한 것입니다. 귀사는 이미 Teams 서비스를 구축했습니다. Teams를 아직 배포하지 않은 경우 먼저 [Microsoft Teams를 배포하는 방법](./deploy-overview.md)을 읽어보세요.

일반적으로 팀 템플릿에 대한 자세한 내용은 팀 템플릿 시작 을 [참조합니다.](get-started-with-teams-templates-in-the-admin-console.md)

## <a name="global-crisis-or-event"></a>글로벌 위기 또는 이벤트

비즈니스 단위에서 위기 팀에 대한 공동 작업을 중앙 집중화하고 비즈니스 연속성 계획을 만들고, 원격 작업 팁을 공유하고, 고객 통신을 추적하고, 공지 및 뉴스를 사용하여 모든 사람을 루프에 유지할 수 있습니다.

| 기본 서식 파일 형식|baseTemplateId | 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
| ------------------|-- |----------------------------------------------------- |
| 글로벌 위기 또는 이벤트에 대한 공동 작업|`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |채널 <ul><li>일반<li>공지 사항</li><li>세계 뉴스</li><li>비즈니스 연속성</li><li>원격 작업</li><li>내부 커미스</li><li>외부 커미스</li><li>승인 요청</li><li>고객 불만</li><li>Kudos</li><li>임원 업데이트</li></ul>앱: <ul><li>칭찬하기</li><li>Wiki</li><li>웹 사이트</li><li>Planner</li></ul>|
||||

## <a name="collaborate-within-a-bank-branch"></a>은행 지점 내에서 공동 작업

Huddles, 고객 모임, 모기지 공동 작업과 같은 비즈니스 프로세스에서 은행 지점 직원에 대한 공동 작업을 중앙 집중화하고 공지사항 및 Kudos를 사용하여 모든 사람을 루프에 유지합니다.

| 기본 서식 파일 형식 |baseTemplateId| 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
| ------------------ |--|----------------------------------------------------- |
|은행 지점 내에서 공동 작업|`com.microsoft.teams.template.CollaborateWithinABankBranch` |채널 <ul><li>일반<li>공지 사항</li><li>장애 요소</li><li>고객 모임</li><li>승인 요청</li><li>코칭</li><li>기술 개발</li><li>대출 처리</li><li>고객 불만</li><li>Kudos</li><li>재미있는 물건</li><li>규정 준수</li></ul>앱:<ul><li>칭찬하기</li></ul>|
||||