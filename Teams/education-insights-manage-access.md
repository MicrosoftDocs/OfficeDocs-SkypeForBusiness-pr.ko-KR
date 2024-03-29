---
title: Education Insights에 대한 사용자 액세스 관리
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams의 Education Insights에 대한 사용자 액세스를 관리합니다.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7203c9bda1a6e5c2bf9d90b490492fe7bbc3f64c
ms.sourcegitcommit: 78fbfcf4a1aafce5d39eea79c9461a9fc1bb3d38
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2023
ms.locfileid: "69707810"
---
# <a name="manage-user-access-to-education-insights"></a>Education Insights에 대한 사용자 액세스 관리

이 문서는 [Microsoft Teams의 Education Insights](class-insights.md)에 대한 사용자 액세스를 관리하는 데 필요한 단계를 제공합니다.

You need to provide permissions for education leaders, district leaders, school principals, head teachers, counselors, heads of learning areas, program directors, social workers, and psychologists. Educators are *automatically* given permission when they own a class team.

조직 수준의 Insights를 제공하려면 Insights가 교육 시스템의 계층 구조를 올바르게 매핑하도록 [SIS(학생 정보 시스템)에서 데이터를 가져와야](education-insights-sis-data-sync.md) 합니다.

> [!NOTE]
> 전역 관리자만이 Insights에 대한 사용자 액세스를 관리할 수 있습니다.

> [!TIP]
> 모든 교육 리더가 각 학교를 이해할 수 있는 데이터와 신속하게 문제를 식별하고 교육자에게 지원을 제공하도록 모든 교육 리더의 Insights를 사용하는 것이 좋습니다. 파일럿을 실행 중인 경우라도 모든 교육 리더에게 Insights를 사용하는 것이 여전히 도움이 될 수 있으나 파일럿 사용자 그룹에 대한 통신만 대상으로 합니다.

## <a name="manage-permissions"></a>사용 권한 관리

* Insights 앱을 열고 **설정** 을 클릭한 다음 **사용자 권한** 을 선택합니다.

:::image type="content" source="media/insights-user-permissions.png" alt-text="설정.":::

> [!NOTE]
> 조직 수준에 대한 권한을 제공하면 사용자는 그 아래의 모든 조직 단위를 볼 수 있습니다.
> 
> 사용 권한이 필요한 교육 리더와 이들이 책임을 맡고 있는 조직 단위에게만 권한을 부여합니다. 특정 조직에 대한 사용자 권한이 필요한지 여부가 불확실한 경우, 해당 기관의 개인 정보 문제 전문가(법률 또는 HR 직원)에게 문의하세요.

> [!IMPORTANT]
> 처음으로 권한을 할당한 후에는 **두 명 이상의** 사용자가 앱에 액세스한 경우에만 앱 내에서 데이터를 볼 수 있습니다. 이 요구 사항은 데이터의 표준 시간대가 올바르게 구성되고 데이터가 모든 사용자에 대해 정확하게 표시되는지 확인하는 데 도움이 됩니다. 권한이 부여된 후 사용자에게 데이터에 액세스하는 데 문제가 발생하는 경우 두 명 이상의 사용자가 앱에 액세스했는지 확인합니다.

## <a name="role-based-permissions"></a>역할 기반 권한

If you use [SDS V2.1 file format](/schooldatasync/sds-v2.1-csv-file-format) or [SDS V2 file format](/schooldatasync/sds-v2-csv-file-format), you can import all roles and the full hierarchy of schools within the education system. This complete mapping enables you to assign permissions to roles. 

> [!NOTE]
> 사용자에게 역할이 할당되면 관련 데이터를 볼 수 있는 올바른 권한이 자동으로 부여됩니다.
>
> 사용자가 더 이상 역할에 속하지 않으면 해당 역할에 대한 권한은 자동으로 취소되지만 개별 권한은 유지될 수 있습니다.

