---
title: 관리 센터에서 정부 팀 템플릿 사용
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
ms.localizationpriority: medium
search.appverid: MET150
description: 관리 센터를 사용하여 미리 정의된 설정, 채널 및 미리 설치된 앱을 제공하여 팀 템플릿을 사용하여 정부 요구 사항에 맞게 설계된 팀 구조를 만드는 방법을 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ca06db512981a87b92fd369799de69532d26420a
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562157"
---
# <a name="use-government-team-templates-in-the-admin-center"></a>관리 센터에서 정부 팀 템플릿 사용

팀 템플릿을 사용하면 미리 정의된 설정, 채널 및 미리 설치된 앱 템플릿을 제공하여 팀을 빠르고 쉽게 만들 수 있습니다.

팀 템플릿에는 정부 요구 사항을 중심으로 설계된 팀 구조에 대한 미리 빌드된 정의가 있습니다. 팀 템플릿을 확장하여 특정 조직의 요구에 맞는 팀을 만들 수도 있습니다.

이 문서에서는 각 팀 템플릿을 소개하고 사용하는 방법을 권장합니다.

이 문서는 정부 조직 전체에서 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우에 적합합니다. 귀사는 이미 Teams 서비스를 구축했습니다. Teams를 아직 배포하지 않은 경우 먼저 [Microsoft Teams를 배포하는 방법](./deploy-overview.md)을 읽어보세요.

일반적으로 팀 템플릿에 대한 자세한 내용은 [팀 템플릿 시작을 참조하세요](get-started-with-teams-templates-in-the-admin-console.md).

## <a name="coordinate-incident-response"></a>인시던트 대응 조정

위기 관리 또는 인시던트 대응 팀을 위한 커뮤니케이션 및 중요 리소스를 중앙 집중화합니다. 이 팀 내에서 다양한 유형의 파일을 포함하면 모든 문서에 대한 중앙 위치를 만들 수 있습니다. 온라인 모임을 사용하여 정보 흐름 및 상황 인식을 개선합니다.

| 기본 서식 파일 형식 |baseTemplateId | 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
|-------------------|-------|---------------------------------------------------------------------------|
|인시던트 대응 조정|`com.microsoft.teams.template.CoordinateIncidentResponse`|채널 <ul><li>일반<li>공지 사항</li><li>물류</li><li>계획</li><li>복구</li><li>긴급</li></ul> 앱: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
||||