---
title: 'Lync Server 2013: 게이트웨이에서 ELIN 대 한 위치 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing locations for ELIN gateways
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48185496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b447a150a48255a04e5a332cc5d0f56110848f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a><span data-ttu-id="5fd9d-102">Lync Server 2013의 게이트웨이에서 ELIN 대 한 위치 관리</span><span class="sxs-lookup"><span data-stu-id="5fd9d-102">Managing locations for ELIN gateways in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fd9d-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5fd9d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5fd9d-104">Lync Server에서 네트워크 내의 클라이언트에 대 한 위치를 자동으로 제공 하도록 하려면 다음 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-104">To have Lync Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

  - <span data-ttu-id="5fd9d-105">네트워크 wiremap 매핑으로 위치 정보 서비스 데이터베이스를 채우고 CompanyName 필드에 비상 위치 Id 번호 (ELINs)를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-105">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

  - <span data-ttu-id="5fd9d-106">네트워크의 클라이언트에서 사용할 수 있도록 위치를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-106">Publish the locations so that they are available for clients in your network.</span></span>

  - <span data-ttu-id="5fd9d-107">PSTN (공개 교환 전화 네트워크)의 ALI (자동 위치 확인) 데이터베이스에 ELINs을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-107">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="5fd9d-108">이러한 작업을 수행 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 위치 데이터베이스 구성을](lync-server-2013-configure-the-location-database.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-108">For details about how to perform these tasks, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5fd9d-109">중앙 위치 데이터베이스에 추가 된 위치는 Lync Server Management Shell 명령을 사용 하 여 게시 되거나 풀의 로컬 저장소에 복제 될 때까지 클라이언트에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-109">Locations added to the central location database are not available to the client until they have been published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="5fd9d-110">자세한 내용은 배포 설명서의 <A href="lync-server-2013-publish-the-location-database.md">Lync Server 2013에서 위치 데이터베이스 게시</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-110">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="5fd9d-111">이 섹션에서는 위치 데이터베이스를 업데이트 하 고 유지 관리 하는 데 고려해 야 할 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-111">This section describes things to consider as you plan to update and maintain the location database.</span></span>

<div>

## <a name="planning-emergency-locations"></a><span data-ttu-id="5fd9d-112">응급 위치 계획</span><span class="sxs-lookup"><span data-stu-id="5fd9d-112">Planning Emergency Locations</span></span>

<span data-ttu-id="5fd9d-113">게이트웨이에서 ELIN 사용 하는 경우 위치 정보 서비스 데이터베이스를 도심 주소, 건물 내의 특정 위치, 각 위치에 대해 하나 이상의 ELIN으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-113">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="5fd9d-114">계획 단계에서는 위치의 이름을 지정할 방법과 ELINs을 지정 하는 방법을 결정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-114">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

<div>

## <a name="planning-location-names"></a><span data-ttu-id="5fd9d-115">계획 위치 이름</span><span class="sxs-lookup"><span data-stu-id="5fd9d-115">Planning Location Names</span></span>

<span data-ttu-id="5fd9d-116">위치 정보 서비스 **위치** 필드에는 건물 내의 특정 위치가 포함 되며, 최대 길이는 20 자 (공백 포함)입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-116">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="5fd9d-117">제한 된 길이 내에 다음을 포함 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-117">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="5fd9d-118">응급 응답 자가 도심 주소에 도착할 때 바로 특정 위치를 찾을 수 있도록 911 발신자의 위치를 식별 하는 이해 하기 쉬운 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-118">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address.</span></span> <span data-ttu-id="5fd9d-119">이 위치 이름에는 건물 번호, 바닥 번호, 날개 지정자, 방 번호 등이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-119">This location name may include a building number, floor number, wing designator, room number, and so on.</span></span> <span data-ttu-id="5fd9d-120">직원 에게만 알려진 닉네임을 사용 하지 마세요 .이로 인해 비상 응답 자가 잘못 된 위치로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-120">Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="5fd9d-121">사용자의 Lync 클라이언트가 올바른 위치를 선택 했는지 쉽게 확인할 수 있도록 돕는 위치 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-121">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="5fd9d-122">Lync 클라이언트는 검색 된 **위치** 및 **도시** 필드를 해당 머리글에 자동으로 연결 하 여 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-122">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="5fd9d-123">좋은 방법은 각 위치 식별자에 건물의 거리를 추가 하는 것입니다 (예: "1 층 \<거리 번호\>").</span><span class="sxs-lookup"><span data-stu-id="5fd9d-123">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="5fd9d-124">이 주소가 없으면 "1 층"과 같은 일반적인 위치 식별자가 도시의 모든 건물에 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-124">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="5fd9d-125">위치가 무선 액세스 포인트로 결정 되기 때문에 근사값 인 경우에는 근처에 단어를 추가할 수 있습니다 (예: "가까운 1 층 1234").</span><span class="sxs-lookup"><span data-stu-id="5fd9d-125">If the location is approximate because it’s determined by a wireless access point, you may want to add the word Near (for example, "Near 1st Floor 1234").</span></span>

