---
title: Microsoft Teams에서 클라우드 음성 기능에 대한 네트워크 토폴로지 관리
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams에서 클라우드 음성 기능에 대한 네트워크 설정을 구성하는 방법을 배워야 합니다.
ms.openlocfilehash: 7d8bc7f06934134538fca59a3f19285d97756e2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802578"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Microsoft Teams에서 클라우드 음성 기능에 대한 네트워크 토폴로지 관리

조직에서 직접 라우팅 [](location-based-routing-plan.md) 또는 동적 긴급 통화를 위한 [](configure-dynamic-emergency-calling.md)위치 기반 라우팅을 배포하는 경우 Microsoft Teams에서 이러한 클라우드 음성 기능과 함께 사용할 네트워크 설정을 구성해야 합니다. 네트워크 설정은 Teams 클라이언트의 위치를 결정하고 네트워크 지역, 네트워크 사이트, 서브넷 및 신뢰할 수 있는 IP 주소를 포함하기 위해 사용됩니다. 배포하는 클라우드 음성 기능 및 기능에 따라 이러한 설정의 일부 또는 전체를 구성합니다. 이러한 용어에 대한 자세한 내용은 클라우드 음성 기능에 대한 [네트워크 설정을 참조하세요.](cloud-voice-network-settings.md)

Microsoft Teams 관리  센터의 네트워크 토폴로지 페이지에서 또는 네트워크 설정을 사용하여 Windows PowerShell.

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터에서 네트워크 설정 구성

[!INCLUDE [preview-feature](includes/preview-feature.md)]

네트워크 토폴로지 페이지의 네트워크 사이트 탭에서  네트워크 지역, 네트워크 사이트 및 서브넷을 **정의합니다.** 여기에서 네트워크 사이트를 만들거나 수정하고, 사이트를 네트워크 지역과 연결하고, 사이트에 서브넷을 연결하고, 위치 기반 라우팅을 설정하고, 사이트에 긴급 정책을 할당할 수 있습니다. 모든 사이트에 전역적으로 사용할 수 있는 네트워크 지역을 추가할 수도 있습니다.

#### <a name="add-and-configure-a-network-site"></a>네트워크 사이트 추가 및 구성

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **위치** 네트워크 토폴로지로 이동한 다음 네트워크 사이트  >   **탭을** 클릭합니다.
2. **추가를** 클릭한 다음 사이트의 이름과 설명을 입력합니다.

    ![네트워크 사이트 추가 페이지의 스크린샷](media/manage-network-topology-add-site.png)

3. 사이트를 네트워크 지역과 연결하려면 네트워크 지역 추가를 클릭하고 **기존** 지역을 선택하거나 추가를 클릭하여 지역을 추가한 다음 링크를 **클릭합니다.**   
4. 사이트에 Location-Based 라우팅을 사용하도록 설정하려면 위치 기반 **라우팅을 켜야 합니다.**
5. 사이트에 응급 서비스 정책을 할당하기 위해 다음 중 하나 또는 둘 다를 적용합니다.

    - 조직에서 통화 요금제 또는 배포된 전화 시스템 직접 라우팅을 사용하는 경우 긴급 통화 정책에서 원하는 정책을 선택합니다.
    - 조직에서 전화 시스템 직접 라우팅을 배포한 경우 긴급 통화 라우팅 정책에서 원하는 정책을 선택합니다. 

6. 서브넷을 사이트에 연결하려면 **서브넷 아래에서** 서브넷 **추가를 클릭합니다.** IP 버전, IP 주소, 네트워크 범위를 지정하고 설명을 추가한 다음 적용을 **클릭합니다.** 각 서브넷은 특정 사이트와 연결되어야 합니다.
7. **저장** 을 클릭합니다.

#### <a name="modify-a-network-site"></a>네트워크 사이트 수정

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **위치** 네트워크 토폴로지로 이동한 다음 네트워크 사이트  >   **탭을** 클릭합니다.
2. 사이트 이름 왼쪽을 클릭하여 사이트를 선택한 다음 편집을 **클릭합니다.**
3. 원하는 내용을 변경한 다음 저장을 **클릭합니다.**

### <a name="manage-external-trusted-ip-addresses"></a>외부 신뢰할 수 있는 IP 주소 관리

Microsoft Teams 관리 센터의  네트워크 토폴로지 페이지의 신뢰할 수 있는 IP 탭에서 외부 신뢰할 수 있는 IP 주소를 관리합니다.  신뢰할 수 있는 외부 IP 주소를 무제한으로 추가할 수 있습니다.

