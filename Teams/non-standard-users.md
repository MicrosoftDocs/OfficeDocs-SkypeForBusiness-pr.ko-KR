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
description: Microsoft Teams의 앱이 비표준 사용자에 대해 어떻게 행동하는지 배워야 합니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 66754565737929ec9d34125ca421c7e3eed9fe65
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278548"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a>비표준 사용자에 대한 Microsoft Teams 앱 동작

이 문서에서는 게스트, 외부(페더러티) 및 익명 사용자가 Teams 컨텍스트에 있을 때 Teams의 앱이 어떻게 행동하는지 설명하고 있습니다.

- 게스트 **사용자는** 조직의 직원, 학생 또는 구성원이 아닌 사람입니다. 조직에 학교 또는 직장 계정을 가지고 있지 않아야 합니다.

- **외부(페더러화)** 사용자는 다른 도메인에 속하며 조직의 팀 또는 팀 리소스에 액세스할 수 없습니다.

>[!Note]
> 게스트와 외부 사용자 비교에 대한 자세한 비교는 다른 조직의 사용자와 [통신을 참조합니다.](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations)

- 익명 **사용자는** 사용자가 링크를 통해 모임에 참가한 Teams 모임의 개념입니다. 사용자가 자신의 Microsoft 또는 조직의 계정으로 로그인하지 않은 경우

## <a name="guest-user-access"></a>게스트 사용자 액세스

### <a name="install-update-and-delete-for-guest-users"></a>게스트 사용자에 대한 설치, 업데이트 및 삭제

게스트는 채팅, 채널 또는 모임과 같은 공유 컨텍스트에 앱을 설치, 업데이트 또는 삭제할 수 없습니다. 메시지 확장 및 직접 링크를 사용하여 앱을 개인 범위로 설치, 업데이트 또는 삭제할 수 있습니다. 게스트는 Teams 앱 스토어에 액세스할 수 없습니다.

### <a name="usage-behavior-and-policy-for-guest-users"></a>게스트 사용자에 대한 사용 동작 및 정책

네이티브 사용자가 앱을 설치한 경우 게스트는 앱을 사용할 수 있습니다.

봇은 게스트 사용자에게 사전 메시지를 보낼 수 있지만 게스트는 봇과 상호 작용할 수 없습니다. 게스트는 봇에 1:1 메시지를 보내거나@ 봇을 언급하거나 봇과 통신하는 적응형 카드와 상호 작용할 수 없습니다.

게스트는 모든 앱에 대한 호스트 테넌트에 대해 설정된 전역 및 전체 권한 정책을 준수합니다. 즉, 전체 호스트 조직에 대해 앱이 차단된 경우 게스트는 앱을 사용할 수 없습니다.

설치 정책은 게스트 사용자에게 적용되지 않습니다. 즉, 기본 정책에서 관리자가 고정한 앱은 게스트 사용자에게 영향을 주지 않습니다.

## <a name="external-federated-user-access"></a>외부(페더러화) 사용자 액세스

### <a name="install-update-and-delete-for-external-users"></a>외부 사용자에 대한 설치, 업데이트 및 삭제

외부 사용자는 개인, 채팅, 채널 또는 모임과 같은 컨텍스트에 앱을 설치, 업데이트 또는 삭제할 수 없습니다. Teams 앱 스토어에 액세스할 수 없습니다.

### <a name="usage-behavior-and-policy-for-external-users"></a>외부 사용자에 대한 사용 동작 및 정책

외부 사용자는 Teams 앱을 사용할 수 없습니다. 외부 사용자가 네이티브 사용자와 함께 컨텍스트에 추가될 때 모든 사용자(네이티브 및 외부)는 더 이상 앱을 사용할 수 없습니다.

외부 사용자는 Teams 앱을 사용할 수 없습니다.

## <a name="anonymous-user-in-meetings-access"></a>모임 액세스의 익명 사용자

### <a name="install-update-and-delete-for-anonymous-users"></a>익명 사용자에 대한 설치, 업데이트 및 삭제

익명 사용자는 모임에서 앱을 설치, 업데이트 또는 삭제할 수 없습니다.

### <a name="usage-behavior-and-policy-for-anonymous-users"></a>익명 사용자에 대한 사용 동작 및 정책

익명 사용자는 모임에서 앱을 직접 사용할 수 없습니다. 익명 사용자가 있는 경우 네이티브 사용자는 모임 앱을 계속 사용할 수 있습니다. 앱에서 채팅에서 적응형 카드를 보내는 경우 익명 사용자는 카드와 상호 작용할 수 있습니다.

익명 사용자는 사용자 수준 전역 기본 사용 권한 정책을 상속합니다. 이 컨트롤을 사용하면 익명 사용자가 사용자 수준 사용 권한 정책이 앱을 사용하도록 설정한 경우 Teams 모임에서 앱과 상호 작용할 수 있습니다. 익명 사용자는 모임에서 이미 사용할 수 있으며 이러한 앱을 획득 및/또는 관리할 수 없는 앱과만 상호 작용할 수 있습니다.
