---
title: 직접 라우팅을 위한 로컬 미디어 최적화 구성
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: 직접 라우팅을 위한 로컬 미디어 최적화 구성
appliesto:
- Microsoft Teams
ms.openlocfilehash: 004f4ba43bda1502041ba2ec9e34194fd8be93fb
ms.sourcegitcommit: b17e5acadcca0261eaccc64e1b4ee457348f975c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/17/2021
ms.locfileid: "58365635"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>직접 라우팅을 위한 로컬 미디어 최적화 구성

로컬 미디어 최적화 구성은 라우팅 및 동적 긴급 호출과 같은 다른 클라우드 음성 기능에 Location-Based 네트워크 설정을 기반으로 합니다. 네트워크 지역, 네트워크 사이트, 네트워크 서브넷 및 신뢰할 수 있는 IP 주소에 대한 자세한 내용은 클라우드 음성 기능에 대한 네트워크 설정을 [참조하세요.](cloud-voice-network-settings.md)

로컬 미디어 최적화를 구성하기 전에 직접 라우팅에 대한 로컬 미디어 최적화 [를 참조합니다.](direct-routing-media-optimization.md)  

로컬 미디어 최적화를 구성하려면 다음 단계가 필요합니다. 관리 센터 또는 Teams 사용할 수 있습니다. 자세한 내용은 네트워크 [토폴로지 관리를 참조합니다.](manage-your-network-topology.md)

1. 사용자 및 SBC 사이트를 구성합니다(이 문서에 설명된 바와 같이).
2. 로컬 미디어 최적화용 SBC를 구성합니다(SBC 공급업체 사양에 따라).

다음 다이어그램은 이 문서 전체의 예제에 사용된 네트워크 설정을 보여 주었다.

![예제에 대한 네트워크 설정을 보여주는 다이어그램](media/direct-routing-media-op-9.png "예제에 대한 네트워크 설정")


## <a name="configure-the-user-and-the-sbc-sites"></a>사용자 및 SBC 사이트 구성

사용자 및 SBC 사이트를 구성하려면 다음이 필요합니다.

