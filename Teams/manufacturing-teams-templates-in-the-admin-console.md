---
title: 관리 센터에서 제조 팀 템플릿 시작
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
ms.localizationpriority: medium
search.appverid: MET150
description: 팀 템플릿을 사용하여 관리 센터를 사용하여 미리 정의된 설정, 채널 및 미리 설치된 앱을 제공하여 제조 요구 사항을 위해 디자인된 팀 구조를 만드는 방법을 알아보습니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b030b3a9635c0ba3f7737e4b749d47ac93fba862
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604417"
---
# <a name="use-manufacturing-team-templates-in-the-admin-center"></a>관리 센터에서 제조 팀 템플릿 사용

팀 템플릿을 사용하면 설정, 채널 및 미리 설치된 앱의 미리 정의된 템플릿을 제공하여 빠르고 쉽게 팀을 만들 수 있습니다.

팀 템플릿에는 제조 요구 사항을 중심으로 설계된 팀 구조에 대한 미리 작성된 정의가 있습니다. 팀 템플릿을 확장하여 특정 조직 요구에 맞게 팀을 만들 수도 있습니다.

이 문서에서는 각 팀 템플릿을 소개하고 이를 사용하는 방법을 권장합니다.

이 문서는 제조 조직 전반에 걸쳐 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우를 위한 것입니다. 귀사는 이미 Teams 서비스를 구축했습니다. Teams를 아직 배포하지 않은 경우 먼저 [Microsoft Teams를 배포하는 방법](./deploy-overview.md)을 읽어보세요.

일반적으로 팀 템플릿에 대한 자세한 내용은 팀 템플릿 시작 을 [참조합니다.](get-started-with-teams-templates-in-the-admin-console.md)

## <a name="quality-and-safety"></a>품질 및 안전

Manufacturing Plant 팀을 통해 통신, 리소스에 대한 액세스 및 플랜트 작업을 중앙 집중화합니다. 정책 및 절차 문서, 교육 비디오, 안전 고지, 교대 근무 프로세스를 포함합니다.

| 기본 서식 파일 형식|baseTemplateId| 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
| ------------------|-- |----------------------------------------------------- |
|품질 및 안전|`com.microsoft.teams.template.QualitySafety` |채널 <ul><li>일반<li>공지 사항</li><li>1줄</li><li>2줄</li><li>3줄</li><li>안전</li><li>교육</li><li>유지 관리</li><li>재미있는 물건</li></ul> 앱: <ul><li>Wiki</li><li>Planner</li></ul>|
||||