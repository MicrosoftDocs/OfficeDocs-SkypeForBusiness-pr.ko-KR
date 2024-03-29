---
title: 비교육 테넌트용 감독 채팅 사용
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.custom: chat-teams-channels-revamp
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams 모임에서 비교육 테넌트용 감독 채팅에 대해 알아봅니다.
ms.collection:
- M365-collaboration
ms.openlocfilehash: dc7ddf23b600ec2a7f4d4f02c2328587627572fc
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198290"
---
# <a name="supervised-chats-for-non-educational-tenants"></a>비교육 테넌트용 감독 채팅

감독 채팅을 사용하면 지정된 감독자가 조직의 모든 사용자와 채팅을 시작하고 적절한 감독자가 없는 한 제한된 사용자가 새 채팅을 시작하지 못하도록 차단할 수 있습니다. 채팅 감독을 사용하도록 설정하면 감독자는 채팅을 종료할 수 없으며 다른 참가자는 채팅을 제거할 수 없으므로 제한된 사용자와 관련된 채팅이 제대로 감독되도록 합니다.

이러한 제한 사항은 감독된 채팅이 완전히 활성화된 후에 만들어진 새 비공개 채팅에만 적용됩니다. 기존 비공개 채팅, 모임 채팅 또는 채널에는 적용되지 않습니다.

감독 채팅은 교육 기관의 요구에 맞게 조정되지만 비 교육 테넌트에서도 사용할 수 있습니다.

> [!NOTE]
> 감독된 채팅은 기능이 적용된 후 만든 새 채팅을 보호합니다. 기존 채팅은 보호하지 않습니다.

## <a name="enable-supervised-chat"></a>감독된 채팅 사용

> [!NOTE]
> 감독되지 않는 채팅에 대한 사용자 액세스를 원치 않게 제한하지 않도록 기관에 채팅을 사용하도록 설정하기 전에 채팅 권한 역할 및 역할 기반 채팅 권한 정책을 설정했는지 확인합니다.

**사용자 환경의 각 사용자에 대한 채팅 권한 역할을 정의합니다**.

감독된 채팅이 예상대로 작동하려면 환경 내의 각 사용자에게 올바른 채팅 권한 역할이 할당되어야 합니다. 사용자에게 할당할 수 있는 세 가지 역할이 있습니다.

- 전체 권한: 이 역할은 사용자 환경의 채팅 감독자에게 할당되어야 합니다. 사용자 환경 내의 모든 사용자와 채팅을 시작할 수 있습니다. 전체 권한이 있는 사용자는 참여하는 채팅을 감독해야 합니다. 페더레이션 테넌트에서 감독하는 채팅 또는 시작하는 채팅에서 나가거나 제거할 수 없습니다.

- 제한된 권한: 이 역할은 제한된 사용자에 대해서만 감독된 액세스 권한이 있어야 하는 직원에게 적합합니다. 전체 또는 제한된 사용자와 채팅을 시작할 수 있지만 제한된 사용자와 채팅을 시작할 수는 없습니다. 전체 권한이 있는 사용자가 제한된 사용자와 채팅을 시작하는 경우 제한된 사용자를 대화로 가져올 수 있습니다. 이 액세스는 제한된 사용자와 제한된 사용자 간의 공동 작업을 감독할 수 있는 모든 권한이 있는 사용자가 있기 때문에 발생합니다.

- 제한된 권한: 이 역할은 감독해야 하는 사용자에게 적합합니다. 전체 권한이 있는 사용자와만 채팅을 시작할 수 있습니다. 모든 권한이 있는 사용자가 초대하는 모든 대화에 참여할 수 있습니다. 페더레이션된 채팅의 경우 제한된 사용자는 제한된 사용자의 테넌트에서 온 모든 권한이 있는 사용자만 채팅에 추가할 수 있습니다.

사용자의 채팅 권한 역할을 설정하려면 Teams 관리 포털의 메시징 정책 옵션에 있는 **채팅 권한 역할** 정책을 사용합니다. PowerShell을 사용하여 Full, Limited 또는 Restricted 값으로 ChatPermissionRole 정책을 사용하여 역할을 정의할 수 있습니다. 이 정책은 [CsTeamsMessagingPolicy 아래에 있습니다](/powershell/module/skype/set-csteamsmessagingpolicy).

테넌트의 게스트에는 역할을 할당할 수 없습니다. 게스트에게 제한된 역할이 할당됩니다.

## <a name="allow-supervised-chat"></a>감독된 채팅 허용

테넌트에서 감독된 채팅은 기본적으로 사용하지 않도록 설정됩니다. 사용자에 대한 채팅 권한 역할을 설정한 후 **Teams Teams** \> **설정** 으로 이동하고 **역할 기반 채팅 권한** 정책을 **켜** 기로 설정하여 테넌트 내에서 감독된 채팅을 사용하도록 설정할 수 있습니다. AllowRoleBasedChatPermissions를 True로 설정하여 PowerShell을 사용하여 감독된 채팅을 사용하도록 설정할 수도 있습니다. 이 cmdlet은 [CsTeamsClientConfiguration 아래에 있습니다](/powershell/module/skype/set-csteamsclientconfiguration).

테넌트 내의 모든 사용자에 대해 감독된 채팅을 사용하도록 설정해야 하며 사용자의 일부에 대해서만 사용하도록 설정할 수 없습니다.

**채팅 사용**:

Teams 관리 센터에서 사용할 수 있는 기존 채팅 정책을 사용하여 모든 사용자에게 채팅을 사용하도록 설정합니다.

**감독된 채팅 유지 관리**:

감독된 채팅을 처음 사용하도록 설정한 후에는 사용자 환경의 채팅이 감독된 상태로 유지되도록 몇 가지 작업을 수행해야 합니다.

- 테넌트 가입하는 모든 새 사용자에게 적절한 역할을 할당합니다. 기본적으로 사용자에게 제한된 역할이 할당됩니다.

- 모든 권한이 있는 사용자가 테넌트에서 나가거나 제거되면 감독하던 채팅은 무인 상태로 남게 됩니다. 원래 사용자를 제거하기 전에 채팅을 감독할 수 있도록 전체 권한이 있는 다른 사용자가 이러한 대화에 추가되었는지 확인합니다. 원래 감독자가 제거되면 새 참가자를 대화에 추가할 수 없지만 현재 참가자는 계속 통신할 수 있습니다.
