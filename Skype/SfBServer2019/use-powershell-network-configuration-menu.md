---
title: 네트워크 구성 메뉴의 작업에 PowerShell 사용
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: '요약: 비즈니스용 Skype 서버 메뉴에 대한 Cmdlet 매핑에 대한 제어판을 제공합니다.'
ms.openlocfilehash: aa42ac465ffd72a4aff9c03293124c857e5b712c
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626302"
---
# <a name="network-configuration"></a>네트워크 구성

이 문서에서는 cmdlet을 사용하여  레거시 제어판의 네트워크 구성 메뉴 항목과 비슷한 결과를 얻을 수 있는 방법에 대해 설명합니다.

이 문서에서는 다음과 같은 하위 메뉴에 대해 설명합니다.

- [네트워크 구성](#network-configuration)
  - [위치 정책](#location-policy)
  - [대역폭 정책](#bandwidth-policy)
  - [지역](#region)
  - [Site](#site)
  - [서브넷](#subnet)
  - [지역 링크](#region-link)
  - [지역 경로](#region-route)

## <a name="location-policy"></a>위치 정책

**위치 정책** 하위 메뉴는 E9-1-1 기능과 관련된 설정을 적용하는 데 사용됩니다. 사용자가 E9-1-1을 사용하도록 설정되어 있는지 여부를 확인하고, 설정된 경우 응급 통화에 대한 행동을 결정합니다.

사용자가 위치 정책에 대해 수행할 수 있는 다양한 작업을 고려해 비즈니스용 Skype 이러한 작업을 매핑합니다.

---

> **시나리오 1:** 모든 위치 정책 나열

   ![목록 위치 정책](./media/location-policy-1.png)

***Cmdlet***

[Get-CsLocationPolicy](/powershell/module/skype/get-cslocationpolicy)

***예***

```powershell
 Get-CsLocationPolicy
```

---

> **시나리오 2:** 새 위치 정책 만들기

   ![위치 정책 만들기](./media/location-policy-2.png)

***Cmdlet***

[New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy)  

***예***

```powershell
 New-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True
```

---

> **시나리오 3:** 선택한 위치 정책에 대한 세부 정보 확인

   ![Get Location Policy](./media/location-policy-3.png)

***Cmdlet***

[Get-CsLocationPolicy](/powershell/module/skype/get-cslocationpolicy)

***예***

```powershell
 Get-CsLocationPolicy -Identity Reno
```

---

> **시나리오 4:** 선택한 위치 정책 삭제

   ![위치 정책 삭제](./media/location-policy-4.png)

***Cmdlet***

[Remove-CsLocationPolicy](/powershell/module/skype/remove-cslocationpolicy)

***예***

```powershell
 Remove-CsLocationPolicy -Identity Reno
```

---

> **시나리오 5:** 위치 정책 업데이트

   ![위치 정책 업데이트](./media/location-policy-5.png)

***Cmdlet***

[Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy)

***예***

```powershell
 Set-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True
```

---

## <a name="bandwidth-policy"></a>대역폭 정책

대역폭 정책은 CAC(통화 허용 제어)의 일부로 특정 형식에 대한 대역폭 제한을 정의하는 데 사용됩니다. 이 비즈니스용 Skype 서버 오디오 및 비디오에만 대역폭 제한을 할당할 수 있습니다. 이 cmdlet은 이러한 정책에 대한 컨테이너 프로필을 만듭니다. 이 cmdlet을 호출할 때 오디오 및 비디오 대역폭 제한을 지정하여 컨테이너 내에 개별 정책을 정의합니다.

사용자가 BANDWIDTH POLICY에 대해 수행할 수 있는 다양한 작업을 고려해 비즈니스용 Skype 매핑할 수 있습니다.

---
> **시나리오 1:** 모든 대역폭 정책 나열

   ![목록 대역폭 정책](./media/bandwidth-policy-1.png)

***Cmdlet***

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile)

***예***

```powershell
 Get-CsNetworkBandwidthPolicyProfile
```

---

> **시나리오 2:** 새 대역폭 정책 만들기

   ![새 대역폭 정책](./media/bandwidth-policy-2.png)

***Cmdlet***

[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/new-csnetworkbandwidthpolicyprofile)  

***예***

```powershell
 New-CsNetworkBandwidthPolicyProfile -Identity LowBWLimits -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400 -VideoBWSessionLimit 500
```

---

> **시나리오 3:** 선택한 대역폭 정책에 대한 세부 정보 확인

   ![대역폭 정책 사용](./media/bandwidth-policy-3.png)

***Cmdlet***

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile)

***예***

```powershell
 Get-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
```

---

> **시나리오 4:** 선택한 대역폭 정책 삭제

   ![대역폭 정책 삭제](./media/bandwidth-policy-4.png)

***Cmdlet***

[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile)

***예***

```powershell
 Remove-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
```

---

> **시나리오 5:** 대역폭 정책 업데이트

   ![대역폭 정책 업데이트](./media/bandwidth-policy-5.png)

***Cmdlet***

[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/set-csnetworkbandwidthpolicyprofile)

***예***

```powershell
 Set-CsNetworkBandwidthPolicyProfile -Identity LowBWLimit -VideoBWLimit 2500 -VideoBWSessionLimit 300
```

---

## <a name="region"></a>지역

네트워크 지역은 여러 지역의 많은 네트워크 부분을 교차합니다. 모든 네트워크 지역은 중앙 사이트와 연결되어야 합니다. 관리자는 **REGION** 메뉴를 사용하여 연결된 중앙 사이트 및 오디오 및 비디오 연결에 대체 경로를 허용할지 여부를 결정하는 설정을 포함하여 하나 이상의 네트워크 지역에 대한 정보를 관리하고 지역 내의 사이트를 미디어 우회 구성과 연결합니다.

---

> **시나리오 1:** 모든 지역 나열

   ![목록 영역](./media/network-region-1.png)

***Cmdlet***

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion)

***예***

```powershell
 Get-CsNetworkRegion
```

---

> **시나리오 2:** 새 지역 만들기

   ![지역 만들기](./media/network-region-2.png)

***Cmdlet***

[New-CsNetworkRegion](/powershell/module/skype/new-csnetworkregion)  

***예***

```powershell
 New-CsNetworkRegion -Identity NorthAmerica -Description "All North American Locations" -CentralSite Redmond-NA-MLS
```

---

> **시나리오 3:** 선택한 지역에 대한 세부 정보 확인

   ![Get Region](./media/network-region-3.png)

***Cmdlet***

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion)

***예***

```powershell
 Get-CsNetworkRegion -Identity NorthAmerica
```

---

> **시나리오 4:** 선택한 지역 삭제

   ![지역 삭제](./media/network-region-4.png)

***Cmdlet***

[Remove-CsNetworkRegion](/powershell/module/skype/remove-csnetworkregion)

***예***

```powershell
 Remove-CsNetworkRegion -Identity NorthAmerica
```

---

> **시나리오 5:** 지역 업데이트

   ![업데이트 지역](./media/network-region-5.png)

- **주석 1 - 결과**

    이미지에 대한 이 주석은 결과, 즉 검색 및 표시되는 데이터를 나타냅니다.

    ***Cmdlet***

    [Get-CsNetworkSite from Region](/powershell/module/skype/get-csnetworksite)

    ***예***

    ```powershell
     Get-CsNetworkSite | Where-Object {$_.NetworkRegionID -eq "AKR"}
    ```

- **주석 2 - 옵션(사용자용)**

    이미지에 대한 이 주석은 사용자가 구현할 옵션, 즉 네트워크 지역을 저장하는 옵션을 나타냅니다.

    [Set-CsNetworkRegion](/powershell/module/skype/set-csnetworkregion)

   ***예***

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -Description "North American Region"
   ```

---

## <a name="site"></a>사이트

네트워크 사이트는 각 CAC 또는 E9-1-1 배포 영역 내에 구성된 사무실 또는 위치입니다. **사이트** 하위 메뉴를 사용하면 관리자가 설정을 추가, 제거 또는 관리할 수 있습니다.

사용자가 **SITE** 및 에서 수행할 수 있는 다양한 작업을 고려해 비즈니스용 Skype cmdlet을 사용합니다.

---

> **시나리오 1:** 모든 사이트 나열

   ![목록 사이트](./media/network-site-1.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksite)

***예***

```powershell
 Get-CsNetworkSite
```

---

> **시나리오 2:** 새 사이트 만들기

   ![사이트 만들기](./media/network-site-2.png)

***Cmdlet***

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksite)  

***예***

```powershell
 New-CsNetworkSite -Identity Vancouver -NetworkRegionID NorthAmerica
```

---

> **시나리오 3:** 선택한 사이트의 세부 정보 확인

   ![사이트 얻기](./media/network-site-3.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksite)

***예***

```powershell
 Get-CsNetworkSite -Identity Redmond
```

---

> **시나리오 4:** 선택한 사이트 삭제

   ![사이트 삭제](./media/network-site-4.png)

***Cmdlet***

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksite)

***예***

```powershell
 Remove-CsNetworkSite -Identity Vancouver
```

---

> **시나리오 5:** 사이트 업데이트

   ![사이트 업데이트](./media/network-site-5.png)

- **주석 1 - 결과**

    이미지에 대한 이 주석은 결과, 즉 검색 및 표시되는 데이터를 나타냅니다.

    ***Cmdlet***

    [사이트에서 Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

    ***예***

    ```powershell
     Get-CsNetworkSubnet | Where-Object {$_.NetworkSiteID -eq "Vancouver"}
    ```

- **주석 2 - 옵션(사용자용)**

    이미지에 대한 이 주석은 사용자가 구현할 수 있는 옵션, 즉 네트워크 사이트를 저장하는 옵션을 나타냅니다.

   ***Cmdlet***

   [Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksite)

   ***예***

   ```powershell
    Set-CsNetworkSite -Identity Vancouver - BWPolicyProfileID LowBWLimits
   ```

---

## <a name="subnet"></a>서브넷

관리자는 **SUBNET** 하위 메뉴를 사용하여 네트워크 서브넷을 만들고 업데이트하고 관리할 수 있습니다.

**사용자가 SUBNET** 및 서브넷에서 수행할 수 있는 다양한 작업을 비즈니스용 Skype cmdlet에 매핑합니다.

---

> **시나리오 1:** 모든 서브넷 나열

   ![목록 서브넷](./media/network-subnet-1.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

***예***

```powershell
 Get-CsNetworkSubnet
```

---

> **시나리오 2:** 새 서브넷 만들기

   ![서브넷 만들기](./media/network-subnet-2.png)

***Cmdlet***

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet)  

***예***

```powershell
 New-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 24 -NetworkSiteID Vancouver
```

---

> **시나리오 3:** 선택한 서브넷에 대한 세부 정보 확인

   ![서브넷 얻기](./media/network-subnet-3.png)

***Cmdlet***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

***예***

```powershell
 Get-CsNetworkSubnet -Identity 172.11.15.0
```

---

> **시나리오 4:** 선택한 서브넷 삭제

   ![서브넷 삭제](./media/network-subnet-4.png)

***Cmdlet***

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksubnet)

***예***

```powershell
 Remove-CsNetworkSubnet -Identity 172.11.15.0
```

---

> **시나리오 5:** 서브넷 업데이트

   ![서브넷 업데이트](./media/network-subnet-5.png)

***Cmdlet***

[Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksubnet)

***예***

```powershell
 Set-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 25 -NetworkSiteID Chicago
```

---

## <a name="region-link"></a>지역 링크

네트워크 내의 지역은 실제 WAN 연결을 통해 연결됩니다. 관리자는 REGION **LINK** 하위 메뉴를 사용하여 네트워크 서브넷을 만들고 업데이트하고 관리할 수 있습니다.

**사용자가 REGION LINK에** 대해 수행할 수 있는 다양한 작업을 고려해 비즈니스용 Skype 매핑할 수 있습니다.

---

> **시나리오 1:** 모든 지역 링크 나열

   ![목록 지역 링크](./media/network-regionlink-1.png)

***Cmdlet***

[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

***예***

```powershell
 Get-CsNetworkRegionLink
```

---

> **시나리오 2:** 새 지역 링크 만들기

   ![지역 링크 만들기](./media/network-regionlink-2.png)

***Cmdlet***

[New-CsNetworkRegionLink](/powershell/module/skype/new-csnetworkregionLink)  

***예***

```powershell
 New-CsNetworkRegionLink -Identity NA_EMEA -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID LowBWLimits
```

---

> **시나리오 3:** 선택한 지역 링크에 대한 세부 정보 다운로드

   ![지역 링크 다운로드](./media/network-regionlink-3.png)

***Cmdlet***

[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

***예***

```powershell
 Get-CsNetworkRegionLink -Identity NA_EMEA
```

---

> **시나리오 4:** 선택한 지역 링크 삭제

   ![지역 링크 삭제](./media/network-regionlink-4.png)

***Cmdlet***

[Remove-CsNetworkRegionLink](/powershell/module/skype/remove-csnetworkregionLink)

***예***

```powershell
 Remove-CsNetworkRegionLink -Identity NA_EMEA
```

---

> **시나리오 5:** 지역 링크 업데이트

   ![지역 링크 업데이트](./media/network-regionlink-5.png)

***Cmdlet***

[Set-CsNetworkRegionLink](/powershell/module/skype/set-csnetworkregionLink)

***예***

```powershell
 Set-CsNetworkRegionLink -Identity NA_EMEA -BWPolicyProfileID HighBWLimits
```

---

## <a name="region-route"></a>지역 경로

CAC 구성 내의 모든 영역에는 다른 모든 영역에 액세스할 수 있는 방법이 있어야 합니다. 영역 링크는 영역 간 연결에 대한 대역폭 제한을 설정하고 실제 링크를 나타내며, 경로는 한 영역에서 다른 영역으로 연결이 통과하게 되는 링크된 경로를 결정합니다. 관리자는 REGION **ROUTE** 하위 메뉴를 사용하여 이러한 항목을 만들고 업데이트하고 관리할 수 있습니다.

사용자가 REGION **ROUTE에** 대해 수행할 수 있는 다양한 작업을 고려해 비즈니스용 Skype 이러한 작업을 매핑합니다.

---

> **시나리오 1:** 모든 지역 경로 나열

   ![목록 지역 경로](./media/network-regionroute-1.png)

***Cmdlet***

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute)

***예***

```powershell
 Get-CsNetworkInterRegionRoute
```

---

> **시나리오 2:** 새 지역 경로 만들기

   ![지역 경로 만들기](./media/network-regionroute-2.png)

***Cmdlet***

[New-CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute)  

***예***

```powershell
 New-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA_EMEA,EMEA_APAC"
```

---

> **시나리오 3:** 선택한 지역 경로에 대한 세부 정보 확인

   ![지역 경로 얻기](./media/network-regionroute-3.png)

***Cmdlet***

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute)

***예***

```powershell
 Get-CsNetworkInterRegionRoute -Filter *APAC*
```

---

> **시나리오 4:** 선택한 지역 경로 삭제

   ![지역 경로 삭제](./media/network-regionroute-4.png)

***Cmdlet***

[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute)

***예***

```powershell
 Remove-CsNetworkInterRegionRoute -Identity NA_APAC_Route
```

---

> **시나리오 5:** 지역 경로 업데이트

   ![지역 경로 업데이트](./media/network-regionroute-5.png)

- **주석 1 - 옵션(사용자용)**

    이미지에 대한 이 주석은 결과, 즉 검색 및 표시되는 데이터를 나타냅니다.

   ***Cmdlet***

   [Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

   ***예***

   ```powershell
   Get-CsNetworkRegionLink
   ```

- **주석 2 - 옵션(사용자용)**

    이미지에 대한 이 주석은 사용자가 구현할 수 있는 옵션, 즉 네트워크 지역 경로를 저장하는 옵션을 나타냅니다.

    ***Cmdlet***

   [Set-CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute)

   ***예***

   ```powershell
   Set-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionLinkIDs "NA_SA,SA_APAC"
   ```

---
---
