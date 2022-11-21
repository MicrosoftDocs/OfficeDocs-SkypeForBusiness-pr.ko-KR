---
title: Teams 룸 ServiceNow 구성
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Teams 룸 Pro 관리 포털에서 ServiceNow 구성에 대해 알아보기
f1keywords: ''
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
ms.openlocfilehash: 2166332df2c4ea388256d32a9dbc35a709042041
ms.sourcegitcommit: baf29d244b428712052553f9e4484e72e727247e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2022
ms.locfileid: "69046857"
---
# <a name="configure-servicenow-for-teams-rooms"></a>Teams 룸 ServiceNow 구성

이 문서에서는 Teams 룸 Pro 관리 포털에서 ServiceNow 환경을 구성하기 위한 필수 구성 요소 및 단계를 설명합니다.

## <a name="watch-microsoft-teams-rooms-pro-management--service-now-integration"></a>시청: Microsoft Teams 룸 Pro 관리 - Service Now 통합

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4ZK4B]


### <a name="teams-rooms-prerequisites"></a>Teams 룸 필수 구성 요소

- 할당된 서비스 관리자 역할이 있어야 합니다. 자세한 내용은 [Microsoft Teams 룸 Pro 관리를 사용하여 역할 기반 액세스 제어](rooms-pro-rbac.md)를 참조하세요.

### <a name="servicenow-prerequisites"></a>ServiceNow 필수 구성 요소

- 기본 권한 부여 로그인 또는 [OAuth](https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/security/concept/c_OAuthApplications.html) 로그인. 자세한 내용은 ServiceNow에서 [자격 증명 만들기](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) 를 참조하세요.
- ServiceNow 인스턴스 및 해당 인스턴스 호스트 이름 및 API URI
- incident_manager 이상의 역할
- Table API를 지원하는 ServiceNow의 소프트웨어 버전

## <a name="configure-your-environment"></a>환경 구성

환경 구성 방법은 사용자 지정이 가능하며 조직의 요구 사항에 따라 달라집니다. 다음 단계에서는 ServiceNow의 기존 구성을 Teams 룸 Pro 관리 포털에 복사하는 방법을 안내합니다.

