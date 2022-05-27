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
ms.openlocfilehash: 58cf5f560a22a58cb76ea28389d0dce1e3b3f4fb
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674880"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>직접 라우팅을 위한 로컬 미디어 최적화 구성

로컬 미디어 최적화 구성은 Location-Based 라우팅 및 동적 긴급 통화와 같은 다른 클라우드 음성 기능에 공통적인 네트워크 설정을 기반으로 합니다. 네트워크 지역, 네트워크 사이트, 네트워크 서브넷 및 신뢰할 수 있는 IP 주소에 대한 자세한 내용은 [클라우드 음성 기능에 대한 네트워크 설정을](cloud-voice-network-settings.md) 참조하세요.

로컬 미디어 최적화를 구성하기 전에 [직접 라우팅에 대한 로컬 미디어 최적화를 참조하세요](direct-routing-media-optimization.md).

로컬 미디어 최적화를 구성하려면 다음 단계가 필요합니다. Teams 관리 Center 또는 PowerShell을 사용할 수 있습니다. 자세한 내용은 [네트워크 토폴로지 관리를 참조하세요](manage-your-network-topology.md).

1. 사용자 및 SBC 사이트를 구성합니다(이 문서에 설명된 대로).
2. SBC 공급업체 사양에 따라 로컬 미디어 최적화를 위한 SBC를 구성합니다.

다음 다이어그램은 이 문서의 예제에서 사용되는 네트워크 설정을 보여 줍니다.

> [!div class="mx-imgBorder"]
> ![예를 들어 네트워크 설정을 보여 주는 다이어그램](media/direct-routing-media-op-9.png "예제에 대한 네트워크 설정")

## <a name="configure-the-user-and-the-sbc-sites"></a>사용자 및 SBC 사이트 구성

사용자 및 SBC 사이트를 구성하려면 다음을 수행해야 합니다.

