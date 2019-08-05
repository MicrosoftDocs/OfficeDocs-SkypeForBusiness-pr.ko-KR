---
title: 위치 기반 라우팅에 대 한 네트워크 설정 구성
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: 직접 라우팅에 대 한 위치 기반 라우팅에 대 한 네트워크 지역, 사이트 및 서브넷을 만들고 설정 하는 방법에 대해 알아봅니다.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ed7f58489a43a1bd9e781cd7e8fb69bd6a6dc58
ms.sourcegitcommit: 60c868155c7709df35fad23a41330483f8b59fee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2019
ms.locfileid: "36185018"
---
# <a name="configure-network-settings-for-location-based-routing"></a>위치 기반 라우팅에 대 한 네트워크 설정 구성

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

아직 수행 하지 않은 경우 위치 기반 라우팅에 대 한 네트워크 설정을 구성 하기 전에 수행 해야 하는 다른 단계를 검토 하도록 [직접 라우팅 계획 위치 기반 라우팅을](location-based-routing-plan.md) 읽어 보세요.

이 문서에서는 위치 기반 라우팅에 대 한 네트워크 설정을 구성 하는 방법을 설명 합니다. 조직에 직접 전화 시스템 라우팅을 배포한 후 다음 단계는 네트워크 지역, 네트워크 사이트 및 네트워크 서브넷을 만들고 설정 하는 것입니다. 이 문서의 단계를 완료 하려면 PowerShell cmdlet에 대해 잘 알고 있어야 합니다. 자세히 알아보려면 [팀 PowerShell 개요](teams-powershell-overview.md)를 참조 하세요.

## <a name="define-network-regions"></a>네트워크 지역 정의
 네트워크 영역은 여러 지리적 영역에 걸친 네트워크의 다양 한 부분을 상호 구성 합니다. [새-Csten앤틸리스 지역](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet을 사용 하 여 네트워크 지역을 정의 합니다. 영역 ID 매개 변수는 영역의 지리를 나타내는 논리 이름이 며, 종속성 또는 제한이 없으며 CentralSite &lt;site ID&gt; 매개 변수는 선택 사항입니다. 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

이 예제에서는 인도 라는 네트워크 영역을 만듭니다. 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a>네트워크 사이트 정의

[새-Csten앤틸리스 site](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet을 사용 하 여 네트워크 사이트를 정의 합니다. 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
이 예제에서는 인도 지역에 2 개의 새 네트워크 사이트, 뉴델리 및 Hyderabad을 만듭니다. 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
다음 표에는이 예제에 정의 된 네트워크 사이트가 나와 있습니다. 

||사이트 1 |사이트 2 |
|---------|---------|---------|
|사이트 ID    |    사이트 1(뉴델리)     |  Site 2 (Hyderabad)       |
|지역 ID  |     지역 1 (인도)    |   지역 1 (인도)      |

## <a name="define-network-subnets"></a>네트워크 서브넷 정의

[새-Csten앤틸리스 subnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet을 사용 하 여 네트워크 서브넷을 정의 하 고 네트워크 사이트에 연결 합니다. 각 내부 서브넷은 한 사이트에만 연결 될 수 있습니다. 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
이 예제에서는 서브넷 192.168.0.0과 뉴델리 네트워크 사이트 간 연결과 서브넷 2001 간 연결 (4898: e8:25:844e: 926f: 85ad: dd8e 및 Hyderabad network site를 만듭니다.
```
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
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
이 예제에서 CSV 파일은 다음과 같습니다.
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a>외부 서브넷 정의
[New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet을 사용 하 여 외부 서브넷을 정의 하 고 테 넌 트에 할당 합니다. 테 넌 트에 대해 무제한 개수의 서브넷을 정의할 수 있습니다. 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
예를 들면 다음과 같습니다.
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a>다음 단계
[직접 라우팅에 대해 위치 기반 라우팅 사용](location-based-routing-enable.md)으로 이동 합니다.

### <a name="related-topics"></a>관련 항목
- [직접 라우팅에 대 한 위치 기반 라우팅 계획](location-based-routing-plan.md)
- [위치 기반 라우팅 용어](location-based-routing-terminology.md)
