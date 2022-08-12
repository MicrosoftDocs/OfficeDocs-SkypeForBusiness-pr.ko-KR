---
title: Microsoft Teams의 앱 업데이트 환경
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 이 문서에서는 Microsoft Teams의 Microsoft 앱, 사용자 지정 앱 및 타사 앱을 업데이트하는 방법과 관리자가 이를 용이하게 하는 방법을 알아봅니다.
ms.openlocfilehash: ed91ad441b773833838796d9ea8c71038c842b88
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299047"
---
# <a name="update-apps-in-microsoft-teams"></a>Microsoft Teams에서 앱 업데이트

대부분의 경우 Teams 스토어에서 새 버전의 앱을 사용할 수 있게 되면 사용자를 위해 앱이 자동으로 업데이트됩니다. 그러나 새 앱 버전의 몇 가지 특정 변경 사항을 적용하려면 앱 업데이트에 대한 사용자 동의가 필요합니다. 사용자 동의는 기능 또는 액세스와 같은 변경 사항에 대한 인식을 보장합니다. 앱 개발자가 Microsoft Teams 앱을 다음과 같이 구체적으로 변경할 경우 최종 사용자가 앱 업데이트를 승인해야 합니다.

* 봇이 추가됩니다.
* 기존 봇의 `botId` 속성 또는 `isNotificationOnly` 속성이 변경됩니다.
* 봇의 `SupportsCalling`, `SupportsVideo`, `SupportsFiles` 기능이 추가됩니다.
* 메시징 확장이 추가됩니다.
* 권한 부여 내의 사용 권한이 추가되거나 변경됩니다.
* `Id` 또는 `ApplicationPermissionsHash` 또는 둘 다 `webApplicationInfo` 내에서 변경됩니다.

<!--- image update
:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="New version available." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="Upgrade option for an app." lightbox="media/manage-your-custom-apps-update2.png":::
--->

## <a name="related-articles"></a>관련 기사

* [앱에서 수행된 업데이트에 대한 매니페스트 스키마를 이해합니다.](/microsoftteams/platform/resources/schema/manifest-schema).
