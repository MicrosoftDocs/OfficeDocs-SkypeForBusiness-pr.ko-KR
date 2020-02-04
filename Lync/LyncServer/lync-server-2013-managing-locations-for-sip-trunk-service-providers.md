---
title: 'Lync Server 2013: SIP 트렁크 서비스 공급자의 위치 관리'
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
ms.openlocfilehash: e9ebc471459c8e406914f5a075d7e4cf8b69fadd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a><span data-ttu-id="e3e6c-102">Lync Server 2013에서 SIP 트렁크 서비스 공급자의 위치 관리</span><span class="sxs-lookup"><span data-stu-id="e3e6c-102">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3e6c-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e3e6c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e3e6c-104">네트워크 내에서 클라이언트를 자동으로 찾기 위해 Lync Server를 구성 하려면 네트워크 wiremap 매핑 및 위치 게시를 사용 하 여 위치 정보 서비스 데이터베이스를 채우고 올바른 파일이 이미 포함 된 외부 데이터베이스에 연결 해야 합니다. 매핑에서.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-104">To configure Lync Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="e3e6c-105">이 프로세스의 일환으로, E9-1-1 서비스 공급자를 사용 하 여 위치의 도심 주소에 대 한 유효성을 검사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-105">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="e3e6c-106">자세한 내용은 배포 설명서의 [Lync Server 2013에서 위치 데이터베이스 구성을](lync-server-2013-configure-the-location-database.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-106">For details, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e3e6c-107">위치 정보 서비스 데이터베이스를 ERL (긴급 응답 위치)로 채우면 도시 주소와 건물 내의 특정 주소로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-107">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="e3e6c-108">위치 정보 서비스 **위치** 필드 (건물 내의 특정 위치)는 최대 길이가 20 자 (공백 포함)입니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-108">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="e3e6c-109">제한 된 길이 내에 다음을 포함 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-109">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="e3e6c-110">응급 응답 자가 도심 주소에 도착할 때 바로 특정 위치를 찾을 수 있도록 911 발신자의 위치를 식별 하는 이해 하기 쉬운 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-110">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address.</span></span> <span data-ttu-id="e3e6c-111">이 위치 이름에는 건물 번호, 바닥 번호, 날개 지정자, 방 번호 등이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-111">This location name may include a building number, floor number, wing designator, room number, and so on.</span></span> <span data-ttu-id="e3e6c-112">사람만 사용할 수 있는 애칭을 사용 하지 마세요 .이로 인해 비상 응답 자가 잘못 된 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-112">Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="e3e6c-113">사용자의 Lync 클라이언트가 올바른 위치를 선택 했는지 쉽게 확인할 수 있도록 돕는 위치 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-113">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="e3e6c-114">Lync 클라이언트는 검색 된 **위치** 및 **도시** 필드를 해당 머리글에 자동으로 연결 하 여 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-114">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="e3e6c-115">좋은 방법은 각 위치 식별자에 건물의 거리를 추가 하는 것입니다 (예: "1 층 \<거리 번호\>").</span><span class="sxs-lookup"><span data-stu-id="e3e6c-115">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="e3e6c-116">이 주소가 없으면 "1 층"과 같은 일반적인 위치 식별자가 도시의 모든 건물에 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-116">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="e3e6c-117">위치가 무선 액세스 지에 따라 결정 되는 근사치 인 경우에는 근처에 단어를 추가할 수 있습니다 (예: "가까운 1 층 1234").</span><span class="sxs-lookup"><span data-stu-id="e3e6c-117">If the location is approximate because it’s determined by a wireless access point, you can add the word Near (for example, "Near 1st Floor 1234").</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e3e6c-118">중앙 위치 데이터베이스에 추가 된 위치는 Lync Server Management Shell 명령을 사용 하 여 게시 하 고 풀의 로컬 저장소에 복제 될 때까지 클라이언트에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-118">Locations added to the central location database are not available to the client until they are published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="e3e6c-119">자세한 내용은 배포 설명서의 <A href="lync-server-2013-publish-the-location-database.md">Lync Server 2013에서 위치 데이터베이스 게시</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-119">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="e3e6c-120">다음 섹션에서는 위치 데이터베이스를 채우고 유지 관리 하기 위해 고려해 야 할 고려 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-120">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="e3e6c-121">위치 데이터베이스 채우기</span><span class="sxs-lookup"><span data-stu-id="e3e6c-121">Populating the Location Database</span></span>

