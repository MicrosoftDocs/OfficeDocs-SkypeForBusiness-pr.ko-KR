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
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 이 문서에서는 Microsoft Teams의 Microsoft 앱, 사용자 지정 앱 및 타사 앱을 업데이트하는 방법을 알아봅니다.
ms.openlocfilehash: 27d51a487af918e6fcee2b7806c81d31506bd1af
ms.sourcegitcommit: 70185cd963c5a9d539e65e302d4230018209ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2022
ms.locfileid: "66958043"
---
# <a name="update-apps-in-microsoft-teams"></a>Microsoft Teams에서 앱 업데이트

대부분의 경우 앱 개발자가 앱 업데이트를 게시하면 사용자에 대해 새 버전이 자동으로 표시됩니다. 그러나 [Microsoft Teams 매니페스트](/microsoftteams/platform/resources/schema/manifest-schema) 에 대한 일부 업데이트는 사용자가 동의해야 완료해야 합니다.

* 봇이 추가되거나 제거되었습니다.
* 기존 봇의 "botId" 속성이 변경되었습니다.
* 기존 봇의 "isNotificationOnly" 속성이 변경되었습니다.
* 봇의 SupportsCalling, SupportsVideo 및 SupportsFiles 기능이 추가되었습니다.
* 메시징 확장이 추가되었습니다.
* 새 커넥터가 추가되었습니다.
* "권한 부여" 내의 사용 권한이 추가되거나 변경되었습니다.

:::image type="content" source="media/manage-your-custom-apps-update1.png" alt-text="새 버전을 사용할 수 있습니다." lightbox="media/manage-your-custom-apps-update1.png":::

:::image type="content" source="media/manage-your-custom-apps-update2.png" alt-text="앱에 대한 업그레이드 옵션입니다." lightbox="media/manage-your-custom-apps-update2.png":::

> [!NOTE]
> 업데이트 프로세스는 Microsoft 앱, 사용자 지정 앱 및 타사 앱에 대한 모든 앱 업데이트에 적용됩니다.
