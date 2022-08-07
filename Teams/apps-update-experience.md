---
title: Microsoft Teams의 앱 업데이트 환경
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
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
ms.localizationpriority: high
search.appverid: MET150
description: 이 문서에서는 Microsoft Teams의 Microsoft 앱, 사용자 지정 앱 및 타사 앱이 어떻게 업데이트되는지 알아봅니다.
ms.openlocfilehash: bcd06b9814b03d917014d8136f51a280e30007d1
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272063"
---
# <a name="update-apps-in-microsoft-teams"></a>Microsoft Teams에서 앱 업데이트

대부분의 경우 앱 개발자가 앱 업데이트를 게시한 후 새 버전이 사용자에게 자동으로 표시됩니다. 그러나 완료하려면 사용자 동의가 필요한 [Microsoft Teams 매니페스트](/microsoftteams/platform/resources/schema/manifest-schema)에 대한 일부 업데이트가 있습니다.

* 봇이 추가 또는 제거되었습니다.
* 기존 봇의 "botId" 속성이 변경되었습니다.
* 기존 봇의 "isNotificationOnly" 속성이 변경되었습니다.
* 봇의 SupportsCalling, SupportsVideo 및 SupportsFiles 기능이 추가되었습니다.
* 메시징 확장이 추가되었습니다.
* 새로운 커넥터가 추가되었습니다.
* "권한 부여" 내의 권한이 추가 또는 변경되었습니다.

:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="새 버전을 사용할 수 있습니다." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="앱의 업그레이드 옵션." lightbox="media/manage-your-custom-apps-update2.png":::

> [!NOTE]
> 업데이트 프로세스는 Microsoft 앱, 사용자 지정 앱 및 타사 앱에 대한 모든 앱 업데이트에 적용됩니다.
