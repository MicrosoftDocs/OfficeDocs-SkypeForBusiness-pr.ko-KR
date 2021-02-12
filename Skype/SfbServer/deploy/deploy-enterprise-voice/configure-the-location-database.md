---
title: 비즈니스용 Skype 서버에서 위치 데이터베이스 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: 비즈니스용 Skype 서버에서 E9-1-1 위치 데이터베이스를 구성, 채우기 및 Enterprise Voice.
ms.openlocfilehash: 70158864446c12b2e7636a2962aced05d87c49a0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804088"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 위치 데이터베이스 구성
 
비즈니스용 Skype 서버에서 E9-1-1 위치 데이터베이스를 구성, 채우기 및 Enterprise Voice. 
  
클라이언트가 네트워크 내에서 자신의 위치를 자동으로 감지하도록 하려면 먼저 위치 데이터베이스를 구성해야 합니다. 
  
위치 데이터베이스를 구성하려면 다음 작업을 수행합니다.
  
- 데이터베이스를 위치에 대한 네트워크 요소 매핑으로 채웁니다. ELIN(Emergency Location Identification Number) 게이트웨이를 사용하는 경우 필드에 ELIN을 포함해야 \<CompanyName\> 합니다.
    
    위치 정책에서 **위치 필요** 가 **예** 나 **고지 사항** 으로 설정되었을 때 위치 데이터베이스를 채우지 않으면 위치를 수동으로 입력하라는 메시지가 클라이언트에 표시됩니다.
    
- E9-1-1 서비스 공급자가 유지 관리하는 MSAG(마스터 주소 가이드)에 대해 주소를 확인합니다.
    
- 업데이트된 데이터베이스를 게시합니다.
    
## <a name="populate-the-location-database"></a>위치 데이터베이스 채우기

네트워크에서 클라이언트를 자동으로 찾으려면 먼저 네트워크 요소를 구/군/시 주소로 매핑하는 네트워크 와이어맵(wiremap)으로 위치 데이터베이스를 채워야 합니다. 서브넷, 무선 액세스 지점, 스위치 및 포트를 사용하여 와이어맵(wiremap)을 정의할 수 있습니다.
  
위치 데이터베이스에는 주소를 개별적으로 추가하거나 다음 표에 설명된 열 형식이 포함된 CSV 파일을 사용하여 일괄적으로 추가할 수 있습니다.
  
ELIN(Emergency Location Identification Number) 게이트웨이를 사용하는 경우 각 위치의 **CompanyName** 필드에 ELIN을 포함합니다. 각 위치마다 세미콜론으로 구분하여 여러 ELIN을 포함할 수 있습니다.
  
|**네트워크 요소**|**필수 열**|
|:-----|:-----|
|**무선 액세스 지점** <br/> |\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**서브넷** <br/> |\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Port(포트)** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…  <br/> …\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Switch** <br/> |\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>위치 데이터베이스에 네트워크 요소를 추가하려면

1. 다음 cmdlet를 실행하여 위치 데이터베이스에 서브넷 위치를 추가합니다.
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    ELIN 게이트웨이의 경우, CompanyName 필드에 ELIN을 추가합니다. 두 개 이상의 ELIN을 포함할 수 있습니다. 예를 들면 다음과 같습니다.
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    또는 다음 cmdlet를 실행하고 'subnets.csv' 파일을 사용하여 서브넷 위치를 일괄적으로 업데이트할 수도 있습니다.
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. 다음 cmdlet를 실행하여 위치 데이터베이스에 무선 위치를 추가합니다.
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   또는 다음 cmdlet를 실행하고 csv 파일 ‘waps.csv’를 사용하여 무선 위치를 일괄적으로 업데이트할 수 있습니다.
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. 다음 cmdlet를 실행하여 위치 데이터베이스에 스위치 위치를 추가합니다.
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   또는 다음 cmdlet를 실행하고 csv 파일 ‘switches.csv’를 사용하여 스위치 위치를 일괄적으로 업데이트할 수 있습니다.
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. 다음 cmdlet를 실행하여 위치 데이터베이스에 포트 위치를 추가합니다.
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   PortIDSubType의 기본값은 LocallyAssigned이며, 이 값을 InterfaceAlias 또는 InterfaceName으로 설정할 수도 있습니다.
    
   또는 다음 cmdlet를 실행하고 'ports.csv' 파일을 사용하여 포트 위치를 일괄적으로 업데이트할 수도 있습니다.
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>주소 유효성 검사

### <a name="to-validate-addresses-located-in-the-location-database"></a>위치 데이터베이스에 있는 주소의 유효성을 검사하려면

1.  비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
2. 다음 cmdlet을 실행하여 긴급 서비스 공급자 연결을 구성합니다.
    
   ```powershell
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. 다음 cmdlet을 실행하여 위치 데이터베이스의 주소에 대한 유효성을 검사합니다.
    
   ```powershell
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   **Test-CsLisCivicAddress cmdlet을** 사용하여 개별 주소의 유효성을 검사할 수도 있습니다.
    
## <a name="publish-the-location-database"></a>위치 데이터베이스 게시

위치 데이터베이스에 추가한 새 위치는 게시될 때까지 클라이언트에서 사용할 수 없습니다.
  
ELIN(Emergency Location Identification Number) 게이트웨이를 사용하는 경우 PSTN(Public Switched Telephone Network) 통신사 ALI(자동 위치 식별) 데이터베이스에도 ELIN을 업로드해야 합니다. PSTN 통신 사업자에서 ELIN 레코드에 대해 특정 형식을 사용해야 할 수 있습니다. 자세한 내용은 PSTN 통신 사업자에 문의하십시오. 위치 정보 서비스 데이터베이스에서 레코드를 내보내고 필요한 서식을 지정합니다.
  
### <a name="to-publish-the-location-database"></a>위치 데이터베이스를 게시하려면

-  비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
- 다음 cmdlet을 실행하여 위치 데이터베이스를 게시합니다.
    
  ```powershell
  Publish-CsLisConfiguration
  ```


