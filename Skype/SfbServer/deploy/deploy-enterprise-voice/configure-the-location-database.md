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
# <a name="configure-the-location-database-in-skype-for-business-server"></a><span data-ttu-id="5f6eb-103">비즈니스용 Skype 서버에서 위치 데이터베이스 구성</span><span class="sxs-lookup"><span data-stu-id="5f6eb-103">Configure the location database in Skype for Business Server</span></span>
 
<span data-ttu-id="5f6eb-104">비즈니스용 Skype 서버에서 E9-1-1 위치 데이터베이스를 구성, 채우기 및 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-104">Configure, populate, and publish the E9-1-1 location database in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="5f6eb-105">클라이언트가 네트워크 내에서 자신의 위치를 자동으로 감지하도록 하려면 먼저 위치 데이터베이스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-105">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> 
  
<span data-ttu-id="5f6eb-106">위치 데이터베이스를 구성하려면 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-106">To configure the location database, perform the following tasks:</span></span>
  
- <span data-ttu-id="5f6eb-107">데이터베이스를 위치에 대한 네트워크 요소 매핑으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="5f6eb-108">ELIN(Emergency Location Identification Number) 게이트웨이를 사용하는 경우 필드에 ELIN을 포함해야 \<CompanyName\> 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>
    
    <span data-ttu-id="5f6eb-109">위치 정책에서 **위치 필요** 가 **예** 나 **고지 사항** 으로 설정되었을 때 위치 데이터베이스를 채우지 않으면 위치를 수동으로 입력하라는 메시지가 클라이언트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-109">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>
    
- <span data-ttu-id="5f6eb-110">E9-1-1 서비스 공급자가 유지 관리하는 MSAG(마스터 주소 가이드)에 대해 주소를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-110">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>
    
- <span data-ttu-id="5f6eb-111">업데이트된 데이터베이스를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-111">Publish the updated database.</span></span>
    
## <a name="populate-the-location-database"></a><span data-ttu-id="5f6eb-112">위치 데이터베이스 채우기</span><span class="sxs-lookup"><span data-stu-id="5f6eb-112">Populate the location database</span></span>

<span data-ttu-id="5f6eb-113">네트워크에서 클라이언트를 자동으로 찾으려면 먼저 네트워크 요소를 구/군/시 주소로 매핑하는 네트워크 와이어맵(wiremap)으로 위치 데이터베이스를 채워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-113">To automatically locate clients within a network, you first need to populate the location database with a network wiremap, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="5f6eb-114">서브넷, 무선 액세스 지점, 스위치 및 포트를 사용하여 와이어맵(wiremap)을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-114">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>
  
<span data-ttu-id="5f6eb-115">위치 데이터베이스에는 주소를 개별적으로 추가하거나 다음 표에 설명된 열 형식이 포함된 CSV 파일을 사용하여 일괄적으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-115">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>
  
<span data-ttu-id="5f6eb-p103">ELIN(Emergency Location Identification Number) 게이트웨이를 사용하는 경우 각 위치의 **CompanyName** 필드에 ELIN을 포함합니다. 각 위치마다 세미콜론으로 구분하여 여러 ELIN을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-p103">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location. You can include multiple ELINs for each location, each separated by a semicolon.</span></span>
  
|<span data-ttu-id="5f6eb-118">**네트워크 요소**</span><span class="sxs-lookup"><span data-stu-id="5f6eb-118">**Network Element**</span></span>|<span data-ttu-id="5f6eb-119">**필수 열**</span><span class="sxs-lookup"><span data-stu-id="5f6eb-119">**Required Columns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5f6eb-120">**무선 액세스 지점**</span><span class="sxs-lookup"><span data-stu-id="5f6eb-120">**Wireless access point**</span></span> <br/> |<span data-ttu-id="5f6eb-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span><span class="sxs-lookup"><span data-stu-id="5f6eb-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="5f6eb-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="5f6eb-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="5f6eb-123">**서브넷**</span><span class="sxs-lookup"><span data-stu-id="5f6eb-123">**Subnet**</span></span> <br/> |<span data-ttu-id="5f6eb-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span><span class="sxs-lookup"><span data-stu-id="5f6eb-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="5f6eb-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="5f6eb-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="5f6eb-126">**Port(포트)**</span><span class="sxs-lookup"><span data-stu-id="5f6eb-126">**Port**</span></span> <br/> |<span data-ttu-id="5f6eb-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span><span class="sxs-lookup"><span data-stu-id="5f6eb-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span></span>  <br/> <span data-ttu-id="5f6eb-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="5f6eb-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="5f6eb-129">**Switch**</span><span class="sxs-lookup"><span data-stu-id="5f6eb-129">**Switch**</span></span> <br/> |<span data-ttu-id="5f6eb-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span><span class="sxs-lookup"><span data-stu-id="5f6eb-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="5f6eb-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="5f6eb-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="5f6eb-132">위치 데이터베이스에 네트워크 요소를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="5f6eb-132">To add network elements to the location database</span></span>