<span data-ttu-id="e3e6c-122">다음 질문은 위치 데이터베이스를 채우는 방법을 결정 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-122">The following questions can help you determine how to populate the location database.</span></span>

  - <span data-ttu-id="e3e6c-123">**위치 데이터베이스를 채우는 데 어떤 프로세스를 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e3e6c-123">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="e3e6c-124">데이터는 어디에 있으며 데이터를 위치 데이터베이스에서 요구 하는 형식으로 변환 하기 위해 수행 해야 하는 단계는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="e3e6c-124">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database?</span></span> <span data-ttu-id="e3e6c-125">CSV 파일을 사용 하 여 개별적으로 또는 대량으로 위치를 추가 하나요?</span><span class="sxs-lookup"><span data-stu-id="e3e6c-125">Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="e3e6c-126">**위치 매핑이 이미 포함 되어 있는 타사 데이터베이스를 사용 하 고 있나요?**</span><span class="sxs-lookup"><span data-stu-id="e3e6c-126">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="e3e6c-127">타사 데이터베이스에 연결 하기 위해 Lync 서버의 보조 위치 정보 서비스 옵션을 사용 하면 오프 라인 플랫폼을 사용 하 여 위치를 그룹화 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-127">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="e3e6c-128">이 방법의 장점은 위치를 네트워크 식별자와 연결 하는 것 외에 위치를 사용자와 연결할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-128">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="e3e6c-129">즉, 위치 정보 서비스는 보조 위치 정보 서비스에서 가져온 여러 주소를 Lync Server 클라이언트로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-129">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="e3e6c-130">그러면 사용자가 가장 적합 한 위치를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-130">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="e3e6c-131">위치 정보 서비스와 통합 하려면 타사 데이터베이스가 Lync 서버 위치 요청/응답 스키마를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-131">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="e3e6c-132">자세한 내용은에서\[\] <http://go.microsoft.com/fwlink/p/?linkid=213819>"E911WS: E911 지원 프로토콜 사양에 대 한 웹 서비스"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-132">For details, see "\[MS-E911WS\]: Web Service for E911 Support Protocol Specification" at <http://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="e3e6c-133">보조 위치 정보 서비스 배포에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 보조 위치 정보 서비스 구성을](lync-server-2013-configure-a-secondary-location-information-service.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-133">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="e3e6c-134">위치 데이터베이스를 채우는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 위치 데이터베이스 구성을](lync-server-2013-configure-the-location-database.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-134">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="e3e6c-135">위치 데이터베이스 유지 관리</span><span class="sxs-lookup"><span data-stu-id="e3e6c-135">Maintaining the Location Database</span></span>

<span data-ttu-id="e3e6c-136">위치 데이터베이스를 채운 후에는 네트워크 구성 변경으로 데이터베이스를 업데이트 하기 위한 전략을 개발 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-136">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes.</span></span> <span data-ttu-id="e3e6c-137">다음 질문은 위치 데이터베이스를 유지 관리 하는 방법을 결정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-137">The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="e3e6c-138">**위치 데이터베이스를 업데이트 하는 방법은 무엇 인가요?**</span><span class="sxs-lookup"><span data-stu-id="e3e6c-138">**How will you update the location database?**</span></span>  
    <span data-ttu-id="e3e6c-139">위치 데이터베이스에 대 한 업데이트가 필요한 몇 가지 시나리오에는 WAPs, office recabling 추가 (다른 전환 지정) 및 서브넷 확장이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-139">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="e3e6c-140">각각의 개별 위치를 직접 업데이트 하거나 CSV 파일을 사용 하 여 모든 위치의 대량 업데이트를 수행할지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-140">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="e3e6c-141">**Lync 클라이언트 MAC 주소와 포트 및 스위치 식별자를 비교 하는 데 SNMP 응용 프로그램을 사용 하나요?**</span><span class="sxs-lookup"><span data-stu-id="e3e6c-141">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="e3e6c-142">SNMP 응용 프로그램을 사용 하는 경우 SNMP 응용 프로그램과 위치 데이터베이스 간에 스위치 섀시 및 포트 정보를 일관성 있게 유지 하는 수동 프로세스를 개발 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-142">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="e3e6c-143">SNMP 응용 프로그램이 데이터베이스에 포함 되지 않은 섀시 IP 주소나 포트 ID를 반환 하는 경우 위치 정보 서비스에서 클라이언트에 대 한 위치를 반환할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3e6c-143">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

