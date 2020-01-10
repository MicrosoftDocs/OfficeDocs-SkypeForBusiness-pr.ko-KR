---
title: 비즈니스용 Skype 서버에서 위치 데이터베이스 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: 비즈니스용 Skype Server Enterprise Voice에서 E9-1 위치 데이터베이스를 구성, 채우기, 게시 합니다.
ms.openlocfilehash: 1e972e78af1a83e68c2d28d0f636128b7c339cf2
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001308"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a><span data-ttu-id="a724f-103">비즈니스용 Skype 서버에서 위치 데이터베이스 구성</span><span class="sxs-lookup"><span data-stu-id="a724f-103">Configure the location database in Skype for Business Server</span></span>
 
<span data-ttu-id="a724f-104">비즈니스용 Skype Server Enterprise Voice에서 E9-1 위치 데이터베이스를 구성, 채우기, 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-104">Configure, populate, and publish the E9-1-1 location database in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="a724f-105">클라이언트가 네트워크 내에서 해당 위치를 자동으로 검색할 수 있도록 하려면 먼저 위치 데이터베이스를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-105">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> 
  
<span data-ttu-id="a724f-106">위치 데이터베이스를 구성 하려면 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-106">To configure the location database, perform the following tasks:</span></span>
  
- <span data-ttu-id="a724f-107">네트워크 요소를 위치에 매핑하는 방법으로 데이터베이스를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="a724f-108">비상 위치 Id 번호 (ELIN) 게이트웨이를 사용 하는 경우 \<CompanyName\> 필드에 elin을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>
    
    <span data-ttu-id="a724f-109">위치 데이터베이스를 채우지 않고 위치 정책에 **필요한 위치가** **예** 또는 **부인**로 설정 된 경우 클라이언트는 사용자에 게 위치를 수동으로 입력 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-109">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>
    
- <span data-ttu-id="a724f-110">E9-1 서비스 공급자가 유지 관리 하는 MSAG (마스터 거리 주소 가이드)에 대해 주소의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-110">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>
    
- <span data-ttu-id="a724f-111">업데이트 된 데이터베이스를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-111">Publish the updated database.</span></span>
    
## <a name="populate-the-location-database"></a><span data-ttu-id="a724f-112">위치 데이터베이스 채우기</span><span class="sxs-lookup"><span data-stu-id="a724f-112">Populate the location database</span></span>

<span data-ttu-id="a724f-113">네트워크 내에서 클라이언트를 자동으로 찾으려면 먼저 네트워크 요소를 도시 (즉, 거리) 주소로 매핑하는 network wiremap 매핑으로 위치 데이터베이스를 채워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-113">To automatically locate clients within a network, you first need to populate the location database with a network wiremap, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="a724f-114">서브넷, 무선 액세스 지점, 스위치 및 포트를 사용 하 여 wiremap 매핑 정의를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-114">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>
  
<span data-ttu-id="a724f-115">다음 표에 설명 된 열 서식이 포함 된 CSV 파일을 사용 하 여 위치 데이터베이스에 개별적으로 또는 대량으로 주소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-115">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>
  
<span data-ttu-id="a724f-116">비상 위치 Id 번호 (ELIN) 게이트웨이를 사용 하는 경우 각 위치에 대 한 **CompanyName** 필드에 elin을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-116">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location.</span></span> <span data-ttu-id="a724f-117">각각 세미콜론으로 구분 하 여 각 위치에 여러 개의 ELINs을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-117">You can include multiple ELINs for each location, each separated by a semicolon.</span></span>
  
|<span data-ttu-id="a724f-118">**네트워크 요소**</span><span class="sxs-lookup"><span data-stu-id="a724f-118">**Network Element**</span></span>|<span data-ttu-id="a724f-119">**필수 열**</span><span class="sxs-lookup"><span data-stu-id="a724f-119">**Required Columns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a724f-120">**무선 액세스 지점의**</span><span class="sxs-lookup"><span data-stu-id="a724f-120">**Wireless access point**</span></span> <br/> |<span data-ttu-id="a724f-121">\<BSSID\>,\<설명\>,\<위치\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<predirectional\>,...</span><span class="sxs-lookup"><span data-stu-id="a724f-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="a724f-122">... \<StreetName\>,\<StreetSuffix\>,\<postdirectional\>,\<시\>,\<주\>,\<우편\>,\<국가\></span><span class="sxs-lookup"><span data-stu-id="a724f-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="a724f-123">**서브넷**</span><span class="sxs-lookup"><span data-stu-id="a724f-123">**Subnet**</span></span> <br/> |<span data-ttu-id="a724f-124">\<서브넷\>,\<설명\>,\<위치\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<predirectional\>,...</span><span class="sxs-lookup"><span data-stu-id="a724f-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="a724f-125">... \<StreetName\>,\<StreetSuffix\>,\<postdirectional\>,\<시\>,\<주\>,\<우편\>,\<국가\></span><span class="sxs-lookup"><span data-stu-id="a724f-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="a724f-126">**포트**</span><span class="sxs-lookup"><span data-stu-id="a724f-126">**Port**</span></span> <br/> |<span data-ttu-id="a724f-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<설명\>,\<위치\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,...</span><span class="sxs-lookup"><span data-stu-id="a724f-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span></span>  <br/> <span data-ttu-id="a724f-128">... \<Predirectional\>,\<StreetName\>,\<StreetSuffix\>,\<postdirectional\>,\<구\>/\<군\>/\<시\>,\<주, PostalCode, 국가\></span><span class="sxs-lookup"><span data-stu-id="a724f-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="a724f-129">**바꾸려면**</span><span class="sxs-lookup"><span data-stu-id="a724f-129">**Switch**</span></span> <br/> |<span data-ttu-id="a724f-130">\<ChassisID\>,\<설명\>,\<위치\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<predirectional\>,...</span><span class="sxs-lookup"><span data-stu-id="a724f-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="a724f-131">... \<StreetName\>,\<StreetSuffix\>,\<postdirectional\>,\<시\>,\<주\>,\<우편\>,\<국가\></span><span class="sxs-lookup"><span data-stu-id="a724f-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="a724f-132">위치 데이터베이스에 네트워크 요소를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="a724f-132">To add network elements to the location database</span></span>

