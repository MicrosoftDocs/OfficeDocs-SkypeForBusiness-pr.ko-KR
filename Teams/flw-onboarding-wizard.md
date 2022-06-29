---
title: 최전선 직원 온보딩 마법사를 사용하여 최전선 인력을 가동하고 실행할 수 있습니다.
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 최전방 작업자 온보딩 마법사를 사용하여 조직의 일선 작업자 및 관리자에 맞게 조정된 Teams 환경을 신속하게 배포하는 방법을 알아봅니다.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 160a8347e0ea79198f337fce460ced90f5de2931
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494515"
---
# <a name="use-the-frontline-worker-onboarding-wizard-to-get-your-frontline-workforce-up-and-running"></a>최전선 직원 온보딩 마법사를 사용하여 최전선 인력을 가동하고 실행할 수 있습니다.

## <a name="overview"></a>개요

Microsoft 365 관리 센터 일선 작업자 온보딩 마법사를 사용하면 조직에 일선 작업자 온보딩이 간소화됩니다. 마법사를 사용하면 Microsoft Teams에서 일선 인력에 맞게 조정된 환경을 신속하게 배포할 수 있습니다. 마법사를 사용하여 조직의 최전방 작업자를 위한 Teams 파일럿 배포를 쉽게 시작할 수 있습니다.

마법사는 일선 작업자를 위한 팀을 설정하고 각 팀 구성원에게 라이선스 및 [정책 패키지를 할당합니다](manage-policy-packages.md) . 팀을 처음부터 또는 [팀 템플릿](get-started-with-teams-templates-in-the-admin-console.md)에서 만든 다음 사용자를 추가하고 역할을 할당할 수 있습니다. 역할은 마법사가 각 사용자에게 할당하는 정책 패키지를 결정합니다.

현재 마법사는 실행할 때마다 100명의 사용자를 추가할 수 있도록 지원합니다. 곧 실행당 사용자 수를 늘리기 위해 노력하고 있습니다. 최신 업데이트는 여기로 다시 확인하세요.

마법사는 [F 라이선스](https://www.microsoft.com/microsoft-365/enterprise/frontline)가 하나 이상 있는 모든 조직에서 사용할 수 있습니다. 조직 전체의 여러 위치 또는 사이트에 있는 최전방 인력에게 Teams를 배포해야 하는 만큼 마법사를 여러 번 실행할 수 있습니다.

마법사를 실행하여 최전방 인력을 온보딩하는 방법에 대한 개요는 이 짧은 비디오를 확인하세요.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWN6oh]

> [!NOTE]
> 마법사는 아직 [민감도 레이블을](sensitivity-labels.md) 지원하지 않습니다. 조직에서 팀을 만들기 위해 민감도 레이블이 필요한 경우 Microsoft 365 관리 센터 마법사가 표시되지 않습니다.

## <a name="run-the-wizard"></a>마법사 실행

