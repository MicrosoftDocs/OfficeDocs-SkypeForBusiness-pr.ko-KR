---
title: Teams에서 앱을 관리하기 위한 앱 정책 개요
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
search.appverid: ''
description: Microsoft Teams에서 앱을 관리하는 데 사용되는 앱 권한 정책, 앱 설정 정책 및 사용자 지정 앱 정책에 대해 알아보세요.
audience: admin
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 5a377923412ad1835e4a0a3c099d31adf283267b
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299037"
---
# <a name="overview-of-app-policies-used-to-manage-access-to-apps"></a>앱 액세스 권한 관리에 사용되는 앱 정책 개요

Microsoft Teams는 정책을 사용하여 액세스 및 설치 동작을 제어합니다. 정책은 Teams 관리자가 다음 앱 동작을 제어하는 데 도움이 됩니다.

* 세분화된 수준에서 사용자에 대한 앱 액세스를 구성합니다. 이는 각 최종 사용자가 관리자가 허용한 앱만 사용하는 데 도움이 됩니다.

* 특정 사용자에 대한 관련 앱을 고정합니다. 고정된 앱은 개입 없이 자동으로 설치되므로 최종 사용자가 쉽게 시작하고 관련 앱에 빠르게 액세스할 수 있습니다.

## <a name="app-permission-policies"></a>앱 사용 권한 정책

Teams 관리자는 앱 사용 권한 정책을 사용하여 조직의 특정 사용자가 사용할 수 있는 앱을 제어할 수 있습니다. 앱과 사용자 사이 또는 둘 모두에 대한 어떠한 조합에 대해서도 정확한 액세스 매핑을 정의할 수 있습니다. 예를 들어 모든 사용자에 대해 몇 가지 앱을 허용하거나, 특정 사용자 그룹에 대해 몇 가지 앱을 허용하거나, 특정 사용자에 대해 특정 앱을 허용할 수 있습니다.

앱 사용 권한 정책은 Teams에서 사용할 수 있는 모든 유형의 앱에 적용됩니다. 예를 들어 앱 사용 권한 정책을 사용하여 특정 사용자에 대해 타사 앱 또는 사용자 지정 앱을 허용함으로써 해당 앱을 점진적으로 롤아웃할 수 있습니다.

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="앱 권한 정책의 스크린샷." lightbox="media/app-permission-policy.png":::

자세한 내용은 [사용자 지정 앱 정책 및 설정 관리 방법](teams-app-permission-policies.md)을 참조하세요.

## <a name="app-setup-policies"></a>앱 설정 정책

앱 설정 정책을 사용하면 사용자에 대한 앱 환경을 사용자 지정할 수 있습니다. Teams 클라이언트의 앱 바에 고정할 앱과 웹, 데스크톱 및 모바일 클라이언트에서 앱이 표시되는 순서를 선택합니다.

아래에 앱 설정 정책을 사용하는 방법에 대한 몇 가지 예가 있습니다.

* 개인 Teams 환경에 최종 사용자를 위한 앱을 설치합니다. 이렇게 하면 원하는 앱을 인식해 채택하는 데 도움이 됩니다. 예를 들어 HR 팀원들을 위한 사용자 지정 채용 및 인재 관리 앱을 고정합니다.
* 채팅, Teams 및 통화 같은 핵심 앱을 선택적으로 고정합니다.

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Teams 관리 센터의 앱 설정 정책 스크린샷." lightbox="media/app-setup-policy.png":::

자세한 내용은 [앱 설정 정책 관리 방법](teams-app-setup-policies.md)을 참조하세요.

## <a name="custom-app-policies"></a>사용자 지정 앱 정책

Teams를 사용하면 조직 내 개발자가 조직 내부 사용자를 위한 사용자 지정 앱을 빌드, 테스트 및 배포할 수 있습니다. 개발자는 Teams 관리자의 승인을 위해 Teams를 통해 사용자 지정 앱을 제출할 수 있습니다. 앱 설정 정책을 사용하여 조직에서 사용자 지정 앱을 업로드할 수 있는 사용자를 제어할 수 있습니다. 관리자는 조직 전체 앱 설정을 사용해 조직의 최종 사용자가 사용자 지정 앱을 사용하고 개발자는 사용자 지정 앱을 업로드하도록 허용할 수 있습니다.

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="조직 전체 설정 패널에서 조직에 사용자 지정 앱을 허용하는 방법을 보여 주는 스크린샷" lightbox="media/custom-app-policy.png":::

자세한 내용은 [사용자 지정 앱 정책 및 설정 관리 방법](teams-custom-app-policies-and-settings.md)을 참조하세요.

## <a name="related-articles"></a>관련 기사

* [정책을 준수하여 Teams 관리](manage-teams-with-policies.md)
