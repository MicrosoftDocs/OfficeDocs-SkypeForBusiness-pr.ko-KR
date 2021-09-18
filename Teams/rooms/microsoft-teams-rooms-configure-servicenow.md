---
title: 서비스용 ServiceNow Teams 룸
author: cazawideh
ms.author: czawideh
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 포털에서 ServiceNow를 Teams 룸 Premium 대해 자세히 알아보기
f1keywords: ''
ms.openlocfilehash: a8f1e43ca52ee9fa155115fb911f88221cb6fdd0
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432710"
---
# <a name="configure-servicenow-for-teams-rooms"></a>서비스용 ServiceNow Teams 룸

이 문서에서는 포털에서 ServiceNow 환경을 구성하는 Teams 룸 Premium 설명합니다.

## <a name="before-you-begin"></a>시작하기 전에

### <a name="teams-rooms-prerequisites"></a>Teams 룸 전제

- 할당된 서비스 관리자 역할이 있어야 합니다. 자세한 내용은 Managed Services 를 사용하여 역할 [기반 액세스 Microsoft Teams 룸 참조하세요.](microsoft-teams-rooms-premium-rbac.md)

### <a name="servicenow-prerequisites"></a>ServiceNow 전제

- 기본 권한 부여 로그인 또는 OAuth 로그인입니다. 자세한 내용은 ServiceNow에서 [자격 증명](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) 만들기를 참조하세요.
- ServiceNow 인스턴스 및 해당 인스턴스 호스트 이름 및 API URI
- 상위 incident_manager 역할
- Table API를 지원하는 ServiceNow의 소프트웨어 버전

## <a name="configure-your-environment"></a>환경 구성

환경을 구성하는 방식은 매우 사용자 지정이 가능하고 조직의 요구에 따라 달라 집니다. 다음 단계는 ServiceNow의 기존 구성을 포털에 복사하는 Teams 룸 Premium 단계입니다.

