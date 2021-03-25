---
title: 관리 센터에서 Teams 판매점 서식 파일 사용
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
description: 관리 센터를 사용하여 미리 정의한 설정, 채널 및 미리 설치된 앱을 제공하여 판매점 요구 사항을 위해 설계된 팀 구조를 만드는 방법을 알아보세요.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a63602f07e0c248b4decbc733e41b16fdafc3911
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117616"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a>관리 센터에서 Teams 판매점 서식 파일 사용

Teams 서식 파일을 사용하면 미리 정의된 설정, 채널 및 미리 설치된 앱 서식 파일을 제공하여 팀을 쉽고 빠르게 만들 수 있습니다.

Teams 서식 파일은 판매점 요구 사항을 위해 설계된 팀 구조를 미리 구성합니다. Teams 서실 파일을 사용하여 판매점에 적합한 팀 유형을 신속하게 생성하여 조직 전체에 배포할 수 있습니다. Teams 서식 파일을 확장하여 특정 조직 요구에 맞는 팀을 만들 수도 있습니다.

이 문서에서는 각 Teams 서식 파일과 이러한 서식 파일을 사용하는 방법에 대해 소개합니다.

이 문서는 판매점 조직 전체에 걸쳐 여러 Teams를 계획, 배포 및 관리하는 업무를 담당하는 사용자를 위한 것입니다. 귀사가 이미 Teams 서비스를 구축했다고 가정합니다. Teams를 아직 배포하지 않은 경우 먼저 [Microsoft Teams를 배포하는 방법](./deploy-overview.md)을 읽어보세요.

일반적인 팀 서식 파일에 대한 자세한 내용은 [Teams 서식 파일 시작하기](get-started-with-teams-templates-in-the-admin-console.md)를 참조하세요.

## <a name="organize-a-store"></a>스토어 구성

하나의 중앙 집중식 경험을 통해 판매점 직원들을 하나로 묶어 작업을 관리하고, 문서를 공유하며, 고객 문제를 해결합니다. 추가 애플리케이션을 통합하여 교대 근무 시작 및 종료 프로세스를 효율화할 수 있습니다.

| 기본 서식 파일 형식 |baseTemplateId | 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
| ------------------|-- |----------------------------------------------------- |
|스토어 구성|`retailStore`|채널 <ul><li>일반<li>교대 근무 전달</li><li>학습</li></ul> 앱: <ul><li>Wiki</li></ul>|
||||

## <a name="manager-collaboration"></a>관리자 공동 작업

관리자 공동 작업 서식 파일은 관리자 집합이 여러 상점/지역 등에서 협업할 팀을 만드는 데 이상적입니다. 예를 들어 조직에 지역이 있는 경우 캘리포니아 지역에 대한 관리자 공동 작업 팀을 생성하고 해당 지역의 모든 스토어 매니저와 해당 지역의 지역 관리자를 포함할 수 있습니다.

| 기본 서식 파일 형식| baseTemplateId | 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
| ------------------|- |----------------------------------------------------- |
|소매 - 관리자 공동 작업|`retailManagerCollaboration` |채널 <ul><li>일반<li>작업</li><li>학습</li></ul> 앱: <ul><li>Wiki</li></ul>|
||||