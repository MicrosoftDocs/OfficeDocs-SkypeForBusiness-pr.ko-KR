---
title: Microsoft 팀의 외부 (페더레이션된) 사용자를 위한 기본 채팅 환경
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: 모든 사용자가 팀 전용 업그레이드 모드에 있는 외부 사용자 간에 사용할 수 있는 Microsoft 팀의 외부 액세스 (페더레이션된) 사용자를 위한 기본 팀 채팅 환경에 대해 알아봅니다.
ms.openlocfilehash: 572087d86672294b566cd99365599dbead1aa3e7
ms.sourcegitcommit: 1448bb2e66074322b8f4bf234fce36ea9c8f9913
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "39966761"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Microsoft 팀의 외부 (페더레이션된) 사용자를 위한 기본 채팅 환경
======================================

Microsoft 팀 사용자가 외부 (페더레이션된) 사용자와 채팅을 하는 경우 채팅 환경은 텍스트로 제한 됩니다. 그러나 팀 테 넌 트가 나 외부 사용자가 모두 TeamsOnly 업그레이드 모드인 경우, 다양 한 서식, @mentions, 기타 채팅 기능을 포함 하는 "기본 팀 채팅 환경"이 있을 수 있습니다. 즉, 조직의 사용자와 마찬가지로, 적격 외부 사용자와 동일한 다양 한 1:1 팀 채팅 환경을 제공할 수 있습니다. 외부 사용자와의 기본 팀 채팅은 여전히 1:1 채팅으로 제한 됩니다 (외부 사용자는 그룹 채팅을 수행할 수 없음).

외부 사용자에 대 한 기본 채팅 환경은 모든 팀 테 넌 트에 대해 설정 되어 있지만 모든 사용자가 사용할 수 있는 것은 아닙니다. 기본 채팅 환경을 제공 하려면 발신자와 수신자가 모두 TeamsOnly 업그레이드 모드를 실행 하는 팀 테 넌 트에 있어야 합니다. 업그레이드 정책에 대해 자세히 알아보려면 [공존 및 업그레이드 설정 설정을](setting-your-coexistence-and-upgrade-settings.md)참조 하세요.

팀의 외부 액세스 사용자에 대 한 기능 목록을 보려면 [외부 및 게스트 액세스 비교](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)를 참조 하세요.

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>기본 채팅을 하 고 있는지 어떻게 알 수 있나요?

외부 사용자와 채팅의 텍스트만 교환할 수 있는 경우에는 표준 외부 액세스 (페더레이션된) 채팅을 사용 하 고 있는 것입니다. 서식, @mentions, emojis 등의 다른 채팅 기능을 모두 사용 하는 경우, 외부 사용자와의 기본 팀 채팅을 하 고 있는 것입니다. 

팀은 외부 사용자에 대 한 업그레이드 모드를 정기적으로 확인 하 고, 팀의 다른 업그레이드 모드에서 실행 중인 외부 사용자가 발견 되 면 기본 팀 채팅으로 전환 하 여 원래 채팅을 잠그려고 하 라는 메시지를 표시 합니다.

기본 팀 채팅으로 전환 하는 경우 팀은 두 대화를 병합 하지 않습니다. 대신 채팅 피드의 채팅을 모두 볼 수 있습니다. 새로운 기본 팀 채팅은 활성 이지만, 이전 텍스트 전용 채팅은 잠겨 있습니다.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>사용자가 팀 전용 모드에 있지 않은 경우에는 어떻게 되나요?

외부 사용자와 기본 팀이 채팅을 하 고 있는 경우, 팀은 자신에 게 기본 팀 채팅을 잠그고 제한 된 텍스트만 채팅에 대 한 링크를 제공 합니다. 기본 팀 채팅에서 계속할 수 없게 됩니다. 기본 팀 채팅은 계속 읽을 수 있지만, 대화를 계속 진행 하는 것은 불가능 합니다.

팀이이 외부 사용자와 함께 오래 된 텍스트 전용 채팅을 발견 하면 해당 채팅을 회복 됩니다. 그렇지 않으면 팀이 새로운 텍스트 전용 채팅을 만듭니다.


## <a name="related-topics"></a>관련 항목

[팀에서 외부 액세스 관리](manage-external-access.md)
