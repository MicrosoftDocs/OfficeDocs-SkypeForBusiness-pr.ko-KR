---
title: 비즈니스용 Skype 서버에서 ELIN 게이트웨이 위치 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: 비즈니스용 Skype 서버의 E9-1-1 게이트웨이를 사용하는 E9-1-1 배포에 대해 위치 정보 데이터베이스 또는 유사한 외부 데이터베이스를 계획하는 데 Enterprise Voice.
ms.openlocfilehash: 387b94ca59ef7750a80d06c88b371a0afef9313d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834398"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a><span data-ttu-id="67cd4-103">비즈니스용 Skype 서버에서 ELIN 게이트웨이 위치 관리</span><span class="sxs-lookup"><span data-stu-id="67cd4-103">Manage locations for ELIN gateways in Skype for Business Server</span></span>

<span data-ttu-id="67cd4-104">비즈니스용 Skype 서버의 E9-1-1 게이트웨이를 사용하는 E9-1-1 배포에 대해 위치 정보 데이터베이스 또는 유사한 외부 데이터베이스를 계획하는 데 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="67cd4-104">Decisions necessary for planning an the location information database, or a similar external database, for an E9-1-1 deployment using ELIN gateways, in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="67cd4-105">비즈니스용 Skype 서버에서 네트워크 내의 클라이언트에 대한 위치를 자동으로 제공하려면 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-105">To have Skype for Business Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

- <span data-ttu-id="67cd4-106">네트워크 와이어맵으로 위치 정보 서비스 데이터베이스를 채우고 CompanyName 필드에 LINS(Emergency Location Identification Numbers)를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-106">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

- <span data-ttu-id="67cd4-107">네트워크의 클라이언트에서 사용할 수 있도록 위치를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-107">Publish the locations so that they are available for clients in your network.</span></span>

- <span data-ttu-id="67cd4-108">PSTN(Public Switched Telephone Network) 통신사 ALI(자동 위치 식별) 데이터베이스에 ELIN을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-108">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="67cd4-109">이러한 작업을 수행하는 방법에 대한 자세한 [](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) 내용은 배포 설명서에서 위치 데이터베이스 구성을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="67cd4-109">For details about how to perform these tasks, see [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="67cd4-110">중앙 위치 데이터베이스에 추가된 위치는 비즈니스용 Skype 서버 관리 셸 명령을 사용하여 게시하고 풀의 로컬 저장소로 복제될 때까지 클라이언트에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-110">Locations added to the central location database are not available to the client until they have been published by using a Skype for Business Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="67cd4-111">자세한 내용은 배포 설명서에서 [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="67cd4-111">For details, see [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) in the Deployment documentation.</span></span>

<span data-ttu-id="67cd4-112">이 섹션에서는 위치 데이터베이스를 업데이트 및 유지 관리하기 위해 계획할 때 고려해야 할 작업들을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-112">This section describes things to consider as you plan to update and maintain the location database.</span></span>

## <a name="planning-emergency-locations"></a><span data-ttu-id="67cd4-113">응급 위치 계획</span><span class="sxs-lookup"><span data-stu-id="67cd4-113">Planning Emergency Locations</span></span>

<span data-ttu-id="67cd4-114">ELIN 게이트웨이를 사용하는 경우 위치 정보 서비스 데이터베이스를 구민 주소, 건물 내의 특정 위치 및 각 위치에 대해 하나 이상의 ELIN으로 채우게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-114">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="67cd4-115">계획 단계에서는 위치 이름을 지정할 방법과 LINS를 할당할 방법을 결정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-115">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

### <a name="planning-location-names"></a><span data-ttu-id="67cd4-116">위치 이름 계획</span><span class="sxs-lookup"><span data-stu-id="67cd4-116">Planning Location Names</span></span>

<span data-ttu-id="67cd4-117">건물 내의  특정 위치를 보유하는 위치 정보 서비스 위치 필드는 최대 20자(공백 포함)입니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-117">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="67cd4-118">이 제한 길이 내에서 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-118">Within that limited length, try to include the following:</span></span>

- <span data-ttu-id="67cd4-119">911 발신자 위치를 식별하여 응급 응답자가 구민 주소에 도착할 때 특정 위치를 즉시 찾을 수 있도록 하는 쉽게 이해할 수 있는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-119">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address.</span></span> <span data-ttu-id="67cd4-120">이 위치 이름에는 건물 번호, 바닥 번호, 날개 지정자, 방 번호가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-120">This location name may include a building number, floor number, wing designator, room number, and so on.</span></span> <span data-ttu-id="67cd4-121">직원에게만 알려진 별명을 피하여 응급 응답자는 잘못된 위치로 이동하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-121">Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

- <span data-ttu-id="67cd4-122">사용자가 클라이언트가 올바른 위치를 선택했다는 것이 쉽게 확인될 수 있도록 하는 위치 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-122">A location identifier that helps users to easily see that their client picked up the correct location.</span></span> <span data-ttu-id="67cd4-123">비즈니스용 Skype 클라이언트는 헤더에 검색된 위치  및  도시 필드를 자동으로 연결하고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-123">The Skype for Business client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="67cd4-124">각 위치 식별자에 건물의 주소(예: "1층")를 추가하는 것이 <street number> 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-124">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor <street number>").</span></span> <span data-ttu-id="67cd4-125">번지를 사용하지 않을 경우 "1층"과 같은 일반 위치 식별자를 도시의 모든 건물에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-125">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

