---
title: Microsoft 팀의 클라우드 음성 기능에 대 한 네트워크 토폴로지 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1keywords: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 클라우드 음성 기능에 대 한 네트워크 설정을 구성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 87cdf39e03999a9e249b7ec40af7ea2ad8612e69
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991643"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Microsoft 팀의 클라우드 음성 기능에 대 한 네트워크 토폴로지 관리

조직에서 직접 라우팅 또는 [동적 비상 전화](configure-dynamic-emergency-calling.md) [에 대 한 위치 기반 라우팅을](location-based-routing-plan.md) 배포 하는 경우에는 Microsoft 팀의 이러한 클라우드 음성 기능에 사용할 네트워크 설정을 구성 해야 합니다. 네트워크 설정은 팀 클라이언트의 위치를 확인 하 고 네트워크 지역, 네트워크 사이트, 서브넷, 신뢰할 수 있는 IP 주소를 포함 하는 데 사용 됩니다. 배포 하는 클라우드 음성 기능 및 기능에 따라 이러한 설정을 일부 또는 모두 구성 합니다. 이러한 용어에 대 한 자세한 내용은 [클라우드 음성 기능에 대 한 네트워크 설정을](cloud-voice-network-settings.md)참조 하세요.

Microsoft 팀 관리 센터의 **네트워크 토폴로지** 페이지에서 또는 Windows PowerShell을 사용 하 여 네트워크 설정을 구성 합니다.

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Microsoft 팀 관리 센터에서 네트워크 설정 구성

[!INCLUDE [preview-feature](includes/preview-feature.md)]

네트워크 **토폴로지** 페이지의 **네트워크 사이트** 탭에서 네트워크 지역, 네트워크 사이트 및 서브넷을 정의 합니다. 여기서는 네트워크 사이트를 만들거나 수정 하 고, 사이트와 네트워크 영역을 연결 하 고, 서브넷을 사이트에 연결 하 고, 위치 기반 라우팅을 설정 하 고, 사이트에 응급 정책을 할당할 수 있습니다. 모든 사이트에 전체적으로 사용할 수 있는 네트워크 지역을 추가할 수도 있습니다.

#### <a name="add-and-configure-a-network-site"></a>네트워크 사이트 추가 및 구성

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **위치** > **네트워크 토폴로지로**이동한 다음 **네트워크 사이트** 탭을 클릭 합니다.
2. **새로 만들기**를 클릭 한 다음 사이트의 이름과 설명을 입력 합니다.

    ![네트워크 사이트 추가 페이지의 스크린샷](media/manage-network-topology-add-site.png)

3. 사이트를 네트워크 지역에 연결 하려면 **네트워크 지역 연결**을 클릭 하 고, 기존 지역을 선택 하거나, **추가** 를 클릭 하 여 지역을 추가 하 고 **링크**를 클릭 합니다.  
4. 사이트의 위치 기반 라우팅을 사용 하려면 **위치 기반 라우팅을**설정 합니다.
5. 사이트에 응급 서비스 정책을 할당 하려면 다음 중 하나 또는 모두를 수행 합니다.

    - 조직에서 통화 계획 또는 배포 된 전화 시스템 직접 라우팅을 사용 하는 경우 **비상 전화 정책**에서 원하는 정책을 선택 합니다.
    - 조직에서 전화 시스템 직접 라우팅을 배포한 경우 **비상 전화 라우팅 정책**에서 원하는 정책을 선택 합니다.

6. 서브넷을 사이트에 연결 하려면 **서브넷**에서 **서브넷 추가**를 클릭 합니다. IP 버전, IP 주소, 네트워크 범위, 설명 추가를 지정 하 고 **적용**을 클릭 합니다. 각 서브넷은 특정 사이트와 연결 되어야 합니다.
7. **저장**을 클릭 합니다.

#### <a name="modify-a-network-site"></a>네트워크 사이트 수정

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **위치** > **네트워크 토폴로지로**이동한 다음 **네트워크 사이트** 탭을 클릭 합니다.
2. 사이트 이름 왼쪽에 있는을 클릭 하 여 사이트를 선택 하 고 **편집**을 클릭 합니다.
3. 원하는 변경 작업을 수행한 다음 저장을 클릭 **합니다.**

### <a name="manage-external-trusted-ip-addresses"></a>신뢰할 수 있는 외부 IP 주소 관리

Microsoft 팀 관리 센터의 **네트워크 토폴로지** 페이지에서 **신뢰할** 수 있는 ip 주소를 관리 합니다. 외부 신뢰 IP 주소를 무제한으로 추가할 수 있습니다.

