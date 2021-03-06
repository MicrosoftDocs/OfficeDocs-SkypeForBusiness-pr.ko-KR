---
title: 관리 센터에서 Teams 템플릿 사용
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
description: Teams 템플릿을 사용하여 미리 설치된 템플릿을 사용하여 다양한 토픽에 대한 채널을 사용하여 공동 작업 공간을 만드는 방법을 알아보습니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 62bee9c494cc6155a84b30d75ae71528656133be
ms.sourcegitcommit: 113f587a1c09d42b7394ba1195c32cb054bdf31c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508011"
---
# <a name="get-started-with-teams-templates-in-the-admin-center"></a>관리 센터에서 Teams 템플릿 시작

**사용자 지정 템플릿을 만드는 능력은 아직 EDU 고객에게 지원되지 않습니다.**

> [!NOTE]
> Teams 템플릿은 현재 개인 채널 만들기를 지원하지 않습니다. 개인 채널 만들기는 템플릿 정의에 포함되지 않습니다.

Teams 템플릿은 비즈니스 필요 또는 프로젝트를 중심으로 디자인된 팀 구조의 미리 작성된 정의입니다. 미리 작성된 템플릿을 사용하거나 사용자만의 템플릿을 만듭니다. Teams 템플릿을 사용하면 다양한 토픽에 대한 채널을 사용하여 풍부한 공동 작업 공간을 빠르게 만들고, 중요한 콘텐츠 및 서비스를 끌어오기 위해 앱을 미리 설치할 수 있습니다. Teams 템플릿은 조직 전체에서 일관된 팀을 쉽게 만들 수 있도록 미리 정의된 팀 구조를 제공합니다. 현재 Teams의 템플릿에서 또는 Microsoft Graph를 사용하여 팀을 [만들 수 있습니다.](get-started-with-teams-templates.md)

이 문서에서는 템플릿에서 정의할 수 있는 속성, 기본 템플릿 유형 및 몇 가지 샘플 요청을 사용하여 템플릿에서 팀을 만드는 방법을 설명합니다.

이 문서는 조직 전체에서 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우를 위한 문서입니다.

## <a name="teams-template-capabilities"></a>Teams 템플릿 기능

팀의 대부분의 속성은 템플릿에 의해 포함 및 지원됩니다. 그러나 현재 지원되지 않는 몇 가지 속성 및 기능이 있습니다. 다음 표에서는 Teams 템플릿에 포함된 내용과 포함되지 않은 내용에 대한 간소한 요약을 제공합니다.

| **Teams 템플릿에서 지원하는 팀 속성** | **Teams 템플릿에서 아직 지원되지 않는 팀 속성** |
| ------------------------------------------------ | -------------------------------------------------------- |
| 기본 템플릿 유형 | 팀 구성원 |
| 팀 이름 | 팀 사진 |
| 팀 설명 | 채널 설정 |
| 팀 가시성(공개 또는 비공개) | 커넥터 |
| 팀 설정(예: 멤버, 게스트, @ 언급) | 파일 및 내용 |
| Autofavorite 채널 | |
| 설치된 앱 | |
| 고정된 탭 | |

> [!NOTE]
> Microsoft Teams의 향후 릴리스에서 템플릿 기능이 더 추가될 예정이니 지원되는 속성에 대한 최신 정보를 다시 확인하세요.

## <a name="what-are-base-template-types"></a>기본 템플릿 형식은 무엇일지

기본 템플릿 형식은 Microsoft가 특정 산업에 대해 만든 특수 템플릿입니다. 이러한 기본 템플릿에는 종종 앱 스토어에서 사용할 수 없는 독점 앱이 포함되어 있습니다.

기본 템플릿 형식이 정의된 후 지정할 추가 속성으로 이러한 특수 템플릿을 확장하거나 다시 정의할 수 있습니다. 일부 기본 템플릿 유형에는재정할 수 없는 속성이 포함되어 있습니다.

> [!NOTE]
> Microsoft Teams에 제공된 미리 정의된 기본 템플릿은 복제할 수 있지만 편집할 수 없습니다.

