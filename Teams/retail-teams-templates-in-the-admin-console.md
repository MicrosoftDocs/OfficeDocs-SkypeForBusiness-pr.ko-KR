---
title: 관리 센터에서 Teams 정품 서식 파일 사용
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
description: 관리 센터를 사용하여 미리 정의한 설정, 채널 및 미리 설치된 앱을 제공하여 소매점 요구 사항을 위해 설계된 팀 구조를 만들기 위해 Teams 템플릿을 사용하는 방법을 배워야 합니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b40da8fd1cc8182d0e5ad80c30f5a459f17d26f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662643"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a>관리 센터에서 Teams 정품 서식 파일 사용

Teams 서식 파일을 사용하면 설정, 채널 및 미리 설치된 앱의 미리 정의된 서식 파일을 제공하여 빠르고 쉽게 팀을 만들 수 있습니다.

Teams 템플릿에는 소매점 요구 사항을 중심으로 설계된 팀 구조에 대한 미리 작성된 정의가 있습니다. Teams 서식 파일을 사용하여 소매점에 잘 작동하고 조직 전체에 배포할 수 있는 팀 유형을 빠르게 만들 수 있습니다. Teams 서식 파일을 확장하여 특정 조직 요구에 맞는 팀을 만들 수도 있습니다.

이 문서에서는 각 Teams 서식 파일과 이를 사용하는 것이 좋은 방법을 소개합니다.

이 문서는 소매 조직에서 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우를 위한 것입니다. 조직에 Teams 서비스를 이미 배포했다고 가정합니다. 아직 Teams를 롤아웃하지 않은 경우 먼저 Microsoft Teams를 롤아웃하는 [방법을 읽어 읽습니다.](How-to-roll-out-teams.md)

일반적으로 팀 서식 파일에 대한 자세한 내용은 Teams 서식 파일 [시작을 참조합니다.](get-started-with-teams-templates-in-the-admin-console.md)

## <a name="organize-a-store"></a>스토어 구성

소매 직원을 하나의 중앙 환경으로 함께 가져와 작업을 관리하고, 문서를 공유하고, 고객 문제를 해결하세요. 추가 애플리케이션을 통합하여 최종 프로세스에서 전환 시작을 & 간소화합니다.

| 기본 템플릿 형식 |baseTemplateId | 이 기본 템플릿과 함께 사용할 속성 |
| ------------------|-- |----------------------------------------------------- |
|스토어 구성|`retailStore`|채널: <ul><li>일반<li>Shift Handoff</li><li>학습</li></ul> 앱: <ul><li>Wiki</li></ul>|
||||

## <a name="manager-collaboration"></a>관리자 공동 작업

관리자 공동 작업 템플릿은 매장/지역 등에서 공동 작업할 관리자 집합에 대한 팀을 만드는 데 적합합니다. 예를 들어 조직에 지역이 있는 경우 캘리포니아 지역에 대한 관리자 공동 작업 팀을 만들고 해당 지역의 모든 스토어 관리자와 해당 지역의 지역 관리자를 포함할 수 있습니다.

| 기본 템플릿 형식| baseTemplateId | 이 기본 템플릿과 함께 사용할 속성 |
| ------------------|- |----------------------------------------------------- |
|소매 - 관리자 공동 작업|`retailManagerCollaboration` |채널: <ul><li>일반<li>운영</li><li>학습</li></ul> 앱: <ul><li>Wiki</li></ul>|
||||