1. [외부 신뢰할 수 있는 IP 주소를 관리합니다.](#manage-external-trusted-ip-addresses)  

2. [네트워크 지역,](#define-the-network-topology) 네트워크 사이트 및 네트워크 서브넷을 구성하여 네트워크 토폴로지 정의

3. [관련 모드](#define-the-virtual-network-topology) 및 프록시 SBC 값을 사용하여 사이트에 SBC를 할당하여 가상 네트워크 토폴로지 정의


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>SBC 공급업체 사양에 따라 로컬 미디어 최적화를 위한 SBC 구성

이 문서에서는 Microsoft 구성 요소에 대한 구성을 설명합니다. SBC 구성에 대한 자세한 내용은 SBC 공급업체 설명서를 참조하세요. 로컬 미디어 최적화를 지원하는 SBC 공급업체에 대한 자세한 내용은 직접 라우팅 인증 세션 테두리 컨트롤러를 [참조하세요.](direct-routing-border-controllers.md)

## <a name="manage-external-trusted-ip-addresses"></a>외부 신뢰할 수 있는 IP 주소 관리

외부 신뢰할 수 있는 IPS는 엔터프라이즈 네트워크의 인터넷 외부 IPS입니다. 이러한 IP는 클라이언트에 연결할 때 Microsoft Teams 클라이언트에서 사용하는 IP Microsoft 365. 로컬 미디어 최적화를 사용하는 사용자가 있는 각 사이트에 대해 이러한 외부 IPS를 추가해야 합니다.

각 사이트에 대한 공용 IP 주소를 추가하기 위해 New-CsTenantTrustedIPAddress cmdlet을 사용합니다. 테넌트에 대한 신뢰할 수 있는 IP 주소를 무제한으로 정의할 수 있습니다. 외부 IP가 IPv4 Microsoft 365 IPv6 주소인 경우 두 유형의 IP 주소를 모두 추가해야 합니다. IPv4의 경우 마스크 32를 사용 합니다. IPv6의 경우 마스크 128을 사용 합니다. cmdlet에 다른 MaskBits를 지정하여 개별 외부 IP 주소와 외부 IP 서브넷을 둘 다 추가할 수 있습니다.

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


신뢰할 수 있는 IP 주소를 추가하는 예제입니다.

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a>네트워크 토폴로지 정의

이 섹션에서는 네트워크 토폴로지에 대한 네트워크 지역, 네트워크 사이트 및 네트워크 서브넷을 정의하는 방법을 설명합니다.

모든 매개 변수는 대소문자에 민감하기 때문에 설정 중에 사용된 동일한 사례를 사용해야 합니다.  (예를 들어 GatewaySiteID 값 "베트남" 및 "베트남"은 다른 사이트로 처리됩니다.)

### <a name="define-network-regions"></a>네트워크 지역 정의

네트워크 지역을 정의하기 위해 New-CsTenantNetworkRegion cmdlet을 사용 합니다. RegionID 매개 변수는 지역의 지역을 나타내는 논리적 이름로 종속성 또는 제한 사항이 없습니다. CentralSite `<site ID>` 매개 변수는 선택 사항입니다.

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

다음 예제에서는 APAC라는 네트워크 지역을 만듭니다.

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a>네트워크 사이트 정의

네트워크 사이트를 정의하기 위해 New-CsTenantNetworkSite cmdlet을 사용 합니다. 각 네트워크 사이트는 네트워크 지역과 연결되어야 합니다.

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

다음 예제에서는 APAC 지역에 베트남, 인도네시아 및 싱가포르의 세 개의 새 네트워크 사이트를 만듭니다.

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>네트워크 서브넷 정의

네트워크 서브넷을 정의하고 네트워크 사이트에 연결하기 위해 New-CsTenantNetworkSubnet cmdlet을 사용 합니다. 각 네트워크 서브넷은 하나의 사이트와만 연결될 수 있습니다. 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

다음 예제에서는 세 개의 네트워크 서브넷을 정의하고 세 개의 네트워크 사이트(베트남, 인도네시아 및 싱가포르)와 연결합니다.

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a>가상 네트워크 토폴로지 정의 

먼저 테넌트 관리자는 New-CsOnlinePSTNGateway cmdlet을 사용하여 각 관련 SBC에 대한 새 SBC 구성을 만듭니다.
테넌트 관리자는 다음 cmdlet을 사용하여 PSTN 게이트웨이 개체에 대한 네트워크 사이트를 지정하여 가상 네트워크 토폴로지 Set-CsOnlinePSTNGateway 정의합니다.

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

다음에 유의하세요. 
   - 고객이 단일 SBC를 사용하는 경우 -ProxySBC 매개 변수는 필수 $null SBC FQDN 값(중앙 SBC와 중앙 트렁크 시나리오)되어야 합니다.
   - 로컬 미디어 최적화를 지원하려면 -MediaBypass 매개 변수를 $true 설정해야 합니다.
   - SBC에 -BypassMode 매개 변수 집합이 없는 경우 X-MS 헤더는 전송되지 않습니다. 
   - 모든 매개 변수는 대소문자 구분이 있으므로 설정 중에 사용된 동일한 사례를 사용해야 합니다.  (예를 들어 GatewaySiteID 값 "베트남" 및 "베트남"은 다른 사이트로 처리됩니다.)

다음 예제에서는 Always bypass 모드가 있는 APAC 지역의 네트워크 사이트 베트남, 인도네시아 및 싱가포르에 3개의 SBC를 추가합니다.

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

참고: 로컬 미디어 최적화 및 LBR(Location-Based 라우팅)을 동시에 구성할 때 작업을 확정하려면 GatewaySiteLbrEnabled 매개 변수를 각 다운스트림 SBC에 대해 $true 설정하여 LBR에 대해 다운스트림 SBC를 사용하도록 설정해야 합니다. (이 설정은 프록시 SBC에 필수가 아닙니다.)

위의 정보를 기반으로 직접 라우팅에는 다음 표와 같이 SIP 초대 및 다시 초대에 대한 3개의 독점 SIP 헤더가 포함됩니다.

BypassMode가 정의되어 있는 경우 초대 및 Re-Invites 직접 라우팅에 소개된 X-MS 헤더:

| 헤더 이름 | 값 | 설명 | 
|:------------|:-------|:-------|
| X-MS-UserLocation | 내부/외부 | 사용자가 내부 또는 외부인지 나타냅니다. |
| Request-URI INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0 | SBC FQDN | SBC가 직접 라우팅에 연결되지 않은 경우에도 호출을 대상으로 하는 FQDN |
| X-MS-MediaPath | 예: proxysbc.contoso.com, VNsbc.contoso.com | 사용자와 대상 SBC 간의 미디어 경로에 사용해야 하는 SBC의 순서입니다. 최종 SBC는 항상 마지막 |
| X-MS-UserSite | usersiteID | 테넌트 관리자가 정의한 문자열 |

## <a name="call-flows"></a>통화 흐름 

다음은 두 가지 모드에 대한 호출 흐름을 보여줍니다.

- [Always Bypass](#always-bypass-mode)
- [로컬 사용자만 해당](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>Always Bypass 모드

Always Bypass 모드는 구성하는 가장 간단한 옵션입니다. 테넌트 관리자는 모든 사이트에서 모든 SBC에 도달할 수 있는 경우 모든 사용자 및 SBC에 대해 단일 사이트를 구성할 수 있습니다.

예제에서는 다음 시나리오에 대해 Always bypass 모드를 보여 니다.

- [아웃바운드 호출 및 사용자가 SBC와 동일한 위치에 있습니다.](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [인바운드 호출 및 사용자가 SBC와 동일한 위치에 있습니다.](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [아웃바운드 호출 및 사용자가 외부](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [인바운드 호출 및 사용자가 외부](#inbound-calls-and-the-user-is-external-with-always-bypass)

다음 표에서는 예제에 사용된 FQDN 및 IP 주소를 보여 주었다.

| FQDN | SBC 외부 IP 주소 | SBC 내부 IP 주소 | 내부 서브넷 | 위치 | 외부 NAT(신뢰할 수 있는 IP) |
|:------------|:-------|:-------|:-------|:-------|:-------|
| VNsbc.contoso.com | 없음 | 192.168.1.5 | 192.168.1.0/24 | 베트남 | 172.16.240.110 |
| IDsbc.contoso.com | 없음 | 192.168.2.5 | 192.168.2.0/24 | 인도네시아 | 172.16.240.120 |
| proxysbc.contoso.com | 172.16.240.133 | 192.168.3.5 | 192.168.3.0/24 | 싱가포르 | 172.16.240.130 |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>아웃바운드 호출 및 사용자는 Always Bypass를 통해 SBC와 동일한 위치에 있습니다.

| 모드 |    사용자 |  위치 |  통화 방향 |
|:------------|:-------|:-------| :-------|
| AlwaysBypass |    내부 |  SBC와 동일한 사이트 |  아웃바운드 |

다음 표에서는 최종 사용자 구성 및 작업을 보여줍니다.

| 사용자 물리적 위치| 사용자가 번호로/받는 전화 걸기 또는 수신 | 사용자 전화 번호  | 온라인 음성 라우팅 정책 | SBC에 대해 구성된 모드 |
|:------------|:-------|:-------|:-------|:-------|
| 베트남 | +84 4 3926 3000 | +84 4 5555 5555   | 우선 순위 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> 우선 순위 2: .* - proxysbc.contoso.com   | VNsbc.contoso.com – Always Bypass <br> proxysbc.contoso.com – Always Bypass


다음 다이어그램은 Always bypass 모드로 아웃바운드 호출에 대한 SIP 사다리와 SBC와 동일한 위치에 있는 사용자를 보여 주며,

![아웃바운드 호출을 보여주는 다이어그램](media/direct-routing-media-op-10.png "아웃바운드 호출")

다음 표에서는 직접 라우팅으로 전송된 X-MS 헤더를 보여 주었다.

| 매개 변수 | 설명 |
|:------------|:-------|
| +8443926300@VNsbc.contoso.com | 온라인 음성 라우팅 정책에 정의된 SBC의 대상 FQDN이 요청 URI에서 전송됩니다. | 
| X-MS-UserLocation: 내부 | 사용자가 회사 네트워크 내부에 있는 것으로 표시된 필드 |
| X-MS-MediaPath: VNsbc.contoso.com |   클라이언트가 대상 SBC로 트래버스해야 하는 SBC를 지정합니다. 이 경우 Always Bypass가 있으며 클라이언트는 헤더의 유일한 이름으로 전송된 대상 이름 내부에 있습니다. | 
|X-MS-UserSite: 베트남 |   사용자가 있는 사이트 내에 표시된 필드입니다. |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>인바운드 호출 및 사용자는 Always Bypass를 통해 SBC와 동일한 위치에 있습니다.

| 모드 |    사용자 |  위치 |  통화 방향 |
|:------------|:-------|:-------|:-------|:-------|
| AlwaysBypass |    내부 | SBC와 동일한 사이트 | 인바운드 |


인바운드 호출 시 사용자의 위치를 알 수 없는 경우 SBC는 사용자가 있는 위치를 추측해야 합니다. 추측이 정확하지 않은 경우 다시 초대해야 합니다. 이 경우 사용자가 내부에 있으며 미디어가 직접 흐름할 수 있으며 추가 작업이 필요하지 않습니다(다시 초대).를 가정합니다.
직접 라우팅 서비스에 연결된 SBC는 필드 및 연락처 필드를 제공하여 원래 SBC Record-Route 보고합니다. 이러한 필드를 기반으로 미디어 경로는 직접 라우팅으로 계산됩니다.

참고: 사용자가 여러 엔드포인트를 사용할 수 있는 경우 183을 지원할 수 없습니다. 이 경우 직접 라우팅은 항상 180 Ringing을 사용하게됩니다. 

다음 다이어그램에서는 AlwaysBypass 모드를 사용하여 인바운드 호출에 대한 SIP 사다리가 표시되어 있으며 사용자는 SBC와 동일한 위치에 있습니다.

![SIP 사다리가 있는 다이어그램입니다.](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>아웃바운드 호출 및 사용자가 Always Bypass를 통해 외부

| 모드 |    사용자 |  사이트 |  통화 방향
|:------------|:-------|:-------|:-------|
AlwaysBypass |  외부 |  해당 없음 | 아웃바운드 |


다음 다이어그램에서는 AlwaysBypass 모드를 사용하여 아웃바운드 호출에 대한 SIP 사다리가 표시되어 사용자가 외부입니다.

![다이어그램에는 SIP 사다리가 표시됩니다.](media/direct-routing-media-op-12.png)

다음 표에서는 직접 라우팅 서비스에 의해 전송된 X-MS 헤더를 보여줍니다.

| 매개 변수 |   설명 |
|:------------|:-------|
|+8443926300@VNsbc.contoso.com | 온라인 음성 라우팅 정책에 정의된 SBC의 대상 FQDN이 요청 URI에 전송됩니다.|
| X-MS-UserLocation: 외부 | 필드는 사용자가 회사 네트워크 외부에 있습니다. |
| X-MS-MediaPath: proxysbc.contoso.com VNsbc.contoso.com    | 클라이언트가 대상 SBC로 트래버스해야 하는 SBC를 지정합니다. 이 경우 Always Bypass가 있으며 클라이언트는 외부입니다. |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>인바운드 호출 및 Always Bypass를 통해 외부

| 모드 | 사용자 | 사이트 |  통화 방향 |
|:------------|:-------|:-------|:-------|
AlwaysBypass |  외부 |  해당 없음 |   인바운드 |

인바운드 호출의 경우 직접 라우팅에 연결된 SBC는 사용자의 위치가 외부인 경우 다시 초대(기본적으로 로컬 미디어 후보는 항상 제공)를 보내야 합니다.  X-MediaPath는 지정한 SBC Record-Route 기준으로 계산됩니다.

다음 다이어그램에서는 AlwaysBypass 모드를 사용하여 인바운드 호출에 대한 SIP 사다리가 표시되어 사용자가 외부입니다.

![SIP 사다리가 다시 보여진 다이어그램입니다.](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a>로컬 사용자 모드만

대상 SBC의 로컬 미디어 후보는 사용자가 SBC와 동일한 위치에 있는 경우만 제공됩니다. 다른 모든 경우 미디어는 프록시 SBC의 내부 또는 외부 IP를 통해 흐르게 됩니다.

다음 시나리오는 다음과 같습니다.

- [아웃바운드 호출 및 사용자가 SBC와 동일한 위치에 있습니다.](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [인바운드 호출 및 사용자가 SBC와 동일한 위치에 있습니다.](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [사용자가 SBC와 동일한 위치에 있지 않지만 회사 네트워크에 있습니다.](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [인바운드 호출 및 사용자는 내부이지만 SBC와 동일한 위치에 있지 않습니다.](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

다음 표에서는 최종 사용자 구성 및 작업을 보여줍니다.

| 사용자 물리적 위치 |  사용자가 번호로/받는 전화 걸기 또는 수신 |  사용자 전화 번호 | 온라인 음성 라우팅 정책 |   SBC에 대해 구성된 모드 |
|:------------|:-------|:-------|:-------|:-------|
| 베트남 | +84 4 3926 3000 |  +84 4 5555 5555 | 우선 순위 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> 우선 순위 2: .* - proxysbc.contoso.com | VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>아웃바운드 호출 및 사용자는 로컬 사용자 전용으로 SBC와 동일한 위치에 있습니다.

| 모드 | 사용자 | 사이트 | 통화 방향 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   내부 |SBC와 동일   | 아웃바운드 |

다음 다이어그램은 OnlyForLocalUsers 모드로 아웃바운드 호출을 보여 주며 사용자는 SBC와 동일한 위치에 있습니다. 사용자가 SBC와 동일한 위치에 있는 경우 아웃바운드 호출에 표시된 [흐름과 동일합니다.](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)

![다이어그램은 SIP 사다리가 다시 표시됩니다.](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>인바운드 호출 및 사용자는 로컬 사용자 전용으로 SBC와 동일한 위치에 있습니다.

| 모드 | 사용자 | 사이트 | 통화 방향 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   내부 | SBC와 동일 | 인바운드 |

다음 다이어그램은 OnlyForLocalUsers 모드로 인바운드 호출을 보여 주며 사용자는 SBC와 동일한 위치에 있습니다. 사용자가 SBC와 동일한 위치에 있는 경우 인바운드 호출에 표시된 흐름과 [동일합니다.](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)

![SIP 사다리가 있는 또 다른 다이어그램입니다.](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>사용자가 SBC와 동일한 위치에 있지 않지만 로컬 사용자만 있는 회사 네트워크에 있습니다.

| 모드 | 사용자 | 사이트 |통화 방향 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers  | 내부 |   SBC와 다릅니다. | 아웃바운드 |

직접 라우팅은 SBC에 구성된 사용자 및 모드의 보고된 위치를 기반으로 X-MediaPath를 계산합니다.


다음 다이어그램은 OnlyForLocalUsers 모드와 SBC와 동일한 위치에 있지 않은 내부 사용자를 사용하여 아웃바운드 호출을 보여줍니다.

![다른 다이어그램에서는 SIP 사다리가 표시됩니다.](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>인바운드 호출 및 사용자는 내부이지만 로컬 사용자만 있는 SBC와 동일한 위치에 있지 않습니다.

| 모드 |    사용자 |  사이트 |  통화 방향 |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers | 내부 |    SBC와 다릅니다. |    인바운드 |

다음 다이어그램은 OnlyForLocalUsers 모드로 인바운드 호출을 보여 주며 SBC와 동일한 위치에 있지 않은 내부 사용자를 보여줍니다.

![그러나 SIP 사다리가 있는 또 다른 다이어그램입니다.](media/direct-routing-media-op-17.png)









