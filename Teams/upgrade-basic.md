---
title: 업그레이드 검사 목록| Teams로 Skype 비즈니스 업그레이드 | 기본 단계
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 이 가속화된 10단계 작업 계획에 따라 기본 비즈니스용 Skype 설정에서 Microsoft Teams 설정으로 전환합니다.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- seo-marvel-apr2020
- Teams-upgrade-guidance
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-in
- ms.teamsadmincenter.dashboard.widget.upgrade.opt-out
- ms.teamsadmincenter.dashboard.widget.upgrade.scheduled
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: aab5ff20ef241b3e80eaf7909fb960eff94bfbe8
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606027"
---
# <a name="upgrade-basic"></a>기본 업그레이드

<a name="about-upgrade-basic"></a>

소규모 조직 또는 메신저(채팅) 및 모임에만 비즈니스용 Skype Online을 사용하는 조직을 위해 설계된 업그레이드 기본 검사 목록은 비즈니스용 Skype Teams로의 성공적인 이동을 구현하기 위한 핵심, 권장 활동 및 관련 리소스를 포함하는 가속화된 작업 계획입니다.

이러한 10가지 쉬운 단계는 성공적인 업그레이드에 필요한 모든 것을 제공합니다. 약 30~45일 이내에 완료되도록 설계되었지만 조직의 업그레이드 일정에 따라 작업 완료 날짜를 조정해야 합니다.

> [!IMPORTANT]
> 비즈니스용 Skype Online은 2021년 7월 31일에 은퇴했습니다. 혜택 실현을 최대화하고 조직에서 업그레이드를 구현할 적절한 시간을 갖도록 하려면 현재 Microsoft Teams로의 여정을 시작하는 것이 좋습니다.

업그레이드 후 비즈니스용 Skype 어떻게 됩니까? 사용자를 Teams로 업그레이드한 후(**Teams 전용** 모드):

- 비즈니스용 Skype 클라이언트가 비활성화되고 모든 채팅 및 통화가 Teams로 이동합니다. 이렇게 하면 데스크톱에서 클라이언트가 제거되지 않습니다.
- 업그레이드 전에 예약된 모든 비즈니스용 Skype 모임은 설계대로 작동하지만 모든 새 모임은 Teams에서 예약됩니다. 비즈니스용 Skype 플러그 인은 Outlook에서 더 이상 사용할 수 없습니다. 
- 사용자가 비즈니스용 Skype 로그인하려고 하면 클라이언트에서 Teams로 업그레이드되었다는 알림이 표시됩니다.
- 사용자는 모바일 디바이스에서 비즈니스용 Skype 클라이언트를 수동으로 제거해야 합니다.

업그레이드에 대한 추가 질문은 [FAQ](./faq-journey.yml) 를 참조하세요.

