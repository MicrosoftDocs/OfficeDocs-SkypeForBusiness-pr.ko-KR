---
title: 관리 센터에서 Teams 정부 서식 파일 사용
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
description: 사용 방법을 배워야 합니다. 관리 센터를 사용하여 미리 정의한 설정, 채널 및 미리 설치된 앱을 제공하여 정부 요구를 위해 설계된 팀 구조를 만드는 Teams 템플릿입니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: db0d8fa4a2744f0f3c3591918230e3f569727ae7
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662203"
---
# <a name="use-teams-government-templates-in-the-admin-center"></a>관리 센터에서 Teams 정부 서식 파일 사용

Teams 서식 파일을 사용하면 설정, 채널 및 미리 설치된 앱의 미리 정의된 서식 파일을 제공하여 빠르고 쉽게 팀을 만들 수 있습니다.

Teams 템플릿에는 정부 요구 사항을 중심으로 설계된 팀 구조에 대한 미리 작성된 정의가 있습니다. Teams 서식 파일을 확장하여 특정 조직 요구에 맞는 팀을 만들 수도 있습니다.

이 문서에서는 각 Teams 서식 파일을 소개하고 이를 사용하는 방법을 권장합니다.

이 문서는 정부 조직에서 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우를 위한 것입니다. 조직에 Teams 서비스를 이미 배포했습니다. 아직 Teams를 출시하지 않은 경우 먼저 Microsoft Teams를 롤아웃하는 [방법을 읽어 읽습니다.](How-to-roll-out-teams.md)

일반적으로 팀 서식 파일에 대한 자세한 내용은 Teams 서식 파일 [시작을 참조합니다.](get-started-with-teams-templates-in-the-admin-console.md)

## <a name="coordinate-incident-response"></a>인시던트 대응 조정

위기 관리 또는 인시던트 대응 팀을 위한 통신 및 중요한 리소스를 중앙 집중화합니다. 이 팀 내에서 다양한 유형의 파일을 포함하면 모든 문서에 대한 중앙 장소를 만들 수 있습니다. 온라인 모임을 사용하여 정보 흐름 및 상황 인식을 개선합니다.

| 기본 템플릿 형식 |baseTemplateId | 이 기본 템플릿과 함께 사용할 속성 |
|-------------------|-------|---------------------------------------------------------------------------|
|인시던트 대응 조정|`com.microsoft.teams.template.CoordinateIncidentResponse`|채널: <ul><li>일반<li>공지</li><li>물류</li><li>계획</li><li>복구</li><li>긴급</li></ul> 앱: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
||||