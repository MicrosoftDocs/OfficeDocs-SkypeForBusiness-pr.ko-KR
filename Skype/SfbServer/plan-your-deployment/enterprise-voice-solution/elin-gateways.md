---
title: 비즈니스용 Skype 서버의 게이트웨이에서 ELIN 대 한 위치 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: 비즈니스용 Skype Server Enterprise Voice에서 게이트웨이에서 ELIN 사용 하는 E9-1 배포에 대해 위치 정보 데이터베이스 또는 유사한 외부 데이터베이스를 계획 하는 데 필요한 결정
ms.openlocfilehash: e1645be8ed1c6188d1976d794727d0668b79c12e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187719"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a><span data-ttu-id="e067d-103">비즈니스용 Skype 서버의 게이트웨이에서 ELIN 대 한 위치 관리</span><span class="sxs-lookup"><span data-stu-id="e067d-103">Manage locations for ELIN gateways in Skype for Business Server</span></span>

<span data-ttu-id="e067d-104">비즈니스용 Skype Server Enterprise Voice에서 게이트웨이에서 ELIN 사용 하는 E9-1 배포에 대해 위치 정보 데이터베이스 또는 유사한 외부 데이터베이스를 계획 하는 데 필요한 결정</span><span class="sxs-lookup"><span data-stu-id="e067d-104">Decisions necessary for planning an the location information database, or a similar external database, for an E9-1-1 deployment using ELIN gateways, in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="e067d-105">비즈니스용 Skype 서버가 네트워크 내의 클라이언트에 대 한 위치를 자동으로 제공 하도록 하려면 다음 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-105">To have Skype for Business Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

- <span data-ttu-id="e067d-106">네트워크 wiremap 매핑으로 위치 정보 서비스 데이터베이스를 채우고 CompanyName 필드에 비상 위치 Id 번호 (ELINs)를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-106">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

- <span data-ttu-id="e067d-107">네트워크의 클라이언트에서 사용할 수 있도록 위치를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-107">Publish the locations so that they are available for clients in your network.</span></span>

- <span data-ttu-id="e067d-108">PSTN (공개 교환 전화 네트워크)의 ALI (자동 위치 확인) 데이터베이스에 ELINs을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-108">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="e067d-109">이러한 작업을 수행 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [위치 데이터베이스 구성을](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e067d-109">For details about how to perform these tasks, see [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="e067d-110">중앙 위치 데이터베이스에 추가 된 위치는 비즈니스용 Skype Server Management Shell 명령을 사용 하 여 게시 되거나 풀의 로컬 저장소에 복제 될 때까지 클라이언트에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-110">Locations added to the central location database are not available to the client until they have been published by using a Skype for Business Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="e067d-111">자세한 내용은 배포 설명서에서 [위치 데이터베이스 게시](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e067d-111">For details, see [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) in the Deployment documentation.</span></span>

<span data-ttu-id="e067d-112">이 섹션에서는 위치 데이터베이스를 업데이트 하 고 유지 관리 하는 데 고려해 야 할 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-112">This section describes things to consider as you plan to update and maintain the location database.</span></span>

## <a name="planning-emergency-locations"></a><span data-ttu-id="e067d-113">응급 위치 계획</span><span class="sxs-lookup"><span data-stu-id="e067d-113">Planning Emergency Locations</span></span>

<span data-ttu-id="e067d-114">게이트웨이에서 ELIN 사용 하는 경우 위치 정보 서비스 데이터베이스를 도심 주소, 건물 내의 특정 위치, 각 위치에 대해 하나 이상의 ELIN으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-114">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="e067d-115">계획 단계에서는 위치의 이름을 지정할 방법과 ELINs을 지정 하는 방법을 결정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-115">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

### <a name="planning-location-names"></a><span data-ttu-id="e067d-116">계획 위치 이름</span><span class="sxs-lookup"><span data-stu-id="e067d-116">Planning Location Names</span></span>

<span data-ttu-id="e067d-117">위치 정보 서비스 **위치** 필드에는 건물 내의 특정 위치가 포함 되며, 최대 길이는 20 자 (공백 포함)입니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-117">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="e067d-118">제한 된 길이 내에 다음을 포함 하세요.</span><span class="sxs-lookup"><span data-stu-id="e067d-118">Within that limited length, try to include the following:</span></span>

- <span data-ttu-id="e067d-119">응급 응답 자가 도심 주소에 도착할 때 바로 특정 위치를 찾을 수 있도록 911 발신자의 위치를 식별 하는 이해 하기 쉬운 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-119">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address.</span></span> <span data-ttu-id="e067d-120">이 위치 이름에는 건물 번호, 바닥 번호, 날개 지정자, 방 번호 등이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-120">This location name may include a building number, floor number, wing designator, room number, and so on.</span></span> <span data-ttu-id="e067d-121">직원 에게만 알려진 닉네임을 사용 하지 마세요 .이로 인해 비상 응답 자가 잘못 된 위치로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-121">Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

- <span data-ttu-id="e067d-122">클라이언트가 올바른 위치를 선택 하는 것을 쉽게 확인할 수 있도록 지 원하는 위치 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-122">A location identifier that helps users to easily see that their client picked up the correct location.</span></span> <span data-ttu-id="e067d-123">비즈니스용 Skype 클라이언트는 검색 된 **위치** 및 **도시** 필드를 해당 머리글에 자동으로 연결 하 고 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-123">The Skype for Business client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="e067d-124">좋은 방법은 각 위치 식별자 (예: "1 층 <street number>")에 건물의 거리를 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-124">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor <street number>").</span></span> <span data-ttu-id="e067d-125">이 주소가 없으면 "1 층"과 같은 일반적인 위치 식별자가 도시의 모든 건물에 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-125">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

