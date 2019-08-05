---
title: 팀 서식 파일 시작 하기
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/25/2019
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: phlouie
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: 팀 서식 파일을 사용 하 여 미리 정의 된 채널을 사용 하 여 팀을 만드는 방법을 알아봅니다.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: b620f163f1dc071bde8a0ed43bf7fe546a9bc04a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "36181631"
---
# <a name="get-started-with-teams-templates"></a>팀 서식 파일 시작 하기 

팀 템플릿은 비즈니스 요구 또는 프로젝트를 기준으로 설계 된 팀의 구조에 대 한 미리 작성 된 정의입니다. 팀 서식 파일을 사용 하 여 다양 한 주제 및 사전 설치 앱에 대 한 채널을 사용 하 여 업무에 중요 한 콘텐츠 및 서비스에 대 한 공동 작업 공간을 빠르게 만들 수 있습니다. 팀 서식 파일은 조직에서 일관 된 팀을 쉽게 만들 수 있도록 미리 정의 된 팀 구조를 제공 합니다. 

이 문서에서는 템플릿에서 정의할 수 있는 속성, 기본 서식 파일 형식, 몇 가지 샘플 요청을 사용 하 여 서식 파일에서 팀을 만드는 방법에 대해 설명 합니다.
 
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
| 팀 설정 (예: 회원, 게스트, @ 멘 션) | 파일 및 콘텐츠 |
| 자동 즐겨찾기 채널 | |
| 설치 된 앱 | |
| 고정 된 탭 | | 

> [!NOTE]
> Microsoft 팀의 향후 릴리스에서 서식 파일 기능을 추가 하면 지원 되는 속성에 대 한 최신 정보를 다시 확인 하세요.

## <a name="what-are-base-template-types"></a>기본 서식 파일 형식 이란?

기본 서식 파일 형식은 Microsoft에서 특정 산업에 대해 만든 특수 서식 파일입니다. 이러한 기본 서식 파일에는 팀 템플릿에서 개별적으로 지원 되지 않는 저장소 및 팀 속성에서 사용할 수 없는 독점 앱이 포함 되는 경우가 많습니다.

기본 서식 파일 형식을 정의한 후에는 지정 하려는 추가 속성을 사용 하 여 이러한 특수 템플릿을 확장 하거나 재정의할 수 있습니다. 그러나 일부 기본 서식 파일 형식에는 재정의할 수 없는 속성이 포함 되어 있습니다. 

기본적으로 기본 서식 파일에는 추가 독점 앱 또는 특수 속성이 포함 되지 않은 **표준** 으로 설정 되어 있습니다. 다음은 사용 가능한 기본 서식 파일 형식의 현재 목록입니다.

| 기본 서식 파일 형식 | baseTemplateId | 이 기본 서식 파일에 포함 된 속성 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 표준이 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | 추가 앱 및 속성 없음 |
| Education<br>수업 팀 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | 들<ul><li>OneNote 수업용 전자 필기장 ( **일반** 탭에 고정) </li><li>할당 앱 ( **일반** 탭에 고정 됨)</li></ul> 팀 속성:<ul><li>팀 가시성을 **HiddenMembership** 로 설정 (재정의할 수 없음)</li></ul> |
| Education<br>교직원 팀 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | 들<ul><li>OneNote 교직원 용 전자 필기장 ( **일반** 탭에 고정)</li></ul> |
|Education<br>PLC 팀 |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | 들<ul><li>OneNote PLC 전자 필기장 ( **일반** 탭에 고정)</ul></li>|
| Retail<br>스토어 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | 채널<ul><li>교대 이송</li><li>배웁니다</li></ul>팀 속성<ul><li>팀 가시성을 공개로 설정</li></ul>회원 사용 권한<ul><li>구성원이 채널을 만들거나 업데이트 하거나 제거 하지 못하도록 방지</li><li>구성원이 앱을 추가 하거나 제거 하지 못하도록 방지</li><li>구성원이 커넥터를 만들거나 업데이트 하거나 제거 하지 못하도록 방지</li></ul> |
| Retail<br>관리자 공동 작업 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | 채널<ul><li>교대 이송</li><li>배웁니다</li></ul>팀 속성:<ul><li>팀 표시 유형을 비공개로 설정</li></ul>회원 권한:<ul><li>구성원이 채널을 만들거나 업데이트 하거나 제거 하지 못하도록 방지</li><li>구성원이 앱을 추가 하거나 제거 하지 못하도록 방지</li><li>구성원이 커넥터를 만들거나 업데이트 하거나 제거 하지 못하도록 방지</li></ul>|
| 의료<br>I |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |채널 <ul><li>알림에서\*</li><li>Huddles\*</li><li>소수</li><li>자원\*</li><li>관한\*</li></ul>\*자동 즐겨찾기에 채널 |
|의료<br>병원 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |채널<ul><li>알림에서\*</li><li>충족\*</li><li>Custodial</li><li>인적 자원</li></li><li>Pharmacy</li></ul>\*자동 즐겨찾기에 채널|
|||

> [!NOTE]
> Microsoft 팀의 향후 릴리스에서 기본 서식 파일 형식을 추가 하면 지원 되는 속성에 대 한 최신 정보를 다시 확인 합니다.


## <a name="related-topics"></a>관련 항목

- [팀 만들기](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (미리 보기)
- [신규-팀](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Microsoft 팀의 관리 교육](itadmin-readiness.md)
- [소매 팀 서식 파일 시작 하기](get-started-with-retail-teams-templates.md)
- [의료 조직의 팀 템플릿 시작 하기](expand-teams-across-your-org/healthcare/healthcare-templates.md)
