---
title: Teams 사용자에 대한 앱 동작
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 비표준 사용자에 대해 Microsoft Teams 앱이 어떻게 행동하는지 알아보습니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 046a8f08db43062586230c5d7016ebb117027398
ms.sourcegitcommit: 5c59f9bf5a9477607b378c23fa3c8670930dc428
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2021
ms.locfileid: "53646869"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>Microsoft Teams 사용자에 대한 앱 동작

이 문서에서는 게스트, 외부 Teams 및 익명 사용자가 특정 컨텍스트에 있을 때 앱의 Teams 설명합니다.

- 게스트 **사용자는** 직원, 학생 또는 조직의 구성원이 아닌 사용자입니다. 조직에 학교 또는 직장 계정을 가지고 있지 않아야 합니다.

- **외부(페더리드)** 사용자는 다른 도메인에 속하며 조직의 팀 또는 팀 리소스에 액세스할 수 없습니다.

  > [!Note]
  > 게스트와 외부 사용자에 대한 자세한 비교는 다른 조직의 사용자와 [통신을 참조합니다.](./communicate-with-users-from-other-organizations.md)

- 익명 **사용자는** 사용자가 링크를 통해 Teams 모임에 참가한 모임의 개념입니다. 사용자가 Microsoft 또는 조직의 계정으로 로그인하지 않습니다.

## <a name="guest-users"></a>게스트 사용자

### <a name="install-update-and-delete-for-guest-users"></a>게스트 사용자에 대한 설치, 업데이트 및 삭제

게스트는 채팅, 채널 또는 모임과 같은 공유 컨텍스트에 앱을 설치, 업데이트 또는 삭제할 수 없지만 메시지 확장 및 직접 링크를 사용하여 개인 범위로 보낼 수 있습니다. 게스트는 데스크톱 애플리케이션에서 Teams 앱 스토어에 Teams 없지만 직접 링크로 액세스할 수 있습니다.

### <a name="usage-behavior-and-policy-for-guest-users"></a>게스트 사용자에 대한 사용 동작 및 정책

게스트는 네이티브 사용자가 앱을 설치한 경우 앱을 사용할 수 있습니다.

#### <a name="bots-installed-to-a-channel"></a>채널에 설치된 봇

봇은 게스트 사용자에게 사전 메시지를 보낼 수 있지만 게스트는 봇과 상호 작용할 수 없습니다. 게스트는 봇에게 일대일 메시지를 보내거나, 봇을 언급하거나, 봇과 통신하는 적응형 카드와 상호 작용할 수 없습니다.

#### <a name="personal-bots-installed-with-policies"></a>정책이 설치된 개인 봇

- 게스트는 모든 앱에 대한 호스트 테넌트에 대해 설정된 전역 및 전체 권한 정책을 준수합니다. 전체 호스트 조직에 대해 앱이 차단된 경우 게스트는 앱을 사용할 수 없습니다.
- 전역 기본 앱 설정 정책에 포함된 모든 봇도 게스트에 대해 설치됩니다.
- 봇을 설치한 후 봇은 게스트와 사전 통신할 수 있으며 게스트는 봇과 다시 통신할 수 있습니다.
- 전역 기본 앱 설정 정책에서 게스트를 제거할 수 없습니다.
- 게스트가 봇에 액세스하지 않도록하려면 더 많은 앱 설치 정책을 만들고, 내부 사용자에게 할당하고, 사용자 지정 정책으로 봇을 설치할 수 있습니다.

## <a name="external-federated-users"></a>외부(페더리화) 사용자

### <a name="install-update-and-delete-for-external-users"></a>외부 사용자에 대한 설치, 업데이트 및 삭제

외부 사용자는 개인, 채팅, 채널 또는 모임과 같은 상황에 맞는 앱을 설치, 업데이트 또는 삭제할 수 없습니다. 호스팅 조직의 앱 Teams 액세스할 수 없습니다.

### <a name="usage-behavior-and-policy-for-external-users"></a>외부 사용자에 대한 사용 동작 및 정책

- 다른 조직의 사람들은 호스팅 조직의 전역(조직 전체 기본값) 정책을 준수합니다.
- 호스팅 조직의 사용자는 다른 조직의 사용자와의 모임 채팅에서 앱을 추가할 수 있습니다. 다른 조직의 사람들은 모임 채팅에서 앱을 추가할 수 없지만 채팅에 추가된 봇, 탭 및 메시지 확장과 상호 작용할 수 있습니다.
- 모임 채팅에 봇이 설치되면 해당 채팅의 다른 조직의 사용자와 사전 통신할 수 있으며 해당 사용자도 봇과 통신할 수 있습니다.
- 호스팅 조직의 데이터 정책과 해당 사용자의 조직에서 공유하는 타사 앱의 데이터 공유 관행이 적용됩니다.

## <a name="anonymous-users"></a>익명 사용자

### <a name="install-update-and-delete-for-anonymous-users"></a>익명 사용자에 대한 설치, 업데이트 및 삭제

익명 사용자는 모임에서 앱을 설치, 업데이트 또는 삭제할 수 없습니다.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>익명 사용자에 대한 사용 동작 및 정책

익명 사용자는 모임에서 앱을 직접 사용할 수 없습니다. 익명 사용자가 있는 경우 네이티브 사용자는 모임 앱을 계속 사용할 수 있습니다. 앱에서 채팅에서 적응형 카드를 보내는 경우 익명 사용자가 카드와 상호 작용할 수 있습니다. 자세한 내용은 익명 사용자가 [모임에 참가하도록 허용 을 참조하십시오.](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)

익명 사용자는 사용자 수준 전역 기본 사용 권한 정책을 상속합니다. 사용자 수준 사용 권한 정책이 앱을 사용하도록 설정한 Teams 모임에서 앱과 상호 작용할 수 있습니다. 익명 사용자는 모임에서 이미 사용할 수 있으며 이러한 앱을 획득 및/또는 관리할 수 없는 앱과만 상호 작용할 수 있습니다.

## <a name="related-topics"></a>관련 항목

[앱 설정 정책 관리 Microsoft Teams](teams-app-setup-policies.md)
