---
title: 네트워크 지역, 사이트 및 서브넷을 비즈니스용 Skype
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 네트워크 지역, 네트워크 사이트를 만들거나 수정하고 네트워크 서브넷을 비즈니스용 Skype 서버. 이러한 모든 기능은 미디어 우회, 통화 Enterprise Voice 및 위치 기반 라우팅과 같은 고급 서비스 기능에 사용됩니다.
ms.openlocfilehash: 4d726466153f30b7c5fdd3ac478b1b2444838ae6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856305"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a>네트워크 지역, 사이트 및 서브넷을 비즈니스용 Skype

네트워크 지역, 네트워크 사이트를 만들거나 수정하고 네트워크 서브넷을 비즈니스용 Skype 서버. 이러한 모든 기능은 미디어 우회, 통화 Enterprise Voice 및 위치 기반 라우팅과 같은 고급 서비스 기능에 사용됩니다.

고급 Enterprise Voice [기능은](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)통화 입장 [제어,](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)미디어 [우회,](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)위치 기반 라우팅 및 [E9-1-1입니다.](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md) 이러한 기능을 사용하려면 네트워크 지역, 네트워크 사이트 및 서브넷을 만들어야 합니다. 예를 들어 이러한 모든 기능을 사용하려면 토폴로지의 각 서브넷을 특정 네트워크 사이트와 연결해야 합니다. 각 네트워크 사이트는 네트워크 지역과 연결되어야 합니다. 이러한 용어에 대한 자세한 내용은 에서 고급 Enterprise Voice 기능에 대한 네트워크 [설정을 비즈니스용 Skype 서버.](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)

통화 허용 제어 및 E9-1-1의 경우 네트워크 사이트에 대한 추가 구성 요구 사항이 있습니다.

- 통화 허용 제어의 경우 WAN 대역폭 제한을 통해 제약되는 각 사이트에 대해 대역폭 정책 프로필을 지정해야 합니다. 통화 액세스 제어를 배포하려면 네트워크 사이트를 [구성하기](create-bandwidth-policy-profiles.md) 전에 비즈니스용 Skype 서버 정책 프로필을 만들어야 합니다.

- E9-1-1의 경우 각 사이트에 대해 위치 정책을 지정해야 합니다. E9-1-1을 배포하려면 네트워크 사이트를 구성하기 전에 비즈니스용 Skype 서버 [정책](create-location-policies.md) 만들기를 해야 합니다.

## <a name="create-or-modify-a-network-region"></a>네트워크 지역 만들기 또는 수정

이러한 기능 중 하나에 대한 네트워크 지역을 이미 만든 경우 새 네트워크 지역을 만들 필요가 없습니다. 다른 고급 Enterprise Voice 기능은 동일한 네트워크 지역을 사용하게 됩니다.

그러나 기존 네트워크 지역 정의를 수정하여 기능별 설정을 적용할 수는 있습니다. 예를 들어 E9-1-1용으로 네트워크 지역을 만든 후(연결된 중앙 사이트가 필요하지 않음) 통화 허용 제어를 배포하는 경우에는 네트워크 지역 정의를 수정하여 중앙 사이트를 지정해야 합니다.

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 네트워크 지역을 비즈니스용 Skype 서버

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

2. New-CsNetworkRegion cmdlet을 실행하여 네트워크 지역을 만듭니다.

   ```powershell
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    예:

   ```powershell
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    이 예제에서는 사이트 ID가 CHICAGO인 중앙 사이트와 연결된 "NorthAmerica"라는 네트워크 지역을 만들었다.

3. 토폴로지에 대한 네트워크 지역 만들기를 종료하려면 각 네트워크 지역에 대한 설정을 사용하여 2단계를 반복합니다.

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 네트워크 지역을 비즈니스용 Skype 서버

1. 제어판을 비즈니스용 Skype 서버 를 니다.

2. 왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.

3. **지역** 을 클릭합니다.

4. **새로 만들기** 를 클릭합니다.

5. **새 지역** 페이지에서 **이름** 을 클릭한 다음 네트워크 지역에 대한 이름을 입력합니다.