1. [외부 신뢰할 수 있는 IP 주소를 관리합니다](#manage-external-trusted-ip-addresses).

2. 네트워크 지역, 네트워크 사이트 및 네트워크 서브넷을 구성하여 네트워크 [토폴로지를 정의](#define-the-network-topology)합니다.

3. 관련 모드 및 프록시 SBC 값을 사용하여 사이트에 SBC를 할당하여 [가상 네트워크 토폴](#define-the-virtual-network-topology)로지를 정의합니다.

> [!NOTE]
> 로컬 미디어 최적화는 DR(직접 라우팅) SBC(세션 테두리 컨트롤러) 내부 인터페이스에 도달한 회사 네트워크를 기준으로 외부 또는 내부로 검색되는 클라이언트 위치를 사용합니다.
> 클라이언트 엔드포인트가 고객의 네트워크 외부로 검색되는 분할 터널 VPN 시나리오에서 Microsoft는 클라이언트가 고객의 직접 라우팅 SBC의 내부 인터페이스에 연결할 수 있더라도 외부 위치를 SBC에 알릴 것입니다. 로컬 미디어 최적화를 사용하는 직접 라우팅 고객은 통화 설정 시간이 길어지고 경우에 따라 PSTN에서 전화를 받을 때 오디오가 없을 수 있습니다.
> 이를 방지하려면 VPN 관리자가 원격 VPN 사용자와 직접 라우팅 SBC 내부 인터페이스 간의 액세스를 차단해야 합니다.

## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>SBC 공급업체 사양에 따라 로컬 미디어 최적화에 대한 SBC 구성

이 문서에서는 Microsoft 구성 요소에 대한 구성을 설명합니다. SBC 구성에 대한 자세한 내용은 SBC 공급업체 설명서를 참조하세요. SBC 공급업체가 로컬 미디어 최적화를 지원하는 방법에 대한 자세한 내용은 [직접 라우팅을 위해 인증된 세션 테두리 컨트롤러를 참조하세요](direct-routing-border-controllers.md).

## <a name="manage-external-trusted-ip-addresses"></a>외부 신뢰할 수 있는 IP 주소 관리

외부 신뢰할 수 있는 IP는 엔터프라이즈 네트워크의 인터넷 외부 IP입니다. 이러한 IP는 Microsoft 365 연결할 때 Microsoft Teams 클라이언트에서 사용하는 IP 주소입니다. 로컬 미디어 최적화를 사용하는 사용자가 있는 각 사이트에 대해 이러한 외부 IP를 추가해야 합니다.

각 사이트에 대한 공용 IP 주소를 추가하려면 New-CsTenantTrustedIPAddress cmdlet을 사용합니다. 테넌트에 대한 신뢰할 수 있는 IP 주소는 무제한으로 정의할 수 있습니다. Microsoft 365 표시되는 외부 IP가 IPv4 및 IPv6 주소인 경우 두 가지 유형의 IP 주소를 모두 추가해야 합니다. IPv4의 경우 마스크 32를 사용합니다. IPv6의 경우 마스크 128을 사용합니다. cmdlet에서 서로 다른 MaskBits를 지정하여 개별 외부 IP 주소와 외부 IP 서브넷을 모두 추가할 수 있습니다.

```powershell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```

신뢰할 수 있는 IP 주소를 추가하는 예제입니다.

```powershell
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```

## <a name="define-the-network-topology"></a>네트워크 토폴로지 정의

이 섹션에서는 네트워크 토폴로지에 대한 네트워크 지역, 네트워크 사이트 및 네트워크 서브넷을 정의하는 방법을 설명합니다.

모든 매개 변수는 대/소문자를 구분하므로 설치 중에 사용된 것과 동일한 사례를 사용해야 합니다.  예를 들어 GatewaySiteID 값 "Vietnam" 및 "vietnam"은 다른 사이트로 처리됩니다.

### <a name="define-network-regions"></a>네트워크 지역 정의

네트워크 지역을 정의하려면 New-CsTenantNetworkRegion cmdlet을 사용합니다. RegionID 매개 변수는 지역의 지리를 나타내며 종속성 또는 제한이 없는 논리적 이름입니다. CentralSite `<site ID>` 매개 변수는 선택 사항입니다.

```powershell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>
```

다음 예제에서는 APAC라는 네트워크 지역을 만듭니다.

```powershell
New-CsTenantNetworkRegion -NetworkRegionID "APAC"
```

### <a name="define-network-sites"></a>네트워크 사이트 정의

네트워크 사이트를 정의하려면 New-CsTenantNetworkSite cmdlet을 사용합니다. 각 네트워크 사이트는 네트워크 지역과 연결되어야 합니다.

```powershell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

다음 예제에서는 APAC 지역에 세 개의 새 네트워크 사이트인 베트남, 인도네시아 및 싱가포르를 만듭니다.

```powershell
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>네트워크 서브넷 정의

네트워크 서브넷을 정의하고 네트워크 사이트에 연결하려면 New-CsTenantNetworkSubnet cmdlet을 사용합니다. 각 네트워크 서브넷은 하나의 사이트에만 연결할 수 있습니다.

```powershell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

다음 예제에서는 세 개의 네트워크 서브넷을 정의하고 세 개의 네트워크 사이트인 베트남, 인도네시아 및 싱가포르와 연결합니다.

```powershell
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID "Vietnam"
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID "Indonesia"
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID "Singapore"
```

## <a name="define-the-virtual-network-topology"></a>가상 네트워크 토폴로지 정의

먼저 테넌트 관리자 New-CsOnlinePSTNGateway cmdlet을 사용하여 각 관련 SBC에 대한 새 SBC 구성을 만듭니다.
테넌트 관리자 Set-CsOnlinePSTNGateway cmdlet을 사용하여 PSTN 게이트웨이 개체의 네트워크 사이트를 지정하여 가상 네트워크 토폴로지를 정의합니다.

```powershell
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

다음에 유의하세요.

- 고객에게 단일 SBC가 있는 경우 -ProxySBC 매개 변수는 필수 $null 또는 SBC FQDN 값(중앙 집중식 트렁크 시나리오가 있는 중앙 SBC)이어야 합니다.
- 로컬 미디어 최적화를 지원하려면 -MediaBypass 매개 변수를 $true 설정해야 합니다.
- SBC에 -BypassMode 매개 변수 집합이 없으면 X-MS 헤더가 전송되지 않습니다.
- 모든 매개 변수는 대/소문자를 구분하므로 설치 중에 사용된 것과 동일한 사례를 사용해야 합니다.  예를 들어 GatewaySiteID 값 "Vietnam" 및 "vietnam"은 다른 사이트로 처리됩니다.

다음 예제에서는 APAC 지역의 네트워크 사이트인 베트남, 인도네시아 및 싱가포르에 3개의 SCC를 추가하며 모드는 Always bypass입니다.

```powershell
Set-CSOnlinePSTNGateway -Identity "proxysbc.contoso.com" -GatewaySiteID "Singapore" -MediaBypass $true -BypassMode "Always" -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity "VNsbc.contoso.com" -GatewaySiteID "Vietnam" -MediaBypass $true -BypassMode "Always" -ProxySBC "proxysbc.contoso.com"

Set-CSOnlinePSTNGateway -Identity "IDsbc.contoso.com" -GatewaySiteID "Indonesia" -MediaBypass $true -BypassMode "Always" -ProxySBC "proxysbc.contoso.com"
```

> [!NOTE]
> 로컬 미디어 최적화 및 LBR(Location-Based 라우팅)을 동시에 구성할 때 중단 없는 작업을 보장하려면 GatewaySiteLbrEnabled 매개 변수를 각 다운스트림 SBC에 대해 $true 설정하여 LBR에 대해 다운스트림 SBC를 사용하도록 설정해야 합니다. (이 설정은 프록시 SBC에 필수는 아닙니다.)

위의 정보에 따라 직접 라우팅에는 다음 표와 같이 SIP 초대 및 다시 초대에 대한 세 개의 독점 SIP 헤더가 포함됩니다.

초대 시 직접 라우팅에 도입된 X-MS 헤더 및 BypassMode가 정의된 경우 Re-Invites.

|헤더 이름|값|설명|
|---|---|---|
|X-MS-UserLocation|internal/external|사용자가 내부 또는 외부인지 여부를 나타냅니다.|
|Request-URI INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0|SBC FQDN|SBC가 직접 라우팅에 직접 연결되지 않은 경우에도 호출을 대상으로 하는 FQDN|
|X-MS-MediaPath|예: proxysbc.contoso.com, VNsbc.contoso.com|사용자와 대상 SBC 간의 미디어 경로에 사용해야 하는 SBC의 순서입니다. 최종 SBC는 항상 마지막입니다.|
|X-MS-UserSite|usersiteID|테넌트 관리자 정의한 문자열|

## <a name="call-flows"></a>호출 흐름

다음은 두 가지 모드에 대한 호출 흐름을 보여 줍니다.

- [Always Bypass](#always-bypass-mode)
- [로컬 사용자에 대해서만](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>Always Bypass 모드

Always Bypass 모드는 구성하는 가장 간단한 옵션입니다. 테넌트 관리자 모든 사이트에서 모든 SCC에 연결할 수 있는 경우 모든 사용자 및 SCC에 대해 단일 사이트를 구성할 수 있습니다.

예제에서는 다음 시나리오에 대한 Always 바이패스 모드를 보여 줍니다.

- [아웃바운드 호출 및 사용자가 SBC와 동일한 위치에 있음](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [인바운드 호출 및 사용자가 SBC와 동일한 위치에 있음](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [아웃바운드 호출 및 사용자가 외부에 있는 경우](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [인바운드 호출 및 사용자가 외부에 있는 경우](#inbound-calls-and-the-user-is-external-with-always-bypass)

다음 표에서는 예제에 사용된 FQDN 및 IP 주소를 보여 줍니다.

|FQDN|SBC 외부 IP 주소|SBC 내부 IP 주소|내부 서브넷|위치|외부 NAT(신뢰할 수 있는 IP)|
|---|---|---|---|---|---|
|VNsbc.contoso.com|없음|192.168.1.5|192.168.1.0/24|베트남|172.16.240.110|
|IDsbc.contoso.com|없음|192.168.2.5|192.168.2.0/24|인도네시아|172.16.240.120|
|proxysbc.contoso.com|172.16.240.133|192.168.3.5|192.168.3.0/24|싱가포르|172.16.240.130|

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>아웃바운드 호출 및 사용자가 Always Bypass를 사용하여 SBC와 동일한 위치에 있음

|모드|사용자|위치|통화 방향|
|---|---|---|---|
|AlwaysBypass|내부|SBC와 동일한 사이트|아웃 바운드|

다음 표에서는 최종 사용자 구성 및 작업을 보여 줍니다.

|사용자 실제 위치|사용자가 전화 걸기 또는 수신 번호|사용자 전화 번호|온라인 음성 라우팅 정책|SBC에 대해 구성된 모드|
|---|---|---|---|---|
|베트남|+84 4 3926 3000|+84 4 5555 5555|우선 순위 1: ^\+84(\d{9})$ -VNsbc.contoso.com <br> 우선 순위 2: .* - proxysbc.contoso.com|VNsbc.contoso.com – 항상 바이패스 <br> proxysbc.contoso.com – 항상 바이패스|

다음 다이어그램에서는 Always 바이패스 모드를 사용하는 아웃바운드 호출에 대한 SIP 사다리와 SBC와 동일한 위치에 있는 사용자를 보여 둡다.

> [!div class="mx-imgBorder"]
> ![아웃바운드 호출을 보여 주는 다이어그램](media/direct-routing-media-op-10.png "아웃바운드 호출")

다음 표에서는 직접 라우팅에서 보낸 X-MS 헤더를 보여 줍니다.

|매개 변수|설명|
|---|---|
|초대 +8443926300@VNsbc.contoso.com|온라인 음성 라우팅 정책에 정의된 SBC의 대상 FQDN이 요청 URI로 전송됩니다.|
|X-MS-UserLocation: 내부|사용자가 회사 네트워크 내에 있음을 나타내는 필드|
|X-MS-MediaPath: VNsbc.contoso.com|클라이언트가 대상 SBC로 트래버스해야 하는 SBC를 지정합니다. 이 경우 Always Bypass가 있고 클라이언트는 헤더에서 유일한 이름으로 전송된 대상 이름 내부입니다.|
|X-MS-UserSite: 베트남|사용자가 있는 사이트 내에 표시된 필드입니다.|

#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>인바운드 호출 및 사용자가 Always Bypass를 사용하여 SBC와 동일한 위치에 있음

|모드|사용자|위치|통화 방향|
|---|---|---|---|---|
|AlwaysBypass|내부|SBC와 동일한 사이트|인바운드|

인바운드 호출에서 사용자의 위치를 알 수 없으며 SBC는 사용자가 어디에 있는지 추측해야 합니다. 추측이 올바르지 않으면 다시 초대가 필요합니다. 이 경우 사용자가 내부이고, 미디어가 직접 흐를 수 있으며, 추가 작업이 필요하지 않습니다(다시 초대).
직접 라우팅 서비스에 연결된 SBC는 Record-Route 및 연락처 필드를 제공하여 원래 SBC 위치를 보고합니다. 이러한 필드에 따라 미디어 경로는 직접 라우팅에 의해 계산됩니다.

참고: 사용자에게 여러 엔드포인트가 있을 수 있으므로 183을 지원할 수 없습니다. 이 경우 직접 라우팅은 항상 180 벨소리를 사용합니다.

다음 다이어그램은 AlwaysBypass 모드를 사용하여 인바운드 호출에 대한 SIP 사다리를 보여 하며 사용자는 SBC와 동일한 위치에 있습니다.

> [!div class="mx-imgBorder"]
> ![SIP 사다리를 보여 주는 다이어그램](media/direct-routing-media-op-11.png)

#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>아웃바운드 호출 및 사용자가 Always Bypass를 사용하여 외부에 있는 경우

|모드|사용자|사이트|통화 방향
|---|---|---|---|
|AlwaysBypass|외부|해당 없음|아웃 바운드|

다음 다이어그램은 AlwaysBypass 모드를 사용하는 아웃바운드 호출에 대한 SIP 사다리를 보여 하며 사용자는 외부에 있습니다.

> [!div class="mx-imgBorder"]
> ![다이어그램은 SIP 사다리를 보여줍니다.](media/direct-routing-media-op-12.png)

다음 표에서는 직접 라우팅 서비스에서 보낸 X-MS 헤더를 보여 줍니다.

|매개 변수|설명|
|---|---|
|초대 +8443926300@VNsbc.contoso.com|온라인 음성 라우팅 정책에 정의된 SBC의 대상 FQDN이 요청 URI로 전송됩니다.|
|X-MS-UserLocation: external|사용자가 회사 네트워크 외부에 있음을 나타내는 필드입니다.|
|X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com|클라이언트가 대상 SBC로 트래버스해야 하는 SBC를 지정합니다. 이 경우 Always Bypass가 있고 클라이언트가 외부에 있기 때문에|

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>인바운드 호출 및 사용자가 Always Bypass를 사용하여 외부에 있는 경우

|모드|사용자|사이트|통화 방향|
|---|---|---|---|
|AlwaysBypass|외부|해당 없음|인바운드|

인바운드 호출의 경우 직접 라우팅에 연결된 SBC는 사용자의 위치가 외부인 경우 다시 초대를 보내야 합니다(기본적으로 로컬 미디어 후보는 항상 제공됨).  X-MediaPath는 지정된 SBC 사용자 및 Record-Route 기반으로 계산됩니다.

다음 다이어그램은 AlwaysBypass 모드를 사용하는 인바운드 호출에 대한 SIP 사다리를 보여 하며 사용자는 외부에 있습니다.

> [!div class="mx-imgBorder"]
> ![다시 SIP 사다리를 보여 주는 다이어그램.](media/direct-routing-media-op-13.png)

### <a name="only-for-local-users-mode"></a>로컬 사용자 모드에만 해당

대상 SBC의 로컬 미디어 후보는 사용자가 SBC와 동일한 위치에 있는 경우에만 제공됩니다. 다른 모든 경우에서 미디어는 프록시 SBC의 내부 또는 외부 IP를 통해 흐릅니다.

다음 시나리오에 대해 설명합니다.

- [아웃바운드 호출 및 사용자가 SBC와 동일한 위치에 있음](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [인바운드 호출 및 사용자가 SBC와 동일한 위치에 있음](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [사용자가 SBC와 동일한 위치에 있지 않지만 회사 네트워크에 있습니다.](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [인바운드 호출 및 사용자가 내부이지만 SBC와 동일한 위치에 있지 않습니다.](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

다음 표에서는 최종 사용자 구성 및 작업을 보여 줍니다.

|사용자 실제 위치|사용자가 전화 걸기 또는 수신 번호|사용자 전화 번호|온라인 음성 라우팅 정책|SBC에 대해 구성된 모드|
|---|---|---|---|---|
|베트남|+84 4 3926  3000|+84 4 5555 5555|우선 순위 1: ^\+84(\d{9})$ -VNsbc.contoso.com <br> 우선 순위 2: .* - proxysbc.contoso.com|VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – 항상 바이패스|

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>아웃바운드 호출 및 사용자가 로컬 사용자만 있는 SBC와 동일한 위치에 있습니다.

|모드|사용자|사이트|통화 방향|
|---|---|---|---|
|OnlyForLocalUsers|내부|SBC와 동일|아웃 바운드|

다음 다이어그램은 OnlyForLocalUsers 모드를 사용하는 아웃바운드 호출을 보여 하며 사용자는 SBC와 동일한 위치에 있습니다. [사용자가 SBC와 동일한 위치에 있는 경우 아웃바운드 호출에 표시된 것과 동일한 흐름입니다](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).

> [!div class="mx-imgBorder"]
> ![다이어그램은 다시 SIP 사다리를 보여줍니다.](media/direct-routing-media-op-14.png)

#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>인바운드 호출 및 사용자가 로컬 사용자만 있는 SBC와 동일한 위치에 있습니다.

|모드|사용자|사이트|통화 방향|
|---|---|---|---|
|OnlyForLocalUsers|내부|SBC와 동일|인바운드|

다음 다이어그램은 OnlyForLocalUsers 모드를 사용하는 인바운드 호출을 보여 하며 사용자는 SBC와 동일한 위치에 있습니다. [사용자가 SBC와 동일한 위치에 있는 경우 인바운드 호출에 표시된 것과 동일한 흐름입니다](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).

> [!div class="mx-imgBorder"]
> ![SIP 사다리를 보여 주는 또 다른 다이어그램입니다.](media/direct-routing-media-op-15.png)

#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>사용자가 SBC와 동일한 위치에 있지 않지만 로컬 사용자만 있는 회사 네트워크에 있습니다.

|모드|사용자|사이트|통화 방향|
|---|---|---|---|
|OnlyForLocalUsers|내부|SBC와 다릅니다.|아웃 바운드|

직접 라우팅은 SBC에 구성된 사용자 및 모드의 보고된 위치를 기반으로 X-MediaPath를 계산합니다.

다음 다이어그램에서는 OnlyForLocalUsers 모드를 사용하는 아웃바운드 호출과 SBC와 동일한 위치에 있지 않은 내부 사용자를 보여  있습니다.

> [!div class="mx-imgBorder"]
> ![또 다른 다이어그램은 SIP 사다리를 보여줍니다.](media/direct-routing-media-op-16.png)

#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>인바운드 호출 및 사용자가 내부이지만 로컬 사용자만 있는 SBC와 동일한 위치에 있지 않습니다.

|모드|사용자|사이트|통화 방향|
|---|---|---|---|
|OnlyForLocalUsers|내부|SBC와 다릅니다.|인바운드|

다음 다이어그램에서는 OnlyForLocalUsers 모드를 사용하는 인바운드 호출 및 SBC와 동일한 위치에 있지 않은 내부 사용자를 보여  있습니다.

> [!div class="mx-imgBorder"]
> ![SIP 사다리를 보여 주는 또 다른 다이어그램입니다.](media/direct-routing-media-op-17.png)
