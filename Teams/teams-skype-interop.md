---
title: 팀 및 Skype 상호 연동성
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: 조직의 Teams 사용자와 Skype(소비자) 사용자 간에 상호 연동성 기능에 대해 자세히 알아보습니다.
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093958"
---
# <a name="teams-and-skype-interoperability"></a>팀 및 Skype 상호 연동성

이 문서에서는 Microsoft Teams와 Skype(소비자) 간의 상호 작동성 기능에 대한 개요를 제공합니다. Teams 사용자 및 Skype 사용자가 채팅 및 통화 및 적용되는 관리자 컨트롤을 통해 통신하는 방법을 알아보습니다.

조직의 팀 사용자는 전자 메일 주소를 사용하여 Skype 사용자와 채팅하고 전화를 걸 수 있으며 그 반대의 경우도 마찬가지입니다.

- Teams 사용자는 Skype 사용자와 일대일 텍스트 전용 대화 또는 오디오/비디오 통화를 검색하고 시작할 수 있습니다.
- Skype 사용자는 Teams 사용자와 일대일 텍스트 전용 대화 또는 오디오/비디오 통화를 검색하고 시작할 수 있습니다.

이러한 기능은 Teams 및 Skype 모두에 대해 데스크톱, 웹 및 모바일(Android 및 iOS) 클라이언트에서 사용할 수 있습니다. 최적의 환경을 위해 Skype 버전 8.58 이상을 권장합니다.

> [!NOTE]
> 이 문서에서 설명하는 Teams 및 Skype Interop 기능은 GCC, GCC High 또는 DOD 배포 또는 사설 클라우드 환경에서 사용할 수 없습니다.

## <a name="chat-and-calling-experience"></a>채팅 및 통화 환경

다음은 채팅 및 통화 경험에 대한 개요입니다.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams 사용자가 Skype 사용자와 채팅 또는 통화를 시작합니다.

Teams 사용자는 새 채팅 또는 검색 표시줄에 전자 메일 주소를 입력하여 Skype 사용자를 검색할 수 있습니다.  그런 다음 Teams 사용자는 검색 결과에서 Skype 사용자를 선택하여 채팅을 시작하거나 해당 사용자와 통화할 수 있습니다.

Skype 사용자는 검색 결과에 나타나지 않을 수 있습니다. 이 경우 Teams 및 Teams 사용자가 검색 결과에 표시되지 않습니다.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype 사용자가 Teams 사용자와 채팅 또는 통화를 시작합니다.

Skype 사용자는 전자 메일 주소를 사용하여 Teams 사용자와 채팅을 검색하고 시작할 수 있습니다. Teams 사용자는 Skype 사용자의 새 메시지가 있으며 먼저 메시지를 수락해야 회신할 수 있습니다.

- Teams 사용자가 **수락을** 선택하면 대화가 수락됩니다. 두 사용자가 서로 채팅하고 통화할 수 있습니다.
- Teams 사용자가 차단을 **선택하면** 대화가 차단됩니다. 해당 Skype 사용자의 후속 메시지 및 호출이 차단됩니다.
- Teams 사용자가 메시지 보기를 선택하면 메시지가 Teams에 표시되어 사용자가 대화를 수락하거나 차단할지 여부를 결정하는 데 도움이 됩니다.

> [!NOTE]
> 비즈니스용 Skype에서 Teams로 업그레이드하고 사용자가 Teams 전용 모드인 경우 Skype 사용자에서 Teams로의 채팅 및 통화가 Teams로 전달됩니다. 사용자가 제도 모드인 경우 Skype 사용자에서 Teams 사용자로의 채팅 및 통화가 비즈니스용 Skype로 배달됩니다.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams 사용자 차단 또는 Skype 사용자 차단 해제

Teams 사용자가 Skype 사용자의 초기 대화 요청을 수락하거나 차단한 후 해당 사용자를 차단하거나 차단 해제하도록 선택할 수 있습니다. 대화 또는 Teams의 개인 정보 설정에서 이 작업을 할 수 있습니다. Skype 사용자는 차단된 것을 알지 못합니다.