6. **중앙 사이트** 를 클릭한 다음 목록에서 중앙 사이트를 클릭합니다.

7. 필요한 경우 **설명** 을 클릭한 다음 이 네트워크 사이트를 설명하는 추가 정보를 입력합니다.

8. **커밋** 을 클릭합니다.

9. 토폴로지에 대한 네트워크 지역 만들기를 종료하려면 다른 지역에 대한 설정을 사용하여 4-8단계를 반복합니다.

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 네트워크 비즈니스용 Skype 서버 수정하려면

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

2. Set-CsNetworkRegion cmdlet을 실행하여 기존 네트워크 지역을 수정합니다.

   ```powershell
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    예:

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    이 예제에서는 설명을 변경하여 "NorthAmerica"라는 기존 네트워크 지역(이 항목의 앞부분에 있는 절차를 사용하여 만든)을 수정했습니다. "NorthAmerica" 지역에 대한 설명이 있는 경우 이 명령은 이 값으로 덮어 덮어 행위를 합니다. 설명이 설정되지 않은 경우 이 명령은 설명을 설정합니다.

3. 다른 네트워크 지역을 수정하려면 다른 지역에 대한 설정을 사용하여 2단계를 반복합니다.

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 네트워크 비즈니스용 Skype 서버 수정하려면

1. 제어판을 비즈니스용 Skype 서버 를 니다.

2. 왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.

3. **지역** 탐색 단추를 클릭합니다.

4. 테이블에서 수정할 네트워크 지역을 클릭합니다.

5. **편집** 을 클릭한 다음 **자세한 정보 표시...** 를 클릭합니다.

6. 지역 **편집 페이지에서** 이 네트워크 지역의 설정 값을 적절하게 변경합니다.

7. **커밋** 을 클릭합니다.

8. 네트워크 지역 수정을 완료하려면 다른 지역에 대한 설정을 사용하여 4-7단계를 반복합니다.

## <a name="create-or-modify-a-network-site"></a>네트워크 사이트 만들기 또는 수정

이러한 기능 중 하나에 대한 네트워크 사이트를 이미 만든 경우 새 네트워크 사이트를 만들 필요가 없습니다. 다른 고급 Enterprise Voice 기능은 동일한 네트워크 사이트를 사용하게 됩니다. 그러나 기능별 설정을 적용하려면 기존 네트워크 사이트 정의를 수정해야 할 수 있습니다. 예를 들어 E9-1-1에 대한 네트워크 사이트를 만든 경우 대역폭 정책 프로필을 적용하려면 통화 제한을 배포하는 동안 네트워크 사이트를 수정해야 합니다.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 네트워크 비즈니스용 Skype 서버

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

2. New-CsNetworkSite cmdlet을 실행하여 네트워크 사이트를 만듭니다.

   ```powershell
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    예:

   ```powershell
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    이 예제에서는 "NorthAmerica" 네트워크 지역에 있는 "시카고"라는 네트워크 사이트를 만들었다.

    > [!NOTE]
    > 이 명령을 실행하려면 북미 네트워크 지역이 이미 존재해야 합니다.

3. 토폴로지에 대한 네트워크 사이트 만들기를 종료하려면 다른 사이트에 대한 설정을 사용하여 2단계를 반복합니다.

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 네트워크 비즈니스용 Skype 서버 만들 수 있습니다.

1. 제어판을 비즈니스용 Skype 서버 를 니다.

2. 왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.

3. **사이트** 탐색 단추를 클릭합니다.

4. **새로 만들기** 를 클릭합니다.

5. **네트워크 사이트** 페이지에서 **이름** 을 클릭한 다음 네트워크 사이트 이름을 입력합니다.

6. **지역** 을 클릭한 다음 목록에서 지역을 클릭합니다.

7. 필요한 경우 **대역폭 정책** 을 클릭한 다음 목록에서 대역폭 정책을 클릭합니다.

    > [!NOTE]
    > 대역폭 정책은 사이트에 통화 허용 제어를 배포할 경우에만 필요합니다.

8. 필요한 경우 **위치 정책** 을 클릭한 다음 목록에서 위치 정책을 클릭합니다.

    > [!NOTE]
    > 위치 정책은 사이트에 E9-1-1을 배포할 경우에만 필요합니다.

9. 필요한 경우 **설명** 을 클릭한 다음 이 네트워크 사이트를 설명하는 추가 정보를 입력합니다.

10. **커밋** 을 클릭합니다.

11. 토폴로지에 대한 네트워크 사이트 만들기를 종료하려면 다른 사이트에 대한 설정을 사용하여 4~10단계를 반복합니다.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 네트워크 비즈니스용 Skype 서버 수정하려면

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

2. Set-CsNetworkSite cmdlet을 실행하여 네트워크 사이트를 수정합니다.

   ```powershell
   Set-CsNetworkSite -Identity <string>
   ```

    예:

   ```powershell
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    이 예제에서는 "앨버커키"라는 사이트가 "NorthAmerica" 네트워크 지역으로 이동됩니다. 통화 허용 제어, E9-1-1 또는 미디어 바이패스를 배포하기 위해 네트워크 사이트 구성을 수정하려면 각각 BWPolicyProfileID 또는 LocationPolicy 매개 변수와 함께 Set-CsNetworkSite cmdlet을 실행하여 네트워크 사이트 설정을 수정합니다.

    > [!NOTE]
    > 미디어 바이패스에는 BypassID 매개 변수가 있지만 자동으로 생성된 바이패스 ID를 재정의하지 않는 것이 좋습니다. 미디어 바이패스에 대한 네트워크 사이트를 구성하기 위해 추가 매개 변수를 지정할 필요는 없습니다.

