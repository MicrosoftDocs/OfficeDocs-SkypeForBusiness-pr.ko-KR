---
title: 비즈니스용 Skype 서버에서 위치 데이터베이스 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 비즈니스용 Skype Server Enterprise Voice에서 E9-1 위치 데이터베이스를 구성, 채우기, 게시 합니다.
ms.openlocfilehash: 4b8848637130886250d08847c45df3c2dc080f5b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768111"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 위치 데이터베이스 구성
 
비즈니스용 Skype Server Enterprise Voice에서 E9-1 위치 데이터베이스를 구성, 채우기, 게시 합니다. 
  
클라이언트가 네트워크 내에서 해당 위치를 자동으로 검색할 수 있도록 하려면 먼저 위치 데이터베이스를 구성 해야 합니다. 
  
위치 데이터베이스를 구성 하려면 다음 작업을 수행 합니다.
  
- 네트워크 요소를 위치에 매핑하는 방법으로 데이터베이스를 채웁니다. 비상 위치 Id 번호 (ELIN) 게이트웨이를 사용 하는 경우 \<CompanyName\> 필드에 elin을 포함 해야 합니다.
    
    위치 데이터베이스를 채우지 않고 위치 정책에 **필요한 위치가** **예** 또는 **부인**로 설정 된 경우 클라이언트는 사용자에 게 위치를 수동으로 입력 하 라는 메시지를 표시 합니다.
    
- E9-1 서비스 공급자가 유지 관리 하는 MSAG (마스터 거리 주소 가이드)에 대해 주소의 유효성을 검사 합니다.
    
- 업데이트 된 데이터베이스를 게시 합니다.
    
## <a name="populate-the-location-database"></a>위치 데이터베이스 채우기

네트워크 내에서 클라이언트를 자동으로 찾으려면 먼저 네트워크 요소를 도시 (즉, 거리) 주소로 매핑하는 network wiremap 매핑으로 위치 데이터베이스를 채워야 합니다. 서브넷, 무선 액세스 지점, 스위치 및 포트를 사용 하 여 wiremap 매핑 정의를 할 수 있습니다.
  
다음 표에 설명 된 열 서식이 포함 된 CSV 파일을 사용 하 여 위치 데이터베이스에 개별적으로 또는 대량으로 주소를 추가할 수 있습니다.
  
비상 위치 Id 번호 (ELIN) 게이트웨이를 사용 하는 경우 각 위치에 대 한 **CompanyName** 필드에 elin을 포함 합니다. 각각 세미콜론으로 구분 하 여 각 위치에 여러 개의 ELINs을 포함할 수 있습니다.
  
|**네트워크 요소**|**필수 열**|
|:-----|:-----|
|**무선 액세스 지점의** <br/> |\<BSSID\>,\<설명\>,\<위치\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<predirectional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<postdirectional\>,\<시\>,\<주\>,\<우편\>,\<국가\>  <br/> |
|**서브넷** <br/> |\<서브넷\>,\<설명\>,\<위치\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<predirectional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<postdirectional\>,\<시\>,\<주\>,\<우편\>,\<국가\>  <br/> |
|**포트** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<설명\>,\<위치\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,...  <br/> ... \<Predirectional\>,\<StreetName\>,\<StreetSuffix\>,\<postdirectional\>,\<구\>/\<군\>/\<시\>,\<주, PostalCode, 국가\>  <br/> |
|**바꾸려면** <br/> |\<ChassisID\>,\<설명\>,\<위치\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<predirectional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<postdirectional\>,\<시\>,\<주\>,\<우편\>,\<국가\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>위치 데이터베이스에 네트워크 요소를 추가 하려면

1. 다음 cmdlet을 실행 하 여 위치 데이터베이스에 서브넷 위치를 추가 합니다.
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    게이트웨이에서 ELIN 대해 CompanyName 필드에 ELIN 넣으십시오. 두 개 이상의 ELIN을 포함할 수 있습니다. 예를 들면 다음과 같습니다.
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    또는 다음 cmdlet을 실행 하 고 "subnet. .csv" 이라는 파일을 사용 하 여 서브넷 위치를 대량으로 업데이트할 수 있습니다.
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. 다음 cmdlet을 실행 하 여 위치 데이터베이스에 무선 위치를 추가 합니다.
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   또는 다음 cmdlet을 실행 하 고 "waps" 라는 파일을 사용 하 여 무선 위치를 대량으로 업데이트할 수 있습니다.
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. 다음 cmdlet을 실행 하 여 위치 데이터베이스에 전환 위치를 추가 합니다.
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   또는 다음 cmdlet을 실행 하 고 "스위치인 .csv" 라는 파일을 사용 하 여 스위치 위치를 대량으로 업데이트할 수 있습니다.
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. 다음 cmdlet을 실행 하 여 위치 데이터베이스에 포트 위치를 추가 합니다.
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   PortIDSubType의 기본값은 LocallyAssigned입니다. 또한이를 인터페이스 별칭 또는 InterfaceName로 설정할 수 있습니다.
    
   또는 다음 cmdlet을 실행 하 고 "포트인 .csv" 이라는 파일을 사용 하 여 포트 위치를 대량으로 업데이트할 수 있습니다.
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>주소 유효성 검사

### <a name="to-validate-addresses-located-in-the-location-database"></a>위치 데이터베이스에 있는 주소의 유효성을 검사 하려면

1.  비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. 다음 cmdlet을 실행 하 여 응급 서비스 공급자 연결을 구성 합니다.
    
   ```powershell
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. 다음 cmdlet을 실행 하 여 위치 데이터베이스에서 주소의 유효성을 검사 합니다.
    
   ```powershell
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   **테스트 CsLisCivicAddress** cmdlet을 사용 하 여 개별 주소의 유효성을 검사할 수도 있습니다.
    
## <a name="publish-the-location-database"></a>위치 데이터베이스 게시

위치 데이터베이스에 추가한 새 위치는 게시 될 때까지 클라이언트에서 사용할 수 없게 됩니다.
  
비상 위치 Id 번호 (ELIN) 게이트웨이를 사용 하는 경우에도 ELIN을 PSTN (공개 통신 네트워크)의 ALI (자동 위치 확인) 데이터베이스에 업로드 해야 합니다. PSTN 통신 회사에서는 레코드의 ELIN 특정 형식을 사용 해야 할 수 있습니다. 자세한 내용은 PSTN 캐리어에 문의 하세요. 위치 정보 서비스 데이터베이스에서 레코드를 내보내고 필요에 따라 서식을 지정할 수 있습니다.
  
### <a name="to-publish-the-location-database"></a>위치 데이터베이스를 게시 하려면

-  비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
- 다음 cmdlet을 실행 하 여 위치 데이터베이스를 게시 합니다.
    
  ```powershell
  Publish-CsLisConfiguration
  ```


