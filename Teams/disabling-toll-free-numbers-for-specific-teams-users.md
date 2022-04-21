---
title: 특정 Teams 사용자에 대해 무료 전화 번호 비활성화
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 이끌이가 오디오 회의 브리지 모임에 무료 번호를 사용하는 방법을 제어하는 방법을 알아봅니다.
ms.openlocfilehash: 6d841a48381609a019a1749095aac4a95901a7c4
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2022
ms.locfileid: "65016630"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>특정 Teams 사용자에 대해 무료 전화 번호 비활성화

조직에 Microsoft Audio Conferencing Bridge의 무료 번호가 있는 경우 특정 이끌이 모임에서 해당 사용자의 사용을 허용하거나 방지할 수 있습니다.  

기본적으로 조직의 모든 사용자는 무료 번호를 사용할 수 있습니다. 즉, 해당 번호를 사용할 수 있는 경우 참가자가 모임에 참가하는 데 사용할 수 있습니다. 조직의 일부 사용자에게 원하는 동작이 아닌 경우 무료 번호 사용 제어를 통해 특정 사용자가 모임에서 해당 숫자를 사용하지 못하도록 제한할 수 있습니다.

지정된 이끌이에 대해 무료 번호가 사용하지 않도록 설정된 경우:

- 무료 번호는 모임 초대에 더 이상 포함되지 않습니다.
- 무료 번호는 모임 초대에서 참조되는 "로컬 번호 찾기" 페이지에 더 이상 나열되지 않습니다.
- 참가자는 무료 조직 번호로 전화를 걸면 지정된 이끌이의 모임에 참가할 수 없습니다.
- 참가자는 요금 번호를 사용하여 이끌이의 모임에 계속 참가할 수 있습니다.

## <a name="disabling-toll-free-numbers-for-specific-users"></a>특정 사용자의 무료 전화 번호 사용 안 함

해당 사용자에게 할당된 *TeamsAudioConferencingPolicy* 내에서 *AllowTollFreeDialIn* 에 대한 설정을 **Off** 로 변경하여 특정 사용자에 대해 무료 번호를 사용하지 않도록 설정할 수 있습니다. 이러한 사용자가 만든 새 모임이 해제되면 무료 전화 번호는 포함되지 않습니다. [유료 및 무료 번호에 대한 오디오 회의 정책 설정에는](audio-conferencing-toll-free-numbers-policy.md) 자세한 정보가 있습니다.

> [!IMPORTANT]
> 이전 및 이전에 예약된 되풀이 모임은 여전히 무료 번호를 표시할 수 있으며 참가자는 무료 번호를 사용하여 이러한 모임에 참가할 수 없습니다. 이러한 사용자에 대한 모든 이전 및 되풀이 모임의 일정을 조정하고 MMS를 사용하여 수신자 부담 전화 번호를 제거할 수 있습니다.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
