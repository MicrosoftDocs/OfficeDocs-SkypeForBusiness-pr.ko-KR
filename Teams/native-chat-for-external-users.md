---
title: 외부(페더리화) 사용자에 대한 네이티브 채팅 Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 두 사용자가 TeamsOnly 업그레이드 모드에 Teams 외부 액세스(페더리화) 사용자에 대한 네이티브 Microsoft Teams 채팅 환경에 대해 자세히 알아보습니다.
ms.openlocfilehash: 992b4dd28d17f1ba8abf7217d622da18813c3118
ms.sourcegitcommit: 74d3ab35c344d70b2399bc46a6ced3ab2762a470
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60138234"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>외부(페더리화) 사용자에 대한 네이티브 채팅 Microsoft Teams

사용자가 Microsoft Teams(페더리화) 사용자와 채팅하는 경우 채팅 환경은 텍스트로 제한됩니다. 그러나 사용자와 다른 조직의 Teams 모두 TeamsOnly 업그레이드 모드에 있는 경우 서식, Teams 및 기타 채팅 기능을 포함하는 "네이티브 Teams 채팅 환경"을 @mentions 수 있습니다.

다른 조직의 사용자에 대한 네이티브 채팅 환경은 모든 테넌트에 대해 Teams 있지만 모든 사용자에 대해 자격이 없습니다. 네이티브 채팅 환경을 제공하려면 발신자 및 수신기를 TeamsOnly 업그레이드 모드로 구성해야 합니다. 업그레이드 정책에 대한 자세한 내용은 공존 및 업그레이드 설정 설정을 [읽어 보십시오.](setting-your-coexistence-and-upgrade-settings.md)

외부 액세스 사용자에 대한 기능 목록을 Teams 및 게스트 액세스 비교를 [참조하세요.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>네이티브 채팅에 있는 경우 어떻게 알 수 있나요?

채팅의 텍스트만 다른 조직의 사용자와 교환할 수 있는 경우 표준 외부 액세스(페더리화된) 채팅에 있습니다. 서식, @mentions, 이모지 등 다른 채팅 기능이 있는 경우 네이티브 채팅에 Teams 있습니다. 

Teams 다른 조직의 사용자에 대한 업그레이드 모드를 정기적으로 확인하고 TeamsOnly 업그레이드 모드에서 Teams 실행 중인 사용자가 발견될 때 기본 채팅으로 전환하고 원래 채팅을 Teams 메시지가 표시됩니다.

네이티브 채팅으로 전환하면 Teams 대화가 Teams 병합되지 않습니다. 대신 채팅 피드에 두 채팅이 모두 표시됩니다. 새 네이티브 Teams 채팅이 활성화되어 있지만 이전 텍스트 전용 채팅은 잠겨 있습니다.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>사용자가 더 이상 전용 모드에 Teams 경우 어떻게 하나요?

다른 조직의 Teams 사용자와 채팅을 하다가 TeamsOnly 업그레이드 모드에서 전환되는 경우 네이티브 Teams 채팅을 Teams 제한된 텍스트 전용 채팅에 대한 링크를 제공합니다. 네이티브 채팅에서 계속할 수 Teams 없습니다. 네이티브 채팅을 계속 읽을 Teams 있지만 대화를 계속할 수 없습니다.

이 Teams 텍스트 전용 채팅을 찾은 경우 해당 채팅이 다시 표시됩니다. 그렇지 Teams 새 텍스트 전용 채팅을 만듭니다.


## <a name="related-topics"></a>관련 항목

[외부 액세스 관리 Teams](manage-external-access.md)