</div>

<div>

## <a name="planning-elins"></a><span data-ttu-id="5fd9d-126">ELINs</span><span class="sxs-lookup"><span data-stu-id="5fd9d-126">Planning ELINs</span></span>

<span data-ttu-id="5fd9d-127">건물 공간을 위치로 나누는 방법을 결정 한 후에는 각 위치에 할당할 ELINs의 수를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-127">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location.</span></span> <span data-ttu-id="5fd9d-128">예를 들어 multifloor 또는 다중 테 넌 트 빌드에서는 건물의 다른 영역에 다른 긴급 영역을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-128">For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones.</span></span> <span data-ttu-id="5fd9d-129">일반적으로 건물의 각 층은 위치로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-129">Typically, each floor in a building is designated as a location.</span></span> <span data-ttu-id="5fd9d-130">그런 다음, 긴급 통화 중에 전화 번호로 사용 되는 하나 이상의 ELINs을 각 위치에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-130">Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call.</span></span> <span data-ttu-id="5fd9d-131">ELINs에 사용할 수 있는 전화 번호는 PSTN 통신 회사에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-131">Contact your PSTN carrier for phone numbers that you can use for ELINs.</span></span> <span data-ttu-id="5fd9d-132">다음 표에서는 특정 주소에 대 한 위치의 예를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-132">The following table provides an example of locations for a specific street address.</span></span>

### <a name="sample-location-and-elin-assignments"></a><span data-ttu-id="5fd9d-133">과제에 대 한 예제 위치 및 ELIN</span><span class="sxs-lookup"><span data-stu-id="5fd9d-133">Sample Location and ELIN Assignments</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fd9d-134">건물 면적</span><span class="sxs-lookup"><span data-stu-id="5fd9d-134">Building Area</span></span></th>
<th><span data-ttu-id="5fd9d-135">위치</span><span class="sxs-lookup"><span data-stu-id="5fd9d-135">Location</span></span></th>
<th><span data-ttu-id="5fd9d-136">ELIN</span><span class="sxs-lookup"><span data-stu-id="5fd9d-136">ELIN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fd9d-137">1 층</span><span class="sxs-lookup"><span data-stu-id="5fd9d-137">First floor</span></span></p></td>
<td><p><span data-ttu-id="5fd9d-138">1</span><span class="sxs-lookup"><span data-stu-id="5fd9d-138">1</span></span></p></td>
<td><p><span data-ttu-id="5fd9d-139">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="5fd9d-139">425-555-0100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fd9d-140">2 층</span><span class="sxs-lookup"><span data-stu-id="5fd9d-140">Second floor</span></span></p></td>
<td><p><span data-ttu-id="5fd9d-141">2</span><span class="sxs-lookup"><span data-stu-id="5fd9d-141">2</span></span></p></td>
<td><p><span data-ttu-id="5fd9d-142">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="5fd9d-142">425-555-0111</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fd9d-143">세 번째 층</span><span class="sxs-lookup"><span data-stu-id="5fd9d-143">Third floor</span></span></p></td>
<td><p><span data-ttu-id="5fd9d-144">3</span><span class="sxs-lookup"><span data-stu-id="5fd9d-144">3</span></span></p></td>
<td><p><span data-ttu-id="5fd9d-145">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="5fd9d-145">425-555-0123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5fd9d-146">정의한 위치는 다음 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-146">The locations you define should meet the following requirements:</span></span>

  - <span data-ttu-id="5fd9d-147">지역 및 국가/지역 규정에 대 한 각 위치 당 최대 영역과 해당 주소에 대 한 위치 수를 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-147">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

  - <span data-ttu-id="5fd9d-148">는 긴급 전화 발신자를 쉽게 찾을 수 있도록 충분히 특별 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-148">Are specific enough to make it easy to locate the emergency caller.</span></span>

</div>