1. [Microsoft 365 관리 센터](https://admin.microsoft.com/) 왼쪽 탐색 영역에서 **설치** 프로그램을 선택합니다. **앱 및 전자 메일** 섹션으로 이동한 다음 **, 최전방 인력을 가동 및 실행** 하기 아래에서 **보기를** 선택합니다. 여기서는 일선 작업자용 Microsoft 365에서 제공하는 기능에 대해 자세히 알아볼 수 있습니다.

    :::image type="content" source="media/flw-onboarding-wizard-get-started.png" alt-text="Microsoft 365 관리 센터 최전방 작업자 온보딩 환경의 세부 정보 페이지 스크린샷" lightbox="media/flw-onboarding-wizard-get-started.png":::

2. 준비가 되면 **시작하기** 를 선택하여 마법사를 실행합니다.

3. 팀의 이름을 입력하고, 하나 이상의 팀 소유자를 추가하고, 개인 정보 설정을 선택합니다. 그런 다음, 팀을 처음부터 만들지 또는 팀 템플릿에서 만들 것인지 선택합니다. 팀 템플릿에는 특정 비즈니스 요구 사항 또는 프로젝트에 대해 팀을 최적화하는 미리 정의된 채널과 탭이 함께 제공됩니다.

    :::image type="content" source="media/flw-onboarding-wizard-set-up-team.png" alt-text="마법사의 팀 설정 페이지 스크린샷" lightbox="media/flw-onboarding-wizard-set-up-team.png":::

4. 팀에 사용자를 추가합니다. 그룹을 추가할 수도 있습니다. 그룹을 추가하는 경우 라이선스 및 정책 패키지가 그룹 자체가 아니라 그룹의 각 사용자에게 직접 할당된다는  사실에 유의하세요.

    :::image type="content" source="media/flw-onboarding-wizard-add-users.png" alt-text="팀에 사용자 및 그룹을 추가하는 마법사의 사용자 추가 페이지 스크린샷" lightbox="media/flw-onboarding-wizard-add-users.png":::

5. 각 팀 구성원에게 다음 역할 중 하나를 할당합니다. 최전방 작업자, 최전방 관리자, 없음. 
  
    :::image type="content" source="media/flw-onboarding-wizard-assign-roles.png" alt-text="팀 구성원에게 역할, 위치 및 라이선스를 할당하는 마법사의 작업 역할 할당 페이지 스크린샷" lightbox="media/flw-onboarding-wizard-assign-roles.png":::

    최전방 작업자 또는 최전방 관리자 역할을 할당하면 해당 사용자는 정책 패키지를 받게 됩니다. 정책 패키지는 Teams에서 자신의 역할에 맞게 조정된 환경을 만듭니다. 이 환경에는 정상 최전방 작업자 및 관리자 커뮤니케이션 및 협업을 위한 미리 고정된 앱과 정책이 포함됩니다.

    다음으로 위치를 선택하고 각 팀 구성원에게 Microsoft 365 F 라이선스를 할당합니다. 라이선스가 충분하지 않은 경우 **더 많은 라이선스 구매를 선택하여 더 많은 라이선스를** 구매할 수 있습니다.  

6. 마법사가 완료된 후 상태 전자 메일을 받는 사람을 선택합니다. 이 전자 메일에는 마법사&mdash;가 팀을 만들고, 팀 구성원을 추가하고, 각 팀 구성원에게 라이선스 및 정책 패키지를 할당하는 작업에 대한 성공 및 실패 정보가 포함되어 있습니다. 이 정보를 사용하여 발생할 수 있는 오류를 해결합니다.

    :::image type="content" source="media/flw-onboarding-wizard-email-recipients.png" alt-text="마법사의 상태 전자 메일 받는 사람 추가 페이지 스크린샷" lightbox="media/flw-onboarding-wizard-email-recipients.png":::

7. 선택 항목을 검토한 다음 **확인을 선택합니다.**

    :::image type="content" source="media/flw-onboarding-wizard-review-team.png" alt-text="팀 설정을 검토하는 마법사의 팀 검토 페이지 스크린샷" lightbox="media/flw-onboarding-wizard-review-team.png":::

    마법사는 팀을 만들고 팀 구성원에게 라이선스 및 정책 패키지를 할당합니다. 완료하는 데 몇 분 정도 걸릴 수 있으며, 그 후에 선택한 받는 사람이 상태 전자 메일을 받을 수 있습니다.

8. 당신은 당신의 방법에있어하지만 당신은 아직 완료되지 않았습니다! 다음으로, 이 문서의 [마법사 섹션을 실행한 후 수행할 작업을](#what-to-do-after-running-the-wizard) 확인합니다.

## <a name="what-to-do-after-running-the-wizard"></a>마법사를 실행한 후 수행할 일

마법사를 실행한 후에는 다음을 수행해야 합니다.

- 일선 작업자와 관리자에게 Teams 라이선스가 할당되었다는 사실을 알 수 있습니다.
- 조직에서 공유 디바이스를 사용하는 경우 Teams가 해당 디바이스에 설치되어 있는지 확인합니다. 팀에 추가한 사용자는 Teams를 열라는 메시지가 표시되는 환영 전자 메일을 받게 됩니다.
- 조직에서 BYOD("Bring Your Own Device)" 모델을 사용하는 경우 팀에 추가한 각 사용자에게 Teams를 다운로드하여 디바이스에 설치해야 한다는 사실을 알립니다. 또한 Teams를 다운로드하라는 메시지가 표시되는 환영 전자 메일을 받게 됩니다.

    > [!NOTE]
    > F1 라이선스에 전자 메일 액세스가 포함되지 않으므로 F1 라이선스가 있는 사용자는 환영 전자 메일을 받지 않습니다.  

일선 직원이 처음으로 Teams를 열면 Teams 내에서 채팅 및 채널, 통화 및 작업 관리를 포함하는 맞춤형 첫 실행 환경을 받게 됩니다.

## <a name="related-articles"></a>관련 기사

- [Teams에서 정책 패키지 관리](manage-policy-packages.md)
- [Teams 관리 센터에서 팀 템플릿 사용](get-started-with-teams-templates-in-the-admin-console.md)
