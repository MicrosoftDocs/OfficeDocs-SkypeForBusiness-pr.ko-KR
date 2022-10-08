---
title: Teams에서 앱을 관리하기 위한 앱 정책 개요
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-apps
ms.date: 09/25/2022
search.appverid: ''
description: Microsoft Teams에서 앱을 관리하는 데 사용되는 앱 권한 정책 및 설정 정책에 대해 알아봅니다.
audience: admin
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 1c99cd9c0be3251a237b547cd8a2096d2d0e02af
ms.sourcegitcommit: d6e180791134426445a35fd485dcca18bde2006b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2022
ms.locfileid: "68494651"
---
# <a name="app-policies-used-to-manage-access-to-and-installation-of-apps"></a>앱에 대한 액세스 및 설치를 관리하는 데 사용되는 앱 정책

Microsoft Teams는 앱 정책을 사용하여 앱의 액세스 및 설치 동작을 제어합니다. 앱 정책은 Teams 관리자가 다음 앱 동작을 제어하는 데 도움이 됩니다.

* 각 개별 사용자 또는 사용자 그룹에 대한 앱 액세스를 구성합니다. 관리자가 각 최종 사용자에 대해 허용되는 앱을 제어하는 데 도움이 됩니다.

* 조직의 요구 사항과 관련된 최종 사용자를 위해 해당 앱을 고정합니다. 또한 관리자는 사용자 개입 없이 최종 사용자를 위한 앱을 설치할 수 있습니다. 최종 사용자가 관련 앱을 쉽게 시작하는 데 도움이 됩니다.

* 조직의 개발자가 관리자 승인을 위해 사용자 지정 앱을 제출할 수 있는 것을 제어합니다. 사용자 지정 앱 업로드 기능에 대한 액세스를 제어하는 데 도움이 됩니다.

## <a name="app-permission-policies"></a>앱 사용 권한 정책

앱 사용 권한 정책을 사용하여 Teams 관리자는 조직의 각 사용자가 사용할 수 있는 앱을 제어합니다. 모든 사용자에 대해 몇 가지 앱을 허용하거나, 특정 사용자 그룹에 대해 몇 가지 앱을 허용하거나, 특정 사용자에 대해 특정 앱을 허용할 수 있습니다. 앱 권한 정책은 조직 전체 설정과 함께 작동하며 각 개별 앱의 상태를 허용하거나 차단합니다.

앱 사용 권한 정책은 [Teams에서 사용할 수 있는 모든 유형의 앱에](deploy-apps-microsoft-teams-landing-page.md) 적용됩니다. 앱 권한 정책을 사용하는 몇 가지 예제 시나리오는 다음과 같습니다.

* 처음에는 일부 사용자와 모든 사용자에게 앱을 점진적으로 롤아웃합니다.
* HR 부서의 구성원에 대해서만 사용자 지정 채용 및 인재 관리 앱을 허용하고 다른 모든 조직 사용자에 대해 차단합니다.

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="앱 권한 정책의 스크린샷." lightbox="media/app-permission-policy.png":::

자세한 내용은 [앱 권한 정책을 관리하는 방법을](teams-app-permission-policies.md) 참조하세요.

## <a name="app-setup-policies"></a>앱 설정 정책

앱 설정 정책을 사용하면 Teams 클라이언트에서 사용자가 사용할 수 있는 앱의 방법과 위치를 구성할 수 있습니다. Teams 클라이언트의 앱 표시줄에 고정하려는 앱을 선택하고 앱이 표시되는 순서를 정의합니다.

앱을 고정하거나 설치하면 조직에서 원하는 앱을 인식하고 채택하는 데 도움이 됩니다. 변경 내용은 웹, 데스크톱 및 모바일 Teams 클라이언트에 적용됩니다.

앱 설정 정책을 사용하는 몇 가지 예제 시나리오는 다음과 같습니다.

* HR 팀 구성원을 위한 사용자 지정 채용 및 인재 관리 앱을 고정합니다.
* 조직의 사용자에 대해 미리 고정된 핵심 앱의 순서를 변경합니다.

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Teams 관리 센터의 앱 설정 정책 스크린샷." lightbox="media/app-setup-policy.png":::

자세한 내용은 [앱 설정 정책 관리 방법](teams-app-setup-policies.md)을 참조하세요.

### <a name="option-to-upload-custom-apps"></a>사용자 지정 앱을 업로드하는 옵션

조직에서 조직 관련 요구 사항에 맞는 사용자 지정 앱 생성을 의뢰할 수도 있습니다. 조직 내 개발자는 조직의 내부 Teams 사용자를 위해 사용자 지정 앱을 빌드, 테스트 및 배포할 수 있습니다. 앱 설정 정책을 사용하여 조직에서 사용자 지정 앱을 업로드할 수 있는 사용자를 제어합니다. 조직 전체 설정을 사용하여 최종 사용자가 사용자 지정 앱을 사용할 수 있도록 허용합니다. 사용 권한 정책을 사용하여 특정 최종 사용자만 사용자 지정 앱을 사용하도록 허용합니다.

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="조직 전체 설정 패널에서 조직에 사용자 지정 앱을 허용하는 방법을 보여 주는 스크린샷" lightbox="media/custom-app-policy.png":::

자세한 내용은 [사용자 지정 앱에 대한 정책 및 설정을 관리하는 방법을 참조하세요](teams-custom-app-policies-and-settings.md).

## <a name="related-articles"></a>관련 기사

* [정책을 준수하여 Teams 관리](manage-teams-with-policies.md)
* [앱 사용 권한 정책 관리](teams-app-permission-policies.md)
* [앱 설정 정책 관리](teams-app-setup-policies.md)
* [사용자 지정 앱에 대한 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)