- <span data-ttu-id="e067d-126">위치가 무선 액세스 포인트로 결정 되기 때문에 근사값 인 경우에는 단어 **[near]** 을 추가 하는 것이 좋습니다 (예: "가까운 1 층 1234").</span><span class="sxs-lookup"><span data-stu-id="e067d-126">If the location is approximate because it's determined by a wireless access point, you may want to add the word **[Near]** (for example, "Near 1st Floor 1234").</span></span>

### <a name="planning-elins"></a><span data-ttu-id="e067d-127">ELINs</span><span class="sxs-lookup"><span data-stu-id="e067d-127">Planning ELINs</span></span>

<span data-ttu-id="e067d-128">건물 공간을 위치로 나누는 방법을 결정 한 후에는 각 위치에 할당할 ELINs의 수를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-128">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location.</span></span> <span data-ttu-id="e067d-129">예를 들어 multifloor 또는 다중 테 넌 트 빌드에서는 건물의 다른 영역에 다른 긴급 영역을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-129">For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones.</span></span> <span data-ttu-id="e067d-130">일반적으로 건물의 각 층은 위치로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-130">Typically, each floor in a building is designated as a location.</span></span> <span data-ttu-id="e067d-131">그런 다음, 긴급 통화 중에 전화 번호로 사용 되는 하나 이상의 ELINs을 각 위치에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-131">Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call.</span></span> <span data-ttu-id="e067d-132">ELINs에 사용할 수 있는 전화 번호는 PSTN 통신 회사에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e067d-132">Contact your PSTN carrier for phone numbers that you can use for ELINs.</span></span> <span data-ttu-id="e067d-133">다음 표에서는 특정 주소에 대 한 위치의 예를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-133">The following table provides an example of locations for a specific street address.</span></span>

<span data-ttu-id="e067d-134">**과제에 대 한 예제 위치 및 ELIN**</span><span class="sxs-lookup"><span data-stu-id="e067d-134">**Sample Location and ELIN Assignments**</span></span>

|<span data-ttu-id="e067d-135">**건물 면적**</span><span class="sxs-lookup"><span data-stu-id="e067d-135">**Building Area**</span></span>|<span data-ttu-id="e067d-136">**위치**</span><span class="sxs-lookup"><span data-stu-id="e067d-136">**Location**</span></span>|<span data-ttu-id="e067d-137">**ELIN**</span><span class="sxs-lookup"><span data-stu-id="e067d-137">**ELIN**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e067d-138">1 층</span><span class="sxs-lookup"><span data-stu-id="e067d-138">First floor</span></span>  <br/> |<span data-ttu-id="e067d-139">raid-1</span><span class="sxs-lookup"><span data-stu-id="e067d-139">1</span></span>  <br/> |<span data-ttu-id="e067d-140">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="e067d-140">425-555-0100</span></span>  <br/> |
|<span data-ttu-id="e067d-141">2 층</span><span class="sxs-lookup"><span data-stu-id="e067d-141">Second floor</span></span>  <br/> |<span data-ttu-id="e067d-142">2</span><span class="sxs-lookup"><span data-stu-id="e067d-142">2</span></span>  <br/> |<span data-ttu-id="e067d-143">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="e067d-143">425-555-0111</span></span>  <br/> |
|<span data-ttu-id="e067d-144">세 번째 층</span><span class="sxs-lookup"><span data-stu-id="e067d-144">Third floor</span></span>  <br/> |<span data-ttu-id="e067d-145">3-4</span><span class="sxs-lookup"><span data-stu-id="e067d-145">3</span></span>  <br/> |<span data-ttu-id="e067d-146">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="e067d-146">425-555-0123</span></span>  <br/> |

<span data-ttu-id="e067d-147">정의한 위치는 다음 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-147">The locations you define should meet the following requirements:</span></span>

- <span data-ttu-id="e067d-148">지역 및 국가/지역 규정에 대 한 각 위치 당 최대 영역과 해당 주소에 대 한 위치 수를 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-148">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

- <span data-ttu-id="e067d-149">는 긴급 전화 발신자를 쉽게 찾을 수 있도록 충분히 특별 합니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-149">Are specific enough to make it easy to locate the emergency caller.</span></span>

## <a name="populating-the-location-database"></a><span data-ttu-id="e067d-150">위치 데이터베이스 채우기</span><span class="sxs-lookup"><span data-stu-id="e067d-150">Populating the Location Database</span></span>

