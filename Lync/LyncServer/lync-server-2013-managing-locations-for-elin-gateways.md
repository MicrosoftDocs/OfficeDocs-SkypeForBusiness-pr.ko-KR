---
title: 'Lync Server 2013: ELIN 게이트웨이에 대 한 위치 관리'
description: 'Lync Server 2013: ELIN 게이트웨이에 대 한 위치를 관리 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for ELIN gateways
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48185496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94fe7797c0f25adb219512cef4a6c0fb7d84b48d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557484"
---
# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a><span data-ttu-id="4f1f8-103">Lync Server 2013의 ELIN 게이트웨이 위치 관리</span><span class="sxs-lookup"><span data-stu-id="4f1f8-103">Managing locations for ELIN gateways in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f1f8-104">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="4f1f8-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4f1f8-105">Lync Server에서 네트워크 내의 클라이언트 위치를 자동으로 제공 하도록 하려면 다음 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-105">To have Lync Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

  - <span data-ttu-id="4f1f8-106">네트워크 wiremap 매핑 기능을 사용 하 여 위치 정보 서비스 데이터베이스를 채우고 CompanyName 필드에 비상 위치 Id 번호 (ELINs)를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-106">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

  - <span data-ttu-id="4f1f8-107">네트워크의 클라이언트에서 사용할 수 있도록 위치를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-107">Publish the locations so that they are available for clients in your network.</span></span>

  - <span data-ttu-id="4f1f8-108">PSTN (공중 전화망) 캐리어의 ALI (자동 위치 식별) 데이터베이스에 ELINs를 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-108">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="4f1f8-109">이러한 작업을 수행 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Configure the location database In Lync Server 2013](lync-server-2013-configure-the-location-database.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-109">For details about how to perform these tasks, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4f1f8-110">중앙 위치 데이터베이스에 추가 된 위치는 Lync Server 관리 셸 명령을 사용 하 여 게시 하 고 풀의 로컬 저장소로 복제 되기 전 까지는 클라이언트에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-110">Locations added to the central location database are not available to the client until they have been published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="4f1f8-111">자세한 내용은 배포 설명서의 " <A href="lync-server-2013-publish-the-location-database.md">Lync Server 2013에서 위치 데이터베이스 게시</A> "를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-111">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="4f1f8-112">이 섹션에서는 위치 데이터베이스의 업데이트 및 유지 관리를 계획할 때 고려해 야 할 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-112">This section describes things to consider as you plan to update and maintain the location database.</span></span>

<div>

## <a name="planning-emergency-locations"></a><span data-ttu-id="4f1f8-113">응급 위치 계획</span><span class="sxs-lookup"><span data-stu-id="4f1f8-113">Planning Emergency Locations</span></span>

<span data-ttu-id="4f1f8-114">ELIN 게이트웨이를 사용 하는 경우 위치 정보 서비스 데이터베이스를 도심 주소, 건물 내의 특정 위치, 각 위치에 대해 하나 이상의 ELIN으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-114">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="4f1f8-115">계획 단계 중에 위치 이름을 지정 하는 방법과 ELINs를 할당할 방법을 결정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-115">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

<div>

## <a name="planning-location-names"></a><span data-ttu-id="4f1f8-116">위치 이름 계획</span><span class="sxs-lookup"><span data-stu-id="4f1f8-116">Planning Location Names</span></span>

<span data-ttu-id="4f1f8-117">건물 내에서 특정 위치를 보유 하는 위치 정보 서비스 **위치** 필드에는 최대 길이 20 자 (공백 포함)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-117">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="4f1f8-118">이 제한 길이 내에서 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-118">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="4f1f8-119">응급 응답 자가 도심 주소에 도착 했을 때 즉시 특정 위치를 찾을 수 있도록 911 발신자의 위치를 식별 하는 이해 하기 쉬운 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-119">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address.</span></span> <span data-ttu-id="4f1f8-120">이 위치 이름에는 건물 번호, 바닥 번호, 윙 지정자, 방 번호 등이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-120">This location name may include a building number, floor number, wing designator, room number, and so on.</span></span> <span data-ttu-id="4f1f8-121">직원 에게만 알려진 애칭을 사용 하지 않으며,이로 인해 응급 응답 자가 잘못 된 위치로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-121">Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="4f1f8-122">Lync 클라이언트가 정확한 위치를 선택했는지 사용자가 쉽게 알 수 있도록 하는 위치 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-122">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="4f1f8-123">Lync 클라이언트가 헤더에서 검색된 **Location** 및 **City** 필드를 자동으로 연결하여 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-123">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="4f1f8-124">각 위치 식별자 (예: "1 층")에 건물의 주소를 추가 하는 것이 좋습니다 \<street number\> .</span><span class="sxs-lookup"><span data-stu-id="4f1f8-124">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="4f1f8-125">번지를 사용하지 않을 경우 "1층"과 같은 일반 위치 식별자를 도시의 모든 건물에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-125">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="4f1f8-126">무선 액세스 지점에 의해 결정 된 것으로 예상 되는 위치인 경우 근처에 단어를 추가할 수 있습니다 (예: "가까운 1 층 1234").</span><span class="sxs-lookup"><span data-stu-id="4f1f8-126">If the location is approximate because it’s determined by a wireless access point, you may want to add the word Near (for example, "Near 1st Floor 1234").</span></span>