1. <span data-ttu-id="5f6eb-133">다음 cmdlet를 실행하여 위치 데이터베이스에 서브넷 위치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-133">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="5f6eb-p104">ELIN 게이트웨이의 경우, CompanyName 필드에 ELIN을 추가합니다. 두 개 이상의 ELIN을 포함할 수 있습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-p104">For ELIN gateways, put the ELIN in the CompanyName field. You can include more than one ELIN. For example:</span></span>
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="5f6eb-137">또는 다음 cmdlet를 실행하고 'subnets.csv' 파일을 사용하여 서브넷 위치를 일괄적으로 업데이트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-137">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. <span data-ttu-id="5f6eb-138">다음 cmdlet를 실행하여 위치 데이터베이스에 무선 위치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-138">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="5f6eb-139">또는 다음 cmdlet를 실행하고 csv 파일 ‘waps.csv’를 사용하여 무선 위치를 일괄적으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-139">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. <span data-ttu-id="5f6eb-140">다음 cmdlet를 실행하여 위치 데이터베이스에 스위치 위치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-140">Run the following cmdlet to add switch locations to the location database.</span></span>
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   <span data-ttu-id="5f6eb-141">또는 다음 cmdlet를 실행하고 csv 파일 ‘switches.csv’를 사용하여 스위치 위치를 일괄적으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-141">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. <span data-ttu-id="5f6eb-142">다음 cmdlet를 실행하여 위치 데이터베이스에 포트 위치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-142">Run the following cmdlet to add port locations to the location database</span></span>
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="5f6eb-p105">PortIDSubType의 기본값은 LocallyAssigned이며, 이 값을 InterfaceAlias 또는 InterfaceName으로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-p105">The default for PortIDSubType is LocallyAssigned. You can also set it to InterfaceAlias or InterfaceName</span></span>
    
   <span data-ttu-id="5f6eb-145">또는 다음 cmdlet를 실행하고 'ports.csv' 파일을 사용하여 포트 위치를 일괄적으로 업데이트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-145">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a><span data-ttu-id="5f6eb-146">주소 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="5f6eb-146">Validate addresses</span></span>

### <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="5f6eb-147">위치 데이터베이스에 있는 주소의 유효성을 검사하려면</span><span class="sxs-lookup"><span data-stu-id="5f6eb-147">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="5f6eb-148">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f6eb-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="5f6eb-149">다음 cmdlet을 실행하여 긴급 서비스 공급자 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-149">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
   ```powershell
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. <span data-ttu-id="5f6eb-150">다음 cmdlet을 실행하여 위치 데이터베이스의 주소에 대한 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-150">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
   ```powershell
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   <span data-ttu-id="5f6eb-151">**Test-CsLisCivicAddress cmdlet을** 사용하여 개별 주소의 유효성을 검사할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-151">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>
    
## <a name="publish-the-location-database"></a><span data-ttu-id="5f6eb-152">위치 데이터베이스 게시</span><span class="sxs-lookup"><span data-stu-id="5f6eb-152">Publish the location database</span></span>

<span data-ttu-id="5f6eb-153">위치 데이터베이스에 추가한 새 위치는 게시될 때까지 클라이언트에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-153">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>
  
<span data-ttu-id="5f6eb-154">ELIN(Emergency Location Identification Number) 게이트웨이를 사용하는 경우 PSTN(Public Switched Telephone Network) 통신사 ALI(자동 위치 식별) 데이터베이스에도 ELIN을 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-154">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="5f6eb-155">PSTN 통신 사업자에서 ELIN 레코드에 대해 특정 형식을 사용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-155">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="5f6eb-156">자세한 내용은 PSTN 통신 사업자에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-156">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="5f6eb-157">위치 정보 서비스 데이터베이스에서 레코드를 내보내고 필요한 서식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-157">You can export the records from the Location Information service database and format them as required.</span></span>
  
### <a name="to-publish-the-location-database"></a><span data-ttu-id="5f6eb-158">위치 데이터베이스를 게시하려면</span><span class="sxs-lookup"><span data-stu-id="5f6eb-158">To publish the location database</span></span>

-  <span data-ttu-id="5f6eb-159">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f6eb-159">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
- <span data-ttu-id="5f6eb-160">다음 cmdlet을 실행하여 위치 데이터베이스를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6eb-160">Run the following cmdlet to publish the location database.</span></span>
    
  ```powershell
  Publish-CsLisConfiguration
  ```