3. 토폴로지에 대한 네트워크 사이트 수정을 종료하려면 다른 사이트에 대한 설정을 사용하여 2단계를 반복합니다.

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 네트워크 비즈니스용 Skype 서버 수정하려면

1. 제어판을 비즈니스용 Skype 서버 를 니다.

2. 왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.

3. **사이트** 탐색 단추를 클릭합니다.

4. 테이블에서 수정할 네트워크 사이트를 클릭합니다.

5. **편집** 을 클릭한 다음 **자세한 정보 표시...** 를 클릭합니다.

6. 사이트 **편집 페이지에서** 이 네트워크 사이트의 설정 값을 적절하게 변경합니다.

7. **커밋** 을 클릭합니다.

8. 네트워크 사이트 수정을 종료하려면 다른 사이트에 대한 설정을 사용하여 4~7단계를 반복합니다.

## <a name="associate-a-subnet-with-a-network-site"></a>네트워크 사이트에 서브넷 연결
<a name="BKMK_AssociateSubnets"> </a>

새 세션이 시작되는 동안 끝점이 있는 네트워크 사이트를 확인하는 데 서브넷 정보가 사용될 수 있기 때문에 네트워크의 모든 서브넷은 특정 네트워크 사이트와 연결되어야 합니다. 세션에서 각 파티의 위치를 알 수 있는 경우 고급 Enterprise Voice 해당 정보를 적용하여 통화 설정 또는 라우팅 처리 방법을 결정할 수 있습니다.

배포에 있는 오디오/비디오 에지 서버의 구성된 모든 공용 IP 주소를 네트워크 구성 설정에 추가해야 합니다. 이러한 IP 주소는 마스크가 32인 서브넷으로 추가됩니다. 연결된 네트워크 사이트는 구성된 적절한 네트워크 사이트에 해당해야 합니다. 예를 들어 시카고 중앙 사이트의 A/V 에지 서비스에 해당하는 공용 IP 주소는 NetworkSiteID Chicago가 됩니다.

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 서브넷을 네트워크 사이트에 비즈니스용 Skype 서버

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

2. **New-CsNetworkSubnet** cmdlet을  실행하여 서브넷과 네트워크 사이트를 연결합니다.

   ```powershell
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    예를 들면 다음과 같습니다.

   ```powershell
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    이 예제에서는 서브넷 172.11.12.13과 네트워크 사이트 "Chicago" 간에 연결합니다.

3. 토폴로지의 모든 서브넷에 대해 2단계를 반복합니다.

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>CSV 파일을 가져와서 서브넷과 네트워크 사이트를 연결하려면

