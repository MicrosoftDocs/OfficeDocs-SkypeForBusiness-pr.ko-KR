---
title: Microsoft Teams에 Reflect를 위한 IT 관리자 가이드
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 교육용 Microsoft Teams의 Reflect IT 관리자 가이드입니다.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a7cb846cfeafeff3009890b8745e9b13fc6bdd97
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268383"
---
# <a name="it-admin-guide-to-reflect-in-microsoft-teams"></a>Microsoft Teams에 Reflect를 위한 IT 관리자 가이드

이 문서는 [Microsoft Teams의 교육 인사이트](class-insights.md)의 필수적인 부분인 [Microsoft Reflect](https://aka.ms/reflect)에 관한 정보를 제공합니다. Reflect는 학생들이 정기적으로 공유하고 들을 수 있는 기회를 제공함으로써 그들의 감정을 인식하고 탐색하도록 도와줍니다. Reflect는 학습자의 정서적 어휘를 넓히고 동료에 대한 공감을 심화시키는 동시에 건강한 교실 커뮤니티를 위한 교육자들에게 귀중한 피드백을 제공하는 데 도움이 될 수 있습니다.

이 무료 체크인 앱은 이모지와 문자를 사용하여 학생들이 감정적 세부 사항을 개발할 수 있도록 도와줍니다. 연구에 따르면 사회적 및 정서적 기술을 명시적으로 가르치는 것은 학생의 학업 및 행동 수행 능력을 향상시키고 평생 긍정적인 영향을 미칩니다.

## <a name="privacy-and-security"></a>개인 정보 및 보안

Reflect는 학생들의 중요한 정보를 보호하기 위해 [교육 Insights](class-insights.md)와 동일한 개인 정보 보호 및 보안 표준을 따릅니다.

Microsoft 365의 일부인 Reflect는 [GDPR](/compliance/regulatory/gdpr) 및 학생의 교육 기록의 프라이버시를 보호하는 [FERPA(가족 교육 권한 및 개인 정보 보호법)](/compliance/regulatory/offering-ferpa)를 포함하여 데이터 수집과 사용에 대한 국가, 지역 및 산업별 규정을 충족합니다.

데이터는 기관에 속하며, Microsoft는 데이터를 오로지 수집하고 저장합니다. Microsoft 직원은 데이터 복구와 같은 서비스를 유지하기 위한 감사 방식으로 규정 준수에 의해 허용되는 경우를 제외하고는 데이터에 액세스하거나 데이터를 볼 수 없습니다.

학생들은 본인이 어떻게 반응했는지만 확인할 수 있고 다른 학생들의 이름을 *절대* 볼 수 없습니다. 반응 분포는 볼 수 있지만 각 반영과 연관된 이름은 *절대* 볼 수 없습니다.

> [!NOTE]
> 5명 미만의 학생이 응답하면 데이터는 학생에게 표시되지 않습니다. 이는 학생들이 서로의 반응을 확인할 가능성을 최소화하기 위한 것입니다.

> [!TIP]
> * [Microsoft 보안 센터](https://www.microsoft.com/trust-center)에 방문하여 Microsoft에서 어떻게 데이터를 보호하는지 자세히 알아보세요.
> * [Microsoft 규정 준수 서비스](/compliance/regulatory/offering-home)에서 조직이 규정 준수 표준을 충족하는 데 있어 Microsoft 365가 어떻게 도움을 주는지 알아보세요.

## <a name="data-collection-and-storage"></a>데이터 수집 및 저장소
데이터는 교육 기관에 속하며, Microsoft는 데이터를 오로지 수집하고 저장합니다. Microsoft 직원은 데이터 복구와 같은 서비스를 유지하기 위한 감사 방식으로 규정 준수에 의해 허용되는 경우를 제외하고는 데이터에 액세스하거나 데이터를 볼 수 없습니다.

데이터는 Insights에 저장됩니다. 기본적으로 Insights 활용이 설정되어 있습니다. 옵트아웃하면 반영을 위해 **수집된 정보는 삭제됩니다**. Insights를 다시 설정하면 사용 설정된 이후부터 데이터 수집을 시작됩니다.

[Insights IT 관리자 가이드](class-insights.md)에서 Insights자 작동하는 방식(저장소 위치 포함)과 데이터를 삭제하거나 서비스를 삭제하고 싶을 때 [Insights를 켜고 끄는 방법](class-insights.md#turn-on-and-off-insights)을 알아 볼 수 있습니다.

게스트 데이터는 수집되지 않지만 학생의 반영으로부터 데이터가 수집됩니다. **학생이 게스트로 정의된 경우 해당 데이터는 수집되지 않습니다.**

## <a name="enable-reflect"></a>반영 사용
기관에 대한 앱 설정 정책을 관리하는 경우 Reflect가 *허용* 될 수 있도록 설정합니다. Teams 관리 센터에서 관련 클래스 팀에 Reflect를 추가할 수도 있습니다.

사용자가 앱을 설치하고 상호 작용하도록 하려면 **앱 관리** 페이지의 조직 수준에서 앱과 사용자에게 할당된 **앱 권한 정책** 을 허용해야 합니다.

각 앱을 허용해야 한다고 이전에 정의한 경우 앱 관리 페이지로 이동하여 반영 '허용'을 선택하세요. **앱을 차단하면 조직의 어떤 사용자도 Teams에는 해당 앱이 나타나지 않습니다.**

> [!NOTE]
> Reflect 앱에 액세스하려면 Microsoft 365용 A1, A3 또는 A5 라이선스가 필요합니다.

> [!TIP]
> 자세한 내용은 [앱 허용 방법 또는 수업 팀에 추가하는 방법](manage-apps.md#allow-and-block-apps)을 참조하세요.

## <a name="where-do-educators-find-reflect"></a>강사는 어디에서 반영을 찾을 수 있나요?
Reflect는 기본적으로 모든 수업 또는 교직원 팀에서 사용할 수 있습니다. 앱에 액세스하려면 원하는 팀으로 이동한 다음, Reflect 탭을 선택합니다.

> [!TIP]
> 자세한 내용은 [Reflect 지원 페이지](https://support.microsoft.com/topic/e9198f62-7860-4532-821f-53ef14afa79a)를 방문하세요. 이 페이지는 교육자와 학생 모두를 위한 지침을 제공하며, 첫 Reflect 체크인을 만드는 방법을 설명합니다.
