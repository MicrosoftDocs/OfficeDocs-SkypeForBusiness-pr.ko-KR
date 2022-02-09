---
title: 앱 업데이트 환경 Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
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
description: 앱에서 앱을 업데이트하는 Microsoft Teams.
ms.openlocfilehash: bcece8d3b6da3f0e89694b29d61752634ea1bc18
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62409871"
---
# <a name="update-apps-in-microsoft-teams"></a>앱 업데이트 Microsoft Teams

대부분의 경우 앱 개발자가 앱 업데이트를 게시하면 새 버전이 사용자에게 자동으로 나타납니다. 그러나 사용자 수락을 완료해야 하는 <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank"></a> Microsoft Teams 매니페스트에 대한 몇 가지 업데이트가 있습니다.

* 봇이 추가되거나 제거되었습니다.
* 기존 봇의 "botId" 속성이 변경된 경우
* 기존 봇의 "isNotificationOnly" 속성이 변경된 경우
* 봇의 SupportsCalling, SupportsVideo 및 SupportsFiles 기능이 추가되었습니다.
* 메시징 확장이 추가되었습니다.
* 새 커넥터가 추가되었습니다.
* "webApplicationInfo" 내부 속성이 변경되었습니다.

![새 버전을 사용할 수 있습니다.](media/manage-your-custom-apps-update1.png)

![앱의 업그레이드 옵션입니다.](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> 업데이트 프로세스는 Microsoft 앱, 사용자 지정 앱 및 타사 앱에 대한 모든 앱 업데이트에 적용됩니다. 

## <a name="related-topics"></a>관련 항목

[앱 관리](manage-apps.md)
