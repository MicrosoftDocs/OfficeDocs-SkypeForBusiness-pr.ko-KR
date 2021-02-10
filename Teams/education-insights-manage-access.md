---
title: Education Insights에 대한 사용자 액세스 관리
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams의 Education Insights에 대한 사용자 액세스를 관리합니다.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32bd773975ff6b67d28ab765ffa7c932e978af7d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145942"
---
# <a name="manage-user-access-to-education-insights"></a>Education Insights에 대한 사용자 액세스 관리

이 문서는 [Microsoft Teams의 Education Insights](class-insights.md)에 대한 사용자 액세스를 관리하는 데 필요한 단계를 제공합니다.

교육 리더, 학군 리더, 교장, 교사 부장, 상담 교사, 학습 분야 책임자, 프로그램 디렉터, 사회복지사, 심리학자에게 사용 권한을 부여해야 합니다. 교육자는 수업 팀을 맡게 되면 *자동으로* 권한을 부여받습니다.

조직 수준의 Insights를 제공하려면 Insights가 교육 시스템의 계층 구조를 올바르게 매핑하도록 [SIS(학생 정보 시스템)에서 데이터를 가져와야](education-insights-sis-data-sync.md) 합니다.

> [!NOTE]
> 전역 관리자만이 Insights에 대한 사용자 액세스를 관리할 수 있습니다.

> [!TIP]
> 모든 교육 리더가 각 학교를 이해할 수 있는 데이터와 신속하게 문제를 식별하고 교육자에게 지원을 제공하도록 모든 교육 리더의 Insights를 사용하는 것이 좋습니다. 파일럿을 실행 중인 경우라도 모든 교육 리더에게 Insights를 사용하는 것이 여전히 도움이 될 수 있으나 파일럿 사용자 그룹에 대한 통신만 대상으로 합니다.



## <a name="grant-permissions"></a>사용 권한 부여

* Insights 앱을 열고 **설정** 을 클릭한 다음 **사용자 권한** 을 선택합니다.

:::image type="content" source="media/insights-user-permissions.png" alt-text="설정":::

* **사용자 추가** 를 선택합니다.
* 각 사용자의 사용자 이름 또는 전자 메일 주소를 입력합니다.
* 사용 권한 수준을 선택합니다.
  * **모든 조직에 대한 액세스** 는 사용자가 모든 수준에서 모든 조직 단위를 본다는 것을 의미합니다.
  * **특정 학교에 대한 액세스** 는 사용자가 선택한 학교를 본다는 것을 의미합니다. 입력을 시작하고 목록에서 학교를 선택합니다. 여러 학교를 함께 추가할 수 있습니다.
* **새 사용자 추가** 를 클릭합니다.

:::image type="content" source="media/insights-add-users.png" alt-text="사용 권한 부여":::

> [!NOTE]
> 사용 권한이 필요한 교육 리더와 이들이 책임을 맡고 있는 조직 단위에게만 권한을 부여합니다. 특정 조직에 대한 사용자 권한이 필요한지 여부가 불확실한 경우, 해당 기관의 개인 정보 문제 전문가(법률 또는 HR 직원)에게 문의하세요.

## <a name="edit-permissions"></a>사용 권한 편집
* 특정 사용자를 선택한 다음 **사용자 권한 편집** 을 선택합니다.
* 사용 권한 수준 또는 학교 목록을 업데이트하고 **사용 권한 업데이트** 를 클릭합니다.

:::image type="content" source="media/insights-edit-users.png" alt-text="사용 권한 편집":::

## <a name="remove-permissions"></a>사용 권한 제거
* 제거하려는 사용자를 선택한 다음 **사용자 제거** 를 선택합니다.
* 이러한 사용자는 더 이상 조직 수준의 Insights에 액세스할 수 없지만, 수업 팀을 맡은 경우 수업 수준 Insights에 계속 액세스할 수 있습니다.

:::image type="content" source="media/insights-remove-users.png" alt-text="사용 권한 제거":::
