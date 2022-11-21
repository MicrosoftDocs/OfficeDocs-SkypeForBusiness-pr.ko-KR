---
title: 다양한 유형의 사용자에 의한 Teams 앱의 가용성 및 사용
author: ashishguptaiitb
ms.author: guptaashish
ms.reviewer: kojika
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: teams-apps
search.appverid: MET150
description: 게스트, 페더레이션 사용자 및 익명 사용자를 위해 Microsoft Teams의 앱이 작동하는 방식을 알아봅니다.
ms.localizationpriority: high
ms.date: 09/28/2022
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3511dec4f3238babc3356bafbe2bb69e791e7632
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131317"
---
# <a name="use-of-teams-apps-for-external-attendees-or-guest-from-outside-an-organization"></a>외부 참석자 또는 조직 외부의 게스트를 위한 Teams 앱 사용

Teams 앱은 조직 외부 사용자와의 공동 작업을 허용합니다. 관리자는 Teams 채팅, 모임 및 채널에 액세스하여 조직의 사용자와 공동 작업할 수 있는 사용자를 제어합니다. 자세한 내용은 [외부 참석자와의 공동 작업을 허용하는 방법](manage-external-access.md) 및 [게스트가 Teams에서 수행할 수 있는 작업을 참조하세요](guest-access.md). 이 문서에서는 조직 외부의 사용자가 앱을 사용하는 데 중점을 둡니다.

다음 유형의 사용자가 Teams 채팅 또는 모임에 있을 수 있으며, 허용하는 경우 Teams에서 앱을 사용할 수 있습니다.

* **게스트 사용자는** 조직의 직원, 학생 또는 구성원이 아닌 사람입니다. 조직에 학교 또는 직장 계정을 가지고 있지 않아야 합니다.

* **외부(페더레이션된) 사용자는** 다른 도메인 출신이며 조직의 Teams 리소스에 액세스할 수 없습니다.

* **익명 사용자는** 링크를 통해 모임에 참가하는 사용자입니다. 사용자는 Microsoft 계정 또는 조직의 계정으로 로그인되지 않습니다.

게스트 사용자와 외부 사용자 간의 자세한 비교는 [다른 조직의 사용자와 통신](communicate-with-users-from-other-organizations.md)을 참조하세요.

## <a name="guests"></a>게스트

### <a name="install-update-and-delete-apps-for-guests"></a>게스트용 앱 설치, 업데이트 및 삭제

게스트는 채팅, 채널 또는 모임과 같은 공유 컨텍스트에 앱을 설치, 업데이트 또는 삭제할 수 없습니다. 게스트는 메시지 확장 및 직접 링크를 사용하여 개인 범위에서 이 작업을 수행할 수 있습니다. 게스트는 Teams 데스크톱 앱에서 Teams 앱 스토어에 액세스할 수 없지만 직접 링크를 사용하여 스토어에 액세스할 수 있습니다.

### <a name="usage-behavior-and-policy-for-guests"></a>게스트에 대한 사용 동작 및 정책

게스트는 조직의 사용자가 앱을 설치한 경우 앱을 사용할 수 있습니다.

#### <a name="bots-installed-to-a-channel"></a>채널에 설치된 봇

게스트는 봇을 언급하고 적응형 카드와 상호 작용할 수 있습니다.

#### <a name="personal-bots-installed-with-policies"></a>정책과 함께 설치된 개인 봇

* 모든 앱의 경우 게스트는 호스트 조직에 대해 설정된 전역 및 조직 전체 권한 정책을 준수합니다. 전체 호스트 조직에 대해 앱이 차단된 경우 게스트도 앱을 사용할 수 없습니다.
* 전역 기본 앱 설정 정책에 포함된 모든 봇도 게스트에 대해 설치됩니다.
* 봇이 설치되면 봇과 게스트가 사전에 서로 통신할 수 있습니다.
* 전역 기본 앱 설정 정책에서 게스트를 제거할 수 없습니다.
* 게스트가 봇에 액세스하지 못하도록 하려면 더 많은 앱 설정 정책을 만들고, 내부 사용자에게 할당하고, 사용자 지정 정책을 사용하여 봇을 설치할 수 있습니다.

