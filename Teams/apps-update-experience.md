---
title: 앱 업데이트 환경 Microsoft Teams
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: 앱에서 앱을 업데이트하는 Microsoft Teams.
ms.openlocfilehash: a1a5cc6d926e7bc183db9950f1d11c1e3ffcd06c
ms.sourcegitcommit: 85017cf88789c750836780dad2ef707c1c6c39b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2021
ms.locfileid: "58359145"
---
# <a name="update-apps-in-microsoft-teams"></a>앱 업데이트 Microsoft Teams

대부분의 경우 앱 개발자가 앱 업데이트를 게시하면 새 버전이 사용자에게 자동으로 나타납니다. 그러나 사용자 수락을 <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank"></a> 완료해야 하는 Microsoft Teams 매니페스트에 대한 몇 가지 업데이트가 있습니다.

* 봇이 추가되거나 제거되었습니다.
* 기존 봇의 "botId" 속성이 변경된 경우
* 기존 봇의 "isNotificationOnly" 속성이 변경된 경우
* 봇의 SupportsCalling, SupportsVideo 및 SupportsFiles 기능이 추가되었습니다.
* 메시징 확장이 추가되었습니다.
* 새 커넥터가 추가되었습니다.
* "webApplicationInfo" 내부 속성이 변경되었습니다.

![새 버전 사용 가능](media/manage-your-custom-apps-update1.png)

![앱의 업그레이드 옵션](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> 업데이트 프로세스는 Microsoft 앱, 사용자 지정 앱 및 타사 앱에 대한 모든 앱 업데이트에 적용됩니다. 

## <a name="related-topics"></a>관련 항목

[앱 관리](manage-apps.md)
