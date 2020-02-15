---
title: 'Lync Server 2013: SIP 트렁크 서비스 공급자 위치 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2ffa9b16a2c582af2de990eab52b55c175121bc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a><span data-ttu-id="787bd-102">Lync Server 2013에서 SIP 트렁크 서비스 공급자 위치 관리</span><span class="sxs-lookup"><span data-stu-id="787bd-102">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="787bd-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="787bd-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="787bd-104">네트워크 내의 클라이언트를 자동으로 찾도록 Lync Server를 구성 하려면 위치 정보 서비스 데이터베이스를 네트워크 와이어 맵 매핑 및 게시 하거나, 해당 위치를 게시할 수 있는 외부 데이터베이스에 연결 해야 합니다. 매핑.</span><span class="sxs-lookup"><span data-stu-id="787bd-104">To configure Lync Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="787bd-105">이 프로세스의 일부로, E9-1-1 서비스 공급자를 통해 구/군/시 주소를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-105">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="787bd-106">자세한 내용은 배포 설명서에서 [Lync Server 2013의 Configure the location database](lync-server-2013-configure-the-location-database.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="787bd-106">For details, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<span data-ttu-id="787bd-107">위치 정보 서비스 데이터베이스를 건물의 구/군/시 주소와 특정 주소로 구성된 ERL(비상 응답 위치)로 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-107">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="787bd-108">건물 내에서 특정 위치에 해당 하는 위치 정보 서비스 **위치** 필드의 최대 길이는 20 자입니다 (공백 포함).</span><span class="sxs-lookup"><span data-stu-id="787bd-108">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="787bd-109">이 제한 길이 내에서 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-109">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="787bd-p103">119 발신자 위치를 식별하는 알기 쉬운 이름으로 비상 응답자가 구/군/시 주소에 도착하자 마자 특정 위치를 찾을 수 있도록 도와줍니다. 이 위치 이름에는 건물 번호, 층, 윙 지정자, 호수 등이 포함될 수 있습니다. 직원만 알고 있는 별칭은 가급적 사용하지 마십시오. 이러한 이름은 비상 응답자를 잘못된 위치로 이동시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-p103">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="787bd-113">Lync 클라이언트가 정확한 위치를 선택했는지 사용자가 쉽게 알 수 있도록 하는 위치 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-113">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="787bd-114">Lync 클라이언트가 헤더에서 검색된 **Location** 및 **City** 필드를 자동으로 연결하여 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-114">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="787bd-115">건물의 주소를 각 위치 식별자 (예: "1 층 \<거리 번호\>")로 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-115">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="787bd-116">번지를 사용하지 않을 경우 "1층"과 같은 일반 위치 식별자를 도시의 모든 건물에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-116">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="787bd-117">위치가 무선 액세스 지점에 의해 결정되기 때문에 정확하지 위치가 아니라 대략적인 위치인 경우 Near(예: "1층 1234 근거리")라는 단어를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-117">If the location is approximate because it’s determined by a wireless access point, you can add the word Near (for example, "Near 1st Floor 1234").</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="787bd-118">중앙 위치 데이터베이스에 추가 된 위치는 Lync Server 관리 셸 명령을 사용 하 여 게시 하 고 풀의 로컬 저장소에 복제 되기 전 까지는 클라이언트에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-118">Locations added to the central location database are not available to the client until they are published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="787bd-119">자세한 내용은 배포 설명서의 " <A href="lync-server-2013-publish-the-location-database.md">Lync Server 2013에서 위치 데이터베이스 게시</A> "를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="787bd-119">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="787bd-120">다음 섹션에서는 위치 데이터베이스를 채우고 유지 관리할 때 고려해야 할 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-120">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="787bd-121">위치 데이터베이스 채우기</span><span class="sxs-lookup"><span data-stu-id="787bd-121">Populating the Location Database</span></span>

