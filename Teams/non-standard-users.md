---
title: 사용자 유형에 따라 앱 동작 Teams
author: guptaashish
ms.author: guptaashish
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams 앱이 다양한 유형의 사용자에 대해 어떻게 작동하는지 알아봅니다.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: a407564986d5e4c758d39e2684e5c068539bb9dc
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922469"
---
# <a name="microsoft-teams-apps-behavior-based-on-types-of-users"></a>사용자 유형에 따라 앱 동작 Microsoft Teams

Teams 앱은 게스트, 외부(페더레이션됨) 및 익명 사용자가 Teams 컨텍스트에 있을 때 동작합니다.

* **게스트 사용자는** 조직의 직원, 학생 또는 구성원이 아닌 사람입니다. 조직에 학교 또는 직장 계정을 가지고 있지 않아야 합니다.

* **외부(페더레이션된) 사용자는** 다른 도메인에 속하며 조직의 팀 또는 팀 리소스에 액세스할 수 없습니다.

  > [!Note]
  > 게스트와 외부 사용자에 대한 자세한 비교는 [다른 조직의 사용자와 통신하는 것을 참조하세요](./communicate-with-users-from-other-organizations.md).

* **익명 사용자는** 사용자가 링크를 통해 모임에 참가한 Teams 모임의 개념입니다. 사용자가 Microsoft 또는 조직의 계정으로 로그인하지 않았습니다.

## <a name="guest-users"></a>게스트 사용자

### <a name="install-update-and-delete-for-guest-users"></a>게스트 사용자에 대한 설치, 업데이트 및 삭제

게스트는 채팅, 채널 또는 모임과 같은 공유 컨텍스트로 앱을 설치, 업데이트 또는 삭제할 수 없지만 메시지 확장 및 직접 링크를 사용하여 개인 범위로 연결할 수 있습니다. 게스트는 Teams 데스크톱 애플리케이션에서 Teams 앱 스토어에 액세스할 수 없지만 직접 링크를 사용하여 액세스할 수 있습니다.

### <a name="usage-behavior-and-policy-for-guest-users"></a>게스트 사용자에 대한 사용 동작 및 정책

게스트는 네이티브 사용자가 앱을 설치한 경우 앱을 사용할 수 있습니다.

#### <a name="bots-installed-to-a-channel"></a>채널에 설치된 봇

게스트 사용자는 봇을 언급하고 적응형 카드와 상호 작용할 수 있습니다.

#### <a name="personal-bots-installed-with-policies"></a>정책과 함께 설치된 개인 봇

* 게스트는 모든 앱의 호스트 테넌트에 대해 설정된 전역 및 조직 전체 권한 정책을 준수합니다. 전체 호스트 조직에 대해 앱이 차단된 경우 게스트도 앱을 사용할 수 없습니다.
* 전역 기본 앱 설정 정책에 포함된 모든 봇도 게스트용으로 설치됩니다.
* 봇이 설치되면 봇은 게스트와 사전에 통신할 수 있고 게스트는 봇과 다시 통신할 수 있습니다.
* 전역 기본 앱 설정 정책에서 게스트를 제거할 수 없습니다.
* 게스트가 봇에 액세스하지 못하도록 하려면 더 많은 앱 설정 정책을 만들고, 내부 사용자에게 할당하고, 사용자 지정 정책을 사용하여 봇을 설치할 수 있습니다.

## <a name="external-federated-users"></a>외부(페더레이션된) 사용자

### <a name="install-update-and-delete-for-external-users"></a>외부 사용자에 대한 설치, 업데이트 및 삭제

외부 사용자는 개인, 채팅, 채널 또는 모임과 같은 컨텍스트에 앱을 설치, 업데이트 또는 삭제할 수 없습니다. 호스팅 조직의 Teams 앱 스토어에 액세스할 수 없습니다.

### <a name="usage-behavior-and-policy-for-external-users"></a>외부 사용자에 대한 사용 동작 및 정책

* 다른 조직의 사람들은 호스팅 조직의 전역(조직 전체 기본값) 정책을 준수합니다.
* 호스팅 조직의 사용자는 다른 조직의 사용자와 모임 채팅에서 앱을 추가할 수 있습니다. 다른 조직의 사용자는 모임 채팅에서 앱을 추가할 수 없지만 채팅에 추가된 봇, 탭 및 메시지 확장과 상호 작용할 수 있습니다.
* 모임 채팅에 봇이 설치되면 해당 채팅에 있는 다른 조직의 사용자와 사전에 통신할 수 있으며 해당 사용자는 봇과 통신할 수 있습니다.
* 호스팅 조직의 데이터 정책 및 해당 사용자 조직에서 공유하는 타사 앱의 데이터 공유 관행이 적용됩니다.

## <a name="anonymous-users"></a>익명 사용자

### <a name="install-update-and-delete-for-anonymous-users"></a>익명 사용자에 대한 설치, 업데이트 및 삭제

익명 사용자는 모임에서 앱을 설치, 업데이트 또는 삭제할 수 없습니다.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>익명 사용자에 대한 사용 동작 및 정책

익명 사용자는 모임에서 앱을 직접 사용할 수 없습니다. 익명 사용자는 사용자 수준 전역 기본 권한 정책을 상속합니다. 앱이 채팅에서 적응형 카드를 보내는 경우 익명 사용자는 카드와 상호 작용할 수 있습니다. 이러한 사용자는 사용자 수준 권한 정책이 앱을 사용하도록 설정하는 경우 Teams 모임에서 앱과 상호 작용할 수 있습니다.

익명 사용자는 모임에서 이미 사용 가능한 앱과만 상호 작용할 수 있으며 이러한 앱을 획득하고 관리할 수 없습니다. 네이티브 사용자는 익명 사용자가 모임에 참석하는 경우에도 모임 앱을 계속 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

* [익명 사용자가 모임에 참가할 수 있도록 허용합니다](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).
* [Microsoft Teams 앱 설정 정책을 관리](teams-app-setup-policies.md)합니다.
