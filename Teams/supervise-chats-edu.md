---
title: 감독 채팅 사용
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 모임에서 감독되는 채팅에 대해 Microsoft Teams.
ms.openlocfilehash: e705120eb2f8b92ea437c78be67c139018f786fc
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506688"
---
# <a name="supervised-chats-in-microsoft-teams"></a>관리자의 감독된 Microsoft Teams

교육 기관은 학생들에게 안전하고 건강한 디지털 공간을 제공합니다. 디지털 공간에는 전자 메일, 온라인 모임 및 통화 및 메시지가 Teams. 부적절한 메시징 동작을 방지하기 위해 많은 학교에서 개인 채팅을 사용하지 않도록 Teams. 안타깝게도 채팅을 사용할 수 없습니다. 또한 교사가 개인 설정된 학습을 위해 학생에게 비공개로 다가설 수 있는 기회도 차단됩니다. 채팅을 사용하지 않도록 설정하면 수업 팀에 메시지를 공개적으로 게시하지 않을 경우 학생들은 교사에게 다가가지 못합니다.

감독된 채팅을 사용하면 지정된 교사가 학생과 채팅을 시작하고 적절한 교사가 없는 한 학생이 새 채팅을 시작하는 데 차단할 수 있습니다. 채팅 감독을 사용하도록 설정하면 감독자는 채팅을 떠날 수 없습니다. 다른 참가자는 채팅을 제거할 수 없습니다. 학생과 관련된 채팅이 제대로 감독되었는지 확인합니다.

