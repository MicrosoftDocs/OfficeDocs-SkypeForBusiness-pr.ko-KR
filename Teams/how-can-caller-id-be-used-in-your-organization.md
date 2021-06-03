---
title: 조직에서 발신자 ID를 사용하는 방법
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: CallingLineIdentity라는 정책을 사용하여 전화 시스템 사용자에 대한 인바운드 및 아웃바운드 호출에 대해 호출자 ID를 제어할 수 있습니다.
ms.openlocfilehash: 43d3d6633ca46485aa111a7d97b9bd37b0547818
ms.sourcegitcommit: 02e243d6c58eab463a00ed45dadd80112087006e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52723549"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>조직에서 발신자 ID를 사용하는 방법

발신자 ID는 두 개의 사용자 식별 가능한 정보로 구성됩니다.

- 전화 번호(일반적으로 CLID 또는 전화 회선 ID라고도 합니다. 발신자 식별으로 제시된 PSTN(공용 전환 전화 번호)입니다.

- 호출 파티 이름(일반적으로 CNAM이라고도 합니다. 
  
발신자 ID 기능은 PSTN 연결 옵션에 전화 시스템 모든 사용자가 사용할 수 있습니다.

- Microsoft 통화 계획 

- 전화 시스템 직접 라우팅 
  
CallingLineIdentity라는 정책을 사용하여 인바운드 및 아웃바운드 호출에 대해 호출자 ID를 제어할 수 있습니다. 자세한 내용은 전화선 ID 및 통화 파티 이름에 대한 [자세한 정보를 참조하세요.](more-about-calling-line-id-and-calling-party-name.md)

  
## <a name="outbound-pstn-caller-id"></a>아웃바운드 PSTN 호출자 ID

아웃바운드 PSTN 호출자 ID의 경우 다음 옵션을 사용할 수 있습니다. 
  
- 사용자에게 할당된 전화 번호(기본값)입니다.

- 사용자의 PSTN 번호의 프레젠테이션을 제거하여 사용할 수 있는 익명입니다. 

- 대체 전화 번호( 다음이 될 수 있습니다.

  - 전화 요금제 전화 번호 인벤토리에서 서비스 및 무료 번호로 분류되는 전화 번호입니다. 일반적으로 큐 또는 Teams 자동 전화 교환 할당됩니다.

  - 전화 큐 또는 전화 큐에서 사용하는 리소스 계정에 할당된 직접 라우팅을 통한 Teams 자동 전화 교환 전화 번호입니다. 

- 아웃바운드 PSTN 호출에 설정된 호출 파티 이름 또는 CNAM입니다.  
    
자세한 내용은 사용자의 [발신자 ID 설정 을 참조하세요.](./set-the-caller-id-for-a-user.md)
  
### <a name="end-user-control-of-outbound-caller-id"></a>아웃바운드 호출자 ID의 최종 사용자 제어

사용자는 EnableUserOverride  특성을 설정하여 발신자 ID 설정을 익명으로 변경할 수 있습니다. 

아웃바운드 호출자 ID가 익명으로 설정되어 있는 경우 EnableUserOverride에는 효과가 없습니다. 호출자 ID는 항상 익명으로 설정됩니다. EnableUserOverride의 기본값은 False입니다.

최종 사용자는 통화를 호출할 수 설정 > 익명으로 설정한 다음 발신자 **ID에서** 모든 통화에 대한 내 전화 번호 **및** 프로필 정보 숨기기 를 선택할 **수 있습니다.**

### <a name="notes"></a>참고

다음을 염두에 두어야 합니다.

- 아웃바운드 호출자 ID에 대해 다음 유형의 전화 번호를 할당할 수 없습니다.

  - 통화 계획 전화 번호 인벤토리의 사용자로 분류되는 모든 전화 번호입니다.

  - 사용자에게 할당된 직접 라우팅을 통한 모든 프레미스 전화 번호입니다.

  - 비즈니스용 Skype 서버 전화 번호입니다.

- 리소스 계정 전화 번호 대치의 사용은 사용자에 Teams 작동합니다. 서비스 전화 번호의 대치는 온라인 사용자 및 비즈니스용 Skype 사용자 모두에 Teams 작동합니다.

- 발신자 이름은 발신자 ID가 LineUri, 서비스 또는 리소스 계정 전화 번호로 대체되는 통화 및 발신자인 경우만 Teams 전송됩니다.

- 파티 이름을 호출하면 최대 200자까지 있을 수 있지만 다운스트림 시스템은 더 적은 수의 문자를 지원할 수 있습니다.

- 직접 라우팅의 경우 전화 번호 대칭 및 통화 파티 이름이 FROM SIP 헤더에 전송됩니다. 해당 OnlinePstnGateway가 ForwardPai = True로 구성된 경우 P-ASSERTED-IDENTITY SIP 헤더에는 실제 호출 사용자가 포함되어 있습니다.

- EnableUserOverride는 대용을 익명으로 설정하지 않는 한 정책의 다른 설정보다 우선합니다. 예를 들어 정책 인스턴스에 리소스 계정을 사용하여 대치가 있으며 EnableUserOverride가 설정되어 사용자가 사용하도록 설정되어 있는 것으로 가정합니다. 이 경우 아웃바운드 호출자 ID가 차단됩니다. 익명이 사용됩니다. 정책 인스턴스에 익명으로 대치가 설정되어 있으며 EnableUserOverride가 설정되어 있는 경우 아웃바운드 호출자 ID는 최종 사용자 설정에 관계없이 항상 익명이 됩니다.

   
## <a name="inbound-caller-id"></a>인바운드 호출자 ID

전화 시스템 외부 전화 번호를 호출자 ID로 표시합니다. 번호가 Azure AD 또는 개인 연락처의 사용자 또는 연락처와 연결된 경우 해당 비즈니스용 Skype Teams 클라이언트에 해당 정보에 따라 발신자 ID가 표시됩니다. 전화 번호가 Azure AD 또는 개인 연락처에 없는 경우 사용할 수 있는 경우 전화로 제공된 표시 이름이 표시됩니다.

BlockIncomingCallerID 특성은 들어오는 PSTN 호출에서 호출자 ID를 차단할 수 있습니다. 이 특성을 설정할 수 있지만 사용자 설정 페이지에서 최종 사용자가 사용할 수 없습니다. 이 설정을 사용하도록 설정하면 들어오는 PSTN 호출자는 익명에서 오는 것으로 표시됩니다.
  
인바운드 호출자 ID를 차단하는 경우 사용자의 [발신자 ID 설정 을 참조합니다.](./set-the-caller-id-for-a-user.md)
  
## <a name="related-topics"></a>관련 항목
[전화 번호 전송 자주 묻는 질문](./phone-number-calling-plans/port-order-overview.md)

[통화 계획에 사용되는 다양한 종류의 전화 번호](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)

[긴급 통화 사용 약관](./emergency-calling-terms-and-conditions.md)

[비즈니스용 Skype 온라인: 긴급 통화 고지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
