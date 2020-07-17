---
title: Microsoft 팀 필수 구성 요소 | 종속성 채택 업그레이드
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 이 지침을 사용 하 여 조직에서 팀을 배포 하기 위한 필수 구성 요소 및 환경 종속성에 대해 알아보세요.
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
ms.openlocfilehash: 1199bacde9ed41152cde6054975963cfd5a19ae9
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158736"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>팀에 대 한 전제 조건 및 환경 종속성

![여행 다이어그램 업그레이드, 기술 준비 단계 강조](media/upgrade-banner-tech-readiness.png "기술 준비 단계에 중점을 두어 업그레이드 여행 단계")

이 문서는 사용자 준비 단계와 병행 하 여 완료 한 활동 인 업그레이드 여행에 대 한 기술 준비 단계의 일부입니다. 계속 하기 전에 이전 단계에서 다음 활동을 완료 했는지 확인 합니다.

- [프로젝트 이해 관계자 참여](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](https://aka.ms/SkypetoTeams-Scope)
- [비즈니스용 Skype 및 팀의 공존 성과 상호 운영성 이해](https://aka.ms/SkypeToTeams-Coexist)
- [업그레이드 여행 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

팀은 여러 Microsoft 365 및 Office 365 서비스를 결합 하므로 이러한 서비스의 올바른 구현과 작동에 따라 달라 집니다. 이러한 서비스에는 SharePoint Online, Exchange Online, 비즈니스용 OneDrive 등이 포함 됩니다.

모든 서비스가 필요 하지는 않지만 모두 구현 하는 것이 좋습니다. 특정 서비스를 구현 하지 않도록 선택 하는 경우 팀이 조직을 제공할 수 있는 기능에 영향을 줍니다. 예를 들어 SharePoint Online을 구현할 필요가 없지만, 팀에서는 그룹 대화의 파일 공유 같은 특정 기능에 대해 SharePoint Online을 사용 하므로이 서비스를 구현 하지 않으면 클라이언트를 통해 제공 되는 기능을 줄일 수 있습니다.

다음 문서를 참조 하 여 필수 구성 요소와 팀이 다른 기술과 상호 작용 하는 방식에 대해 알아보세요.

- 조직에서 Microsoft 365 또는 Office 365 작업을 배포 하지 않은 경우 [시작](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)을 참조 하세요.

- 조직에서 Microsoft 365 또는 Office 365에 대해 확인 된 도메인을 추가 하거나 구성 하지 않은 경우에는 [도메인 FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)를 참조 하세요.

- 조직이 Azure Active Directory에 대 한 id를 동기화 하지 않은 경우 [Microsoft 팀의 id 모델 및 인증](identify-models-authentication.md)을 참조 하세요.

- 조직에 Exchange Online이 없는 경우 [exchange 및 Microsoft 팀의 상호 작용 방법 이해](Exchange-Teams-interact.md)를 참조 하세요.

- 조직에 SharePoint Online이 없는 경우 [Sharepoint online 및 비즈니스용 OneDrive For Business가 Microsoft 팀과 어떻게 상호 작용 하는지 이해](SharePoint-OneDrive-interact.md)를 참조 하세요.

- [Microsoft 365 그룹 및 Microsoft 팀의 상호 작용](Office-365-groups.md)방법에 대해 알아보세요.

- 조직이 교육 기관 이거나 학생 정보 시스템을 사용 하는 경우 Microsoft [School Data Sync 시작](https://docs.microsoft.com/schooldatasync) 을 참조 하세요.

- 조직이 PSTN (공개 통신 네트워크) 전화 옵션을 고려 하는 경우 [음성 전화 시스템 및 pstn 연결](cloud-voice-landing-page.md)을 참조 하 고, [전화 시스템 다이렉트 라우팅](direct-routing-landing-page.md) [에 대 한 통화 요금제가 적합](calling-plan-landing-page.md)합니다.

- 팀 롤아웃 전에 모든 네트워크 요구 사항이 충족 되었는지 확인 하려면 [Microsoft 팀 용 조직의 네트워크 준비](prepare-network.md)를 참조 하세요.

해당 환경이 적용 가능한 모든 필수 구성 요소를 충족 하는지 확인 한 후 [팀에 대 한 현재 환경을 평가](upgrade-plan-journey-evaluate-environment.md)합니다.