이러한 제한은 감독된 채팅이 완전히 활성화된 후에 생성된 새 개인 채팅에만 적용됩니다. 기존 개인 채팅, 모임 채팅 또는 채널에는 적용되지 않습니다. 모임 채팅, 채널 안전 및 학생 안전 유지에 대한 모범 사례에 대한 자세한 내용은 을 사용하는 동안 학생 [안전을 Teams.](https://support.microsoft.com/topic/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8?ui=en-us&rs=en-us&ad=us#ID0EBBAAA=For_educators&ID0EDD=For_educators)

> [!Note]
> 감독 채팅은 기능이 적용된 후 생성된 새 채팅을 보호합니다.  기존 채팅을 보호하지 않습니다.

## <a name="review-use-cases-for-supervised-chats"></a>감독된 채팅에 대한 사용 사례 검토

다음 예제는 감독된 채팅이 필요한 경우의 설명입니다.

- 학생들이 공개적으로 질문을 공유하거나 질문하는 것이 편하지 않을 때 교사와의 1.1 후속조치.

- 과제, 최근 수업 상호 작용(또는 부족) 또는 기타 항목에 대해 학생에게 1.1에 도달하는 교사.

- 교사가 모니터링하는 학생 그룹 토론.

- 교사가 아닌 교직원이 감독되는 환경에서 학생과 채팅할 수 있도록 허용합니다.

## <a name="enable-supervised-chat"></a>감독 채팅 사용

> [!Note]
> 교육 기관에 대해 채팅을 사용하도록 설정하기 전에 채팅 권한 역할 및 역할 기반 채팅 권한 정책을 설정하여 관리되지 않은 채팅에 대한 원치 않는 학생 액세스가 방지되도록 합니다.

### <a name="define-chat-permission-roles-for-each-user-in-your-environment"></a>환경의 각 사용자에 대한 채팅 권한 역할 정의

감독된 채팅이 환경 내의 각 사용자에게 예상대로 작동하려면 올바른 채팅 권한 역할을 할당해야 합니다. 사용자가 할당할 수 있는 세 가지 역할이 있습니다.

- *전체 사용 권한* - 이 역할은 학생 및 다른 교직원에 대한 전체 액세스 권한이 있는 교사에게 이상적입니다. 사용자 환경 내의 모든 사용자와 채팅을 시작할 수 있습니다. 모든 권한이 있는 사용자는 참여하는 채팅을 감독해야 합니다. 시작한 채팅 또는 페더링된 테넌트에서 감독하는 채팅에서 떠날 수 없습니다.

- *제한된 사용 권한* – 이 역할은 학생에 대한 감독된 액세스 권한만이 있으며 다른 교직원 및 교사에 대한 전체 액세스 권한이 있는 교직원에게 이상적입니다. 전체 사용자 또는 제한된 사용자와 채팅을 시작할 수 있지만 제한된 사용자와 채팅을 시작할 수 없습니다. 전체 사용 권한이 있는 사용자가 제한된 사용자와 채팅을 시작하는 경우 제한된 사용자를 대화에 참여할 수 있습니다. 이 액세스는 제한된 사용자와 제한된 사용자 간의 공동 작업을 감독할 수 있는 전체 권한이 있는 사용자가 있기 때문에 발생합니다.

- *제한된 권한* - 이 역할은 감독해야 하는 학생에게 이상적입니다. 모든 권한이 있는 사용자와의 채팅을 시작할 수 있습니다. 모든 권한이 있는 사용자가 초대하는 모든 대화에 참가할 수 있습니다. 페더리드 채팅의 경우 제한된 사용자만 제한된 사용자의 테넌트에서 제공된 모든 권한이 있는 사용자가 채팅에 추가할 수 있습니다.

사용자의 채팅 권한 역할을 설정하려면   관리 포털의 메시징 정책 옵션에 있는 채팅 권한 역할 정책을 Teams 있습니다. PowerShell을 사용하여 Full, Limited 또는 Limited 값으로 ChatPermissionRole 정책을 사용하여 역할을 정의할 수 있습니다. 이 정책은 CsTeamsMessagingPolicy 아래에 있습니다.

설정에 대해 자세히 알아보고자 합니다. Teams 정책은 Teams 정책 및 정책 패키지를 참조하고 많은 사용자 가이드 집합에 정책을 할당합니다.

테넌트의 게스트에게 역할을 할당할 수 없습니다. 게스트에게는 제한된 역할이 할당됩니다.

### <a name="allow-supervised-chat"></a>감독 채팅 허용

감독된 채팅은 기본적으로 테넌트에 대해 비활성화됩니다. 사용자에 대한 채팅 권한 역할을 설정한 후 **Org-wide** 설정으로 이동하고 역할 기반 채팅 사용 Teams 설정 설정하여 테넌트 내에서 감독된 채팅을 사용하도록 설정할 수 &gt;  *있습니다.*  PowerShell을 사용하여 AllowRoleBasedChatPermissions를 True로 설정하여 감독 채팅을 사용하도록 설정할 수 있습니다. 이 cmdlet은 CsTeamsClientConfiguration 아래에 있습니다.

테넌트의 모든 사용자에 대해 감독 채팅을 사용하도록 설정해야 합니다. 사용자의 일부에만 사용할 수 없습니다.

### <a name="enable-chat"></a>채팅 사용

관리 센터에서 사용할 수 있는 기존 채팅 정책을 사용하여 모든 Teams 활성화합니다.

## <a name="maintain-supervised-chats"></a>감독되는 채팅 유지 관리

감독 채팅을 처음 사용하도록 설정한 후 환경의 채팅이 감독된 상태로 유지되도록 몇 가지 작업을 해야 합니다.

- 테넌트에 참가하는 모든 새 사용자에게 적절한 역할을 할당합니다. 기본적으로 사용자는 제한된 역할이 할당됩니다.

- 모든 권한이 있는 사용자가 테넌트에서 나가거나 제거된 경우 감독하고 있는 채팅은 무인으로 남게 됩니다. 원래 사용자를 제거하기 전에 채팅을 감독할 수 있도록 모든 권한이 있는 다른 사용자가 이러한 대화에 추가되도록 합니다. 원래 감독자가 제거되면 새 참가자를 대화에 추가할 수 없지만 현재 참가자는 계속 통신할 수 있습니다.

## <a name="related-topics"></a>관련 항목

[교육에서 Teams 감독 채팅](https://support.microsoft.com/topic/supervised-chats-in-microsoft-teams-for-education-ad3aaafc-c85a-416f-95f9-d691f419cbb8?storagetype=live)