<span data-ttu-id="e067d-151">다음 질문은 위치 데이터베이스를 채우는 방법을 결정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-151">The following questions will help you determine how to will populate the location database.</span></span>

 <span data-ttu-id="e067d-152">**위치 데이터베이스를 채우는 데 어떤 프로세스를 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e067d-152">**What process will you use to populate the location database?**</span></span>

<span data-ttu-id="e067d-153">데이터는 어디에 있으며 데이터를 위치 데이터베이스에서 요구 하는 형식으로 변환 하기 위해 수행 해야 하는 단계는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="e067d-153">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database?</span></span> <span data-ttu-id="e067d-154">CSV 파일을 사용 하 여 개별적으로 또는 대량으로 위치를 추가 하나요?</span><span class="sxs-lookup"><span data-stu-id="e067d-154">Will you add locations individually, or in bulk, by using a CSV file?</span></span>

 <span data-ttu-id="e067d-155">**위치 매핑이 이미 포함 되어 있는 타사 데이터베이스를 사용 하 고 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e067d-155">**Do you have a third party database that already contains a mapping of locations?**</span></span>

<span data-ttu-id="e067d-156">타사 데이터베이스에 연결 하기 위한 보조 위치 정보 서비스 옵션을 사용 하면 오프 라인 플랫폼을 사용 하 여 위치를 그룹화 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-156">By using the Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="e067d-157">이 방법의 장점은 위치를 네트워크 식별자와 연결 하는 것 외에 위치를 사용자와 연결할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-157">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="e067d-158">즉, 위치 정보 서비스는 보조 위치 정보 서비스에서 가져온 여러 주소를 비즈니스용 Skype 클라이언트로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-158">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Skype for Business client.</span></span> <span data-ttu-id="e067d-159">그러면 사용자가 가장 적합 한 위치를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-159">The user can then choose the most appropriate location.</span></span>

<span data-ttu-id="e067d-160">위치 정보 서비스와 통합 하려면 타사 데이터베이스가 비즈니스용 Skype 서버 위치 요청/응답 스키마를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-160">To integrate with the Location Information service, the third-party database must follow the Skype for Business Server Location Request/Response schema.</span></span> <span data-ttu-id="e067d-161">자세한 내용은 [E911 지원 프로토콜에 대 한 웹 서비스](https://go.microsoft.com/fwlink/p/?linkid=213819)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e067d-161">For details, see [Web Service for E911 Support Protocol](https://go.microsoft.com/fwlink/p/?linkid=213819).</span></span> <span data-ttu-id="e067d-162">보조 위치 정보 서비스 배포에 대 한 자세한 내용은 배포 설명서의 비즈니스용 [Skype 서버에서 보조 위치 정보 서비스 구성을](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e067d-162">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e067d-163">위치 데이터베이스를 채우는 방법에 대 한 자세한 내용은 배포 설명서에서 [위치 데이터베이스 구성을](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e067d-163">For details about populating the location database, see [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="e067d-164">위치 데이터베이스 유지 관리</span><span class="sxs-lookup"><span data-stu-id="e067d-164">Maintaining the Location Database</span></span>

<span data-ttu-id="e067d-165">위치 데이터베이스를 채운 후에는 네트워크 구성 변경으로 데이터베이스를 업데이트 하기 위한 전략을 개발 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-165">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes.</span></span> <span data-ttu-id="e067d-166">다음 질문은 위치 데이터베이스를 유지 관리 하는 방법을 결정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-166">The following questions will help you determine how to maintain the location database.</span></span>

 <span data-ttu-id="e067d-167">**위치 데이터베이스를 업데이트 하는 방법은 무엇 인가요?**</span><span class="sxs-lookup"><span data-stu-id="e067d-167">**How will you update the location database?**</span></span>

<span data-ttu-id="e067d-168">위치 데이터베이스에 업데이트 해야 하는 몇 가지 시나리오는 WAPs (무선 액세스 지점), office recabling 추가 (다른 전환 지정) 및 서브넷 확장을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-168">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="e067d-169">각각의 개별 위치를 직접 업데이트 하거나 CSV 파일을 사용 하 여 모든 위치의 대량 업데이트를 수행할지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-169">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

 <span data-ttu-id="e067d-170">**SNMP 응용 프로그램을 사용 하 여 비즈니스용 Skype 클라이언트 MAC 주소를 포트 및 스위치 식별자와 일치 시키는가?**</span><span class="sxs-lookup"><span data-stu-id="e067d-170">**Will you use an SNMP application to match Skype for Business client MAC addresses to port and switch identifiers?**</span></span>

<span data-ttu-id="e067d-171">SNMP 응용 프로그램을 사용 하는 경우 SNMP 응용 프로그램과 위치 데이터베이스 간에 스위치 섀시 및 포트 정보를 일관성 있게 유지 하는 수동 프로세스를 개발 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-171">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="e067d-172">SNMP 응용 프로그램이 데이터베이스에 포함 되지 않은 섀시 IP 주소나 포트 ID를 반환 하는 경우 위치 정보 서비스에서 클라이언트에 대 한 위치를 반환할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e067d-172">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>