Teams에 익숙하지 않나요? Teams가 Microsoft 365 및 Office 365 팀워크를 위한 단일 허브를 제공하는 대화, 모임, 파일, Office 앱 및 타사 통합을 통합하는 [방법에 대해 알아봅니](https://products.office.com/microsoft-teams/group-chat-software)다.

<!--ENDOFSECTION-->

<a name="step-1"></a>

## <a name="step-1-notify-your-key-stakeholders"></a>1단계. 주요 이해 관계자에게 알림

*(업그레이드하기 약 4~6주 전)*

고위 경영진은 회사의 성공에 대한 책임이 있습니다. 기술 변화에 대해 계속 알고 있어야 합니다. 모든 사용자가 업그레이드 자격 알림을 받거나 읽는 것은 아니므로 업그레이드 계획을 시작하기 전에 관련자(예: CEO, IT 전문가, 마케팅 및 기술 지원팀 잠재 고객)에게 알려야 합니다.

**리소스:**

- [샘플 이메일: 관련자 커뮤니케이션](upgrade-emails-surveys.md#step-1-email)

[맨 위로 돌아가기](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-2"></a>

## <a name="step-2-prepare-your-organization-for-teams"></a>2단계. Teams를 사용하도록 조직 준비

*(업그레이드하기 약 4~6주 전)*

Teams는 메신저 대화(채팅) 및 모임과 같은 호환 가능한 비즈니스용 Skype 기능을 제공하지만 훨씬 더 많은 작업을 수행할 수도 있습니다. 팀워크의 진정한 허브인 Teams를 사용하면 작업 그룹이 한 위치에서 프로젝트, 파일, 대화 및 앱을 모두 관리할 수 있습니다. 기본적으로 모든 조직에 Teams가 설정되어 있습니다. 조직에서 Teams를 사용하는 방법을 결정하고 성공을 위해 환경을 구성합니다. 

> [!Note]
> 기존 비즈니스용 Skype 고객은 현재 네트워크 인프라가 Teams용으로 이미 구성되어 있을 가능성이 높습니다. 이를 확인하려면 아래에 연결된 "전체 기술 계획" 지침을 따를 수 있습니다(선택 사항).

**리소스:**

- [Teams 개요](Teams-overview.md)
- [Microsoft Teams 시작하기](get-started-with-teams-quick-start.md)

[맨 위로 돌아가기](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-3"></a>

## <a name="step-3-know-your-skype-for-business-users"></a>3단계. 비즈니스용 Skype 사용자 파악

*(업그레이드 약 4주 전)*

비즈니스용 Skype 깊이 채택된 사용자는 Teams로 전환하는 데 좀 더 많은 시간이나 도움이 필요할 수 있습니다. 시간을 내어 현재 비즈니스용 Skype 사용량을 검토하여 추가 지원이 필요한 상위 사용자를 식별하고 업그레이드 후 번호에 대해 추적할 수 있는 사용 기준을 설정합니다.

**리소스:**

- [관리 센터의 Microsoft 365 보고서](/microsoft-365/admin/activity-reports/activity-reports)

[맨 위로 돌아가기](#about-upgrade-basic)

<a name="step-4"></a>

<!--ENDOFSECTION-->

## <a name="step-4-notify-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>4단계. 사용자에게 비즈니스용 Skype Teams로 업그레이드할 것임을 알립니다.

*(업그레이드하기 약 2~3주 전)*

사용자에게 충분한 알림을 제공하면 생산성에 부정적인 영향을 주지 않고 Teams에 익숙해질 수 있는 시간이 제공되므로 더 긍정적인 사용자 환경이 생성됩니다. 커뮤니케이션을 보내서 무엇이 변화하고 있는지, 왜 변화하는지, 그리고 어떻게 준비할 수 있는지 알려줍니다.

> [!Note]
> 필요한 경우 현재 Microsoft 365 관리 센터 통해 사용자를 위해 Teams를 사용하도록 설정할 수 있습니다.

**리소스:**

- [조직에서 Microsoft Teams 설정 관리](enable-features-office-365.md)
- [샘플 이메일: 사용자에게 비즈니스용 Skype 대한 알림](upgrade-emails-surveys.md#step-4-email)

[맨 위로 돌아가기](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-5"></a>

## <a name="step-5-activate-the-user-upgrade-notification"></a>5단계. 사용자 업그레이드 알림 활성화

*(업그레이드 약 1주일 전)*

관리 포털을 통해 사용자 업그레이드 알림을 사용하도록 설정하고 사용자가 비즈니스용 Skype Teams로 업그레이드되는 비즈니스용 Skype 클라이언트에 시각적 경고를 제공하여 업그레이드 모멘텀을 유지합니다.

**리소스:**

- [공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[맨 위로 돌아가기](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-6"></a>

## <a name="step-6-remind-your-users-that-theyll-be-upgrading-from-skype-for-business-to-teams"></a>6단계. 사용자에게 비즈니스용 Skype Teams로 업그레이드할 것임을 알려 줍니다.

*(업그레이드하기 약 5일 전)*

사용자는 일상적인 책임으로 바쁘게 작업하고 있습니다. 보류 중인 업그레이드를 알려면 Teams를 준비하는 데 필요한 단계를 수행해야 합니다. 사용 가능한 교육과 Teams를 시작하는 방법을 사용자에게 알려줄 수 있는 완벽한 시기입니다.

**리소스:**

- [샘플 전자 메일: 사용자에게 Teams를 시작하도록 미리 알림](upgrade-emails-surveys.md#step-6-email)

[맨 위로 돌아가기](#about-upgrade-basic)

<a name="step-7"></a>

<!--ENDOFSECTION-->

## <a name="step-7-upgrade-users-to-teams"></a>7단계. 사용자를 Teams로 업그레이드하세요!

*(업그레이드 일)*

오늘은 조직에서 커뮤니케이션 및 공동 작업 솔루션으로 Teams로 공식적으로 업그레이드하는 날입니다. Microsoft Teams 관리 센터에서 공존 모드를 **Teams 전용** 으로 설정하여 업그레이드 스위치를 활성화합니다. (관리 센터에서 **Teams** > 로 이동 **Teams 업그레이드 설정**.) 사용자는 비즈니스용 Skype 클라이언트에서 Teams로 업그레이드되었다는 알림을 받게 됩니다.

모든 사용자가 업그레이드된 후 Teams에 환영하는 전자 메일을 보내는 것이 좋습니다.

**리소스:**

- [공존 및 업그레이드 설정 지정](setting-your-coexistence-and-upgrade-settings.md)
- [샘플 전자 메일: Teams에 사용자를 환영합니다.](upgrade-emails-surveys.md#step-7-email)

[맨 위로 돌아가기](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-8"></a>

## <a name="step-8-monitor-teams-usage-against-your-baseline"></a>8단계. 기준선에 대한 Teams 사용량 모니터링

*(업그레이드 후 약 1~2주)*

새로운 기술에 적응하는 데는 다소 시간이 걸릴 수 있습니다. 사용량을 확인하여 사용자가 비즈니스용 Skype 때와 동일한 수준 또는 그 이상의 수준에서 Teams를 사용하고 있는지 확인합니다. 예상 수준에서 Teams를 사용하지 않는 사용자를 확인합니다.

**리소스:**

- [사용량 현황 데이터 보기](https://portal.office.com/AdminPortal/Home#/reportsUsage)

[맨 위로 돌아가기](#about-upgrade-basic)

<a name="step-9"></a>

<!--ENDOFSECTION-->

## <a name="step-9-measure-user-satisfaction"></a>9단계. 사용자 만족도 측정

*(업그레이드 후 약 1~2주)*

직원 만족도는 생산성, 보존 및 궁극적으로 비즈니스 결과에 영향을 줄 수 있습니다. 사용자에게 연락하여 업그레이드에 대한 사용자 감정과 Teams에 대한 만족도를 측정합니다.

**리소스:**

- [샘플 이메일: 사용자 및 사용자](upgrade-emails-surveys.md#step-9-email) [설문 조사](upgrade-emails-surveys.md#step-9-surveys)로 체크 인

[맨 위로 돌아가기](#about-upgrade-basic)

<!--ENDOFSECTION-->

<a name="step-10"></a>

## <a name="step-10-maximize-your-roi-with-teams"></a>10단계. Teams를 사용하여 ROI 최대화

*(진행 중)*

사용자가 Teams에서 메신저 대화(채팅) 및 모임에 익숙해지면 Teams 협업 및 앱 통합을 사용하여 새로운 솔루션을 진정으로 최적화하고 투자 수익을 극대화하여 사용 사례를 확장하도록 권장합니다.

**리소스:**

- [샘플 전자 메일: 사용자가 Teams를 추가로 탐색하도록 권장](upgrade-emails-surveys.md#step-10-email)

[맨 위로 돌아가기](#about-upgrade-basic)