</div>

<div>

## <a name="planning-elins"></a><span data-ttu-id="4f1f8-127">ELINs 계획</span><span class="sxs-lookup"><span data-stu-id="4f1f8-127">Planning ELINs</span></span>

<span data-ttu-id="4f1f8-128">건물 공간을 위치로 나누는 방법을 결정 한 후에는 각 위치에 할당할 ELINs 수를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-128">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location.</span></span> <span data-ttu-id="4f1f8-129">예를 들어 multifloor 또는 다중 테 넌 트 건물에서 건물의 각 영역에 서로 다른 응급 영역을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-129">For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones.</span></span> <span data-ttu-id="4f1f8-130">일반적으로 건물의 각 층은 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-130">Typically, each floor in a building is designated as a location.</span></span> <span data-ttu-id="4f1f8-131">그런 다음 각 위치에는 긴급 통화 중에 통화 번호로 사용 되는 하나 이상의 ELINs가 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-131">Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call.</span></span> <span data-ttu-id="4f1f8-132">ELINs에 사용할 수 있는 전화 번호에 대해서는 PSTN 캐리어에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-132">Contact your PSTN carrier for phone numbers that you can use for ELINs.</span></span> <span data-ttu-id="4f1f8-133">다음 표에서는 특정 주소에 대 한 위치의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-133">The following table provides an example of locations for a specific street address.</span></span>

### <a name="sample-location-and-elin-assignments"></a><span data-ttu-id="4f1f8-134">샘플 위치 및 ELIN 할당</span><span class="sxs-lookup"><span data-stu-id="4f1f8-134">Sample Location and ELIN Assignments</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f1f8-135">건물 면적</span><span class="sxs-lookup"><span data-stu-id="4f1f8-135">Building Area</span></span></th>
<th><span data-ttu-id="4f1f8-136">위치</span><span class="sxs-lookup"><span data-stu-id="4f1f8-136">Location</span></span></th>
<th><span data-ttu-id="4f1f8-137">ELIN</span><span class="sxs-lookup"><span data-stu-id="4f1f8-137">ELIN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f1f8-138">첫 번째 층</span><span class="sxs-lookup"><span data-stu-id="4f1f8-138">First floor</span></span></p></td>
<td><p><span data-ttu-id="4f1f8-139">1 </span><span class="sxs-lookup"><span data-stu-id="4f1f8-139">1</span></span></p></td>
<td><p><span data-ttu-id="4f1f8-140">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="4f1f8-140">425-555-0100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f1f8-141">2 층</span><span class="sxs-lookup"><span data-stu-id="4f1f8-141">Second floor</span></span></p></td>
<td><p><span data-ttu-id="4f1f8-142">2</span><span class="sxs-lookup"><span data-stu-id="4f1f8-142">2</span></span></p></td>
<td><p><span data-ttu-id="4f1f8-143">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="4f1f8-143">425-555-0111</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f1f8-144">3 층</span><span class="sxs-lookup"><span data-stu-id="4f1f8-144">Third floor</span></span></p></td>
<td><p><span data-ttu-id="4f1f8-145">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="4f1f8-145">3</span></span></p></td>
<td><p><span data-ttu-id="4f1f8-146">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="4f1f8-146">425-555-0123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4f1f8-147">정의 하는 위치는 다음 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-147">The locations you define should meet the following requirements:</span></span>

  - <span data-ttu-id="4f1f8-148">위치 당 최대 영역과 지역 규정, 주소 당 위치 수 측면에서 현지 및 국가/지역 규제를 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-148">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

  - <span data-ttu-id="4f1f8-149">긴급 전화 건 사람을 쉽게 찾을 수 있도록 구체적으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-149">Are specific enough to make it easy to locate the emergency caller.</span></span>