1. 복사하려는 ServiceNow 인스턴스를 엽니다. Teams 룸 Pro 관리 포털에서 구성 양식을 완료할 때 이를 참조해야 합니다.
2. 새 브라우저 탭에서 [Teams 룸 Pro 관리 포털](https://portal.rooms.microsoft.com/)로 이동하여 **설정** 으로 이동합니다. 그런 다음, 왼쪽 탐색 메뉴에서 **ServiceNow** 를 선택하여 구성 양식을 엽니다.
3. 로그인할 인증 방법을 선택하고 ServiceNow 인스턴스 호스트 및 API URI를 입력합니다.
4. 필드 매핑 섹션의 ServiceNow 필드 열에 있는 모든 필수 항목은 미리 채워져야 합니다. 아래 표에는 각 ServiceNow 필드와 해당 Microsoft Teams 룸 필드가 포함되어 있습니다. 필드 매핑 섹션의 각 행에 대한 작업을 완료합니다. 각 ServiceNow 필드의 정의는 [ServiceNow 필드 정의를 참조하세요](#servicenow-field-definitions).

| ServiceNow 필드 | Microsoft Teams 룸 필드 | 작업 |
| --- | --- | --- |
| short_description | 인시던트 설명 | 작업이 필요하지 않습니다. Teams 룸 필드가 자동으로 채워집니다. |
| 설명 | 첫 번째 메시지 | 작업이 필요하지 않습니다. Teams 룸 필드가 자동으로 채워집니다. |
| assignment_group | 회의실 그룹 | ServiceNow 인스턴스에서 assignment_group 값을 복사하여 구성 양식의 ServiceNow 값 필드에 붙여넣습니다. 둘 이상의 assignment_group 있는 경우 각 추가 사용자 지정 값에 대해 **회의실 그룹 추가** 를 선택합니다. |
| 심각도 | 반지 | 심각도는 ServiceNow의 사용자 지정 값입니다. ServiceNow 인스턴스의 두 번째 열에 있는 네 번째 항목입니다. 값을 복사하여 구성 양식의 ServiceNow 값 필드에 붙여넣습니다. 심각도 값이 두 개 이상인 경우 각 추가 사용자 지정 값에 **대해 링 추가** 를 선택합니다. |
| 주석(선택 사항) | 사용자 지정 값* | 구성 양식에 주석 필드를 추가하려면 필드 매핑 섹션의 맨 위에서 **추가** 를 선택합니다. ServiceNow 인스턴스에서 주석 값을 복사하여 구성 양식의 ServiceNow 필드에 붙여넣습니다. 드롭다운 메뉴에서 Microsoft Teams 룸 필드를 할당하고 ServiceNow 값을 복사하여 붙여넣습니다. |
| 상태(해결됨) | 사용자 지정 값* | ServiceNow 인스턴스에서 확인 상태를 복사하여 구성 양식의 ServiceNow 값 필드에 붙여넣습니다. |
| close_code | 사용자 지정 값* | ServiceNow 인스턴스의 **확인 정보** 탭에서 닫는 코드를 복사하여 ServiceNow 값 필드에 구성 양식에 붙여넣습니다. |

*드롭다운 메뉴에서 사용자 지정 값 선택

>[!NOTE]
>사용자 지정 값을 찾을 수 없는 경우 ServiceNow 관리자에게 문의하세요.

인시던트 해결 섹션에 필요한 필드를 추가하려면 **추가** 를 선택합니다.

## <a name="test-and-enable"></a>테스트 및 사용

구성 양식을 완료한 후 페이지 아래쪽에서 **테스트를** 선택합니다. 구성을 제출하려면 테스트가 필요합니다.

테스트가 성공적으로 통과되면 **제출** 을 선택하여 변경 내용을 저장합니다. 조직에 ServiceNow를 사용하도록 설정할 준비가 되면 **ServiceNow를 사용하도록 설정하시겠습니까?** 토글을 켜기로 전환 **합니다**.

## <a name="servicenow-field-definitions"></a>ServiceNow 필드 정의

- **short_description**: ServiceNow의 간단한 설명 필드는 인시던트에 대한 요약을 제공하는 간단한 160자 영숫자 값입니다. 간단한 설명은 Teams 룸 Pro 관리 포털의 인시던트 설명과 동일합니다.

- **설명**: ServiceNow의 설명 필드는 ServiceNow 인시던트 대화 기록의 첫 번째 값입니다. 설명은 Teams 룸 Pro 관리 포털의 First 메시지와 동일합니다.

- **assignment_group**: ServiceNow의 할당 그룹 필드는 인시던트 구성에 사용됩니다. 할당 그룹은 Teams 룸 Pro 관리 포털의 회의실 그룹과 동일합니다. 기본적으로 하나의 회의실 그룹이 있으며 더 추가할 수 있습니다. 그룹 수와 인시던트 그룹화 방법을 결정합니다. 예를 들어 위치별로 인시던트 구성을 선택할 수 있습니다.

- **심각도**: ServiceNow의 심각도 필드는 우선 순위별로 인시던트 구성에 사용됩니다. 우선 순위를 지정하는 값은 사용자 지정할 수 있습니다. 심각도는 Teams 룸 Pro 관리 포털의 링 필드와 동일합니다. Teams 룸 Pro 관리 포털에서 링을 사용자 지정하려면 왼쪽 탐색 메뉴의 **업데이트** 이동합니다. 그런 다음 **링** 탭으로 이동하여 **링 추가를** 선택합니다.

- **주석**: 설명은 ServiceNow의 선택적 필드로, serviceNow 인스턴스의 사용자 지정 필수 필드를 Teams 룸 Pro 관리 포털 구성에 포함하는 데 사용됩니다. 주석과 동등한 값은 Teams 룸 Pro 관리 포털의 사용자 지정 값입니다.

- **상태(해결됨)**: ServiceNow의 상태(해결됨) 필드는 인시던트가 해결된 방법을 지정하는 데 사용되며 인시던트를 닫는 데 필요합니다. 상태(해결됨) 값은 사용자 지정할 수 있습니다. 상태(해결됨)와 동등한 값은 Teams 룸 Pro 관리 포털의 사용자 지정 값입니다.

- **close_code**: 인시던트가 완전히 해결되면 닫기 코드를 인시던트에 할당해야 합니다. 이 값은 ServiceNow에서 사용자 지정할 수 있습니다. close 코드와 동등한 값은 Teams 룸 Pro 관리 포털의 사용자 지정 값입니다.
