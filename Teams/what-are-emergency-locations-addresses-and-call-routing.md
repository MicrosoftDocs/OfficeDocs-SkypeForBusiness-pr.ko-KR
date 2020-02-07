---
title: 비상 전화, 긴급 주소, 긴급 통화 라우팅, 동적 비상 전화 계획
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
description: 긴급 주소, 긴급 통화 라우팅, 동적 비상 전화에 대 한 정보를 포함 하 여 비상 전화에 대해 알아봅니다.
ms.openlocfilehash: 010a1d3afd6ea1fa490b506b82c46c31bf3a4fa2
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836678"
---
# <a name="manage-emergency-calling"></a>긴급 통화 관리

이 문서에서는 긴급 전화 관리를 위해 알아야 할 개념에 대해 설명 하 고 긴급 주소, 동적 긴급 주소, 긴급 통화 라우팅에 대 한 정보를 포함 합니다. 이 문서에서는 다음 용어를 사용 합니다.

- **긴급 주소** -도심 주소--조직의 비즈니스 장소에 대 한 실제 또는 주소입니다.

  예를 들어 주소 *12345 북쪽 주 주소, Redmond, WA 98052* 을 사용 하 여 긴급 통화를 적절 한 디스패치 기관으로 라우팅하고 긴급 전화 발신자를 찾을 수 있습니다.

- **장소** -일반적으로 바닥, 건물, 윙 또는 사무실 번호입니다. 위치는 비상 주소와 연결 되어 건물 내에서 더 정확한 위치를 제공 합니다. 비상 주소와 연결 된 장소를 무제한으로 사용할 수 있습니다. 예를 들어 조직에 여러 건물을 보유 하 고 있는 경우 각 건물에 각 건물에 대 한 배치 정보를 포함할 수 있습니다.  

- **비상 위치** -위치는 선택 사항인 위치를 포함 하는 도심 주소입니다. 회사에 둘 이상의 실제 위치가 있는 경우 두 개 이상의 긴급 위치가 필요할 수 있습니다. 

  긴급 주소를 만들면이 주소에 대 한 고유한 위치 ID가 자동으로 만들어집니다.  긴급 주소에 위치를 추가 하는 경우 (예: 건물 주소에 층을 추가 하는 경우), 긴급 주소와 장소 조합에 대 한 위치 ID가 생성 됩니다.  이 예제에는 도심 주소에 대 한 두 개의 위치 Id가 있습니다. 하나는 연결 된 도심 주소와 관련 위치입니다.

  사용자 또는 사이트에 응급 위치를 할당 하는 경우 사용자 또는 사이트와 연결 되는 고유한 위치 ID입니다.

- **등록 된 주소** -각 통화 계획 사용자에 게 지정 된 긴급 주소입니다. 때로는 정적 긴급 주소 또는 레코드 주소 라고도 합니다.  (직접 라우팅 사용자에 게 등록 된 주소가 적용 되지 않습니다.)

팀 관리 센터를 사용 하 여 요금제 사용자에 대 한 긴급 주소를 만들 수 있습니다.  

>[!Note]
>PSTN 연결을 위해 전화 시스템의 통화 요금제 또는 전화 시스템 다이렉트 라우팅을 사용 하는지에 따라 긴급 통화를 관리 하는 방법이 다릅니다. 이러한 고려 사항은이 문서 전체에서 설명 합니다.

## <a name="emergency-address-validation"></a>긴급 주소 유효성 검사

사용자 또는 네트워크 식별자에 긴급 주소를 할당 하려면 긴급 주소가 "확인 됨"으로 표시 되어 있는지 확인 해야 합니다.  주소 유효성 검사는 주소가 유효한 지 확인 하 고, 할당 된 후에는 수정할 수 없습니다. 

