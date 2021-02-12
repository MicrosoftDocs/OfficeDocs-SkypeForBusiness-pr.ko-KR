---
title: Teams로 업그레이드하기 위한 전제 구성성 및 환경 종속성
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 이 지침을 사용하여 조직에서 Teams를 배포하기 위한 전제 구성성 및 환경 종속성에 대해 자세히 알아보기
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
ms.openlocfilehash: bcd3de45954ea500a6be0d325370ab0660604a65
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578281"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Teams에 대한 전제 구성성 및 환경 종속성

![기술 준비 단계 강조를 표시하는 업그레이드 여정 다이어그램](media/upgrade-banner-tech-readiness.png "기술 준비 단계에 강조를 두는 업그레이드 단계")

이 문서는 사용자 준비 단계와 병렬로 완료하는 작업인 업그레이드 여정의 기술 준비 단계의 일부입니다. 계속하기 전에 이전 단계에서 이러한 활동을 완료해야 합니다.

- [프로젝트 관련자에 참여](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](https://aka.ms/SkypetoTeams-Scope)
- [비즈니스용 Skype 및 Teams의 공존 및 상호 연동성 이해](https://aka.ms/SkypeToTeams-Coexist)
- [업그레이드 여정 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams는 여러 Microsoft 365 및 Office 365 서비스를 결합하므로 이러한 서비스의 올바른 구현 및 작업에 따라 달라집니다. 이러한 서비스에는 SharePoint Online, Exchange Online 및 비즈니스용 OneDrive가 포함됩니다.

모든 서비스가 필요한 것은 아니지만 모든 서비스를 구현하는 것이 좋습니다. 특정 서비스를 구현하지 않을 경우 Teams에서 조직에 제공할 수 있는 기능에 영향을 미치게 됩니다. 예를 들어 SharePoint Online을 구현할 수 없는 경우 Teams는 그룹 대화에서 파일 공유와 같은 특정 기능에 대해 SharePoint Online을 사용하게 되어 이 서비스를 구현하지 않는 경우 클라이언트를 통해 제공되는 기능이 줄어듭니다.

다음 문서를 참조하여 전제 사항 및 Teams가 다른 기술과 상호 작용하는 방법에 대해 자세히 알아보는 방법을 참조합니다.

- 조직에서 Microsoft 365 또는 Office 365 워크로드를 배포하지 않은 경우 [시작을 참조합니다.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)

- 조직에서 Microsoft 365 또는 Office 365에 대해 확인된 도메인을 추가하거나 구성하지 않은 경우 도메인 [FAQ를 참조합니다.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)

- 조직에서 Azure Active Directory에 ID를 동기화하지 않은 경우 Microsoft Teams에서 ID 모델 및 [인증을 참조하세요.](identify-models-authentication.md)

- 조직에 Exchange Online이 없는 경우 Exchange 및 Microsoft Teams가 상호 작용하는 방법 [이해를 참조하세요.](Exchange-Teams-interact.md)

- 조직에 SharePoint Online이 없는 경우 SharePoint Online 및 [비즈니스용 OneDrive가 Microsoft Teams와](SharePoint-OneDrive-interact.md)상호 작용하는 방식 이해를 참조하세요.

- [Microsoft 365](Office-365-groups.md)그룹 및 Microsoft Teams가 상호 작용하는 방법을 알아보는 방법

- 조직이 교육 기관인 경우 학생 정보 시스템을 사용하는 경우 Microsoft Teams를 배포하기 전에 [Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) 시작을 참조하세요.

- 조직에서 PSTN(Public Switched Telephone Network) 통화 옵션을 고려하는 경우 음성 - 전화 시스템 및 [PSTN](cloud-voice-landing-page.md) [연결,](calling-plan-landing-page.md)적합한 통화 요금제 및 전화 시스템 직접 라우팅을 참조하세요. [](direct-routing-landing-page.md)

- Teams를 배포하기 전에 모든 네트워크 요구 사항이 충족되도록 하기 위해 Microsoft Teams에 대한 조직의 네트워크 [준비를 참조하세요.](prepare-network.md)

환경이 적용 가능한 모든 요구 사항을 충족하는지 확인한 후 Teams에 대한 현재 [환경을 평가합니다.](upgrade-plan-journey-evaluate-environment.md)
