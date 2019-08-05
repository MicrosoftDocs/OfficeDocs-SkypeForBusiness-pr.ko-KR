---
title: 비즈니스용 Skype에서 네트워크 지역, 사이트 및 서브넷 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 비즈니스용 Skype 서버에서 네트워크 지역, 네트워크 사이트 및 네트워크 서브넷 연결을 만들거나 수정 합니다. 이러한 모든 기능은 고급 엔터프라이즈 음성 기능 (미디어 바이패스, 통화 허용 제어 및 위치 기반 라우팅)에 사용 됩니다.
ms.openlocfilehash: 3ce0f4dcf011f57e25c4741c34135bc4ba62085a
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2019
ms.locfileid: "36197848"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a>비즈니스용 Skype에서 네트워크 지역, 사이트 및 서브넷 배포

비즈니스용 Skype 서버에서 네트워크 지역, 네트워크 사이트 및 네트워크 서브넷 연결을 만들거나 수정 합니다. 이러한 모든 기능은 고급 엔터프라이즈 음성 기능 (미디어 바이패스, 통화 허용 제어 및 위치 기반 라우팅)에 사용 됩니다.

고급 엔터프라이즈 음성 기능으로는 [통화 허용 제어](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [미디어 바이패스](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [위치 기반 라우팅](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)및 [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md)이 있습니다. 이러한 기능을 모두 위해서는 네트워크 지역, 네트워크 사이트 및 서브넷을 만들어야 합니다. 예를 들어 이러한 모든 기능을 사용 하려면 토폴로지의 각 서브넷을 특정 네트워크 사이트와 연결 하 고 각 네트워크 사이트는 네트워크 지역과 연결 되어 있어야 합니다. 이러한 용어에 대 한 자세한 내용은 [비즈니스용 Skype 서버의 고급 엔터프라이즈 음성 기능에 대 한 네트워크 설정을](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)참조 하세요.

통화 허용 제어 및 E9-1-1에는 네트워크 사이트에 대 한 추가 구성 요구 사항이 있습니다.

- 호출 허용 제어는 WAN 대역폭 제한에 의해 제한 된 각 사이트에 대해 대역폭 정책 프로필을 지정 해야 합니다. 통화 허용 제어를 배포 하려는 경우에는 네트워크 사이트를 구성 하기 전에 비즈니스용 [Skype 서버에서 대역폭 정책 프로필을 만들어야](create-bandwidth-policy-profiles.md) 합니다.

- E9-1-1은 각 사이트에 대해 위치 정책을 지정 해야 합니다. E9-1-1을 배포 하려는 경우 네트워크 사이트를 구성 하기 전에 [비즈니스용 Skype 서버에서 위치 정책을 만들어야](create-location-policies.md) 합니다.

## <a name="create-or-modify-a-network-region"></a>네트워크 지역 만들기 또는 수정

이러한 기능 중 하나에 대해 이미 네트워크 지역을 만든 경우에는 새 네트워크 지역을 만들 필요가 없습니다. 그 밖의 고급 엔터프라이즈 음성 기능으로는 동일한 네트워크 지역을 사용할 수 있습니다.

그러나 기능별 설정을 적용 하려면 기존 네트워크 지역 정의를 수정 해야 할 수 있습니다. 예를 들어 E9 (연결 된 중앙 사이트가 필요 하지 않음)에 대 한 네트워크 지역을 만든 다음 통화 허용 제어를 배포 하는 경우에는 네트워크 지역 정의를 수정 하 여 중앙 사이트를 지정 해야 합니다.

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 네트워크 지역 만들기

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

2. 새-CsNetworkRegion cmdlet을 실행 하 여 네트워크 지역을 만듭니다.

   ```
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    예를 들면 다음과 같습니다.

   ```
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    이 예제에서는 사이트 ID 시카고를 사용 하 여 중앙 사이트와 연결 되는 "NorthAmerica" 라는 네트워크 영역을 만들었습니다.

3. 토폴로지에 대 한 네트워크 영역 만들기를 마치려면 각 네트워크 영역에 대 한 설정을 사용 하 여 2 단계를 반복 합니다.

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 지역을 만들려면

1. 비즈니스용 Skype Server 제어판을 엽니다.

2. 왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.

3. **지역을**클릭 합니다.

4. **새로 만들기**를 클릭 합니다.

5. **새 지역** 페이지에서 **이름을** 클릭 한 다음 네트워크 영역의 이름을 입력 합니다.

6. **중앙 사이트**를 클릭 한 다음 목록에서 중앙 사이트를 클릭 합니다.

7. 필요에 따라 **설명을**클릭 한 다음 추가 정보를 입력 하 여이 네트워크 사이트를 설명 합니다.

8. **커밋**을 클릭합니다.

9. 토폴로지에 대 한 네트워크 영역 만들기를 완료 하려면 다른 지역에 대 한 설정을 사용 하 여 4 ~ 8 단계를 반복 합니다.

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 네트워크 지역 수정

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

2. 집합-CsNetworkRegion cmdlet을 실행 하 여 기존 네트워크 지역을 수정 합니다.

   ```
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    예를 들면 다음과 같습니다.

   ```
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    이 예제에서는 설명을 변경 하 여 "NorthAmerica" (이 항목의 앞부분에 있는 절차를 사용 하 여 만들어짐) 라는 기존 네트워크 영역을 수정 했습니다. "NorthAmerica" 영역에 대 한 설명이 있는 경우이 명령은이 값으로 덮어씁니다. 설명이 설정 되어 있지 않으면이 명령으로 설정 합니다.

3. 다른 네트워크 지역을 수정 하려면 다른 지역에 대 한 설정으로 2 단계를 반복 합니다.

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 지역을 수정 하려면

1. 비즈니스용 Skype Server 제어판을 엽니다.

2. 왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.

3. **지역** 탐색 단추를 클릭 합니다.

4. 표에서 수정 하려는 네트워크 지역을 클릭 합니다.

5. **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

6. **지역 편집** 페이지에서이 네트워크 지역 설정의 값을 적절 하 게 변경 합니다.

7. **커밋**을 클릭합니다.

8. 네트워크 지역 수정을 완료 하려면 다른 지역에 대 한 설정을 사용 하 여 4 ~ 7 단계를 반복 합니다.

## <a name="create-or-modify-a-network-site"></a>네트워크 사이트 만들기 또는 수정

이러한 기능 중 하나에 대해 네트워크 사이트를 이미 만든 경우 새 네트워크 사이트를 만들 필요가 없습니다. 다른 고급 엔터프라이즈 음성 기능은 동일한 네트워크 사이트를 사용 합니다. 그러나 기능별 설정을 적용 하려면 기존 네트워크 사이트 정의를 수정 해야 할 수 있습니다. 예를 들어 E9-1에 대 한 네트워크 사이트를 만든 경우에는 호출 허용 제어를 배포 하는 동안 네트워크 사이트를 수정 하 여 대역폭 정책 프로필을 적용 해야 합니다.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 네트워크 사이트를 만들려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

2. 새-CsNetworkSite cmdlet을 실행 하 여 네트워크 사이트를 만듭니다.

   ```
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    예를 들면 다음과 같습니다.

   ```
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    이 예제에서는 "NorthAmerica" 네트워크 지역에 "시카고" 라는 네트워크 사이트를 만들었습니다.

    > [!NOTE]
    > 이 명령을 성공적으로 실행 하려면 NorthAmerica 네트워크 지역이 이미 존재 해야 합니다.

3. 토폴로지에 대 한 네트워크 사이트 만들기를 마치려면 다른 사이트에 대 한 설정을 사용 하 여 2 단계를 반복 합니다.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 사이트를 만들려면

1. 비즈니스용 Skype Server 제어판을 엽니다.

2. 왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.

3. **사이트** 탐색 단추를 클릭 합니다.

4. **새로 만들기**를 클릭 합니다.

5. **새 사이트** 페이지에서 **이름을** 클릭 한 다음 네트워크 사이트의 이름을 입력 합니다.

6. **지역을**클릭 한 다음 목록에서 지역을 클릭 합니다.

7. 필요에 따라 **대역폭 정책을**클릭 한 다음 목록에서 대역폭 정책을 클릭 합니다.

    > [!NOTE]
    > 대역폭 정책은 사이트에서 통화 허용 제어를 배포 하는 경우에만 필요 합니다.

8. 필요에 따라 **위치 정책을**클릭 한 다음 목록에서 위치 정책을 클릭 합니다.

    > [!NOTE]
    > 위치 정책은 사이트에 E9-1-1을 배포 하는 경우에만 필요 합니다.

9. 필요에 따라 **설명을**클릭 한 다음 추가 정보를 입력 하 여이 네트워크 사이트를 설명 합니다.

10. **커밋**을 클릭합니다.

11. 토폴로지에 대 한 네트워크 사이트 만들기를 마치려면 다른 사이트의 설정을 사용 하 여 4 ~ 10 단계를 반복 합니다.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 네트워크 사이트를 수정 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

2. 집합-CsNetworkSite cmdlet을 실행 하 여 네트워크 사이트를 수정 합니다.

   ```
   Set-CsNetworkSite -Identity <string>
   ```

    예를 들면 다음과 같습니다.

   ```
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    이 예제에서는 "Albuquerque" 라는 사이트가 "NorthAmerica" 네트워크 지역으로 이동 합니다. 통화 허용 제어, E9-1-1 또는 미디어 바이패스를 배포 하도록 네트워크 사이트 구성을 수정 하려면 BWPolicyProfileID 또는 LocationPolicy 매개 변수를 사용 하 여 Set-CsNetworkSite cmdlet을 실행 하 여 네트워크 사이트 설정을 수정 합니다.

    > [!NOTE]
    > BypassID 매개 변수는 미디어를 우회 하는 데 존재 하지만 자동으로 생성 된 우회 Id를 재정의 하지 않는 것이 좋습니다. 미디어 바이패스를 위해 네트워크 사이트를 구성 하기 위해 추가 매개 변수를 지정할 필요는 없습니다.

3. 토폴로지의 네트워크 사이트 수정을 마치려면 다른 사이트에 대 한 설정을 사용 하 여 2 단계를 반복 합니다.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 네트워크 사이트를 수정 하려면

1. 비즈니스용 Skype Server 제어판을 엽니다.

2. 왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.

3. **사이트** 탐색 단추를 클릭 합니다.

4. 표에서 수정 하려는 네트워크 사이트를 클릭 합니다.

5. **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

6. **사이트 편집** 페이지에서이 네트워크 사이트의 설정 값을 적절 하 게 변경 합니다.

7. **커밋**을 클릭합니다.

8. 네트워크 사이트 수정을 완료 하려면 다른 사이트 설정에 대해 4 ~ 7 단계를 반복 합니다.

## <a name="associate-a-subnet-with-a-network-site"></a>네트워크 사이트에 서브넷 연결
<a name="BKMK_AssociateSubnets"> </a>

네트워크의 모든 서브넷은 새 세션이 시작 되는 동안 끝점이 위치한 네트워크 사이트를 결정 하는 데 사용 되므로 서브넷 정보는 특정 네트워크 사이트와 연결 되어야 합니다. 세션에서 각 파티의 위치를 알고 있는 경우 고급 엔터프라이즈 음성 기능에서 해당 정보를 적용 하 여 전화 설정 또는 라우팅 처리 방법을 결정할 수 있습니다.

배포에 있는 오디오/비디오에 지 서버의 모든 구성 된 공용 IP 주소를 네트워크 구성 설정에 추가 해야 합니다. 이러한 IP 주소는 32의 마스크로 서브넷으로 추가 됩니다. 연결 된 네트워크 사이트는 적절 하 게 구성 된 네트워크 사이트와 일치 해야 합니다. 예를 들어 중앙 사이트 시카고의 A/V Edge 서비스에 해당 하는 공용 IP 주소는 NetworkSiteID 시카고입니다.

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 서브넷을 네트워크 사이트와 연결 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

2. **새-CsNetworkSubnet** cmdlet을 실행 하 여 서브넷을 네트워크 사이트와 연결 합니다.

   ```
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    예를 들면 다음과 같습니다.

   ```
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    이 예제에서는 서브넷 172.11.12.13와 네트워크 사이트 "시카고" 간에 연결을 만들었습니다.

3. 토폴로지의 모든 서브넷에 대해 2 단계를 반복 합니다.

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>CSV 파일을 가져와 서브넷을 네트워크 사이트와 연결 하려면

1. 추가 하려는 모든 서브넷을 포함 하는 CSV 파일을 만듭니다. 예를 들어 다음 콘텐츠를 사용 하 여 **subnet** 이라는 파일을 만듭니다.

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.

3. 다음 cmdlet을 실행 하 여 **서브넷 .csv**를 가져온 다음 Lync Server 관리 저장소에 해당 콘텐츠를 저장 합니다.

   ```
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 서브넷을 네트워크 사이트와 연결 하려면

1. 비즈니스용 Skype Server 제어판을 엽니다.

2. 왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.

3. **서브넷** 탐색 단추를 클릭 합니다.

4. **새로 만들기**를 클릭 합니다.

5. **새 서브넷** 페이지에서 **서브넷 ID**를 클릭 한 다음 네트워크 사이트와 연결 하려는 서브넷이 정의한 IP 주소 범위에 첫 번째 주소를 입력 합니다.

6. **마스크**를 클릭 한 다음 서브넷에 적용할 비트 마스크를 입력 합니다.

7. **네트워크 사이트 id**를 클릭 한 다음이 서브넷을 추가할 사이트의 사이트 id를 선택 합니다.

    > [!NOTE]
    > 아직 네트워크 사이트를 만들지 않은 경우에는이 목록이 비어 있습니다. 절차에 대 한 자세한 내용은 [네트워크 사이트 만들기 또는 수정을](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx)참조 하세요. 또한 **Get-CsNetworkSite** cmdlet을 실행 하 여 배포에 대 한 사이트 id를 검색할 수 있습니다. 자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서를 참조 하세요.

8. 필요에 따라 **설명을**클릭 한 다음 추가 정보를 입력 하 여이 서브넷을 설명 합니다.

9. **커밋**을 클릭합니다.

네트워크 사이트에 다른 서브넷을 추가 하려면이 단계를 반복 합니다.
> [!NOTE]
> 네트워크에는 있지만 서브넷에 연결 되지 않았거나 IP 주소가 포함 된 서브넷이 네트워크 사이트와 연결 되어 있지 않은 경우 KHI (키 상태 표시기) 경고가 발생 하는 것입니다. 이 알림은 8 시간 내에 두 번 이상 발생 하지 않습니다.

관련 경고 정보 및 예제는 다음과 같습니다.

 **원본**: CS 대역폭 정책 서비스 (Core)

 **이벤트 번호**: 36034

 **수준**: 2

 **설명**: 다음 ip 주소의 서브넷: \<ip 주소\> 목록이 구성 되지 않았거나 서브넷이 네트워크 사이트에 연결 되어 있지 않습니다.

 **원인**: 해당 IP 주소에 대 한 서브넷이 네트워크 구성 설정에 없거나 서브넷이 네트워크 사이트에 연결 되어 있지 않습니다.

 **해결**방법: IP 주소 목록에 해당 하는 서브넷을 네트워크 구성 설정에 추가 하 고 모든 서브넷을 네트워크 사이트에 연결 합니다.

예를 들어 alert의 IP 주소 목록에서 10.121.248.226 및 10.121.249.20를 지정 하는 경우 이러한 IP 주소가 서브넷과 연결 되어 있지 않거나 연결 된 서브넷이 네트워크 사이트에 속해 있지 않습니다. 10.121.248.0/24 및 10.121.249.0/24가 이러한 주소에 해당 하는 서브넷 이면 다음과 같이이 문제를 해결할 수 있습니다.

1. IP 주소 10.121.248.226이 10.121.248.0/24 서브넷 및 IP 주소 10.121.249.20와 연결 되어 있는지 확인 하 고 10.121.249.0/24 서브넷과 연결 된 것입니다.

2. 10.121.248.0/24 및 10.121.249.0/24 서브넷이 각각 네트워크 사이트와 연결 되어 있는지 확인 합니다.

## <a name="see-also"></a>참고 항목
<a name="BKMK_AssociateSubnets"> </a>


[새-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[CsNetworkRegion 제거](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[새-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[CsNetworkSubnet 제거](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)

