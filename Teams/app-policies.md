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
ms.openlocfilehash: 8e059199d4963004e287b456c98bb80717f849b3
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912437"
---
# <a name="know-about-policies-to-manage-access-and-installation-of-teams-apps"></a>Teams 앱의 액세스 및 설치를 관리하는 정책에 대해 알아보기

Microsoft Teams는 앱 정책을 사용하여 앱의 액세스 및 설치 동작을 제어합니다. 앱 정책은 Teams 관리자가 다음 앱 동작을 제어하는 데 도움이 됩니다.

* 각 개별 사용자 또는 사용자 그룹에 대한 앱 액세스를 구성합니다. 관리자가 각 최종 사용자에게 허용되는 앱을 제어하는 데 도움이 됩니다.

* 조직의 요구 사항과 관련된 최종 사용자를 위해 해당 앱을 고정합니다. 또한 관리자는 사용자 개입 없이 최종 사용자용 앱을 설치할 수 있습니다. 최종 사용자가 관련 앱을 쉽게 시작할 수 있도록 도와줍니다.

* 관리자 승인을 위해 조직에서 사용자 지정 앱을 제출할 수 있는 개발자를 제어합니다. 사용자 지정 앱 업로드 기능에 대한 액세스를 제어하는 데 도움이 됩니다.

## <a name="app-permission-policies"></a>앱 사용 권한 정책

앱 사용 권한 정책을 사용하여 Teams 관리자는 조직의 각 사용자가 사용할 수 있는 앱을 제어합니다. 모든 사용자에 대해 몇 가지 앱을 허용하거나, 특정 사용자 그룹에 대해 몇 가지 앱을 허용하거나, 특정 사용자에 대해 특정 앱을 허용할 수 있습니다. 앱 권한 정책은 조직 전체 설정과 함께 작동하며 각 개별 앱의 상태를 허용하거나 차단합니다.

앱 권한 정책은 [Teams에서 사용할 수 있는 모든 유형의 앱에](deploy-apps-microsoft-teams-landing-page.md) 적용됩니다. 앱 권한 정책을 사용하는 몇 가지 예제 시나리오는 다음과 같습니다.

* 처음에는 일부 사용자와 모든 사용자에게 앱을 점진적으로 롤아웃합니다.
* HR 부서의 구성원만 채용 및 인재 관리를 위한 사용자 지정 앱을 허용하고 다른 모든 조직 사용자에 대해 차단합니다.

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="앱 권한 정책의 스크린샷." lightbox="media/app-permission-policy.png":::

자세한 내용은 [앱 권한 정책을 관리하는 방법을 참조하세요](teams-app-permission-policies.md).

## <a name="app-setup-policies"></a>앱 설정 정책

앱 설정 정책을 사용하면 Teams 클라이언트의 사용자가 앱을 사용할 수 있는 방법과 위치를 구성할 수 있습니다. Teams 클라이언트의 앱 표시줄에 고정하려는 앱을 선택하고 앱이 표시되는 순서를 정의합니다.

앱을 고정하거나 설치하면 조직에서 원하는 앱을 인식하고 채택하는 데 도움이 됩니다. 변경 내용은 웹, 데스크톱 및 모바일 Teams 클라이언트에 적용됩니다.

앱 설정 정책을 사용하는 몇 가지 예제 시나리오는 다음과 같습니다.

* HR 팀 구성원을 위한 사용자 지정 채용 및 인재 관리 앱을 고정합니다.
* 조직의 사용자에 대한 고정을 사용하여 [핵심 앱](deploy-apps-microsoft-teams-landing-page.md#core-apps) 의 순서를 변경합니다.

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Teams 관리 센터의 앱 설정 정책 스크린샷." lightbox="media/app-setup-policy.png":::

자세한 내용은 [앱 설정 정책 관리 방법](teams-app-setup-policies.md)을 참조하세요.

### <a name="option-to-upload-custom-apps"></a>사용자 지정 앱을 업로드하는 옵션

조직에서 조직 관련 요구 사항에 맞는 사용자 지정 앱 생성을 의뢰할 수도 있습니다. 조직 내 개발자는 조직의 Teams 내부 사용자를 위한 사용자 지정 앱을 빌드, 테스트 및 배포할 수 있습니다. 앱 설정 정책을 사용하여 조직에서 사용자 지정 앱을 업로드할 수 있는 사용자를 제어합니다. 조직 전체 설정을 사용하여 최종 사용자가 사용자 지정 앱을 사용할 수 있도록 허용합니다. 사용 권한 정책을 사용하여 특정 최종 사용자만 사용자 지정 앱을 사용하도록 허용합니다.

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="조직 전체 설정 패널에서 조직에 사용자 지정 앱을 허용하는 방법을 보여 주는 스크린샷" lightbox="media/custom-app-policy.png":::

자세한 내용은 [사용자 지정 앱에 대한 정책 및 설정을 관리하는 방법을 참조하세요](teams-custom-app-policies-and-settings.md).

## <a name="related-articles"></a>관련 기사

* [정책을 준수하여 Teams 관리](manage-teams-with-policies.md)
* [앱 사용 권한 정책 관리](teams-app-permission-policies.md)
* [앱 설정 정책 관리](teams-app-setup-policies.md)
* [사용자 지정 앱에 대한 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)
