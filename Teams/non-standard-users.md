---
title: 비표준 사용자에 대한 Teams 앱 동작
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams의 앱이 비표준 사용자에 대해 어떻게 행동하는지 알아보고
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fc4f4f53262127355afa573b0fc2abec6b05e64
ms.sourcegitcommit: 3861d661d32f507bd8479509ed09b1cfcf0b214f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51607520"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>표준이 아닌 사용자에 대한 Microsoft Teams 앱 동작

이 문서에서는 게스트, 외부(페더리화), 익명 사용자가 Teams 컨텍스트에 있을 때 Teams의 앱이 어떻게 행동하는지 설명합니다.

- 게스트 **사용자는** 직원, 학생 또는 조직의 구성원이 아닌 사용자입니다. 조직에 학교 또는 직장 계정을 가지고 있지 않아야 합니다.

- **외부(페더리드)** 사용자는 다른 도메인에 속하며 조직의 팀 또는 팀 리소스에 액세스할 수 없습니다.

>[!Note]
> 게스트와 외부 사용자에 대한 자세한 비교는 다른 조직의 사용자와 [통신을 참조합니다.](./communicate-with-users-from-other-organizations.md)

- 익명 **사용자는** 사용자가 링크를 통해 모임에 참가한 Teams 모임의 개념입니다. 사용자가 Microsoft 또는 조직의 계정으로 로그인하지 않습니다.

## <a name="guest-user-access"></a>게스트 사용자 액세스

### <a name="install-update-and-delete-for-guest-users"></a>게스트 사용자에 대한 설치, 업데이트 및 삭제

게스트는 채팅, 채널 또는 모임과 같은 공유 컨텍스트에 앱을 설치, 업데이트 또는 삭제할 수 없습니다. 메시지 확장 및 직접 링크를 사용하여 앱을 개인 범위로 설치, 업데이트 또는 삭제할 수 있습니다. 게스트는 Teams 앱 스토어에 액세스할 수 없습니다.

### <a name="usage-behavior-and-policy-for-guest-users"></a>게스트 사용자에 대한 사용 동작 및 정책

게스트는 네이티브 사용자가 앱을 설치한 경우 앱을 사용할 수 있습니다.

봇은 게스트 사용자에게 사전 메시지를 보낼 수 있지만 게스트는 봇과 상호 작용할 수 없습니다. 게스트는 봇 1:1, @ 봇을 언급하거나 봇과 통신하는 적응형 카드와 상호 작용할 수 없습니다.

게스트는 모든 앱에 대한 호스트 테넌트에 대해 설정된 전역 및 전체 권한 정책을 준수합니다. 즉, 전체 호스트 조직에 대해 앱이 차단된 경우 게스트는 앱을 사용할 수 없습니다.

설치 정책은 게스트 사용자에게 적용되지 않습니다. 즉, 기본 정책의 관리자가 고정된 앱은 게스트 사용자에게 영향을 주지 않습니다.

## <a name="external-federated-user-access"></a>외부(페더리화) 사용자 액세스

### <a name="install-update-and-delete-for-external-users"></a>외부 사용자에 대한 설치, 업데이트 및 삭제

외부 사용자는 개인, 채팅, 채널 또는 모임과 같은 상황에 맞는 앱을 설치, 업데이트 또는 삭제할 수 없습니다. Teams 앱 스토어에 액세스할 수 없습니다.

### <a name="usage-behavior-and-policy-for-external-users"></a>외부 사용자에 대한 사용 동작 및 정책

외부 사용자는 Teams 앱을 사용할 수 없습니다. 외부 사용자가 네이티브 사용자와 컨텍스트에 추가될 때 네이티브 및 외부 사용자는 더 이상 앱을 사용할 수 없습니다.

외부 사용자는 Teams 앱을 사용할 수 없습니다.

## <a name="anonymous-user-in-meetings-access"></a>모임 액세스의 익명 사용자

### <a name="install-update-and-delete-for-anonymous-users"></a>익명 사용자에 대한 설치, 업데이트 및 삭제

익명 사용자는 모임에서 앱을 설치, 업데이트 또는 삭제할 수 없습니다.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>익명 사용자에 대한 사용 동작 및 정책

익명 사용자는 모임에서 앱을 직접 사용할 수 없습니다. 익명 사용자가 있는 경우 네이티브 사용자는 모임 앱을 계속 사용할 수 있습니다. 앱에서 채팅에서 적응형 카드를 보내는 경우 익명 사용자가 카드와 상호 작용할 수 있는 자세한 내용은 익명 사용자가 모임에 참가하도록 허용 을 [참조하세요.](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)

익명 사용자는 사용자 수준 전역 기본 사용 권한 정책을 상속합니다. 사용자 수준 사용 권한 정책이 앱을 사용하도록 설정한 경우 Teams 모임에서 앱과 상호 작용할 수 있습니다. 익명 사용자는 모임에서 이미 사용할 수 있으며 이러한 앱을 획득 및/또는 관리할 수 없는 앱과만 상호 작용할 수 있습니다.