<span data-ttu-id="787bd-122">다음 질문은 위치 데이터베이스를 채우는 방법을 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-122">The following questions can help you determine how to populate the location database.</span></span>

  - <span data-ttu-id="787bd-123">**위치 데이터베이스를 채우는 데 사용할 프로세스는 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="787bd-123">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="787bd-p106">데이터가 어디에 있습니까 그리고 이러한 데이터를 위치 데이터베이스에서 요구하는 형식으로 변환하기 위해 수행해야 할 단계는 무엇입니까? 위치를 CSV 파일을 사용하여 일괄적으로 또는 개별적으로 추가하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="787bd-p106">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="787bd-126">**위치 매핑이 이미 포함된 타사 데이터베이스가 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="787bd-126">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="787bd-127">Lync Server의 보조 위치 정보 서비스 옵션을 사용 하 여 타사 데이터베이스에 연결 하는 방법으로 오프 라인 플랫폼을 사용 하 여 위치를 그룹화 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-127">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="787bd-128">이 방법을 사용하면 위치를 네트워크 식별자에게 연결할 수 있을 뿐만 아니라 사용자에게도 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-128">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="787bd-129">즉, 위치 정보 서비스는 보조 위치 정보 서비스에서 시작 하는 여러 주소를 Lync Server 클라이언트에 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-129">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="787bd-130">그러면 사용자는 가장 적합한 위치를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-130">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="787bd-131">위치 정보 서비스와 통합 하려면 타사 데이터베이스가 Lync Server 위치 요청/응답 스키마를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-131">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="787bd-132">자세한 내용은에서\[\] <http://go.microsoft.com/fwlink/p/?linkid=213819>"E911WS: 웹 서비스 for E911 지원 프로토콜 사양"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="787bd-132">For details, see "\[MS-E911WS\]: Web Service for E911 Support Protocol Specification" at <http://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="787bd-133">보조 위치 정보 서비스를 배포 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013의 구성 a 보조 위치 정보 서비스](lync-server-2013-configure-a-secondary-location-information-service.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="787bd-133">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="787bd-134">위치 데이터베이스를 채우는 방법에 대 한 자세한 내용은 배포 설명서의 [Configure the location database In Lync Server 2013](lync-server-2013-configure-the-location-database.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="787bd-134">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="787bd-135">위치 데이터베이스 유지 관리</span><span class="sxs-lookup"><span data-stu-id="787bd-135">Maintaining the Location Database</span></span>

<span data-ttu-id="787bd-p109">위치 데이터베이스를 채우고 나면 네트워크 구성이 변경되므로 데이터베이스를 업데이트하기 위한 전략을 개발해야 합니다. 다음 질문은 위치 데이터베이스를 유지 관리하는 방법을 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-p109">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="787bd-138">**어떤 방법으로 위치 데이터베이스를 업데이트하시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="787bd-138">**How will you update the location database?**</span></span>  
    <span data-ttu-id="787bd-p110">WAP 추가, 사무실 케이블 재연결(스위치 할당이 달라짐) 및 서브넷 확장 등을 포함하여 위치 데이터베이스를 업데이트해야 하는 몇 가지 시나리오가 있습니다. 각 개별 위치를 직접 업데이트하시겠습니까 아니면 CSV 파일을 사용하여 모든 위치를 일괄적으로 업데이트하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="787bd-p110">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="787bd-141">**SNMP 응용 프로그램을 사용하여 Lync 클라이언트 MAC 주소를 포트 및 스위치 식별자와 일치시키시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="787bd-141">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="787bd-142">SNMP 응용 프로그램을 사용할 경우 SNMP 응용 프로그램과 위치 데이터베이스 간 포트 및 스위치 정보를 일치시키기 위한 수동 프로세스를 개발해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-142">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="787bd-143">SNMP 응용 프로그램이 데이터베이스에 포함 되지 않은 섀시 IP 주소 또는 포트 ID를 반환 하는 경우에는 위치 정보 서비스에서 클라이언트에 대 한 위치를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="787bd-143">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

