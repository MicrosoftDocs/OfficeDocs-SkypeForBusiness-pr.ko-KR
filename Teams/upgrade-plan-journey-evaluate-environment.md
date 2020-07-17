---
title: Microsoft 팀 업그레이드 | 환경 평가, 검색 질문
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 이 지침을 사용 하 여 팀으로 업그레이드 하기 위한 현재 환경을 적절 하 게 평가 하는 요구 사항에 대해 알아보세요.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 799d348f05c8fece6684d01768934faedcb7603f
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158746"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a>팀으로 업그레이드 하기 전에 환경 평가

![여행 다이어그램 업그레이드, 기술 준비 단계 강조](media/upgrade-banner-tech-readiness.png "기술 준비 단계에 중점을 두어 업그레이드 여행 단계")

이 문서는 사용자 준비 단계와 병행 하 여 완료 한 활동 인 업그레이드 여행에 대 한 기술 준비 단계의 일부입니다. 계속 하기 전에 이전 단계에서 다음 활동을 완료 했는지 확인 합니다.

- [프로젝트 이해 관계자 참여](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](https://aka.ms/SkypetoTeams-Scope)
- [비즈니스용 Skype 및 팀의 공존 성과 상호 운영성 이해](https://aka.ms/SkypeToTeams-Coexist)
- [업그레이드 여행 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

이 문서에서는 운영 팀의 현재 환경을 적절 하 게 평가 하기 위한 요구 사항을 간략하게 설명 합니다. 환경을 평가 하 여 전체 배포에 영향을 주는 위험 및 요구 사항을 식별 합니다. 이러한 항목을 미리 확인 하 여 성공에 대 한 계획을 조정할 수 있습니다.

## <a name="introduction-to-the-discovery-questionnaire"></a>검색 질문에 대 한 소개

목표 키 결과 (OKRs)를 달성 하기 위해 이전에는 키 서비스 결정을 했습니다. 다음 단계는 환경 검색을 수행 하 여 IT 인프라, 네트워킹 및 작업 관련 모든 측면을 평가 하 여 조직이 솔루션을 구현할 준비가 되었는지 확인 하는 것입니다. 검색은 팀에 대 한 여행 계획을 수립할 때 가장 먼저 수행 하는 주요 단계 중 하나입니다. 환경 검색에는 네트워크가 팀으로 업그레이드를 지원할 수 있도록 네트워크 준비 평가가 포함 되어야 합니다. 자신의 환경에 대 한 상세한 검색을 수행 하 여 현재 상태를 파악 하 고, 문제가 있거나 팀의 출시에 대 한 가능한 차단 가능성을 더욱 중요 하 게 합니다.

환경 평가 및 채택 준비 평가의 일부로 기술 위험을 식별 하 고 식별 된 각 위험에 대 한 완화 계획을 개발 합니다. 이 정보는 위험 등록기에 통합 해야 합니다.

기존 공동 작업 인프라와 Microsoft 365 또는 Office 365 조 직, 네트워킹, 끝점, 운영, 채택 및 준비와 관련 된 모든 문제가 환경 검색 질문의 일부로 포함 됩니다. 프로젝트 팀과 협력 하 여 필요한 정보를 최대한 자세하게 제공 하 여 계획 활동을 촉진 하세요.

이 [질문](upgrade-plan-journey-discovery-questionnaire.md) 서에는 다음 섹션으로 나뉘어 조직에서 팀의 여러 주요 영역에 대 한 준비가 되었는지 확인 합니다.

- Microsoft 365 또는 Office 365 조직 세부 정보
- 기존 공동 작업 플랫폼 요약
- 공동 작업 플랫폼 배포 세부 정보
- 네트워킹 및 Microsoft 365 또는 Office 365 서비스에 대 한 액세스
- 끝점
- 운영
- 채택 및 준비

> [!TIP]
> Microsoft Word 문서로 질문을 복사 하 여 시작할 수 있습니다. 모든 질문에 답을 하 고 이동할 때 모든 세부 정보를 수집 해 보세요.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>판단 요점</td><td><ul><li>환경 평가를 완료 해야 하는 사람은 누구 인가요?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>다음 단계</td><td><ul><li>환경 평가의 결과를 문서화 합니다.</li></ul></td></tr>
</table>


## <a name="project-team"></a>프로젝트 팀

프로젝트 팀에 게 적합 한 사람을 참여 했는지 확인 합니다. [프로젝트 이해 관계자 참여](upgrade-enlist-stakeholders.md)에서 완료 한 단계를 확인 합니다.

환경을 평가한 후에는 다음 단계를 진행 하세요 ( [서비스 준비](upgrade-prepare-environment-prepare-service.md)).