#### <a name="add-a-trusted-ip-address"></a>신뢰할 수 있는 IP 주소 추가

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **위치** > **네트워크 토폴로지로**이동한 다음 **신뢰할 수 있는 ip** 탭을 클릭 합니다.
2. **새로 만들기**를 클릭 합니다.
3. **신뢰할 수 있는 ip 주소 추가** 창에서 ip 버전, ip 주소, 네트워크 범위, 설명 추가를 지정 하 고 **적용**을 클릭 합니다.

    ![신뢰할 수 있는 IP 주소 추가 창 스크린샷](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>신뢰할 수 있는 IP 주소 편집

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **위치** > **네트워크 토폴로지로**이동한 다음 **신뢰할 수 있는 ip** 탭을 클릭 합니다.
2. 왼쪽을 클릭 하 여 IP 주소를 선택 하 고 **편집**을 클릭 합니다.
3. **신뢰할 수 있는 IP 주소 편집** 창에서 원하는 변경 작업을 수행 하 고 **적용**을 클릭 합니다.

## <a name="configure-network-settings-using-powershell"></a>PowerShell을 사용 하 여 네트워크 설정 구성

이 섹션의 단계를 완료 하려면 PowerShell cmdlet에 대해 잘 알고 있어야 합니다. 자세히 알아보려면 [팀 PowerShell 개요](teams-powershell-overview.md)를 참조 하세요.

### <a name="define-network-regions"></a>네트워크 지역 정의

 [새-Csten앤틸리스 지역](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet을 사용 하 여 네트워크 지역을 정의 합니다. 영역 ID 매개 변수는 영역의 지리를 나타내는 논리 이름이 며, 종속성 또는 제한이 없으며 CentralSite &lt;site ID&gt; 매개 변수는 선택 사항입니다.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

이 예제에서는 인도 라는 네트워크 영역을 만듭니다.
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

[집합-Csten\ 네트워크 지역](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion)도 참조 하세요.

### <a name="define-network-sites"></a>네트워크 사이트 정의

[새-Csten앤틸리스 site](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet을 사용 하 여 네트워크 사이트를 정의 합니다. 각 네트워크 사이트는 네트워크 지역과 연결 되어 있어야 합니다.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
이 예제에서는 인도 지역에 2 개의 새 네트워크 사이트, 뉴델리 및 Hyderabad을 만듭니다.
```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```
다음 표에는이 예제에 정의 된 네트워크 사이트가 나와 있습니다.

||사이트 1 |사이트 2 |
|---------|---------|---------|
|사이트 ID    |    사이트 1(뉴델리)     |  Site 2 (Hyderabad)       |
|지역 ID  |     지역 1 (인도)    |   지역 1 (인도)      |

[집합-Csten\ 네트워크 지역](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)도 참조 하세요.

### <a name="define-network-subnets"></a>네트워크 서브넷 정의

[새-Csten앤틸리스 subnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet을 사용 하 여 네트워크 서브넷을 정의 하 고 네트워크 사이트에 연결 합니다. 각 네트워크 서브넷은 한 사이트에만 연결 될 수 있습니다.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

이 예제에서는 서브넷 192.168.0.0과 뉴델리 네트워크 사이트 간 연결과 서브넷 2001 간 연결 (4898: e8:25:844e: 926f: 85ad: dd8e 및 Hyderabad network site를 만듭니다.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"

```
다음 표에는이 예제에 정의 된 서브넷이 나와 있습니다.

||사이트 1 |사이트 2 |
|---------|---------|---------|
|서브넷 ID   |    192.168.0.0     |  2001:4898: e8:25:844e: 926f: 85ad: dd8e     |
|마스킹하  |     fps    |   120      |
|사이트 ID  | 사이트 (뉴델리) | Site 2 (Hyderabad) |

여러 서브넷의 경우 다음과 같은 스크립트를 사용 하 여 CSV 파일을 가져올 수 있습니다.
```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
이 예제에서 CSV 파일은 다음과 같습니다.
```output
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

[집합-Csten앤틸리스 서브넷](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet)을 참조 하세요.

### <a name="define-external-subnets-external-trusted-ip-addresses"></a>외부 서브넷 정의 (외부 신뢰할 수 있는 IP 주소)

[New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet을 사용 하 여 외부 서브넷을 정의 하 고 테 넌 트에 할당 합니다. 테 넌 트에 대 한 무제한 개수의 외부 서브넷을 정의할 수 있습니다.
```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
예를 들면 다음과 같습니다.
```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

[Set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress)를 참조 하세요.

## <a name="related-topics"></a>관련 항목

- [팀의 클라우드 음성 기능에 대 한 네트워크 설정](cloud-voice-network-settings.md)
