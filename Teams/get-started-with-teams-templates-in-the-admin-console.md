---
title: 팀 서식 파일을 사용 하 여 새 팀 만들기
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
description: 팀 서식 파일을 사용 하 여 미리 설치 된 서식 파일을 사용 하는 여러 항목의 채널을 통해 공동 작업 공간을 만드는 방법을 알아보세요
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e75d7c73393fe57f7ae3eaf8611ef3a3311386d8
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218579"
---
# <a name="get-started-with-teams-templates-in-the-admin-console"></a>관리 콘솔에서 팀 서식 파일 시작

[!INCLUDE [template](includes/preview-feature.md)]

**사용자 지정 서식 파일은 현재 .EDU 고객에 대해 지원 되지 않습니다.**

> [!NOTE]
> 팀 템플릿은 현재 개인 채널 만들기를 지원 하지 않습니다. 개인 채널 만들기는 서식 파일 정의에 포함 되지 않습니다.

팀 템플릿은 비즈니스 요구 또는 프로젝트를 기준으로 설계 된 팀의 구조에 대 한 미리 작성 된 정의입니다. 미리 작성 된 서식 파일을 사용 하거나 고유한 서식 파일을 만듭니다. 팀 서식 파일을 사용 하면 다양 한 주제에 대 한 채널을 사용 하 여 중요 한 공동 작업 공간을 신속 하 게 만들 수 있으며, 업무용 콘텐츠 및 서비스에서 가져올 수 있는 앱 팀 서식 파일은 조직에서 일관 된 팀을 쉽게 만들 수 있도록 미리 정의 된 팀 구조를 제공 합니다. 현재 팀 또는 [Microsoft Graph](get-started-with-teams-templates.md)를 사용 하 여 서식 파일에서 팀을 만들 수 있습니다.

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

기본 서식 파일 형식은 Microsoft에서 특정 산업에 대해 만든 특수 서식 파일입니다. 이러한 기본 서식 파일에는 종종 apps store에서 사용할 수 있는 독점 앱이 포함 되어 있습니다.

기본 서식 파일 형식을 정의한 후에는 지정 하려는 추가 속성을 사용 하 여 이러한 특수 템플릿을 확장 하거나 재정의할 수 있습니다. 그러나 일부 기본 서식 파일 형식에는 재정의할 수 없는 속성이 포함 되어 있습니다.

> [!NOTE]
> Microsoft 팀에서 제공 하는 미리 정의 된 기본 서식 파일은 복제만 가능 하 고 편집할 수는 없습니다.

