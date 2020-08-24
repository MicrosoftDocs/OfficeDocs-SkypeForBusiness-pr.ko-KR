---
title: Teams 서식 파일을 사용하여 새 팀 만들기
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: aaglick
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Teams 서식 파일을 사용하여 미리 설치된 서식 파일을 사용하여 여러 항목에 대한 채널이 있는 공동 작업 공간을 만드는 방법을 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 5a43a34ac130f4b5b168d46fa2a69476c42abd7b
ms.sourcegitcommit: cd16ff6007e0a798493e2fa469c6681993380420
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860799"
---
# <a name="get-started-with-teams-templates-in-the-teams-admin-console"></a>Teams 관리 본체에서 Teams 서식 파일 시작

[!INCLUDE [template](includes/preview-feature.md)]

**사용자 지정 서식 파일은 교육 고객에게 아직 지원되지 않습니다.**

> [!NOTE]
> Teams 서식 파일은 현재 비공개 채널 만들기를 지원하지 않습니다. 비공개 채널 만들기는 서식 파일 정의에 포함되어 없습니다.

Teams 서식 파일은 비즈니스 요구 사항 또는 프로젝트를 위해 디자인된 팀의 구조에 미리 정의되어 있습니다. 미리 만들어져 있는 서식 파일을 사용하거나 고유한 서식 파일을 만듭니다. Teams 서식 파일을 사용하면 다양한 주제에 대한 채널을 사용하여 신속하게 공동 작업 공간을 만들고 사전 설치하여 중요한 콘텐츠와 서비스에서 나올 수 있습니다. Teams 템플릿은 조직 전체에서 일관된 팀을 쉽게 만들 수 있는 미리 정의된 팀 구조를 제공합니다. 현재, Teams에서 또는 [Microsoft Graph를 사용하여 팀을 만들 수 있습니다.](get-started-with-teams-templates.md)

이 문서에서는 서식 파일에 정의할 수 있는 속성, 밑을 만드는 기본 서식 파일 형식, 몇 가지 샘플 요청을 사용하여 서식 파일에서 팀을 만드는 방법에 대해 설명합니다.

이 문서는 다음과 유용한 경우 참조하세요.

- 조직전의 여러 팀 계획, 배포, 관리 가능<br>
- 프로그래프로 자동으로 팀을 만들려는 개발자

## <a name="teams-template-capabilities"></a>Teams 서식 파일 기능

팀의 대부분의 속성이 서식 파일에 포함되거나 지원됩니다. 하지만 현재 지원되지 않는 속성 및 기능이 몇 가지 있습니다. 다음 표에는 포함된 항목과 Teams 서식 파일에 포함되지 않은 항목을 간단하게 요약하여 설명합니다.

| **Teams 서식 파일에서 지원하는 팀 속성** | **Teams 템플릿에서 아직 지원되지 않는 팀 속성** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 기본 서식 파일 형식 | 팀 구성원 |
| 팀 이름 | 팀 사진 |
| 팀 설명 | 채널 설정 |
| 팀 표시 가시성(공개 또는 비공개) | 커넥터 |
| 팀 설정(예: 구성원, 게스트, @멘션) | 파일 및 내용 |
| 자동으로 즐겨찾기 채널 | |
| 설치된 앱 | |
| 고정된 탭 | |

> [!NOTE]
> 향후 릴리스된 Microsoft Teams에서 더 많은 템플릿 기능을 추가할 예정이므로 지원되는 속성에 대한 최신 정보를 다시 확인하세요.

## <a name="what-are-base-template-types"></a>기본 서식 파일 형식이란

기본 서식 파일 형식은 Microsoft에서 특정 산업을 위해 만든 특수한 서식 파일입니다. 이러한 기본 서식 파일에는 종종 앱 스토어에서 제공되는 기준 앱이 포함되어 있습니다.

기본 서식 파일 형식이 정의되면 지정하려는 추가 속성으로 이러한 특수 서식 파일을 확장하거나 재정의할 수 있습니다. 그러나 일부 기본 템플릿 유형에는 재정의할 수 없는 속성이 포함되어 있습니다.

> [!NOTE]
> Microsoft Teams에 제공되는 미리 정의된 기본 서식 파일은 복제할 수 있지만 편집할 수는 없습니다.