1. 복사하려는 ServiceNow 인스턴스를 를 포털에서 구성 양식을 완료하면 이 Teams 룸 Premium 합니다.
2. 새 브라우저 탭에서 Teams 룸 Premium 포털로 [이동하여](https://portal.rooms.microsoft.com/) 으로 **설정.** 그런 다음 왼쪽 탐색 메뉴에서 **ServiceNow를** 선택하여 구성 양식을 니다.
3. 로그인할 인증 방법을 선택하고 ServiceNow 인스턴스 호스트 및 API URI를 입력합니다.
4. 필드 매핑 섹션의 ServiceNow 필드 열에 있는 모든 필수 항목은 미리 채워야 합니다. 아래 표에는 각 ServiceNow 필드와 해당 해당 Microsoft Teams 룸 필드가 포함되어 있습니다. 필드 매핑 섹션의 각 행에 대한 작업을 완료합니다. 각 ServiceNow 필드의 정의는 [ServiceNow 필드 정의 를 참조합니다.](#servicenow-field-definitions)

| ServiceNow 필드 | Microsoft Teams 룸 필드 | 작업 |
| --- | --- | --- |
| short_description | 인시던트 설명 | 작업이 필요하지 않습니다. Teams 룸 필드가 자동으로 채워집니다. |
| 설명 | 첫 번째 메시지 | 작업이 필요하지 않습니다. Teams 룸 필드가 자동으로 채워집니다. |
| assignment_group | 룸 그룹 | ServiceNow 인스턴스에서 assignment_group 값을 복사하고 구성 양식의 ServiceNow 값 필드에 붙여넣습니다. 두 개 이상의 사용자 지정 assignment_group  사용자 지정 값에 대해 룸 그룹 추가를 선택합니다. |
| 심각도 | 링 | 심각도는 ServiceNow의 사용자 지정 값입니다. ServiceNow 인스턴스의 두 번째 열에 있는 네 번째 항목입니다. 값을 복사하고 구성 양식의 ServiceNow 값 필드에 붙여넣습니다. 심각도 값이 두 개 이상인 경우 각 추가 사용자 지정 **값에** 대해 링 추가를 선택합니다. |
| 주석(선택 사항) | 사용자 지정 값* | 구성 양식에 주석 필드를 추가하려면 필드 매핑 섹션 맨 위에 **있는** 추가를 선택합니다. ServiceNow 인스턴스에서 주석 값을 복사하고 구성 양식의 ServiceNow 필드에 붙여넣습니다. 드롭다운 메뉴에서 Microsoft Teams 룸 필드를 할당하고 ServiceNow 값을 복사하여 붙여넣습니다. |
| 상태(확인) | 사용자 지정 값* | ServiceNow 인스턴스에서 확인 상태를 복사하고 구성 양식의 ServiceNow 값 필드에 붙여넣습니다. |
| close_code | 사용자 지정 값* | ServiceNow 인스턴스의 해결 정보 탭에서 닫기 코드를 복사하여 ServiceNow 값 필드에 구성 양식에 붙여넣습니다.  |

*드롭다운 메뉴에서 사용자 지정 값 선택

>[!NOTE]
>사용자 지정 값을 찾을 수 없는 경우 ServiceNow 관리자에게 문의합니다.

인시던트 해결 섹션에 필요한 필드를 추가하려면 추가를 **선택합니다.**

## <a name="test-and-enable"></a>테스트 및 사용

구성 양식을 완료한 후 페이지 **아래쪽에서** 테스트를 선택합니다. 구성을 제출하려면 테스트가 필요합니다.

테스트가 성공적으로 통과되면 제출을 **선택하여** 변경 내용을 저장합니다. 조직에서 ServiceNow를 사용하도록 설정할 준비가 되면 **ServiceNow를** 사용하도록 설정하려는가요? 토글을 켜기 으로 **전환합니다.**

## <a name="servicenow-field-definitions"></a>ServiceNow 필드 정의

- **short_description**: ServiceNow의 간단한 설명 필드는 인시던트에 대한 요약을 제공하는 160자 영수 값입니다. 짧은 설명은 포털의 인시던트 Teams 룸 Premium 동일합니다.

- **설명**: ServiceNow의 설명 필드는 ServiceNow 인시던트의 대화 기록의 첫 번째 값입니다. 설명은 포털의 첫 번째 Teams 룸 Premium 동일합니다.

- **assignment_group**: ServiceNow의 할당 그룹 필드는 인시던트 구성에 사용됩니다. 할당 그룹은 포털의 룸 그룹과 Teams 룸 Premium 같습니다. 기본적으로 룸 그룹이 하나씩 있으며 추가를 추가할 수 있습니다. 인시던트의 수와 인시던트 그룹을 그룹화하는 방법을 결정할 수 있습니다. 예를 들어 위치별로 인시던트 구성을 선택할 수 있습니다.

- **심각도**: ServiceNow의 심각도 필드는 우선 순위별로 인시던트 구성에 사용됩니다. 우선 순위를 지정하는 값은 사용자 지정이 가능합니다. 심각도는 포털의 링 필드와 Teams 룸 Premium 동일합니다. 포털에서 링을 사용자 Teams 룸 Premium 왼쪽 탐색 메뉴에서 **업데이트로** 이동하세요. 그런 다음 **링** 탭으로 이동하고 링 **추가를 선택합니다.**

- **주석**: 주석은 ServiceNow의 선택적 필드로, 서비스 포털 구성에 ServiceNow 인스턴스에서 사용자 지정 필수 필드를 Teams 룸 Premium 있습니다. 주석과 동등한 값은 포털의 사용자 지정 Teams 룸 Premium 있습니다.

- **상태(해결)**: ServiceNow의 상태(확인) 필드는 인시던트가 해결된 방법을 지정하는 데 사용하며 인시던트 닫는 데 필요합니다. 상태(확인) 값은 사용자 지정 가능합니다. 동일한 상태(확인)는 포털의 사용자 지정 Teams 룸 Premium 있습니다.

- **close_code**: 인시던트가 완전히 해결되면 인시던트에 닫기 코드를 할당해야 합니다. 이 값은 ServiceNow에서 사용자 지정할 수 있습니다. 닫기 코드와 동등한 값은 포털의 사용자 지정 Teams 룸 Premium 있습니다.