팀 관리 센터에서 주소 맵 검색 기능을 사용 하 여 긴급 주소를 정의 하는 경우 주소가 자동으로 유효성이 검사 된 것으로 표시 됩니다. 유효한 긴급 주소는 수정할 수 없습니다. 따라서 주소의 형식 또는 표현이 변경 되 면 업데이트 된 형식으로 새 주소를 만들어야 합니다.


## <a name="emergency-address-geo-codes"></a>긴급 주소 지역 코드

각 긴급 주소에는 지역 코드 (위도 및 경도)가 연결 되어 있을 수 있습니다. 이러한 지역 코드는 일부 국가에서 동적 위치로 비상 통화를 라우팅하는 데 사용 됩니다. 

팀 관리 센터에서 주소 맵 검색 기능을 사용 하 여 긴급 주소를 정의 하는 경우 지역 코드가 긴급 주소에 자동으로 연결 됩니다. PowerShell을 사용 하 여 주소를 정의 하는 경우 지역 코드를 주소와 연결할 수도 있습니다. 그러나 팀 관리 센터의 지도 검색 기능을 사용 하 여 전화 요금제에 대 한 긴급 주소를 만드는 것이 좋으며,이는 주소가 서식 지정 되 고 유효성을 검사 하 고 해당 지역 코드를가지고 있는지 확인 하는 것입니다.  

>[!Important]
>동적 비상 전화에 대 한 네트워크 식별자에 비상 위치를 할당 하려면 긴급 주소에는 적절 한 지역 코드가 포함 되어 있어야 합니다.


## <a name="considerations-for-calling-plans"></a>통화 요금제에 대 한 고려 사항

해당 지역에서 통화 요금제를 사용할 수 있는지 여부를 확인 하려면 [전화 요금제에 대 한 국가 및 지역 사용 가능성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)을 참조 하세요.


### <a name="emergency-call-enablement"></a>비상 전화를 통한 통화

각 통화 계획 사용자는 비상 전화에 대해 자동으로 사용 하도록 설정 되며 지정 된 전화 번호와 연결 된 긴급 주소가 등록 되어 있어야 합니다. 

전화 번호에 연결 되어 있어야 하는 위치는 국가/지역에 따라 다릅니다.

- 예를 들어 미국 및 캐나다의 경우 사용자에 게 번호를 할당 하면 비상 위치가 필요 합니다.

- 다른 국가의 경우 (예: 유럽, 중동, 아프리카 (EMEA)), Office 365에서 전화 번호를 받을 때 또는 다른 서비스 공급자나 통신 업체에서 전송 되는 경우 긴급 위치가 필요 합니다.

### <a name="dynamic-emergency-calling"></a>동적 비상 전화

Microsoft 호출 요금제에 대 한 동적 비상 통화는 팀 클라이언트의 현재 위치를 기반으로 비상 전화를 구성 하 고 라우팅할 수 있는 기능을 제공 합니다. 적절 한 공개 안전 응답 시점 (PSAP)으로 자동 라우팅 하거나 보안 데스크 직원에 게 알리는 기능은 팀 사용자의 사용 국가에 따라 달라 집니다.  

이번에는 미국에서 전화 요금제 사용자만 동적 위치를 활용 하 여 다음과 같이 비상 전화를 라우팅할 수 있습니다.

- 미국 내 전화 플랜 사용자가 동적으로 미국 내의 긴급 주소를 획득 하는 경우, 해당 주소는 등록 된 주소 대신 긴급 라우팅에 사용 되며, 통화가 자동으로 PSAP에 연결 됩니다. 주소 영역을 처리 하는 중입니다.

- 미국 전화 플랜 사용자를 위한 팀 클라이언트가 미국 내에서 긴급 주소를 동적으로 획득 하지 않은 경우, 등록 된 긴급 주소를 사용 하 여 화면을 통해 통화를 라우팅할 수 있습니다. 그러나 호출자를 적절 한 PSAP에 연결 하기 전에 업데이트 된 주소가 필요한 지 확인 하기 위해 통화가 차단 됩니다.