</div>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="5fd9d-149">위치 데이터베이스 채우기</span><span class="sxs-lookup"><span data-stu-id="5fd9d-149">Populating the Location Database</span></span>

<span data-ttu-id="5fd9d-150">다음 질문은 위치 데이터베이스를 채우는 방법을 결정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-150">The following questions will help you determine how to will populate the location database.</span></span>

  - <span data-ttu-id="5fd9d-151">**위치 데이터베이스를 채우는 데 어떤 프로세스를 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="5fd9d-151">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="5fd9d-152">데이터는 어디에 있으며 데이터를 위치 데이터베이스에서 요구 하는 형식으로 변환 하기 위해 수행 해야 하는 단계는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="5fd9d-152">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database?</span></span> <span data-ttu-id="5fd9d-153">CSV 파일을 사용 하 여 개별적으로 또는 대량으로 위치를 추가 하나요?</span><span class="sxs-lookup"><span data-stu-id="5fd9d-153">Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="5fd9d-154">**위치 매핑이 이미 포함 되어 있는 타사 데이터베이스를 사용 하 고 있나요?**</span><span class="sxs-lookup"><span data-stu-id="5fd9d-154">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="5fd9d-155">타사 데이터베이스에 연결 하기 위해 Lync 서버의 보조 위치 정보 서비스 옵션을 사용 하면 오프 라인 플랫폼을 사용 하 여 위치를 그룹화 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-155">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="5fd9d-156">이 방법의 장점은 위치를 네트워크 식별자와 연결 하는 것 외에 위치를 사용자와 연결할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-156">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="5fd9d-157">즉, 위치 정보 서비스는 보조 위치 정보 서비스에서 가져온 여러 주소를 Lync Server 클라이언트로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-157">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="5fd9d-158">그러면 사용자가 가장 적합 한 위치를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-158">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="5fd9d-159">위치 정보 서비스와 통합 하려면 타사 데이터베이스가 Lync 서버 위치 요청/응답 스키마를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-159">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="5fd9d-160">자세한 내용은을 참조 <http://go.microsoft.com/fwlink/p/?linkid=213819>하세요.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-160">For details, see <http://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="5fd9d-161">보조 위치 정보 서비스 배포에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 보조 위치 정보 서비스 구성을](lync-server-2013-configure-a-secondary-location-information-service.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-161">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="5fd9d-162">위치 데이터베이스를 채우는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 위치 데이터베이스 구성을](lync-server-2013-configure-the-location-database.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-162">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="5fd9d-163">위치 데이터베이스 유지 관리</span><span class="sxs-lookup"><span data-stu-id="5fd9d-163">Maintaining the Location Database</span></span>

<span data-ttu-id="5fd9d-164">위치 데이터베이스를 채운 후에는 네트워크 구성 변경으로 데이터베이스를 업데이트 하기 위한 전략을 개발 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-164">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes.</span></span> <span data-ttu-id="5fd9d-165">다음 질문은 위치 데이터베이스를 유지 관리 하는 방법을 결정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-165">The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="5fd9d-166">**위치 데이터베이스를 업데이트 하는 방법은 무엇 인가요?**</span><span class="sxs-lookup"><span data-stu-id="5fd9d-166">**How will you update the location database?**</span></span>  
    <span data-ttu-id="5fd9d-167">위치 데이터베이스에 업데이트 해야 하는 몇 가지 시나리오는 WAPs (무선 액세스 지점), office recabling 추가 (다른 전환 지정) 및 서브넷 확장을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-167">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="5fd9d-168">각각의 개별 위치를 직접 업데이트 하거나 CSV 파일을 사용 하 여 모든 위치의 대량 업데이트를 수행할지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-168">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="5fd9d-169">**Lync 클라이언트 MAC 주소와 포트 및 스위치 식별자를 비교 하는 데 SNMP 응용 프로그램을 사용 하나요?**</span><span class="sxs-lookup"><span data-stu-id="5fd9d-169">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="5fd9d-170">SNMP 응용 프로그램을 사용 하는 경우 SNMP 응용 프로그램과 위치 데이터베이스 간에 스위치 섀시 및 포트 정보를 일관성 있게 유지 하는 수동 프로세스를 개발 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-170">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="5fd9d-171">SNMP 응용 프로그램이 데이터베이스에 포함 되지 않은 섀시 IP 주소나 포트 ID를 반환 하는 경우 위치 정보 서비스에서 클라이언트에 대 한 위치를 반환할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fd9d-171">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