## <a name="federated-users"></a>페더레이션된 사용자

### <a name="install-update-and-delete-apps-for-federated-users"></a>페더레이션된 사용자에 대한 앱 설치, 업데이트 및 삭제

페더레이션된 사용자는 개인, 채팅, 채널 또는 모임과 같은 컨텍스트로 앱을 설치, 업데이트 또는 삭제할 수 없습니다. 호스팅 조직의 Teams 앱 스토어에 액세스할 수 없습니다.

### <a name="usage-behavior-and-policy-for-federated-users"></a>페더레이션된 사용자에 대한 사용 동작 및 정책

* 다른 조직의 사람 호스팅 조직의 전역(조직 전체 기본값) 정책을 준수합니다.
* 호스팅 조직의 사용자는 다른 조직의 사용자와 모임 채팅에서 앱을 추가할 수 있습니다. 다른 조직의 사람 모임 채팅에 앱을 추가할 수 없지만 채팅에 추가된 봇, 탭 및 메시지 확장과 상호 작용할 수 있습니다.
* 모임 채팅에 봇이 설치되면 해당 채팅의 다른 조직 사용자와 사전에 통신할 수 있으며, 해당 사용자는 봇과 통신할 수 있습니다.
* 호스팅 조직의 데이터 정책이 적용됩니다.
* 해당 사용자의 조직에서 공유하는 타사 앱의 데이터 공유 사례가 적용됩니다.

## <a name="anonymous-users"></a>익명 사용자

### <a name="install-update-and-delete-apps-for-anonymous-users"></a>익명 사용자를 위한 앱 설치, 업데이트 및 삭제

익명 사용자는 모임에서 앱을 설치, 업데이트 또는 삭제할 수 없습니다.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>익명 사용자를 위한 사용 동작 및 정책

익명 사용자는 모임에서 앱을 직접 사용할 수 없습니다. 앱이 채팅에서 적응형 카드를 보내는 경우 익명 사용자가 카드와 상호 작용할 수 있습니다. 이러한 사용자는 사용자 수준 권한 정책에서 앱을 사용하도록 설정하는 경우 Teams 모임에서 앱과 상호 작용할 수 있습니다. 익명 사용자는 사용자 수준 전역 기본 권한 정책을 상속합니다.

익명 사용자는 모임에서 이미 사용할 수 있지만 이러한 앱을 획득하고 관리할 수 없는 앱과만 상호 작용할 수 있습니다. 네이티브 사용자는 익명 사용자가 모임에 참석하는 경우에도 모임 앱을 계속 사용할 수 있습니다.

### <a name="allow-anonymous-users-to-use-apps-in-meetings"></a>익명 사용자가 모임에서 앱을 사용하도록 허용

기본적으로 익명 사용자는 모임에서 기존 앱과 상호 작용할 수 있습니다. 익명 사용자는 모임에 새 앱을 추가할 수 없습니다. 앱과 상호 작용하기 위해 익명 사용자를 허용하지 않습니다.

1. Teams 관리 센터에 로그인하고 모임 **[모임 설정](https://admin.teams.microsoft.com/meetings/settings)****에 액세스합니다** > .

1. **참가자** 에서 **익명 사용자가 모임의 앱과 상호 작용할 수 있는** 토글을 **끄** 기로 변경합니다.

1. **저장** 을 선택합니다.

## <a name="related-articles"></a>관련 기사

* [익명 사용자가 모임에 참가하도록 허용합니다](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).
* [Microsoft Teams에서 앱 설정 정책을 관리합니다](teams-app-setup-policies.md).
* [게스트 및 외부 참가자와의 공동 작업을 허용하는 방법입니다](manage-external-access.md).
* [게스트가 Teams에서 수행할 수 있는 일](guest-access.md)