- <span data-ttu-id="67cd4-126">위치가 무선 액세스 지점에 의해 결정되어 근사치인 경우 **[Near]이라는** 단어를 추가할 수 있습니다(예: "1층 1234 근처").</span><span class="sxs-lookup"><span data-stu-id="67cd4-126">If the location is approximate because it's determined by a wireless access point, you may want to add the word **[Near]** (for example, "Near 1st Floor 1234").</span></span>

### <a name="planning-elins"></a><span data-ttu-id="67cd4-127">ELINS 계획</span><span class="sxs-lookup"><span data-stu-id="67cd4-127">Planning ELINs</span></span>

<span data-ttu-id="67cd4-128">건물 공간을 위치로 나누는 방법을 결정한 후 각 위치에 할당할 LIEN 수를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-128">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location.</span></span> <span data-ttu-id="67cd4-129">예를 들어 다층 건물이나 다중테니타 건물의 경우 건물의 각 영역에 서로 다른 응급 영역이 할당될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-129">For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones.</span></span> <span data-ttu-id="67cd4-130">일반적으로 건물의 각 층은 위치로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-130">Typically, each floor in a building is designated as a location.</span></span> <span data-ttu-id="67cd4-131">그런 다음 각 위치에는 긴급 통화 중 전화 번호로 사용되는 하나 이상의 LINS가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-131">Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call.</span></span> <span data-ttu-id="67cd4-132">ELIN에 사용할 수 있는 전화 번호는 PSTN 통신사에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-132">Contact your PSTN carrier for phone numbers that you can use for ELINs.</span></span> <span data-ttu-id="67cd4-133">다음 표에서는 특정 주소의 위치 예를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-133">The following table provides an example of locations for a specific street address.</span></span>

<span data-ttu-id="67cd4-134">**샘플 위치 및 ELIN 할당**</span><span class="sxs-lookup"><span data-stu-id="67cd4-134">**Sample Location and ELIN Assignments**</span></span>

|<span data-ttu-id="67cd4-135">**건물 영역**</span><span class="sxs-lookup"><span data-stu-id="67cd4-135">**Building Area**</span></span>|<span data-ttu-id="67cd4-136">**위치**</span><span class="sxs-lookup"><span data-stu-id="67cd4-136">**Location**</span></span>|<span data-ttu-id="67cd4-137">**ELIN**</span><span class="sxs-lookup"><span data-stu-id="67cd4-137">**ELIN**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="67cd4-138">1층</span><span class="sxs-lookup"><span data-stu-id="67cd4-138">First floor</span></span>  <br/> |<span data-ttu-id="67cd4-139">1 </span><span class="sxs-lookup"><span data-stu-id="67cd4-139">1</span></span>  <br/> |<span data-ttu-id="67cd4-140">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="67cd4-140">425-555-0100</span></span>  <br/> |
|<span data-ttu-id="67cd4-141">2층</span><span class="sxs-lookup"><span data-stu-id="67cd4-141">Second floor</span></span>  <br/> |<span data-ttu-id="67cd4-142">2 </span><span class="sxs-lookup"><span data-stu-id="67cd4-142">2</span></span>  <br/> |<span data-ttu-id="67cd4-143">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="67cd4-143">425-555-0111</span></span>  <br/> |
|<span data-ttu-id="67cd4-144">3층</span><span class="sxs-lookup"><span data-stu-id="67cd4-144">Third floor</span></span>  <br/> |<span data-ttu-id="67cd4-145">3 </span><span class="sxs-lookup"><span data-stu-id="67cd4-145">3</span></span>  <br/> |<span data-ttu-id="67cd4-146">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="67cd4-146">425-555-0123</span></span>  <br/> |

<span data-ttu-id="67cd4-147">정의하는 위치는 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-147">The locations you define should meet the following requirements:</span></span>

- <span data-ttu-id="67cd4-148">위치당 최대 영역 및 주소당 위치 수와 관련한 현지 및 국가/지역 규정을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-148">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

- <span data-ttu-id="67cd4-149">긴급 발신자 위치를 쉽게 찾을 수 있을 만큼 구체적입니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-149">Are specific enough to make it easy to locate the emergency caller.</span></span>

## <a name="populating-the-location-database"></a><span data-ttu-id="67cd4-150">위치 데이터베이스 채우기</span><span class="sxs-lookup"><span data-stu-id="67cd4-150">Populating the Location Database</span></span>