1. 추가할 모든 서브넷을 포함하는 CSV 파일을 만듭니다. 예를 들어 다음 내용이 포함된 **subnet.csv** 이름의 파일을 만듭니다.

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**

3. 다음 cmdlet을 실행하여subnet.csv를 가져온 다음 해당 콘텐츠를 Lync Server 관리 저장소에 저장합니다. ****

   ```powershell
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 서브넷을 네트워크 사이트에 비즈니스용 Skype 서버

1. 제어판을 비즈니스용 Skype 서버 를 니다.

2. 왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.

3. **서브넷** 탐색 단추를 클릭합니다.

4. **새로 만들기** 를 클릭합니다.

5. **새 서브넷** 페이지에서 **서브넷 ID** 를 클릭한 다음 네트워크 사이트와 연결할 서브넷에서 정의한 IP 주소 범위에 첫 번째 주소를 입력합니다.

6. **마스크** 를 클릭한 다음 서브넷에 적용할 비트 마스크를 입력합니다.

7. **네트워크 사이트 ID** 를 클릭한 다음 이 서브넷을 추가하고 있는 사이트의 사이트 ID를 선택합니다.

    > [!NOTE]
    > 네트워크 사이트를 아직 만들지 않은 경우에는 이 목록이 비어 있게 됩니다. 절차를 보려면 [Create or Modify a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site)을 참조하십시오. **Get-CsNetworkSite** cmdlet을 실행하여 배포에 사용할 사이트 ID를 검색할 수 있습니다. 자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서를 참조하십시오.

8. 경우에 따라 **설명** 을 클릭하고 이 서브넷을 설명하는 추가 정보를 입력합니다.

9. **커밋** 을 클릭합니다.

다른 서브넷을 네트워크 사이트에 추가하려면 이러한 단계를 반복합니다.
> [!NOTE]
> 네트워크에 있지만 서브넷과 연결되지 않은 IP 주소 목록 또는 IP 주소가 포함되어 있지만 네트워크 사이트에 연결되지 않은 서브넷 목록을 지정하는 KHI(Key Health Indicator) 알림이 표시됩니다. 이 알림은 8시간 간격으로 한 번만 발생합니다(해당되는 경우).

관련 알림 정보 및 예는 다음과 같습니다.

 **원본**: CS 대역폭 정책 서비스(핵심)

 **이벤트 번호**: 36034

 **수준**: 2

 **설명:** 다음 IP 주소에 대한 서브넷이 구성되지 않았습니다. 또는 서브넷이 네트워크 사이트에 \<List of IP Addresses\> 연결되지 않았습니다.

 **원인**: 해당 IP 주소에 대한 서브넷이 네트워크 구성 설정에서 누락되었거나 서브넷이 네트워크 사이트에 연결되지 않았습니다.

 **해결 방법**: IP 주소 목록에 해당하는 서브넷을 네트워크 구성 설정에 추가하고 모든 서브넷을 네트워크 사이트에 연결합니다.

예를 들어 알림에 표시된 IP 주소 목록이 10.121.248.226 및 10.121.249.20을 나타내는 경우 이러한 IP 주소가 서브넷에 연결되지 않았거나, 이러한 IP 주소가 연결된 서브넷이 네트워크 사이트 속해 있지 않습니다. 10.121.248.0/24 및 10.121.249.0/24가 이러한 주소에 해당하는 서브넷인 경우 다음과 같이 이 문제를 해결할 수 있습니다.

1. IP 주소 10.121.248.226이 10.121.248.0/24 서브넷과 연결되고, IP 주소 10.121.249.20이 10.121.249.0/24 서브넷과 연결되어 있는지 확인합니다.

2. 10.121.248.0/24 및 10.121.249.0/24 서브넷이 각각 네트워크 사이트와 연결되어 있는지 확인합니다.

## <a name="see-also"></a>참고 항목
<a name="BKMK_AssociateSubnets"> </a>


[New-CsNetworkRegion](/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[Set-CsNetworkRegion](/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[Remove-CsNetworkRegion](/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)