#### <a name="add-a-trusted-ip-address"></a>신뢰할 수 있는 IP 주소 추가

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **위치** 네트워크 토폴로지로 이동한 다음 신뢰할 수 있는  >   **IP 탭을** 클릭합니다.
2. 새로 **고치기** 클릭
3. 신뢰할 수 있는 IP 주소 추가 **창에서** IP 버전, IP 주소, 네트워크 범위를 지정하고 설명을 추가한 다음 적용을 **클릭합니다.**

    ![신뢰할 수 있는 IP 주소 추가 창의 스크린샷](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>신뢰할 수 있는 IP 주소 편집

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **위치** 네트워크 토폴로지로 이동한 다음 신뢰할 수 있는  >   **IP 탭을** 클릭합니다.
2. 왼쪽을 클릭하여 IP 주소를 선택한 다음 편집을 **클릭합니다.**
3. 신뢰할 수 **있는 IP 주소** 편집 창에서 원하는 내용을 변경한 다음 적용을 **클릭합니다.**

## <a name="configure-network-settings-using-powershell"></a>PowerShell을 사용하여 네트워크 설정 구성

이 섹션의 단계를 완료하려면 PowerShell cmdlet에 대해 잘 알고 있는 것이 필요합니다. 자세한 내용은 [Teams PowerShell 개요를 참조하세요.](teams-powershell-overview.md)

### <a name="define-network-regions"></a>네트워크 지역 정의

 [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet을 사용하여 네트워크 지역을 정의합니다. RegionID 매개 변수는 지역의 지역을 나타내는 논리적 이름이며 종속성 또는 제한 사항이 없습니다. CentralSite 사이트 ID 매개 변수는 &lt; &gt; 선택 사항입니다.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

이 예제에서는 인도라는 네트워크 지역을 생성합니다.
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

[Set-CsTenantNetworkRegion도 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion)

### <a name="define-network-sites"></a>네트워크 사이트 정의

[New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet을 사용하여 네트워크 사이트를 정의합니다. 각 네트워크 사이트는 네트워크 지역과 연결되어야 합니다.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

이 예제에서는 인도 지역에 두 개의 새 네트워크 사이트인 Delhi와 Hyderabad를 만들겠습니다.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

다음 표에서는 이 예제에 정의된 네트워크 사이트를 보여줍니다.

||사이트 1 |사이트 2 |
|---------|---------|---------|
|사이트 ID    |    사이트 1(델리)     |  사이트 2(하이데라바드)       |
|지역 ID  |     지역 1(인도)    |   지역 1(인도)      |

[Set-CsTenantNetworkRegion도 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)

### <a name="define-network-subnets"></a>네트워크 서브넷 정의

[New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet을 사용하여 네트워크 서브넷을 정의하고 네트워크 사이트에 연결합니다. 각 네트워크 서브넷은 하나의 사이트와만 연결될 수 있습니다.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

이 예제에서는 서브넷 192.168.0.0과 Delhi 네트워크 사이트 간과 서브넷 2001:4898:e8:25:844e:926f:85ad:dd8e와 Hyderabad 네트워크 사이트 간을 연결합니다.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

다음 표에서는 이 예제에 정의된 서브넷을 보여줍니다.

||사이트 1 |사이트 2 |
|---------|---------|---------|
|서브넷 ID   |    192.168.0.0     |  2001:4898:e8:25:844e:926f:85ad:dd8e     |
|마스크  |     24    |   120      |
|사이트 ID  | 사이트(델리) | 사이트 2(하이데라바드) |

여러 서브넷의 경우 다음과 같은 스크립트를 사용하여 CSV 파일을 가져올 수 있습니다.

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

이 예제에서 CSV 파일은 다음과 같이 표시됩니다. 

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

[Set-CsTenantNetworkSubnet도 참조합니다.](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet)

### <a name="define-external-subnets-external-trusted-ip-addresses"></a>외부 서브넷 정의(외부 신뢰할 수 있는 IP 주소)

[New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet을 사용하여 외부 서브넷을 정의하고 테넌트에 할당합니다. 테넌트에 대한 외부 서브넷 수를 무제한으로 정의할 수 있습니다.

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

예를 들면 다음과 같습니다.

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

[Set-CsTenantTrustedIPAddress도 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress)

## <a name="related-topics"></a>관련 항목

- [Teams의 클라우드 음성 기능에 대한 네트워크 설정](cloud-voice-network-settings.md)
