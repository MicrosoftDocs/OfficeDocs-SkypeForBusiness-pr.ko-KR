---
title: 팀 및 Skype 상호 운용성
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: 조직의 팀 사용자와 Skype (소비자) 사용자 간의 상호 운용성 기능에 대해 알아봅니다.
localization_priority: Normal
ms.openlocfilehash: 551e39cdb496cc9e64ad962a8a50c06cb72f0aa2
ms.sourcegitcommit: f5ad0fc5be7201b71da4f13586972831c9961e51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47651207"
---
# <a name="teams-and-skype-interoperability"></a>팀 및 Skype 상호 운용성

이 문서에서는 Microsoft 팀과 Skype (소비자) 간의 상호 운용성 기능에 대 한 개요를 제공 합니다. 팀 사용자와 Skype 사용자가 채팅 및 통화와 적용 되는 관리 제어를 통해 통신 하는 방법에 대해 알아봅니다.

조직의 팀 사용자는 전자 메일 주소를 사용 하 여 Skype 사용자와 채팅 하 고 그 반대의 통화를 할 수 있습니다.

- 팀 사용자는 일대일 텍스트 대화 또는 Skype 사용자와의 음성/영상 통화를 검색 하 고 시작할 수 있습니다.
- Skype 사용자는 일대일 텍스트 대화 또는 팀 사용자와의 음성/영상 통화를 검색 하 고 시작할 수 있습니다.

이러한 접근 권한 값은 팀과 Skype 모두를 위한 데스크톱, 웹, 모바일 (Android 및 iOS) 클라이언트에서 사용할 수 있습니다. 최상의 환경을 위해서는 Skype 버전 8.58 이상을 권장 합니다.

> [!NOTE]
> 이 문서에서 설명 하는 팀 및 Skype interop 기능은 GCC, GCC 높음 또는 DOD 배포 또는 사설 클라우드 환경에서 사용할 수 없습니다.

## <a name="chat-and-calling-experience"></a>채팅 및 통화 환경

다음은 채팅 및 통화 환경에 대 한 개요입니다.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>팀 사용자가 Skype 사용자와 채팅 또는 통화 시작

팀 사용자는 새 채팅 또는 검색 창에 전자 메일 주소를 입력 하 여 Skype 사용자를 검색할 수 있습니다.  그런 다음 팀 사용자는 검색 결과에서 Skype 사용자를 선택 하 여 채팅 또는 통화를 시작할 수 있습니다.

Skype 사용자가 검색 결과에 표시 하지 않도록 선택할 수 있습니다. 이 경우 팀에서 검색 결과에 표시 되지 않으며 팀 사용자가 찾을 수 없게 됩니다.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype 사용자와의 채팅 또는 팀 사용자와의 통화 시작

Skype 사용자는 전자 메일 주소를 사용 하 여 팀 사용자와 채팅을 검색 하 고 시작할 수 있습니다. 팀 사용자에 게는 Skype 사용자의 새 메시지가 있음을 알리는 메시지가 표시 됩니다. 팀 사용자는 먼저 메시지를 수락 해야 회신할 수 있습니다.

- 팀 사용자가 **수락**을 선택 하면 대화가 수락 되 고 두 사용자 모두 서로 채팅 하 고 통화할 수 있습니다.
- 팀 사용자가 **블록**을 선택 하면 대화가 차단 되 고 이후 해당 Skype 사용자의 후속 메시지와 통화가 차단 됩니다.
- 팀 사용자가 **메시지 보기**를 선택 하면 해당 메시지가 팀에 표시 되므로 사용자는 대화를 수락 하거나 차단할지 여부를 결정할 수 있습니다.

> [!NOTE]
> 비즈니스용 Skype에서 팀으로 업그레이드 한 경우 사용자가 팀 전용 모드 이면 Skype 사용자와의 채팅 및 통화가 팀에 게 전달 됩니다. 사용자가 군도 모드에 있는 경우 Skype 사용자에 대 한 채팅 및 전화 통화는 비즈니스용 Skype로 전달 됩니다.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>팀 사용자가 Skype 사용자를 차단 하거나 차단을 해제 합니다.

팀 사용자가 Skype 사용자의 초기 대화 요청을 수락 하거나 차단 하 게 되 면 언제 든 지 해당 사용자를 차단 또는 차단 해제 하도록 선택할 수 있습니다. 이 작업은 대화 또는 팀의 개인 정보 설정에서 수행할 수 있습니다. Skype 사용자는 이들이 차단 되었음을 알 수 없습니다.

차단 된 Skype 사용자, 팀 사용자가 차단한 다른 사용자 및 PSTN (공개 전화 네트워크) 전화 번호와 함께 팀의 사용자 차단 연락처 목록에 나열 됩니다.

## <a name="limitations"></a>따릅니다

- 대화는 텍스트 전용입니다. 즉, [기본 팀 채팅 환경](native-chat-for-external-users.md)에서 사용할 수 있는 다양 한 서식, @mentions, emojis 또는 기타 채팅 기능을 사용 하지 않습니다.
- 대화는 일대일로만 가능 합니다. 그룹 채팅은 지원 되지 않습니다.
- 팀 사용자와 Skype 사용자는 서로의 현재 상태를 볼 수 없습니다.
- Skype ID 또는 전화 번호를 사용 하 여 Skype 사용자를 검색 하는 것은 지원 되지 않습니다.
- Skype 사용자는 다른 사용자의 번호로 착신 전환을 설정한 팀 사용자, 대리인 번호 또는 PSTN (공개 통신 네트워크) 번호로 전화를 걸 수 없습니다.  보이스 메일만 지원 됩니다.
- Interop 에스컬레이션, 그룹 통화 및 회의가 지원 되지 않습니다.
- 대리인이 팀 사용자 대신 Skype 사용자에 게 전화를 걸 수 있는 능력은 지원 되지 않습니다.
- 채팅을 사용한 화면 공유는 지원 되지 않습니다.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>팀 사용자가 Skype 사용자와 통신할 수 있는지 여부 설정

관리자는 Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 조직의 사용자가 Skype 사용자와 통신할 수 있는지 여부를 제어 하는 외부 액세스 설정을 설정 합니다. 기본적으로이 접근 권한 값은 새 테 넌 트에 대해 설정 되어 있습니다.

비즈니스용 Skype에서 팀으로 업그레이드 한 경우 비즈니스용 Skype 관리 센터에서 구성한 외부 통신 설정이 팀으로 마이그레이션됩니다.

### <a name="in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터에서

Microsoft 팀 관리 센터에서 **조직 전체 설정**  >  **외부 액세스**로 이동한 다음 **사용자가 Skype 사용자와 통신할 수**있도록 설정 합니다. 이 및 다른 외부 액세스 설정을 구성 하는 방법에 대 한 단계별 지침은 [팀에서 외부 액세스 관리](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains)를 참조 하세요.

### <a name="using-powershell"></a>PowerShell 사용

[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) cmdlet을 매개 변수와 함께 사용 ```EnablePublicCloudAccess``` 하 여 팀 사용자가 Skype 사용자와 통신할 수 있는지 여부를 제어 합니다. ```true```팀 사용자가 Skype 사용자와 통신할 수 있도록 매개 변수를 설정 합니다. 이 ```EnablePublicCloudAudioVideoAccess``` 매개 변수를 사용 하 여 오디오/비디오 통화를 사용 하거나 사용 하지 않도록 설정할 수 있습니다.

## <a name="related-topics"></a>관련 항목

- [팀에서 외부 액세스 관리](manage-external-access.md)
- [Teams PowerShell 개요](teams-powershell-overview.md)
