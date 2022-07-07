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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: CallLineIdentity라는 정책을 사용하여 전화 시스템 사용자의 인바운드 및 아웃바운드 통화에 대해 호출자 ID를 제어할 수 있습니다.
ms.openlocfilehash: 250f8a1a516aec4c9941b0c6396e6d44771b4f53
ms.sourcegitcommit: f608811288c82a6348a6af1671246a93ed06e578
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2022
ms.locfileid: "66660964"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>조직에서 발신자 ID를 사용하는 방법

호출자 ID는 다음 두 가지 사용자 연결 정보로 구성됩니다.

- 전화 번호(CLID 또는 통화 회선 ID라고 함). 호출자의 식별으로 표시되는 PSTN(공중 전화망) 번호입니다.

- 통화 당사자 이름(일반적으로 CNAM이라고 함)입니다. 
  
발신자 ID 기능은 [PSTN 연결 옵션](pstn-connectivity.md)(Microsoft 통화 플랜, 운영자 연결 또는 직접 라우팅)에 관계없이 모든 전화 시스템 사용자가 사용할 수 있습니다. 
  
CallingLineIdentity라는 정책을 사용하여 인바운드 및 아웃바운드 호출 모두에 대한 호출자 ID를 제어할 수 있습니다. 자세한 내용은 [통화 회선 ID 및 통화 파티 이름에 대한 자세한](more-about-calling-line-id-and-calling-party-name.md) 내용을 참조하세요.

  
## <a name="outbound-pstn-caller-id"></a>아웃바운드 PSTN 호출자 ID

아웃바운드 PSTN 호출자 ID의 경우 다음 옵션을 사용할 수 있습니다. 
  
- 사용자에게 할당된 전화 번호(기본값)입니다.

- 익명- 사용자의 PSTN 번호 프레젠테이션을 제거하여 사용할 수 있습니다. 

- 대체 전화 번호입니다. 이 전화 번호는 다음과 같습니다.

  - 통화 플랜 전화 번호 인벤토리에서 서비스 및 무료 번호로 분류되는 전화 번호입니다. Teams 자동 전화 교환 또는 통화 큐에 할당됩니다.

  - Teams 자동 전화 교환 또는 통화 큐에서 사용하는 리소스 계정에 할당된 직접 라우팅을 통한 온-프레미스 전화 번호입니다. 

- 아웃바운드 PSTN 호출에 설정된 통화 파티 이름 또는 CNAM입니다.  
    
자세한 내용은 [사용자의 호출자 ID 설정을 참조하세요](./set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>아웃바운드 호출자 ID의 최종 사용자 제어

사용자는 EnableUserOverride 특성을 설정하여 호출자 ID 설정을 **익명** 으로 변경할 수 있습니다. 

아웃바운드 호출자 ID가 Anonymous로 설정된 경우 EnableUserOverride는 효과가 없으며 호출자 ID는 항상 익명으로 설정됩니다. EnableUserOverride의 기본값은 False입니다.

최종 사용자는 **설정 > 통화** 로 이동하여 발신자 ID를 익명으로 설정한 다음 **, 발신자 ID** 에서 **모든 통화에 대한 내 전화 번호 및 프로필 정보 숨기기를** 선택합니다. 이 설정 변경 내용이 새 호출에 반영되는 데 몇 분 정도 걸립니다. 

### <a name="notes"></a>참고

다음 사항에 유의하세요.

- 아웃바운드 발신자 ID에 대해 다음 유형의 전화 번호를 할당할 수 없습니다.

  - 통화 플랜 전화 번호 인벤토리에서 사용자로 분류되는 모든 전화 번호입니다.

  - 사용자에게 할당된 직접 라우팅을 통한 모든 온-프레미스 전화 번호입니다.

  - 비즈니스용 Skype 서버 온-프레미스 전화 번호입니다.

- 리소스 계정 전화 번호 대체의 사용은 Teams 사용자에게 적합합니다. 서비스 전화 번호의 대체는 Teams 사용자에 대해 작동합니다.

- 통화 당사자 이름은 호출자 ID가 LineUri, 서비스 또는 리소스 계정 전화 번호로 대체되는 통화 및 발신자가 Teams 사용자인 경우 전송됩니다.

- 통화 파티 이름은 최대 200자를 포함할 수 있지만 다운스트림 시스템은 더 적은 수의 문자를 지원할 수 있습니다.

- 직접 라우팅의 경우 FROM SIP 헤더에서 전화 번호 대체 및 통화 당사자 이름이 전송됩니다. 해당 OnlinePstnGateway가 ForwardPai = True로 구성된 경우 P-ASSERTED-IDENTITY SIP 헤더에는 실제 호출 사용자가 포함됩니다.

- 대체가 익명으로 설정되지 않는 한 EnableUserOverride는 정책의 다른 설정보다 우선합니다. 예를 들어 정책 인스턴스에 리소스 계정을 사용하는 대체가 있고 사용자가 EnableUserOverride를 설정하고 사용하도록 설정했다고 가정합니다. 이 경우 아웃바운드 호출자 ID가 차단되고 익명이 사용됩니다. 정책 인스턴스에 익명으로 설정된 대체가 있고 EnableUserOverride가 설정된 경우 최종 사용자 설정에 관계없이 아웃바운드 호출자 ID는 항상 익명입니다.

   
## <a name="inbound-caller-id"></a>인바운드 호출자 ID

전화 시스템은 들어오는 외부 전화 번호를 발신자 ID로 표시합니다. 이 번호가 Azure AD 또는 개인 연락처의 사용자 또는 연락처와 연결된 경우 비즈니스용 Skype 및 Teams 클라이언트는 해당 정보에 따라 발신자 ID를 표시합니다. 전화 번호가 Azure AD 또는 개인 연락처에 없는 경우 통신 제공 표시 이름을 사용할 수 있는 경우 표시됩니다.

BlockIncomingCallerID 특성을 사용하면 들어오는 PSTN 호출에서 호출자 ID를 차단할 수 있습니다. 이 특성을 설정할 수 있지만 사용자 설정 페이지에서 최종 사용자가 사용할 수 없습니다. 이 설정을 사용하도록 설정하면 들어오는 PSTN 호출자가 익명에서 들어오는 것으로 표시됩니다.
  
인바운드 호출자 ID를 차단하려면 [사용자의 호출자 ID 설정을 참조하세요](./set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>관련 항목
[전화 번호 전송 자주 묻는 질문](./phone-number-calling-plans/port-order-overview.md)

[통화 플랜에 사용되는 다양한 종류의 전화 번호](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)

[긴급 통화 사용 약관](./emergency-calling-terms-and-conditions.md)

[비즈니스용 Skype Online: 긴급 통화 고지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
