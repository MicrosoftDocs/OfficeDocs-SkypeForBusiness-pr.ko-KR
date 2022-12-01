---
title: 관리 센터에서 일반 팀 템플릿 사용
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
ms.localizationpriority: medium
search.appverid: MET150
description: Teams 관리 센터에서 일반 팀 템플릿을 관리하고 사용하여 팀을 빠르고 쉽게 만드는 방법을 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01621d73f1f16fa23a6b4c9042e7d0cecdc2f366
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198350"
---
# <a name="use-general-team-templates-in-the-admin-center"></a>관리 센터에서 일반 팀 템플릿 사용

## <a name="overview"></a>개요

Microsoft Teams의 팀 템플릿을 사용하면 설정, 채널 및 사전 설치된 앱의 미리 정의된 팀 구조를 제공하여 팀을 빠르고 쉽게 만들 수 있습니다.

팀 템플릿을 사용하여 조직 전체에 일관된 팀을 배포합니다. 템플릿은 사용자가 Teams를 효과적으로 사용하는 방법을 파악하는 데 도움이 될 수도 있습니다. 템플릿을 확장하여 특정 조직의 요구에 맞는 팀을 만들 수도 있습니다.

Teams에는 특정 비즈니스 요구 사항 및 프로젝트에 대해 만든 미리 빌드된 템플릿이 포함되어 있습니다. 이 문서에서는 다양한 시나리오에 대해 조직에서 사용할 수 있는 템플릿의 일반적인 범주를 소개합니다.

일반적인 팀 템플릿에 대한 자세한 내용은 [Teams 관리 센터에서 팀 템플릿 시작하기](get-started-with-teams-templates-in-the-admin-console.md)를 참조하세요.