1. <span data-ttu-id="a724f-133">다음 cmdlet을 실행 하 여 위치 데이터베이스에 서브넷 위치를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-133">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="a724f-134">게이트웨이에서 ELIN 대해 CompanyName 필드에 ELIN 넣으십시오.</span><span class="sxs-lookup"><span data-stu-id="a724f-134">For ELIN gateways, put the ELIN in the CompanyName field.</span></span> <span data-ttu-id="a724f-135">두 개 이상의 ELIN을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-135">You can include more than one ELIN.</span></span> <span data-ttu-id="a724f-136">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-136">For example:</span></span>
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="a724f-137">또는 다음 cmdlet을 실행 하 고 "subnet. .csv" 이라는 파일을 사용 하 여 서브넷 위치를 대량으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-137">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. <span data-ttu-id="a724f-138">다음 cmdlet을 실행 하 여 위치 데이터베이스에 무선 위치를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-138">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="a724f-139">또는 다음 cmdlet을 실행 하 고 "waps" 라는 파일을 사용 하 여 무선 위치를 대량으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-139">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. <span data-ttu-id="a724f-140">다음 cmdlet을 실행 하 여 위치 데이터베이스에 전환 위치를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-140">Run the following cmdlet to add switch locations to the location database.</span></span>
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   <span data-ttu-id="a724f-141">또는 다음 cmdlet을 실행 하 고 "스위치인 .csv" 라는 파일을 사용 하 여 스위치 위치를 대량으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-141">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. <span data-ttu-id="a724f-142">다음 cmdlet을 실행 하 여 위치 데이터베이스에 포트 위치를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-142">Run the following cmdlet to add port locations to the location database</span></span>
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="a724f-143">PortIDSubType의 기본값은 LocallyAssigned입니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-143">The default for PortIDSubType is LocallyAssigned.</span></span> <span data-ttu-id="a724f-144">또한이를 인터페이스 별칭 또는 InterfaceName로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-144">You can also set it to InterfaceAlias or InterfaceName</span></span>
    
   <span data-ttu-id="a724f-145">또는 다음 cmdlet을 실행 하 고 "포트인 .csv" 이라는 파일을 사용 하 여 포트 위치를 대량으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-145">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a><span data-ttu-id="a724f-146">주소 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="a724f-146">Validate addresses</span></span>

### <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="a724f-147">위치 데이터베이스에 있는 주소의 유효성을 검사 하려면</span><span class="sxs-lookup"><span data-stu-id="a724f-147">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="a724f-148">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="a724f-149">다음 cmdlet을 실행 하 여 응급 서비스 공급자 연결을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-149">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
   ```powershell
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. <span data-ttu-id="a724f-150">다음 cmdlet을 실행 하 여 위치 데이터베이스에서 주소의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-150">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
   ```powershell
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   <span data-ttu-id="a724f-151">**테스트 CsLisCivicAddress** cmdlet을 사용 하 여 개별 주소의 유효성을 검사할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-151">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>
    
## <a name="publish-the-location-database"></a><span data-ttu-id="a724f-152">위치 데이터베이스 게시</span><span class="sxs-lookup"><span data-stu-id="a724f-152">Publish the location database</span></span>

<span data-ttu-id="a724f-153">위치 데이터베이스에 추가한 새 위치는 게시 될 때까지 클라이언트에서 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-153">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>
  
<span data-ttu-id="a724f-154">비상 위치 Id 번호 (ELIN) 게이트웨이를 사용 하는 경우에도 ELIN을 PSTN (공개 통신 네트워크)의 ALI (자동 위치 확인) 데이터베이스에 업로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-154">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="a724f-155">PSTN 통신 회사에서는 레코드의 ELIN 특정 형식을 사용 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-155">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="a724f-156">자세한 내용은 PSTN 캐리어에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="a724f-156">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="a724f-157">위치 정보 서비스 데이터베이스에서 레코드를 내보내고 필요에 따라 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-157">You can export the records from the Location Information service database and format them as required.</span></span>
  
### <a name="to-publish-the-location-database"></a><span data-ttu-id="a724f-158">위치 데이터베이스를 게시 하려면</span><span class="sxs-lookup"><span data-stu-id="a724f-158">To publish the location database</span></span>

-  <span data-ttu-id="a724f-159">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-159">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
- <span data-ttu-id="a724f-160">다음 cmdlet을 실행 하 여 위치 데이터베이스를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a724f-160">Run the following cmdlet to publish the location database.</span></span>
    
  ```powershell
  Publish-CsLisConfiguration
  ```