미국에서는 네트워크 식별자에 할당 된 비상 위치에 속하는 도심 주소를 구성 하 고 관련 지역 코드를 포함 해야 합니다. 자세한 내용은 [동적 비상 전화 계획 및 구성을](configure-dynamic-emergency-calling.md)참조 하세요.


### <a name="emergency-call-routing"></a>긴급 통화 라우팅

팀에서 계획 사용자가 긴급 전화 번호로 전화를 거는 경우, 통화가 PSAP로 라우팅되는 방법은 다음에 따라 달라 집니다.

- 팀 클라이언트에서 긴급 주소를 동적으로 결정 하는지 여부

- 긴급 주소가 사용자의 전화 번호와 연결 된 등록 된 주소인 지 여부

- 해당 국가의 비상 전화 네트워크입니다.

  **미국에서:**

  - 팀 클라이언트가 테 넌 트 정의 동적인 긴급 위치에 있는 경우 해당 클라이언트의 비상 호출은 해당 지리적 위치를 처리 하는 PSAP에 자동으로 라우팅됩니다. 

  - 팀 클라이언트가 테 넌 트로 정의 된 동적 비상 위치에 없으면 해당 클라이언트의 비상 전화를 국가 콜 센터에서 확인 하 여 해당 지리적 위치를 처리 하는 PSAP로 호출을 전달 하기 전에 해당 전화를 통해 발신자의 위치를 결정 합니다.

  - 응급 발신자가 비상 위치를 차단 센터로 업데이트할 수 없는 경우 통화는 등록 된 주소를 처리 하는 PSAP로 전송 됩니다.

  **캐나다, 아일랜드, 영국에**는 통화를 적절 한 디스패치 센터에 연결 하기 전에 사용자의 현재 위치를 확인 하기 위해 먼저 긴급 통화가 차단 되었습니다. 

  **프랑스, 독일, 스페인에서**비상 전화는 호출자의 위치에 관계 없이 해당 번호와 연결 된 비상 주소로 서비스를 제공 하는 psap로 직접 라우팅됩니다.

  **네덜란드에서**비상 전화는 호출자의 위치에 관계 없이 해당 번호의 지역 코드에 대 한 psap로 직접 라우팅됩니다.

  **오스트레일리아에서는**통신 회사 파트너가 긴급 주소를 구성 하 고 라우트 합니다.

  **일본에서는**비상 통화가 지원 되지 않습니다.


자세한 내용은 다음을 참조 하세요.

- [통화 플랜](calling-plan-landing-page.md)

