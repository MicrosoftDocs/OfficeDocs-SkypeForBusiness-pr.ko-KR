---
title: 관리 콘솔에서 팀 소매 서식 파일 사용
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
description: 관리자 콘솔을 사용 하 여 미리 정의 된 설정, 채널 및 사전 설치 앱을 제공 하 여 소매점의 요구 사항에 맞게 설계한 팀 구조를 만드는 방법에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77411e734ebbcfaea4d3e2a0454f48e43a8b8a7d
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308331"
---
# <a name="use-teams-retail-templates-in-the-admin-console"></a>관리 콘솔에서 팀 소매 서식 파일 사용

[!INCLUDE [preview-feature](includes/preview-feature.md)]

팀 서식 파일을 사용 하면 미리 정의 된 서식 파일 (설정, 채널 및 사전 설치 된 앱)을 제공 하 여 빠르고 쉽게 팀을 만들 수 있습니다.

팀 템플릿에는 소매점의 요구 사항에 따라 디자인 된 팀 구조의 정의가 미리 작성 되어 있습니다. 팀 서식 파일을 사용 하 여 소매 업체에 잘 맞는 팀 유형을 신속 하 게 만들고 조직 내에서 배포할 수 있습니다. 팀 템플릿을 확장 하 여 특정 조직의 요구 사항에 맞게 조정 된 팀을 만들 수도 있습니다.

이 문서에서는 각 팀 서식 파일과이를 사용 하는 방법을 소개 합니다.

본 문서는 소매점에서 여러 팀을 계획, 배포 및 관리 해야 하는 경우에 적합 합니다. 조직에 이미 팀 서비스를 배포 했다고 가정 합니다. 아직 팀을 롤아웃하기 않은 경우 먼저 [Microsoft 팀을 배포 하는 방법을](How-to-roll-out-teams.md)읽어 보세요.

일반적으로 팀 서식 파일에 대 한 자세한 내용은 [팀 서식 파일 시작](get-started-with-teams-templates-in-the-admin-console.md)을 참조 하세요.

## <a name="organize-a-store"></a>스토어 구성

소매 직원을 하나의 중앙 환경에서 함께 가져와 작업을 관리 하 고 문서를 공유 하 고 고객 문제를 해결 하세요. 추가 응용 프로그램을 통합 하 여 이동 시작 & 프로세스를 간소화 합니다.

| 기본 서식 파일 형식 |baseTemplateId | 이 기본 서식 파일에 포함 된 속성 |
| ------------------|-- |----------------------------------------------------- |
|스토어 구성| `retailStore`|채널 <ul><li>일반<li>교대 이송</li><li>배웁니다</li></ul> 들 <ul><li>키</li></ul>|
||||

## <a name="manager-collaboration"></a>관리자 공동 작업

관리자 공동 작업 템플릿은 저장소/지역에서 공동 작업 하는 관리자 집합을 위한 팀을 만드는 데 적합 합니다. 예를 들어 조직에 지역이 있는 경우 캘리포니아 지역에 대 한 관리자 공동 작업 팀을 만들고 해당 지역의 모든 스토어 관리자와 해당 지역의 지역 관리자를 함께 포함할 수 있습니다.

| 기본 서식 파일 형식| baseTemplateId | 이 기본 서식 파일에 포함 된 속성 |
| ------------------|- |----------------------------------------------------- |
|소매 관리자 공동 작업|`retailManagerCollaboration` |채널 <ul><li>일반<li>운영</li><li>배웁니다</li></ul> 들 <ul><li>키</li></ul>|
||||