</div>

</div>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="4f1f8-150">위치 데이터베이스 채우기</span><span class="sxs-lookup"><span data-stu-id="4f1f8-150">Populating the Location Database</span></span>

<span data-ttu-id="4f1f8-151">다음은 위치 데이터베이스를 채우는 방법을 결정 하는 데 도움이 되는 질문입니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-151">The following questions will help you determine how to will populate the location database.</span></span>

  - <span data-ttu-id="4f1f8-152">**위치 데이터베이스를 채우는 데 사용할 프로세스는 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="4f1f8-152">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="4f1f8-p107">데이터가 어디에 있습니까 그리고 이러한 데이터를 위치 데이터베이스에서 요구하는 형식으로 변환하기 위해 수행해야 할 단계는 무엇입니까? 위치를 CSV 파일을 사용하여 일괄적으로 또는 개별적으로 추가하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="4f1f8-p107">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="4f1f8-155">**위치 매핑이 이미 포함된 타사 데이터베이스가 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="4f1f8-155">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="4f1f8-156">Lync Server의 보조 위치 정보 서비스 옵션을 사용 하 여 타사 데이터베이스에 연결 하는 방법으로 오프 라인 플랫폼을 사용 하 여 위치를 그룹화 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-156">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="4f1f8-157">이 방법을 사용하면 위치를 네트워크 식별자에게 연결할 수 있을 뿐만 아니라 사용자에게도 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-157">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="4f1f8-158">즉, 위치 정보 서비스는 보조 위치 정보 서비스에서 시작 하는 여러 주소를 Lync Server 클라이언트에 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-158">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="4f1f8-159">그러면 사용자는 가장 적합한 위치를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-159">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="4f1f8-160">위치 정보 서비스와 통합 하려면 타사 데이터베이스가 Lync Server 위치 요청/응답 스키마를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-160">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="4f1f8-161">자세한 내용은를 참조 <https://go.microsoft.com/fwlink/p/?linkid=213819> 하세요.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-161">For details, see <https://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="4f1f8-162">보조 위치 정보 서비스를 배포 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013의 구성 a 보조 위치 정보 서비스](lync-server-2013-configure-a-secondary-location-information-service.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-162">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="4f1f8-163">위치 데이터베이스를 채우는 방법에 대 한 자세한 내용은 배포 설명서의 [Configure the location database In Lync Server 2013](lync-server-2013-configure-the-location-database.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-163">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="4f1f8-164">위치 데이터베이스 유지 관리</span><span class="sxs-lookup"><span data-stu-id="4f1f8-164">Maintaining the Location Database</span></span>

<span data-ttu-id="4f1f8-p110">위치 데이터베이스를 채우고 나면 네트워크 구성이 변경되므로 데이터베이스를 업데이트하기 위한 전략을 개발해야 합니다. 다음 질문은 위치 데이터베이스를 유지 관리하는 방법을 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-p110">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="4f1f8-167">**어떤 방법으로 위치 데이터베이스를 업데이트하시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="4f1f8-167">**How will you update the location database?**</span></span>  
    <span data-ttu-id="4f1f8-168">Wap (무선 액세스 지점), office recabling (서로 다른 스위치 할당의 결과) 및 서브넷 확장을 포함 하 여 위치 데이터베이스를 업데이트 해야 하는 몇 가지 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-168">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="4f1f8-169">각 개별 위치를 직접 업데이트하시겠습니까 아니면 CSV 파일을 사용하여 모든 위치를 일괄적으로 업데이트하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="4f1f8-169">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="4f1f8-170">**SNMP 응용 프로그램을 사용하여 Lync 클라이언트 MAC 주소를 포트 및 스위치 식별자와 일치시키시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="4f1f8-170">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="4f1f8-171">SNMP 응용 프로그램을 사용할 경우 SNMP 응용 프로그램과 위치 데이터베이스 간 포트 및 스위치 정보를 일치시키기 위한 수동 프로세스를 개발해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-171">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="4f1f8-172">SNMP 응용 프로그램이 데이터베이스에 포함 되지 않은 섀시 IP 주소 또는 포트 ID를 반환 하는 경우에는 위치 정보 서비스에서 클라이언트에 대 한 위치를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1f8-172">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