* 필요한 경우 **역할 기반 권한** 탭을 클릭하세요.

  교육 조직의 역할 목록, 각 역할에 대한 해당 계층 구조에서의 수준, 해당 역할이 할당된 사용자 수, 역할의 권한 수준이 표시됩니다. 
  
  :::image type="content" source="media/insights-role-based-permissions.png" alt-text="역할 기반 권한.":::
  
  둘 이상의 조직 수준에 역할이 있는 경우 해당 역할은 각 수준에 대해 한 번씩 여러 번 나타납니다. 스크린샷에서 학교, 학군 및 부서 수준에 보안 주체가 있으므로 ‘보안 주체’에 세 줄이 표시됩니다.
  
* 각 역할에 대해 연필 아이콘을 클릭하여 권한 수준을 선택합니다. 기본값은 역할에 Insights를 볼 수 있는 권한이 없음입니다.
* **View data for their organization**(조직에 대한 데이터 보기) 또는 **없음** 에서 권한 수준을 선택합니다.

  :::image type="content" source="media/insights-role-based-permissions-panel.png" alt-text="역할 기반 사용 권한 패널.":::
  
  목록에 더 미묘한 권한 수준이 필요한 사용자가 있는 경우 [SIS에서 가져온 데이터](education-insights-sis-data-sync.md)에서 역할 및/또는 조직을 조정하고 [개별 권한을 부여](#grant-individual-permission-to-a-user)합니다(필요한 경우).

* **변경 내용 저장** 을 클릭합니다.

  이제 이 권한 수준은 이 역할 및 조직 수준의 새 사용자에게 자동으로 할당됩니다. 사용자는 계층 구조 수준 및 그 아래 수준에서 모든 조직 단위에 대한 데이터를 볼 수 있습니다.  


## <a name="individual-permissions"></a>개별 권한

조직에 대한 SIS 데이터를 가져오는 데 SDS V2를 사용하지 않은 경우 개별 권한을 사용하여 사용자에 대한 권한을 조정하거나 각 사용자에 대한 권한을 할당합니다.

* **Individual permissions**(개별 권한) 탭을 클릭합니다.
  
  개별 권한이 부여된 교육 조직의 사용자가 표시됩니다. 
  
  :::image type="content" source="media/insights-individual-permissions.png" alt-text="개별 권한.":::
  
### <a name="grant-individual-permission-to-a-user"></a>사용자에게 개별 권한 부여
* 화면의 왼쪽 위에서 **Grant individual permission**(개별 권한 부여)를 클릭합니다.
* 각 사용자의 사용자 이름 또는 전자 메일 주소를 입력합니다.
* 사용 권한 수준을 선택합니다.
  * **모두** 사용자가 모든 수준의 모든 조직 단위를 볼 수 있습니다. 이 수준은 거의 사용되지 않습니다.
  * **특정 조직** 사용자가 선택한 조직 단위와 그 아래의 모든 조직 단위를 볼 수 있습니다. 입력을 시작하고 목록에서 조직 단위를 선택합니다.
* **권한 부여** 를 클릭하여 저장합니다.

### <a name="change-the-individual-permission-of-a-user"></a>사용자의 개별 권한 변경
* 관련 사용자인 경우 연필 아이콘을 클릭하여 개별 권한 수준을 선택합니다.
* 권한 수준을 선택합니다.
  * **모두** 사용자가 모든 수준의 모든 조직 단위를 볼 수 있습니다. 이 수준은 거의 사용되지 않습니다.
  * **특정 조직** 사용자가 선택한 조직 단위와 그 아래의 모든 조직 단위를 볼 수 있습니다. 입력을 시작하고 목록에서 조직 단위를 선택합니다.
  * **없음** 사용자가 역할에 따라 자동으로 할당된 조직 단위만 볼 수 있습니다(있는 경우).
  
  :::image type="content" source="media/insights-individual-permissions-panel.png" alt-text="개별 권한 패널.":::

* **변경 내용 저장** 을 클릭하여 저장합니다.
