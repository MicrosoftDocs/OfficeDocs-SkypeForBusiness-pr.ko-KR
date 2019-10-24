---
title: 동적 비상 전화 구성
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
description: 동적 비상 전화 구성
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b166c93bb213fab6e8025a1837ef67baa65c884
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37639361"
---
# <a name="plan-and-configure-dynamic-emergency-calling-for-calling-plans"></a>통화 요금제에 대 한 동적 비상 전화 계획 및 구성
Microsoft 호출 요금제에 대 한 동적 비상 통화는 팀 클라이언트의 현재 위치를 기반으로 비상 전화를 구성 하 고 라우팅할 수 있는 기능을 제공 합니다.  적절 한 공개 안전 응답 시점 (PSAP)으로 자동 라우팅 하거나 보안 데스크 직원에 게 알리는 기능은 팀 사용자의 사용 국가에 따라 달라 집니다.  

> [!Note] 
> 현재 동적 비상 전화는 미국 에서만 사용할 수 있습니다. 그러나 보안 데스크 알림은 국가 경계에서 지원 됩니다.

**미국 내에서**동적 긴급 전화 라우팅을 다음과 같이 구성할 수 있습니다.
  
- 팀 클라이언트가 테 넌 트 정의 동적인 긴급 위치에 있는 경우 해당 클라이언트의 비상 호출은 해당 지리적 위치를 처리 하는 PSAP에 자동으로 라우팅됩니다.  

- 팀 클라이언트가 테 넌 트로 정의 된 동적 비상 위치에 없으면 해당 클라이언트의 비상 전화를 국가 콜 센터에서 확인 하 여 해당 지리적 위치를 처리 하는 PSAP로 호출을 전달 하기 전에 해당 전화를 통해 발신자의 위치를 결정 합니다.

다음과 같이 보안 데스크 알림을 구성할 수 있습니다.

- 팀 클라이언트가 테 넌 트로 정의 된 네트워크 사이트에 있는 경우 해당 사이트에 대해 구성 된 보안 그룹 구성원에 게 알림이 표시 됩니다.

- 팀 클라이언트가 테 넌 트로 정의 된 네트워크 사이트에 없으면 사용자에 대해 구성 된 보안 그룹 구성원에 게 알림이 표시 됩니다.

**미국 이외의 지역**에서 비상 전화는 사용자에 게 할당 된 전화 번호로 매핑되는 psap로 라우팅됩니다.  멋진 영국 및 캐나다와 같은 일부 국가에서는 호출자를 적절 한 PSAP로 이전 하기 전에 전화 국내를, 다른 사용자는 현재 위치에 관계 없이 PSAP로 직접 라우팅합니다. 

모든 통화 계획 사용자에 대해 동적 보안 데스크 알림을 구성할 수 있습니다.


## <a name="supported-clients"></a>지원 되는 클라이언트

현재 지원 되는 클라이언트는 다음과 같습니다.  자주 확인 하 여이 목록에 대 한 업데이트를 확인 하세요.

- Windows 용 팀 데스크톱 클라이언트
- Mac 용 팀 데스크톱 클라이언트

## <a name="configure-dynamic-emergency-calling"></a>동적 비상 전화 구성

동적 비상 전화를 구성 하려면 다음 작업을 수행 해야 합니다.