- [통화 요금제에 사용 되는 다른 종류의 전화 번호](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [긴급 통화 사용 약관](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a>직접 라우팅에 대 한 고려 사항

해당 지역에서 통화 요금제를 사용할 수 없거나 기존 통신 회사를 유지 하려는 경우 [다이렉트 라우팅을](direct-routing-landing-page.md)고려 하세요. 자세한 내용은 [직접 라우팅 구성](direct-routing-configure.md) 및 [긴급 통화 라우팅 정책 관리](manage-emergency-call-routing-policies.md)를 참조 하세요.

### <a name="emergency-call-enablement-and-configuration"></a>응급 통화 설정 및 구성

TeamsEmergencyCallRoutingPolicy를 사용 하 여 긴급 전화 번호 및 연결 된 라우팅 대상을 정의 하 여 다이렉트 라우팅 사용자에 대 한 긴급 통화 정책을 정의 해야 합니다. (등록 된 비상 위치는 다이렉트 라우팅 사용자에 게 지원 되지 않음에 유의 하세요.)

팀 직접 라우팅 사용자 계정, 네트워크 사이트 또는 둘 다에 TeamsEmergencyCallRoutingPolicy를 할당할 수 있습니다. 팀 클라이언트가 네트워크 연결을 시작 하거나 변경 하는 경우 팀은 다음과 같이 클라이언트가 있는 네트워크 사이트의 조회를 수행 합니다.

- TeamsEmergencyCallRoutingPolicy가 사이트와 연결 되어 있는 경우 사이트 정책은 긴급 통화를 구성 하는 데 사용 됩니다.

- 사이트와 연결 된 TeamsEmergencyCallRoutingPolicy 없거나 클라이언트가 정의 되지 않은 사이트에 연결 된 경우에는 사용자 계정과 연결 된 TeamsEmergencyCallRoutingPolicy를 사용 하 여 비상 통화를 구성 합니다. 

- 팀 클라이언트가 TeamsEmergencyCallRoutingPolicy를 가져올 수 없는 경우 사용자는 비상 전화를 사용할 수 없습니다.

### <a name="dynamic-emergency-calling"></a>동적 비상 전화

다이렉트 라우팅 사용자 용 팀 클라이언트는 동적 긴급 주소를 얻을 수 있으며,이는 호출자의 위치에 따라 동적으로 호출을 라우팅하는 데 사용 될 수 있습니다. 자세한 내용은 [동적 긴급 통화 구성을](configure-dynamic-emergency-calling.md)참조 하세요.

### <a name="emergency-call-routing"></a>긴급 통화 라우팅

TeamsEmergencyCallRoutingPolicy는 온라인 PSTN 사용을 참조 하며, 적절 한 PSTN 게이트웨이로 긴급 통화를 제대로 라우팅하도록 적절 한 직접 라우팅 구성이 필요 합니다. 특히 긴급 전화 접속 문자열에 대 한 OnlineVoiceRoute 있는지 확인 해야 합니다. 자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md#configure-voice-routing)참조 하세요. 

(참고: 비즈니스용 Skype 서버에서 긴급 전화 번호 앞에 "+ 911"과 일치 하도록 음성 경로를 정의 해야 하는 "+"가 있습니다. 팀 클라이언트는 긴급 전화 번호 앞에 "+"를 사용 하지 않습니다.

직접 라우팅 사용자를 위해 긴급 통화를 동적으로 라우팅하는 기능은 해당 국가 내의 비상 전화 네트워크에 따라 달라 집니다. 두 가지 해결 방법을 사용할 수 있습니다.

- 긴급 라우팅 서비스 공급자 (미국 전용) 
- 비상 위치 Id 번호 (ELIN) 게이트웨이 응용 프로그램

#### <a name="emergency-routing-service-providers"></a>응급 라우팅 서비스 공급자

미국에는 발신자의 위치에 따라 긴급 통화를 자동으로 라우팅할 수 있는 여러 개의 인증 된 ERSPs (응급 라우팅 서비스 공급자)가 있습니다.

- 긴급 라우팅 서비스 공급자가 직접 라우팅 배포에 통합 되어 있는 경우 동적으로 구입한 위치가 있는 비상 통화가 해당 위치를 처리 하는 PSAP (공개 안전 응답 시점)로 자동으로 라우팅됩니다.

-  업데이트 된 위치에 따라 적절 한 디스패치 센터에 전화를 연결 하기 전에 동적으로 구입 위치 없이 긴급 통화를 먼저 차단 하 여 사용자의 현재 위치를 결정 합니다.

자세한 내용은 [직접 라우팅을 위해 인증 된 세션 경계 컨트롤러](direct-routing-border-controllers.md)를 참조 하세요.


#### <a name="emergency-location-identification-number-elin-applications"></a>비상 위치 Id 번호 (ELIN) 응용 프로그램

SBCs (세션 경계 컨트롤러)는 비상 위치 Id 번호 (ELIN) 응용 프로그램을 포함할 수 있습니다. 응용 프로그램의 SBC ELIN을 직접 라우팅 배포에 통합 하는 경우에는 응용 프로그램의 ELIN 긴급 주소 및 연결 된 전화 번호를 구성한 다음 해당 PSTN의 비상 전화 데이터베이스에 레코드의 ELIN 업로드 해야 합니다. .  식별자가 ELIN 인 팀의 비상 위치는 응용 프로그램의 ELIN 내에서와 일치 해야 합니다.

동적으로 취득 하는 위치가 포함 된 비상 통화가 해당 SBC, 즉 응용 프로그램의 ELIN 같이 라우팅됩니다.

- 호출자의 긴급 위치를 구문 분석 합니다.
- 위치를 레코드의 ELIN와 일치 시킵니다.
- 비상 연락망의 번호를 전화 번호의 ELIN으로 바꿉니다.
- 해당 위치를 처리 하는 PSAP에 대 한 통화를 라우팅하고, 발송자는 업로드 된 ELIN record에서 위치를 가져옵니다.

비상 번호로 다시 전화를 받으면, 응용 프로그램의 ELIN는 원래 비상 전화 번호로 대체 하는 역 번호를 수행 합니다. 

자세한 내용은 [직접 라우팅을 위해 인증 된 세션 경계 컨트롤러](direct-routing-border-controllers.md)를 참조 하세요.


## <a name="security-desk-notification"></a>보안 데스크 알림

Microsoft 통화 요금제와 전화 시스템 직접 라우팅 모두에서 보안 데스크 알림을 받을 수 있습니다.

TeamsEmergencyCallingPolicy를 사용 하 여 긴급 통화 중에 알림을 받을 사람과 알림을 받는 방법 (채팅 전용, conferenced 인 및 음소거)을 구성 하 고, 음소거를 해제 하 고, 음소거를 해제 하는 등의 기능을 수행할 수 있습니다.  또한 사용자 또는 그룹의 외부 PSTN 번호를 지정 하 여 비상 전화를 걸고 참가할 수 있습니다. 

TeamsEmergencyCallingPolicy는 팀 사용자 계정에 게 부여 하거나, 네트워크 사이트에 할당 하거나, 둘 다에 게 부여할 수 있습니다.  팀 클라이언트가 네트워크 연결을 시작 하거나 변경 하는 경우 팀은 클라이언트가 있는 네트워크 사이트의 조회를 수행 합니다.

- TeamsEmergencyCallingPolicy 네트워크 사이트와 연결 된 경우 사이트 정책은 보안 데스크 알림을 구성 하는 데 사용 됩니다.

- 사이트와 연결 된 TeamsEmergencyCallingPolicy 없거나 클라이언트가 정의 되지 않은 사이트에 연결 되어 있는 경우 사용자 계정과 연결 된 TeamsEmergencyCallingPolicy는 보안 데스크 알림을 구성 하는 데 사용 됩니다.  

- 팀 클라이언트가 TeamsEmergencyCallingPolicy를 가져올 수 없는 경우 사용자는 보안 데스크 알림을 사용할 수 없습니다.

비상 전화 시, 보안 데스크는 통화에 conferenced, 보안 데스크 사용자의 경험은 TeamsEmergencyCallingPolicy에 따라 제어 됩니다. 그룹 채팅은 각 보안 데스크 구성원에 게 시작 되며, 긴급 전화 발신자의 위치는 중요 한 메시지 알림을 통해 공유 됩니다.  회의 옵션이 정책의 일부로 구성 되어 있으면 각 보안 데스크 사용자가 회의의 일부로 추가로 호출 됩니다.

    
## <a name="related-topics"></a>관련 항목

- [긴급 전화 정책 관리](manage-emergency-calling-policies.md)
- [긴급 통화 라우팅 정책 관리](manage-emergency-call-routing-policies.md)
- [조직의 응급 위치 추가, 변경 또는 제거](add-change-remove-emergency-location-organization.md)
- [사용자의 긴급 위치 지정 또는 변경](assign-change-emergency-location-user.md)
- [동적인 긴급 전화 계획 및 구성](configure-dynamic-emergency-calling.md)