<span data-ttu-id="67cd4-151">다음 질문은 위치 데이터베이스를 채우는 방법을 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-151">The following questions will help you determine how to will populate the location database.</span></span>

 <span data-ttu-id="67cd4-152">**위치 데이터베이스를 채우는 데 사용할 프로세스는 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="67cd4-152">**What process will you use to populate the location database?**</span></span>

<span data-ttu-id="67cd4-p107">데이터가 어디에 있습니까 그리고 이러한 데이터를 위치 데이터베이스에서 요구하는 형식으로 변환하기 위해 수행해야 할 단계는 무엇입니까? 위치를 CSV 파일을 사용하여 일괄적으로 또는 개별적으로 추가하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="67cd4-p107">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

 <span data-ttu-id="67cd4-155">**위치 매핑이 이미 포함된 타사 데이터베이스가 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="67cd4-155">**Do you have a third party database that already contains a mapping of locations?**</span></span>

<span data-ttu-id="67cd4-156">보조 위치 정보 서비스 옵션을 사용하여 타사 데이터베이스에 연결하면 오프라인 플랫폼을 사용하여 위치를 그룹화하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-156">By using the Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="67cd4-157">이 방법을 사용하면 위치를 네트워크 식별자에게 연결할 수 있을 뿐만 아니라 사용자에게도 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-157">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="67cd4-158">즉, 위치 정보 서비스는 보조 위치 정보 서비스에서 시작된 여러 주소를 비즈니스용 Skype 클라이언트로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-158">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Skype for Business client.</span></span> <span data-ttu-id="67cd4-159">그러면 사용자는 가장 적합한 위치를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-159">The user can then choose the most appropriate location.</span></span>

<span data-ttu-id="67cd4-160">위치 정보 서비스와 통합하려면 타사 데이터베이스가 비즈니스용 Skype 서버 위치 요청/응답 계획에 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-160">To integrate with the Location Information service, the third-party database must follow the Skype for Business Server Location Request/Response schema.</span></span> <span data-ttu-id="67cd4-161">자세한 내용은 [E911 지원 프로토콜에 대한 웹 서비스를 참조합니다.](https://go.microsoft.com/fwlink/p/?linkid=213819)</span><span class="sxs-lookup"><span data-stu-id="67cd4-161">For details, see [Web Service for E911 Support Protocol](https://go.microsoft.com/fwlink/p/?linkid=213819).</span></span> <span data-ttu-id="67cd4-162">보조 위치 정보 서비스 배포에 대한 자세한 내용은 배포 설명서에서 비즈니스용 [Skype 서버에서](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) 보조 위치 정보 서비스 구성을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="67cd4-162">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="67cd4-163">위치 데이터베이스를 채우는 방법에 대한 자세한 내용은 배포 설명서에서 [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="67cd4-163">For details about populating the location database, see [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="67cd4-164">위치 데이터베이스 유지 관리</span><span class="sxs-lookup"><span data-stu-id="67cd4-164">Maintaining the Location Database</span></span>

<span data-ttu-id="67cd4-p110">위치 데이터베이스를 채우고 나면 네트워크 구성이 변경되므로 데이터베이스를 업데이트하기 위한 전략을 개발해야 합니다. 다음 질문은 위치 데이터베이스를 유지 관리하는 방법을 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-p110">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

 <span data-ttu-id="67cd4-167">**어떤 방법으로 위치 데이터베이스를 업데이트하시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="67cd4-167">**How will you update the location database?**</span></span>

<span data-ttu-id="67cd4-168">WAP(무선 액세스 지점) 추가, Office 다시 사용 안함(서로 다른 스위치 할당 생성) 및 서브넷 확장을 포함하여 위치 데이터베이스를 업데이트해야 하는 몇 가지 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-168">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="67cd4-169">각 개별 위치를 직접 업데이트하시겠습니까 아니면 CSV 파일을 사용하여 모든 위치를 일괄적으로 업데이트하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="67cd4-169">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

 <span data-ttu-id="67cd4-170">**SNMP 응용 프로그램을 사용하여 비즈니스용 Skype 클라이언트 MAC 주소를 포트 및 스위치 식별자에 일치시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="67cd4-170">**Will you use an SNMP application to match Skype for Business client MAC addresses to port and switch identifiers?**</span></span>

<span data-ttu-id="67cd4-171">SNMP 응용 프로그램을 사용할 경우 SNMP 응용 프로그램과 위치 데이터베이스 간 포트 및 스위치 정보를 일치시키기 위한 수동 프로세스를 개발해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-171">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="67cd4-172">SNMP 응용 프로그램에서 데이터베이스에 포함되지 않은 섀시 IP 주소 또는 포트 ID를 반환하면 위치 정보 서비스에서 클라이언트로 위치를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67cd4-172">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>


