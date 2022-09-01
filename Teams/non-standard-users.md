---
title: 사용자 유형에 따라 Teams 앱 동작
author: ashishguptaiitb
ms.author: guptaashish
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 게스트, 페더레이션 사용자 및 익명 사용자에 대해 Microsoft Teams의 앱이 어떻게 다르게 작동하는지 알아봅니다.
ms.localizationpriority: high
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 25686bff1059d79376b036d3c5e64893b42fe4ab
ms.sourcegitcommit: 6b4dad9cea8fdad74c493ef62b085dbb9957235d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67486753"
---
# <a name="behavior-of-microsoft-teams-apps-based-on-types-of-in-meeting-users"></a>모임 내 사용자 유형에 따라 Microsoft Teams 앱의 동작

Teams 앱은 게스트, 외부(페더레이션됨) 및 익명 사용자가 Teams 컨텍스트에 있을 때 작동합니다.

* **게스트 사용자는** 조직의 직원, 학생 또는 구성원이 아닌 사람입니다. 조직에 학교 또는 직장 계정을 가지고 있지 않아야 합니다.

* **외부(페더레이션된) 사용자는** 다른 도메인에 있으며 조직의 Teams 리소스에 액세스할 수 없습니다.

  > [!Note]
  > 게스트 사용자와 외부 사용자 간의 자세한 비교는 [다른 조직의 사용자와 통신](./communicate-with-users-from-other-organizations.md)하는 것을 참조하세요.

* **익명 사용자는** 링크를 통해 모임에 참가하는 사용자입니다. 사용자가 Microsoft 계정 또는 조직의 계정으로 로그인되지 않습니다.

## <a name="guests"></a>게스트

### <a name="install-update-and-delete-for-guests"></a>게스트에 대한 설치, 업데이트 및 삭제

게스트는 채팅, 채널 또는 모임과 같은 공유 컨텍스트로 앱을 설치, 업데이트 또는 삭제할 수 없습니다. 게스트는 메시지 확장 및 직접 링크를 사용하여 개인 범위에서 이 작업을 수행할 수 있습니다. 게스트는 Teams 데스크톱 앱에서 Teams 앱 스토어에 액세스할 수 없지만 직접 링크를 사용하여 스토어에 액세스할 수 있습니다.

### <a name="usage-behavior-and-policy-for-guests"></a>게스트에 대한 사용 동작 및 정책

게스트는 네이티브 사용자가 앱을 설치한 경우 앱을 사용할 수 있습니다.

#### <a name="bots-installed-to-a-channel"></a>채널에 설치된 봇

게스트는 봇을 언급하고 적응형 카드와 상호 작용할 수 있습니다.

#### <a name="personal-bots-installed-with-policies"></a>정책과 함께 설치된 개인 봇

* 모든 앱의 경우 게스트는 호스트 조직에 대해 설정된 전역 및 조직 전체 권한 정책을 준수합니다. 전체 호스트 조직에 대해 앱이 차단된 경우 게스트도 앱을 사용할 수 없습니다.
* 전역 기본 앱 설정 정책에 포함된 모든 봇도 게스트용으로 설치됩니다.
* 봇이 설치되면 봇은 게스트와 사전에 통신할 수 있고 게스트는 봇과 다시 통신할 수 있습니다.
* 전역 기본 앱 설정 정책에서 게스트를 제거할 수 없습니다.
* 게스트가 봇에 액세스하지 못하도록 하려면 더 많은 앱 설정 정책을 만들고, 내부 사용자에게 할당하고, 사용자 지정 정책을 사용하여 봇을 설치할 수 있습니다.

## <a name="federated-users"></a>페더레이션된 사용자

### <a name="install-update-and-delete-for-federated-users"></a>페더레이션된 사용자에 대한 설치, 업데이트 및 삭제

페더레이션된 사용자는 개인, 채팅, 채널 또는 모임과 같은 컨텍스트에 앱을 설치, 업데이트 또는 삭제할 수 없습니다. 호스팅 조직의 Teams 앱 스토어에 액세스할 수 없습니다.

### <a name="usage-behavior-and-policy-for-federated-users"></a>페더레이션된 사용자에 대한 사용 동작 및 정책

* 다른 조직의 사람 호스팅 조직의 전역(조직 전체 기본값) 정책을 준수합니다.
* 호스팅 조직의 사용자는 다른 조직의 사용자와 모임 채팅에서 앱을 추가할 수 있습니다. 다른 조직의 사람 모임 채팅에서 앱을 추가할 수 없지만 채팅에 추가된 봇, 탭 및 메시지 확장과 상호 작용할 수 있습니다.
* 모임 채팅에 봇이 설치되면 해당 채팅에 있는 다른 조직의 사용자와 사전에 통신할 수 있으며 해당 사용자는 봇과 통신할 수 있습니다.
* 호스팅 조직의 데이터 정책이 적용됩니다.
* 해당 사용자 조직에서 공유하는 타사 앱의 데이터 공유 사례가 적용됩니다.

## <a name="anonymous-users"></a>익명 사용자

### <a name="install-update-and-delete-for-anonymous-users"></a>익명 사용자에 대한 설치, 업데이트 및 삭제

익명 사용자는 모임에서 앱을 설치, 업데이트 또는 삭제할 수 없습니다.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>익명 사용자에 대한 사용 동작 및 정책

익명 사용자는 모임에서 앱을 직접 사용할 수 없습니다. 앱이 채팅에서 적응형 카드를 보내는 경우 익명 사용자는 카드와 상호 작용할 수 있습니다. 이러한 사용자는 사용자 수준 권한 정책에서 앱을 사용하도록 설정하는 경우 Teams 모임에서 앱과 상호 작용할 수 있습니다. 익명 사용자는 사용자 수준 전역 기본 권한 정책을 상속합니다.

익명 사용자는 모임에서 이미 사용할 수 있지만 이러한 앱을 획득하고 관리할 수 없는 앱과만 상호 작용할 수 있습니다. 네이티브 사용자는 익명 사용자가 모임에 참석하는 경우에도 모임 앱을 계속 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

* [익명 사용자가 모임에 참가할 수 있도록 허용합니다](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).
* [Microsoft Teams에서 앱 설정 정책을 관리합니다](teams-app-setup-policies.md).