> [!NOTE]
> 별표(*)는 템플릿이 *Microsoft 365 연결된 템플릿* 임을 나타냅니다. 사용자가 템플릿을 사용하여 팀을 만들면 연결된 SharePoint 템플릿이 사이트 및 팀에 적용됩니다. 페이지, 목록 및 Power Platform 통합과 같은 SharePoint 구성 요소는 자동으로 추가되고 팀의 일반 채널에 탭으로 고정됩니다. 사용자는 Teams 내에서 바로 이러한 페이지와 목록을 편집할 수 있습니다.
>
> SharePoint 템플릿에 대한 자세한 내용은 [SharePoint 사이트 템플릿 적용 및 사용자 지정을 참조하세요](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

## <a name="manage-a-project"></a>프로젝트 관리*

작업을 관리하고, 문서를 공유하고, 프로젝트 모임을 수행하고, 일반적인 프로젝트 관리를 위해 이 템플릿을 사용하여 위험 및 결정을 문서화합니다.

> [!div class="mx-tdBreakAll"]
> | 서식 파일 유형| TemplateId| 이 템플릿과 함께 제공되는 속성 |
> | ------------------|--|-----------------------------------------------------------|
> | 프로젝트 관리 |`com.microsoft.teams.template.ManageAProject`| 채널 <ul><li>일반</li> <li>공지 사항</li> <li>리소스</li> <li>계획</li></ul> 앱:<ul><li>승인</li><li>게시판</li><li>목록<ul><li>프로젝트 추적기</li><li>문제 추적기</li></ul></li><li>이정표</li><li>OneNote</li><li>Power Automate</li><li>SharePoint Pages<ul><li>사이트</li></ul></li><li>Planner 및 할 일별 작업</li><li>Wiki</li></ul> |

## <a name="manage-an-event"></a>이벤트 관리*

매력적인 이벤트를 제공하는 데 필요한 모든 작업, 문서 및 공동 작업을 관리합니다. 게스트 사용자에게 회사 내부 및 외부의 보안 협업을 사용하도록 초대합니다.

앱 권한 정책에 따라 특정 앱에 액세스할 수 없을 수 있습니다.

> [!div class="mx-tdBreakAll"]
> | 서식 파일 유형 | TemplateId| 이 템플릿과 함께 제공되는 속성 |
> | ------------------ |--|-----------------------------------------------------------|
> | 이벤트 관리|`com.microsoft.teams.template.ManageAnEvent` | 채널 <ul><li>일반</li> <li>공지 사항</li> <li>예산</li> <li>콘텐츠</li><li>물류</li> <li>계획</li> <li> 마케팅 및 PR</li></ul> 앱:<ul><li>승인</li><li>게시판</li> <li>직원 아이디어</li> <li>목록<ul><li>콘텐츠 스케줄러</li></ul><li>이정표</li></li> <li>OneNote</li> <li>Power Automate</li> <li>SharePoint Pages<ul><li>사이트</li><li>이벤트 정보</li></ul><li>Planner 및 할 일별 작업</li><li>Wiki</li> |

## <a name="onboard-employees"></a>직원 온보딩*

리소스, 질문 및 약간의 재미를 위해 이 중앙 팀과 함께 문화를 개선하고 직원 온보딩을 간소화합니다.

> [!div class="mx-tdBreakAll"]
> | 서식 파일 유형 |TemplateId| 이 템플릿과 함께 제공되는 속성 |
> | ------------------|--|-----------------------------------------------------------|
> | 직원 온보딩|`com.microsoft.teams.template.OnboardEmployees` | 채널 <ul><li>일반</li> <li>공지 사항</li> <li>직원 채팅</li> <li>교육</li></ul>앱:<ul><li>게시판</li><li>직원 아이디어</li><li>목록<ul><li>온보딩 검사 목록</li></ul></li><li>이정표</li><li>Power Automate</li> <li>SharePoint Pages<ul><li>시작하기</li><li>교육</li></ul><li>Planner 및 할 일별 작업</li><li>Viva Engage</li><li>Wiki</li></ul>|

## <a name="adopt-office-365"></a>Office 365 채택

동료에게 새로운 기술을 전파하고 도움을 줌으로써 챔피언 커뮤니티 롤아웃을 구축, 성장 및 지속할 수 있습니다.

> [!div class="mx-tdBreakAll"]
> | 서식 파일 유형 |TemplateId| 이 템플릿과 함께 제공되는 속성 |
> | ------------------|--|-----------------------------------------------------------|
> | Office 365 채택 |`com.microsoft.teams.template.AdoptOffice365`|  채널 <ul><li>일반</li> <li>공지 사항</li> <li>챔피언 코너</li> <li>Team Forms</li><li>일정</li></ul> 앱: <ul><li>Wiki</li>  <li>채널 일정</li> <li>이정표</li><li>게시판</li></ul>|

## <a name="organize-help-desk"></a>지원 센터 구성*

기술 지원팀을 지원하는 설명서, 정책 및 프로세스에 대해 공동 작업합니다. 기존 발권 시스템을 통합하거나 템플릿을 사용하여 요청을 관리합니다.

> [!div class="mx-tdBreakAll"]
> | 서식 파일 유형 |TemplateId| 이 템플릿과 함께 제공되는 속성 |
> | ------------------|--|------------------------------------------------------------|
> | 지원 센터 구성| `com.microsoft.teams.template.OrganizeHelpDesk`|채널<ul><li>일반</li><li>공지 사항</li><li>FAQ</li></ul>앱:<ul><li>문제 보고</li><li>목록<ul><li>장치</li><li>티켓</li></ul></li><li>OneNote</li><li>Power Automate</li><li>SharePoint Pages<ul><li>사이트</li><li>FAQ</li></ul></li><li>Planner 및 할 일별 작업</li><li>Wiki</li></ul> |

## <a name="crisis-communications"></a>위기 통신*

위기 관리 또는 인시던트 대응 팀을 위한 통신 및 위험 위기 리소스를 중앙 집중화합니다. 온라인 모임을 사용하여 정보 흐름 및 상황 인식을 개선합니다.

> [!div class="mx-tdBreakAll"]
> | 서식 파일 유형 |TemplateId| 이 템플릿과 함께 제공되는 속성 |
> | ------------------ |--|----------------------------------------------------------|
> | 위기 통신 |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| 채널 <ul><li>일반<li>공지 사항</li><li>임원 업데이트</li><li>계획</li><li>물류</li></ul>앱: <ul><li>승인</li><li>문제 보고</li><li>목록<ul><li>콘텐츠 스케줄러</li><li>프로젝트 계획</li></ul></li><li>OneNote</li><li>Power Automate</li><li>SharePoint Pages<ul><li>사이트</li><li>최신 업데이트</li></ul><li>Planner 및 할 일별 작업</li></ul>|

## <a name="related-articles"></a>관련 기사

- [Teams 관리 센터에서 팀 템플릿 시작하기](get-started-with-teams-templates-in-the-admin-console.md)
- [템플릿으로 팀 만들기](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)