| 기본 서식 파일 형식 | baseTemplateId | 이 기본 서식 파일에 포함 된 속성 |
| ------------------ |----|----------------------------------------------------- |
| Office 365 도입 |`com.microsoft.teams.template.AdoptOffice365`|  채널 <ul><li>일반</li> <li>알림에서</li> <li>챔피언 모서리</li> <li>팀 양식</li></ul> 들 <ul><li>키</li>  <li>일정</li> |
| 프로젝트 관리 |`com.microsoft.teams.template.ManageAProject`| 채널 <ul><li>일반</li> <li>알림에서</li> <li>리소스도</li> <li>계획</li></ul> 들<ul><li>키</li><li>만들어졌으므로</li></ul> |
| 이벤트 관리|`com.microsoft.teams.template.ManageAnEvent` | 채널 <ul><li>일반</li> <li>알림에서</li> <li>예산</li> <li>콘텐트가</li><li>물류</li> <li>계획</li> <li> 마케팅 및 홍보</li></ul> 들<ul><li>키</li><li>웹 사이트</li> <li>YouTube</li> <li>Planner</li> <li>만들어졌으므로</li></ul> |
|내장 직원|`com.microsoft.teams.template.OnboardEmployees` | 채널 <ul><li>일반</li> <li>알림에서</li> <li>직원 채팅</li> <li>교육</li></ul>들<ul><li>키</li><li>커뮤니티</li></ul>|
|지원 센터 구성| `com.microsoft.teams.template.OrganizeHelpDesk`|채널<ul><li>일반</li><li>알림에서</li><li>FAQ</li></ul>들<ul><li>키</li><li>만들어졌으므로</li></ul> |
| 환자 관리에 대 한 공동 작업| `healthcareWard `| 채널<ul><li>일반</li><li>알림에서</li><li>Huddles</li><li>소수</li><li>자원</li><li>교육</li></ul> 들 <ul><li>키</li>|
| 전역 위기 또는 이벤트에 대 한 공동 작업 |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| 채널 <ul><li>일반<li>알림에서</li><li>월드 뉴스</li><li>비즈니스 연속성</li><li>원격 작업</li><li>내부 주석 s</li><li>외부 대화 s</li><li>고객 불만</li><li>보너스</li><li>임원 업데이트</li></ul>들 <ul><li>칭찬</li><li>키</li><li>웹 사이트</li></ul>|
|은행 지사 내에서 공동 작업| `com.microsoft.teams.template.CollaborateWithinABankBranch `|채널 <ul><li>일반<li>알림에서</li><li>Huddles</li><li>고객 모임</li><li>코칭</li><li>기술 개발</li><li>대출 처리</li><li>고객 불만</li><li>보너스</li><li>재미 있는 내용</li><li>규정 준수</li></ul>|
|조정 사고 대응| `com.microsoft.teams.template.CoordinateIncidentResponse`|채널 <ul><li>일반<li>알림에서</li><li>물류</li><li>계획</li><li>복구</li><li>받기</li></ul> 들 <ul><li>키</li><li>0:excel}</li><li>만들어졌으므로</li><li>SharePoint</li><li>Planner</li></ul>|
|병원| `healthcareHospita`l-p |채널 <ul><li>일반<li>알림에서</li><li>규정 준수</li><li>Custodial</li><li>인적 자원</li><li>Pharmacy</li></ul> 들 <ul><li>키</li></ul>|
|스토어 구성| `retailStore` |채널 <ul><li>일반<li>교대 이송</li><li>배웁니다</li></ul> 들 <ul><li>키</li></ul>|
|품질 및 안전 |`com.microsoft.teams.template.QualitySafety`|채널 <ul><li>일반<li>알림에서</li><li>줄 1</li><li>선 2</li><li>선 3</li><li>안전</li><li>교육</li><li>관리할</li><li>재미 있는 내용</li></ul> 들 <ul><li>키</li></ul>|
|소매 관리자 공동 작업| `retailManagerCollaboration` |채널 <ul><li>일반<li>운영</li><li>배웁니다</li></ul> 들 <ul><li>키</li></ul>|
||||

서식 파일 범주에 대 한 자세한 내용은 다음 범주를 참조 하세요.

- [재무 서식 파일](financial-teams-templates-in-the-admin-console.md)
- [일반 서식 파일](general-teams-templates-in-the-admin-console.md)
- [정부 서식 파일](government-teams-templates-in-the-admin-console.md)
- [건강 보험 서식 파일](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [제조 템플릿](manufacturing-teams-templates-in-the-admin-console.md)
- [소매 서식 파일](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>서식 파일 크기 제한

서식 파일은 특정 개수의 채널, 탭 및 앱으로 제한 됩니다.

 > [!Note]
 > 템플릿에서 만든 후 팀에 채널, 탭 및 앱을 추가할 수 있습니다.

|기능 | 한계인|
|-|-|
|템플릿 당 채널 | ~ |
|서식 파일의 채널 당 탭 수 | 명 |
|서식 파일 당 앱 | 50|
|||

자세한 내용은 [팀의 제한 및 사양을](limits-specifications-teams.md) 참조 하세요.

## <a name="related-topics"></a>관련 항목

- [사용자 지정 팀 서식 파일 만들기](create-a-team-template.md)
- [기존 팀 템플릿에서 팀 서식 파일 만들기](create-template-from-existing-template.md)
- [기존 팀에서 서식 파일 만들기](create-template-from-existing-team.md)