| 기본 템플릿 유형 | baseTemplateId | 이 기본 템플릿과 함께 있는 속성 |
| ------------------ | -------------- | ----------------------------------------------------- |
| Office 365 채택 |`com.microsoft.teams.template.AdoptOffice365`|  채널: <ul><li>일반</li> <li>공지사항</li> <li>챔피언 코너</li> <li>팀 양식</li></ul> 앱: <ul><li>위키</li>  <li>일정</li> |
| 프로젝트 관리 |`com.microsoft.teams.template.ManageAProject`| 채널: <ul><li>일반</li> <li>공지사항</li> <li>리소스</li> <li>계획</li></ul> 앱:<ul><li>위키</li><li>OneNote</li><li>Planner</li><li>목록</li>  </ul> |
| 이벤트 관리|`com.microsoft.teams.template.ManageAnEvent` | 채널: <ul><li>일반</li> <li>공지사항</li> <li>예산</li> <li>콘텐츠</li><li>물류</li> <li>계획</li> <li> 마케팅 및 PR</li></ul> 앱:<ul><li>위키</li><li>웹 사이트</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|직원 온보드|`com.microsoft.teams.template.OnboardEmployees` | 채널: <ul><li>일반</li> <li>공지사항</li> <li>직원 채팅</li> <li>교육</li></ul>앱:<ul><li>위키</li><li>커뮤니티</li><li>Planner</li></ul>|
|지원 센터 구성| `com.microsoft.teams.template.OrganizeHelpDesk`|채널:<ul><li>일반</li><li>공지사항</li><li>FAQ</li></ul>앱:<ul><li>위키</li><li>OneNote</li><li>Planner </li><li>찬양</li></ul> |
| 환자 치료에 대한 공동 작업| `healthcareWard`| 채널:<ul><li>일반</li><li>공지사항</li><li>Huddles</li><li>라운드</li><li>직원 수</li><li>교육</li></ul> 앱: <ul><li>위키</li><li>목록  </li></ul>|
| 글로벌 위기 또는 이벤트에 대한 공동 작업 |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| 채널: <ul><li>일반<li>공지사항</li><li>세계 뉴스</li><li>비즈니스 연속성</li><li>원격 작업</li><li>내부 커미스</li><li>외부 커미스</li><li>승인 요청</li><li>고객 불만</li><li>Kudos</li><li>임원 업데이트</li></ul>앱: <ul><li>찬양</li><li>위키</li><li>웹 사이트</li><li>Planner</li></ul>|
|은행 지점 내에서 공동 작업| `com.microsoft.teams.template.CollaborateWithinABankBranch`|채널: <ul><li>일반<li>공지사항</li><li>Huddles</li><li>고객 모임</li><li>승인 요청 </li><li>코칭</li><li>기술 개발</li><li>대출 처리</li><li>고객 불만</li><li>Kudos</li><li>재미있는 물건</li><li>규정 준수</li></ul>앱:<ul><li>찬양 </li></ul>|
|인시던트 응답 조정| `com.microsoft.teams.template.CoordinateIncidentResponse`|채널: <ul><li>일반<li>공지사항</li><li>물류</li><li>계획</li><li>복구</li><li>긴급</li></ul> 앱: <ul><li>위키</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|병원| `healthcareHospital` |채널: <ul><li>일반</li><li>공지사항</li><li>규정 준수</li><li>Custodial</li><li>인적 자원</li><li>약국</li></ul> 앱: <ul><li>위키</li><li>목록  </li></ul>|
|저장소 구성| `retailStore` |채널: <ul><li>일반<li>교대 근무 핸드오프</li><li>학습</li></ul> 앱: <ul><li>위키</li><li>Planner</li></ul>|
|품질 및 안전 |`com.microsoft.teams.template.QualitySafety`|채널: <ul><li>일반<li>공지사항</li><li>1줄</li><li>2줄</li><li>3줄</li><li>안전</li><li>교육</li><li>유지 관리</li><li>재미있는 물건</li></ul> 앱: <ul><li>위키</li><li>Planner</li></ul>|
|소매 - 관리자 공동 작업| `retailManagerCollaboration` |채널: <ul><li>일반<li>운영</li><li>학습</li></ul> 앱: <ul><li>위키</li><li>Planner</li></ul>|
||||

템플릿 범주에 대한 자세한 내용은 다음 범주를 참조하세요.

- [재무 템플릿](financial-teams-templates-in-the-admin-console.md)
- [일반 템플릿](general-teams-templates-in-the-admin-console.md)
- [정부 템플릿](government-teams-templates-in-the-admin-console.md)
- [의료 템플릿](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [제조 템플릿](manufacturing-teams-templates-in-the-admin-console.md)
- [소매 템플릿](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>템플릿 크기 제한

템플릿은 특정 수의 채널, 탭 및 앱으로 제한됩니다.

 > [!Note]
 > 템플릿에서 만든 후 팀에 더 많은 채널, 탭 및 앱을 추가할 수 있습니다.

|기능 | 제한|
|-|-|
|템플릿당 채널 | 15 |
|템플릿의 채널당 탭 | 20 |
|템플릿당 앱 | 50|
|||

자세한 [내용은 Teams의 제한](limits-specifications-teams.md) 및 사양을 참조하세요.

## <a name="related-topics"></a>관련 항목

- [사용자 지정 팀 템플릿 만들기](create-a-team-template.md)
- [기존 팀 템플릿에서 팀 템플릿 만들기](create-template-from-existing-template.md)
- [기존 팀에서 템플릿 만들기](create-template-from-existing-team.md)