차단된 Skype 사용자와 Teams 사용자가 차단한 PSTN(공용 전환된 전화 네트워크) 전화 번호와 함께 Teams의 사용자의 차단된 연락처 목록에 나열됩니다.

## <a name="limitations"></a>제한 사항

- 대화는 텍스트 전용입니다. 즉, 기본 Teams 채팅 경험에서 사용할 수 있는 다양한 서식, @mentions, 이모지 또는 기타 채팅 기능이 [없습니다.](native-chat-for-external-users.md)
- 대화는 일대일 전용입니다. 그룹 채팅은 지원되지 않습니다.
- Teams 사용자와 Skype 사용자는 서로의 현재 상태는 볼 수 없습니다.
- Skype ID 또는 전화 번호를 사용하여 Skype 사용자를 검색하는 것은 지원되지 않습니다.
- Skype 사용자는 다른 사용자의 번호, 대리인의 번호 또는 PSTN(공용 전환 전화 네트워크) 번호로 통화 전달을 설정한 Teams 사용자를 호출할 수 없습니다.  음성메일만 지원됩니다.
- 인터팝 에스컬레이터, 그룹 호출 및 모임은 지원되지 않습니다.
- Teams 사용자를 대신하여 Skype 사용자를 호출하는 대리인의 능력은 지원되지 않습니다.
- 채팅과 화면 공유는 지원되지 않습니다.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>Teams 사용자가 Skype 사용자와 통신할 수 있는지 여부를 설정합니다.

관리자는 Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 조직의 Teams 사용자가 Skype 사용자와 통신할 수 있는지 여부를 제어하기 위해 외부 액세스 설정을 설정합니다. 기본적으로 이 기능은 새 테넌트에 대해 켜져 있습니다. 그러나 도메인에 아직 사용할 수 없는 경우 IT 관리자가 다음 DNS SRV 레코드를 구성해야 합니다(예: _sipfederationtls.contoso.com.  

**서비스**: sipfederationtls<br/>
**프로토콜**: TCP<br/>
**우선** 순위 : 100<br/>
**무게**: 1<br/>
**포트**: 5061<br/>
**대상**: sipfed.online.lync.com

비즈니스용 Skype에서 Teams로 업그레이드한 경우 비즈니스용 Skype 관리 센터에서 구성한 외부 통신 설정이 Teams로 마이그레이션됩니다.

### <a name="in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터에서

Microsoft Teams 관리 센터에서 **Org-wide 설정** 외부 액세스로 이동한 다음 사용자를 켜면 Skype 사용자와  >   **통신할 수 있습니다.** 이 및 기타 외부 액세스 설정을 구성하는 방법에 대한 단계별 지침은 Teams의 외부 [액세스 관리를 참조하세요.](./manage-external-access.md#allow-or-block-domains)

### <a name="using-powershell"></a>PowerShell 사용

다음을 수행합니다. 
1. [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) cmdlet을 매개 변수와 함께 사용하여 Teams 사용자가 Skype 사용자와 통신할 수 있는지 ```EnablePublicCloudAccess``` 여부를 제어합니다. Teams 사용자가 Skype 사용자와 통신할 수 있도록 매개 ```true``` 변수를 설정합니다. 매개 변수를 ```EnablePublicCloudAudioVideoAccess``` 사용하여 오디오/비디오 통화를 사용하도록 설정/사용하지 않도록 설정할 수 있습니다.

2. Teams 사용자가 Skype 사용자와 통신할 수 있도록 [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet을 매개 변수 집합과 함께 ```Provider``` ```"WindowsLive"``` 사용합니다.

## <a name="related-topics"></a>관련 항목

- [Teams에서 외부 액세스 관리](manage-external-access.md)
- [Teams PowerShell 개요](teams-powershell-overview.md)