- [긴급 주소 구성](#configure-emergency-addresses)
- [네트워크 설정 구성](#configure-network-settings)
- [위치 정보 서비스 구성](#configure-location-information-service)
- [응급 정책 구성](#configure-emergency-policies)
- [사용자 및 사이트 사용](#enable-users-and-sites)
- [비상 통화 테스트](#test-emergency-calling)


### <a name="configure-emergency-addresses"></a>긴급 주소 구성

미국 내에서 자동 라우팅을 지원 하려면 네트워크 식별자에 할당 된 비상 위치에 속하는 도심 주소를 완전히 구성 하 고 관련 지역 코드를 포함 해야 합니다. (지역 코드가 없는 긴급 주소는 동적 위치에 필요한 네트워크 식별자에 할당할 수 없습니다.)

- Microsoft 팀 관리 센터를 통해 긴급 주소를 입력 하는 경우 일치 하는 항목이 발견 되 면 지역 코드가 자동으로 포함 됩니다.

- 일치 하는 항목이 자동으로 발견 되지 않으면 긴급 주소를 수동으로 만들 수 있는 기회가 생깁니다.  

즉, 긴급 통화를 위해 기존 긴급 주소를 구성한 경우 지역 코드를 포함 하려면 같은 주소를 다시 만들어야 합니다.  두 주소를 구분 하려면 다른 설명을 포함 해야 합니다. 이전 주소를 가진 사용자에 게 새로운 긴급 주소를 할당할 수 있습니다. 완전히 마이그레이션한 경우 이전 주소를 삭제할 수 있습니다. 

긴급 주소를 구성 하는 방법에 대 한 자세한 내용은 [긴급 위치, 장소 및 통화 라우팅 이란?](what-are-emergency-locations-addresses-and-call-routing.md)을 참조 하세요.

### <a name="configure-network-settings"></a>네트워크 설정 구성

비상 전화를 라우팅하는 데 사용 되는 긴급 위치를 동적으로 획득 하도록 네트워크 설정을 구성 해야 하며, 선택적으로 보안 데스크 알림의 동적 구성을 제공할 수 있습니다. 필요한 응급 통화 환경에 따라 구성 해야 할 네트워크 설정이 결정 됩니다. 

다음 정의를 염두에 두어야 합니다.

- 신뢰할 수 있는 IP에는 엔터프라이즈 네트워크의 인터넷 외부 Ip 컬렉션이 포함 되며 사용자의 끝점이 회사 네트워크 내에 있는지 확인 하는 데 사용 됩니다. 동적 위치는 사용자의 외부 IP가 신뢰할 수 있는 IP 컬렉션의 IP와 일치 하는 경우에만 사용할 수 있습니다.  IPv4 또는 IPv6 IP 주소에 대해 일치가 이루어질 수 있으며, 네트워크 설정으로 전송 되는 IP 패킷의 형식에 따라 달라 집니다.

- 네트워크 지역에는 네트워크 사이트 컬렉션이 포함 됩니다. 

- 네트워크 사이트는 사무실, 건물 집합, 캠퍼스 등의 실제 가치를 가진 조직이 있는 위치를 나타냅니다. 이러한 사이트는 IP 서브넷의 모음으로 정의 됩니다.

- 네트워크 서브넷은 특정 네트워크 사이트와 연결 되어 있어야 합니다. 클라이언트의 위치는 네트워크 서브넷 및 연결 된 네트워크 사이트를 기준으로 결정 됩니다.  


통화 요금제 사용자:

- 보안 데스크 알림의 동적 구성이 필요한 경우에는 신뢰할 수 있는 IP 주소와 네트워크 사이트를 모두 구성 해야 합니다.

- 동적 위치만 필요한 경우에는 신뢰할 수 있는 IP 주소만 구성 해야 합니다. 

- 둘 다 필요 하지 않은 경우 네트워크 설정 구성이 필요 하지 않습니다. 

자세한 내용은 네트워크 설정을 구성 하는 방법을 설명 하는 [위치 기반 라우팅에 대 한 네트워크 설정 구성을](location-based-routing-configure-network-settings.md)참조 하세요. (이 문서의 정보는 호출 계획과 직접 라우팅 모두에 적용 됩니다.)


### <a name="configure-location-information-service"></a>위치 정보 서비스 구성

팀 클라이언트는 다양 한 네트워크 식별자와 연결 된 비상 위치에서 긴급 주소를 얻습니다.  서브넷 및 무선 액세스 지점은 모두 지원 됩니다. (이더넷 스위치/포트에 대 한 지원이 보류 중입니다.)

네트워크 식별자 및 비상 위치를 사용 하 여 LIS (위치 정보 서비스)를 구성 하려면 다음 cmdlet을 사용 합니다.

- Get, Set, Remove-CsOnlineLisPort
- Get, Set, Remove-CsOnlineLisSwitch
- Get, Set, Remove-CsOnlineLisSubnet
- Get, Set, Remove-CsOnlineLisWirelessAccessPoint 

> [!Important] 
> 네트워크 사이트의 일부로 서브넷을 사용 하는 경우 동적 위치를 렌더링 하기 위해 위치 정보 서비스에서 다시 정의 해야 합니다.


### <a name="configure-emergency-policies"></a>응급 정책 구성

응급 정책은 조직의 사용자가 긴급 통화를 할 때 어떤 일이 발생 하는지 결정 합니다.  사용자가 응급 서비스를 호출할 때 알림을 받을 사람과 알림 방법을 설정할 수 있습니다. 예를 들어 조직의 보안 데스크에 자동으로 알리기 위해 정책 설정을 구성 하 고 긴급 통화를 수신 대기 하도록 설정할 수 있습니다.

새로운, 설정 및 부여-CsTeamsEmergencyCalling 정책 cmdlet을 사용 하 여 긴급 정책을 관리할 수 있습니다.  자세한 내용은 [팀에서 긴급 통화 정책 관리](manage-emergency-calling-policies.md)를 참조 하세요.


### <a name="enable-users-and-sites"></a>사용자 및 사이트 사용

통화 계획 사용자는 비상 전화에 대해 자동으로 사용 하도록 설정 되지만 다음 예제에 표시 된 대로 긴급 통화 정책을 구성 하 여 사용자에 게 보안 데스크 알림을 설정 해야 합니다.


```
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

"Contoso 비상 전화 정책 1" 이라는 정책을 사이트 1에 할당 하는 다음 예와 같이 네트워크 사이트에 비상 통화 정책을 할당할 수도 있습니다.

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

긴급 통화 정책을 네트워크 사이트 및 사용자에 게 할당 하 고 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당 된 정책이 사용자에 게 할당 된 정책 보다 우선 합니다.


### <a name="test-emergency-calling"></a>비상 통화 테스트

미국에서 비상 전화를 테스트 하려면 미리 정의 된 긴급 테스트 비상 번호 933를 사용 합니다.  이 번호는 봇으로 라우팅되며 다음으로 발신자 전화 번호 (통화 라인 ID), 긴급 주소 또는 위치, 통화가 자동으로 PSAP에 라우팅되도록 또는 스크린 먼저 표시 되는지 여부 등으로 돌아갑니다.  