| 기본 서식 파일 형식 | 이 기본 서식 파일과 함께 제공되는 속성 |
| ------------------ |----------------------------------------------------- |
| Office 365 적용 |  채널: <ul><li>일반</li> <li>공지 사항</li> <li>선수 모서리</li> <li>팀 양식</li></ul> 앱: <ul><li>Wiki</li>  <li>일정</li> |
| 프로젝트 관리 | 채널: <ul><li>일반</li> <li>공지 사항</li> <li>리소스</li> <li>계획</li></ul> 앱:<ul><li>Wiki</li><li>OneNote</li></ul> |
| 이벤트 관리 | 채널: <ul><li>일반</li> <li>공지 사항</li> <li>예산</li> <li>콘텐츠</li><li>물류</li> <li>계획</li> <li> 마케팅 및 PR</li></ul> 앱:<ul><li>Wiki</li><li>웹 사이트</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|직원 관리 | 채널: <ul><li>일반</li> <li>공지 사항</li> <li>직원 채팅</li> <li>교육</li></ul>앱:<ul><li>Wiki</li><li>커뮤니티</li>|</ul>
|지원 지원 팀 구성| 채널:<ul><li>일반</li><li>공지 사항</li><li>FAQ</li></ul>앱:<ul><li>Wiki</li><li>OneNote</li></ul> |
| 환자 비율에 대해 공동 작업 | 채널:<ul><li>일반</li><li>공지 사항</li><li>Hudles</li><li>올림</li><li>직원</li><li>교육</li></ul> 앱: <ul><li>Wiki</li>|
| 전역 비단또 이벤트에 대해 공동 작업 |채널: <ul><li>일반<li>공지 사항</li><li>전 주보인</li><li>업무 내부</li><li>원격 작업</li><li>내부 수명</li><li>외부 목록</li><li>고객 만든 명도</li><li>Kudos</li><li>임출 업데이트</li></ul>앱: <ul><li>Praise</li><li>Wiki</li><li>웹 사이트</li></ul>|
|은행 지사 내에서 공동 작업 |채널: <ul><li>일반<li>공지 사항</li><li>Hudles</li><li>고객 모임</li><li>코치</li><li>기기능 개발</li><li>대기 중</li><li>고객 만든 명도</li><li>Kudos</li><li>자금 모금</li><li>규정 준수</li></ul>|
|인시트 응답 반복 |채널: <ul><li>일반<li>공지 사항</li><li>물류</li><li>계획</li><li>복구</li><li>에커</li></ul> 앱: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|병원 |채널: <ul><li>일반<li>공지 사항</li><li>규정 준수</li><li>Custodial/li><li>인사 관리</li><li>Pharmacy</li></ul> 앱: <ul><li>Wiki</li></ul>|
|Microsoft Store 구성 |채널: <ul><li>일반<li>Shift Hoffoff</li><li>학습</li></ul> 앱: <ul><li>Wiki</li></ul>|
|품질 및 안전 |채널: <ul><li>일반<li>공지 사항</li><li>줄 1</li><li>선 2</li><li>줄 3</li><li>안전</li><li>교육</li><li>유지 관리</li><li>자금 모금</li></ul> 앱: <ul><li>Wiki</li></ul>|
|소전 - 관리자 공동 작업 |채널: <ul><li>일반<li>운영</li><li>학습</li></ul> 앱: <ul><li>Wiki</li></ul>|
|||

## <a name="template-size-limits"></a>서식 파일 크기 제한

서식 파일은 특정 수의 채널, 탭 및 앱으로 제한됩니다.

 > [!Note]
 > 서식 파일에서 만들어진 후에는 팀에 더 많은 채널, 탭, 앱을 추가할 수 있습니다.

|기능 | 제한|
|-|-|
|서식 파일당 채널 | 15 |
|서식 파일의 채널별 탭 | 20 |
|서식 파일별 앱 | 50|
|||

Teams의 [제한 및 사양을 참조하세요.](limits-specifications-teams.md)

## <a name="related-topics"></a>관련 항목

- [사용자 지정 팀 서식 파일 만들기](create-a-team-template.md)
- [기존 팀 서식 파일에서 팀 서식 파일 만들기](create-template-from-existing-template.md)
- [기존 팀에서 서식 파일 만들기](create-template-from-existing-team.md)
