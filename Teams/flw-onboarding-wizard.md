---
title: Frontline Worker 온보더 마법사를 사용하여 프런트라인 인력을 시작하고 실행합니다.
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Frontline Worker 온보더 마법사를 사용하여 조직의 일선 근로자 및 관리자에 Teams 환경을 빠르게 배포하는 방법에 대해 알아보고
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: da44a5eb25e56a974214472782e424cda735b6dc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58636806"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>Frontline Worker 온보더 마법사를 사용하여 프런트라인 인력을 시작하고 실행합니다.

> [!NOTE]
> 이 문서에서는 아직 릴리스되지 않은 기능을 설명합니다. 곧 출시될 예정입니다. 관리자인 경우 메시지 센터(메시지 센터)에서 이 [기능이 릴리스되는 Microsoft 365 관리 센터.](https://portal.office.com/adminportal/home) 다가오는 다양한 기능을 Teams 자세한 Microsoft 365 [로드맵 을 확인해 보자.](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)

## <a name="overview"></a>개요

프런트라인 작업자 온보더 Microsoft 365 관리 센터 조직에 온보드를 간소화합니다. 마법사를 사용하면 프런트라인 인력에 맞게 Microsoft Teams 환경을 빠르게 배포할 수 있습니다. 마법사를 사용하여 조직의 일선 작업자에 대한 Teams 파일럿 배포를 쉽게 시작할 수 있습니다.

마법사는 프런트라인 작업자에 대한 팀을 설정하고 각 팀 구성원에게 라이선스 및 [정책](manage-policy-packages.md) 패키지를 할당합니다. 처음부터 또는 팀 템플릿에서 팀을 만든 다음 사용자를 추가하고 역할을 할당할 수 있습니다. [](get-started-with-teams-templates-in-the-admin-console.md) 역할은 마법사가 각 사용자에게 할당하는 정책 패키지를 결정합니다.

이 마법사는 F 라이선스가 하나 이상 있는 Microsoft 365 있습니다. 조직 전체의 다른 위치 또는 사이트의 프런트라인 Teams 롤아웃해야 하는 경우 마법사를 여러 번 실행할 수 있습니다.

> [!NOTE]
> 이 마법사를 사용하면 프런트라인 작업자를 신속하게 온보드하여 Teams Microsoft 365 관리 센터. 스크립트를 사용하여 프런트라인 Teams 배포하는 방법에 대한 자세한 내용은 프런트라인 작업자에 Teams 대규모로 프로비전하는 방법을 [참조하세요.](flw-scripted-deployment.md)

## <a name="run-the-wizard"></a>마법사 실행

1. 의 왼쪽 [탐색에서](https://admin.microsoft.com/)Microsoft 365 관리 센터 **을 선택합니다.** 앱 **및** 전자 메일 섹션으로 이동한 다음, **프런트라인** 인력을 시작하고 실행하려면 보기를 **선택합니다.** 여기에서는 프런트라인 작업자가 제공하는 기능에 Microsoft 365 자세히 알아보실 수 있습니다.

2. 준비가 됐을 때 시작을 **선택하여** 마법사를 실행합니다.

3. 팀 이름을 입력하고 개인 정보 설정을 선택하고 하나 이상의 팀 소유자를 추가합니다. 그런 다음 팀을 처음부터 만들지 아니면 팀 템플릿에서 만들지 여부를 선택해야 합니다. 팀 템플릿에는 특정 비즈니스 필요 또는 프로젝트에 맞게 팀을 최적화하는 미리 정의된 채널 및 탭이 있습니다.

4. 팀에 사용자를 추가합니다. 그룹을 추가할 수 있습니다. 그룹을 추가하는 경우 라이선스 및 정책 패키지가 그룹 자체가 아닌 그룹의 각 사용자에게 직접 할당됩니다.

5. 각 팀 구성원에게 다음 역할 중 하나를 할당합니다.

    - 프런트라인 작업자
    - 프런트라인 관리자
    - 없음

    프런트라인 작업자 또는 Frontline 관리자 역할을 할당하면 해당 사용자가 자신의 역할에 Teams 환경을 받게 됩니다. 여기에는 정상 일선 작업자 및 관리자 통신 및 공동 작업을 위한 미리 고정된 앱 및 정책이 포함됩니다.

    다음으로 각 Microsoft 365 F 라이선스를 할당합니다. 라이선스가 충분하지 않은 경우 더 많은  라이선스 구입을 선택하여 더 많은 라이선스를 구입할 수 있습니다.  

6. 마법사가 완료된 후 상태 전자 메일을 받는 사람 선택 전자 메일에는 팀을 만들고, 팀 구성원을 추가하고, 각 팀 구성원에게 라이선스 및 정책 패키지를 할당하는 마법사가 수행한 작업에 대한 성공 및 실패 정보가 &mdash; 포함되어 있습니다. 이 정보를 사용하여 발생할 수 있는 오류를 해결합니다.

7. 선택한 것을 검토한 다음 **확인을 선택합니다.**

    마법사는 팀을 만들고 팀 구성원에게 라이선스 및 정책 패키지를 할당합니다. 완료하는 데 몇 분 정도 걸릴 수 있습니다. 그 후에 선택한 받는 사람이 상태 전자 메일을 수신합니다.

8. 진행 중이지만 아직 완료되지 않았습니다. 다음으로 이 문서의 마법사 섹션을 [실행한](#what-to-do-after-running-the-wizard) 후 할 일(What)을 참조하세요.

## <a name="what-to-do-after-running-the-wizard"></a>마법사를 실행한 후 할 일

마법사를 실행한 후 다음이 중요합니다.

- 프런트라인 작업자와 관리자가 라이선스에 할당된 것을 Teams 알려주세요.
- 공유 디바이스를 사용하는 경우 해당 Teams 설치되어 있는지 확인합니다. 조직에서 "사용자만의 디바이스 가져오기" 모델을 사용하는 경우 프런트라인 작업자와 관리자가 해당 디바이스에 해당 디바이스를 다운로드하고 설치해야 하다는 Teams 알려주세요.

프런트라인 직원이 처음으로 Teams 채팅 및 채널, 통화 및 작업 관리를 포함하는 맞춤형 첫 번째 실행 환경을 받게 Teams.

## <a name="related-articles"></a>관련 문서

- [Teams에서 정책 패키지 관리](manage-policy-packages.md)
- [관리 센터에서 팀 Teams 사용](get-started-with-teams-templates-in-the-admin-console.md)