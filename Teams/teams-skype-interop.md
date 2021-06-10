---
title: Teams 및 Skype 상호 연동성
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
description: 조직의 사용자와 소비자(소비자) Teams 사용자 간의 상호 Skype 기능에 대해 자세히 알아보습니다.
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093958"
---
# <a name="teams-and-skype-interoperability"></a>Teams 및 Skype 상호 연동성

이 문서에서는 사용자와 소비자(소비자) 간의 상호 Microsoft Teams Skype 개요를 제공합니다. 사용자 및 Teams 사용자가 Skype 및 적용되는 관리자 컨트롤을 통해 통신할 수 있는 방법에 대해 알아보습니다.

Teams 사용자가 전자 메일 주소를 사용하여 사용자와 채팅하고 Skype 통화할 수 있습니다.

- Teams 사용자와 일대일 텍스트 전용 대화 또는 오디오/비디오 통화를 검색하고 시작할 Skype 있습니다.
- Skype 사용자와 일대일 텍스트 전용 대화 또는 오디오/비디오 통화를 검색하고 시작할 Teams 있습니다.

이러한 기능은 데스크톱, 웹 및 모바일(Android 및 iOS) 클라이언트에서 Teams 및 Skype. 최적의 환경을 위해 버전 Skype 8.58 이상을 추천합니다.

> [!NOTE]
> 이 문서에서 Teams 및 Skype 인터로프 기능은 GCC 또는 높은 GCC DOD 배포 또는 사설 클라우드 환경에서 사용할 수 없습니다.

## <a name="chat-and-calling-experience"></a>채팅 및 통화 환경

다음은 채팅 및 통화 경험에 대한 개요입니다.

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a>Teams 사용자와 채팅 또는 Skype 시작

Teams 사용자가 새 채팅 또는 검색 Skype 전자 메일 주소를 입력하여 사용자 검색을 검색할 수 있습니다.  그러면 Teams 사용자가 검색 결과에서 Skype 사용자를 선택하여 채팅을 시작하거나 통화할 수 있습니다.

사용자가 Skype 결과에 나타나지 않을 수 있습니다. 이 경우 사용자가 검색 결과에 표시되지 Teams Teams 사용자가 검색할 수 없습니다.

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a>Skype 사용자와 채팅 또는 Teams 시작

Skype 사용자가 전자 메일 주소를 사용하여 Teams 채팅을 검색하고 시작할 수 있습니다. Teams 사용자가 새 메시지를 Skype 메시지가 표시되고 먼저 메시지를 수락해야 회신할 수 있습니다.

- 사용자가 Teams 수락을 선택하면 대화가 수락됩니다. 두 사용자가 서로 채팅하고 통화할 수 있습니다.
- 사용자 Teams 차단을 선택하면 대화가 차단되어 해당 사용자로부터의 후속 메시지와 Skype 차단됩니다.
- Teams 사용자가 메시지 보기를 선택하면 메시지가 Teams 표시되어 사용자가 대화를 수락하거나 차단할지 여부를 결정하는 데 도움이 됩니다.

> [!NOTE]
> 사용자가 비즈니스용 Skype Teams 전용 모드에 있는 경우 Teams 사용자로부터 Skype 사용자로 Teams 채팅 및 통화가 Teams. 사용자가 제도 모드인 경우 사용자로부터 Skype 사용자가 Teams 채팅 및 비즈니스용 Skype.

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a>Teams 사용자 차단 또는 차단 Skype 차단 해제

사용자가 Teams 사용자로부터 초기 대화 요청을 수락하거나 차단한 Skype 사용자는 해당 사용자를 차단하거나 차단 해제하도록 선택할 수 있습니다. 대화 또는 개인 정보 설정에서 이 작업을 Teams. Skype 사용자가 차단된 것을 알지 못합니다.

차단된 Skype 사용자가 차단한 다른 사용자 및 공용 PSTN(공용 전화 네트워크) 전화 번호와 함께 Teams 사용자가 차단한 연락처 목록에 Teams.

## <a name="limitations"></a>제한 사항

- 대화는 텍스트 전용입니다. 즉, 기본 채팅 환경 에서 사용할 수 있는 다양한 서식, @mentions, 이모지 또는 기타 다른 채팅 기능이 Teams [없습니다.](native-chat-for-external-users.md)
- 대화는 일대일 전용입니다. 그룹 채팅은 지원되지 않습니다.
- Teams 사용자 및 Skype 사용자가 서로의 현재 상태는 볼 수 없습니다.
- 자신의 Skype ID 또는 전화 번호를 사용하여 Skype 사용자를 검색하는 것은 지원되지 않습니다.
- Skype 다른 사용자의 Teams 대리자 번호 또는 PSTN(공용 전환 전화 네트워크) 번호로 통화를 설정한 사용자에게 전화를 걸 수 없습니다.  음성메일만 지원됩니다.
- 인터팝 에스컬레이터, 그룹 호출 및 모임은 지원되지 않습니다.
- 대리인이 사용자를 대신하여 Skype 사용자를 호출하는 Teams 지원되지 않습니다.
- 채팅과 화면 공유는 지원되지 않습니다.

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a>사용자가 Teams 통신할 수 있는지 Skype 설정

관리자는 관리 센터 또는 Microsoft Teams PowerShell을 사용하여 외부 액세스 설정을 설정하여 조직의 Teams 사용자와 통신할 수 있는지 여부를 Skype 있습니다. 기본적으로 이 기능은 새 테넌트에 대해 켜져 있습니다. 그러나 도메인에 아직 사용할 수 없는 경우 IT 관리자가 다음 DNS SRV 레코드를 구성해야 합니다(예: _sipfederationtls.contoso.com.  

**서비스**: sipfederationtls<br/>
**프로토콜**: TCP<br/>
**우선** 순위 : 100<br/>
**무게**: 1<br/>
**포트**: 5061<br/>
**대상**: sipfed.online.lync.com

비즈니스용 Skype Teams 업그레이드한 경우 비즈니스용 Skype 관리 센터에서 구성한 외부 통신 설정이 Teams.

### <a name="in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터에서

Microsoft Teams 관리 센터에서 **Org-wide 설정** 외부 액세스로 이동한 다음 사용자를 켜면 사용자와 통신할  >   **Skype 있습니다.** 이 및 기타 외부 액세스 설정을 구성하는 방법에 대한 단계별 지침은 에서 외부 [액세스 관리를 Teams.](./manage-external-access.md#allow-or-block-domains)

### <a name="using-powershell"></a>PowerShell 사용

다음을 수행합니다. 
1. [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) cmdlet을 매개 변수와 함께 사용하여 Teams 사용자와 통신할 수 있는지 Skype ```EnablePublicCloudAccess``` 제어합니다. 매개 변수를 설정하여 Teams ```true``` 사용자와 통신할 Skype 있습니다. 매개 변수를 ```EnablePublicCloudAudioVideoAccess``` 사용하여 오디오/비디오 통화를 사용하도록 설정/사용하지 않도록 설정할 수 있습니다.

2. [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet을 매개 변수 집합과 함께 사용하여 Teams 사용자와 통신할 Skype ```Provider``` ```"WindowsLive"``` 있습니다.

## <a name="related-topics"></a>관련 항목

- [외부 액세스 관리 Teams](manage-external-access.md)
- [Teams PowerShell 개요](teams-powershell-overview.md)