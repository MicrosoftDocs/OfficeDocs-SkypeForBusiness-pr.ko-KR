---
title: Microsoft Teams의 외부(페더레이션된) 사용자를 위한 네이티브 채팅 환경
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 두 사용자가 TeamsOnly 업그레이드 모드에 있는 Microsoft Teams의 외부 액세스(페더레이션된) 사용자를 위한 네이티브 Teams 채팅 환경에 대해 알아봅니다.
ms.openlocfilehash: 134216364fdd7397d8a7d72a2ae6684cfa9f90b4
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198880"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Microsoft Teams의 외부(페더레이션된) 사용자를 위한 네이티브 채팅 환경

Microsoft Teams 사용자가 외부(페더레이션된) 사용자와 채팅하는 경우 채팅 환경은 텍스트로 제한됩니다. 그러나 Teams 사용자와 다른 조직의 사용자가 TeamsOnly 업그레이드 모드에 있는 경우 풍부한 서식, @mentions 및 기타 채팅 기능을 포함하는 "네이티브 Teams 채팅 환경"을 가질 수 있습니다.

다른 조직의 사용자에 대한 네이티브 채팅 환경은 모든 Teams 테넌트에서 켜져 있지만 모든 사용자가 자격이 있는 것은 아닙니다. 네이티브 채팅 환경을 제공하려면 보낸 사람 및 수신자 모두를 TeamsOnly 업그레이드 모드로 구성해야 합니다. 업그레이드 정책에 대한 자세한 내용은 [공존 및 업그레이드 설정 설정을 참조하세요](setting-your-coexistence-and-upgrade-settings.md).

Teams의 외부 액세스 사용자에 대한 기능 목록을 보려면 [외부 및 게스트 액세스 비교](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)를 참조하세요.

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>네이티브 채팅에 있는지 어떻게 할까요? 알 수 있나요?

채팅에서 다른 조직의 사용자와만 텍스트를 교환할 수 있는 경우 표준 외부 액세스(페더레이션된) 채팅에 있는 것입니다. 서식, @mentions, 이모지 등 다른 채팅 기능이 있다면 네이티브 Teams 채팅에 있습니다. 

Teams는 정기적으로 다른 조직의 사용자에 대한 업그레이드 모드를 확인하고 TeamsOnly 업그레이드 모드에서 Teams를 실행하는 사용자를 찾으면 기본 Teams 채팅으로 전환하고 원래 채팅을 잠그라는 메시지가 표시됩니다.

네이티브 Teams 채팅으로 전환하면 Teams는 두 대화를 병합하지 않습니다. 대신 채팅 피드에 두 채팅이 모두 표시됩니다. 새로운 네이티브 Teams 채팅은 활성 상태이지만 이전 텍스트 전용 채팅은 잠겨 있습니다.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>사용자가 Teams 전용 모드에 더 이상 없으면 어떻게 되나요?

다른 조직의 사람들과 네이티브 Teams 채팅을 한 다음 TeamsOnly 업그레이드 모드에서 전환된 경우 Teams는 네이티브 Teams 채팅을 잠그고 제한된 텍스트 전용 채팅에 대한 링크를 제공합니다. 네이티브 Teams 채팅에서는 계속할 수 없습니다. 여전히 네이티브 Teams 채팅을 읽을 수 있지만 대화를 계속할 수는 없습니다.

Teams에서 이 사용자와 오래된 텍스트 전용 채팅을 찾으면 해당 채팅이 다시 활성화됩니다. 그렇지 않으면 Teams에서 새 텍스트 전용 채팅을 만듭니다.


## <a name="related-topics"></a>관련 주제

[Teams에서 외부 액세스 관리](manage-external-access.md)
