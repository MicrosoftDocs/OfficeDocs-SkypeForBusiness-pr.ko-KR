---
title: 비즈니스용 Skype 서버에서 SIP 트렁크 서비스 공급자의 위치 관리
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
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: SIP 트렁크 공급자를 사용하는 E9-1-1 배포에 대한 위치 정보 데이터베이스 또는 유사한 외부 데이터베이스를 계획하는 데 필요한 결정 사항은 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: 9918fc2cb6bc9d05166d648ab3285a964d15f290
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825438"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a><span data-ttu-id="43ee0-103">비즈니스용 Skype 서버에서 SIP 트렁크 서비스 공급자의 위치 관리</span><span class="sxs-lookup"><span data-stu-id="43ee0-103">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>

<span data-ttu-id="43ee0-104">SIP 트렁크 공급자를 사용하는 E9-1-1 배포에 대한 위치 정보 데이터베이스 또는 유사한 외부 데이터베이스를 계획하는 데 필요한 결정 사항은 비즈니스용 Skype 서버 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="43ee0-104">Decisions necessary for planning an the location information database, or a similar external database, for an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="43ee0-105">비즈니스용 Skype 서버가 네트워크 내에서 클라이언트를 자동으로 찾도록 구성하려면 네트워크 와이어맵으로 위치 정보 서비스 데이터베이스를 채우고 위치를 게시하거나 올바른 매핑이 이미 포함된 외부 데이터베이스에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-105">To configure Skype for Business Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="43ee0-106">이 프로세스의 일부로, E9-1-1 서비스 공급자를 통해 구/군/시 주소를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-106">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="43ee0-107">자세한 내용은 배포 설명서에서 [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="43ee0-107">For details, see [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>

<span data-ttu-id="43ee0-108">위치 정보 서비스 데이터베이스를 건물의 구/군/시 주소와 특정 주소로 구성된 ERL(비상 응답 위치)로 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-108">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="43ee0-109">건물 내의  특정 위치인 위치 정보 서비스 위치 필드는 최대 20자(공백 포함)입니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-109">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="43ee0-110">이 제한 길이 내에서 다음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-110">Within that limited length, try to include the following:</span></span>

- <span data-ttu-id="43ee0-p103">119 발신자 위치를 식별하는 알기 쉬운 이름으로 비상 응답자가 구/군/시 주소에 도착하자 마자 특정 위치를 찾을 수 있도록 도와줍니다. 이 위치 이름에는 건물 번호, 층, 윙 지정자, 호수 등이 포함될 수 있습니다. 직원만 알고 있는 별칭은 가급적 사용하지 마십시오. 이러한 이름은 비상 응답자를 잘못된 위치로 이동시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-p103">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

- <span data-ttu-id="43ee0-114">사용자가 비즈니스용 Skype 클라이언트가 올바른 위치를 선택했다는 것이 쉽게 확인될 수 있도록 하는 위치 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-114">A location identifier that helps users to easily see that their Skype for Business client picked up the correct location.</span></span> <span data-ttu-id="43ee0-115">비즈니스용 Skype 클라이언트는 헤더에 검색된 위치  및  도시 필드를 자동으로 연결하고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-115">The Skype for Business client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="43ee0-116">각 위치 식별자에 건물의 주소(예: "1층")를 추가하는 것이 <street number> 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-116">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor <street number>").</span></span> <span data-ttu-id="43ee0-117">번지를 사용하지 않을 경우 "1층"과 같은 일반 위치 식별자를 도시의 모든 건물에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-117">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

- <span data-ttu-id="43ee0-118">위치가 무선 액세스 지점에 의해 결정되어 근사치인 경우 **[Near]이라는** 단어를 추가할 수 있습니다(예: "1층 1234 근처").</span><span class="sxs-lookup"><span data-stu-id="43ee0-118">If the location is approximate because it's determined by a wireless access point, you can add the word **[Near]** (for example, "Near 1st Floor 1234").</span></span>

> [!NOTE]
> <span data-ttu-id="43ee0-119">중앙 위치 데이터베이스에 추가된 위치는 비즈니스용 Skype 서버 관리 셸 명령을 사용하여 게시하고 풀의 로컬 저장소로 복제될 때까지 클라이언트에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-119">Locations added to the central location database are not available to the client until they are published by using a Skype for Business Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="43ee0-120">자세한 내용은 배포 설명서에서 [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="43ee0-120">For details, see [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) in the Deployment documentation.</span></span>

<span data-ttu-id="43ee0-121">다음 섹션에서는 위치 데이터베이스를 채우고 유지 관리할 때 고려해야 할 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-121">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

## <a name="populating-the-location-database"></a><span data-ttu-id="43ee0-122">위치 데이터베이스 채우기</span><span class="sxs-lookup"><span data-stu-id="43ee0-122">Populating the Location Database</span></span>

<span data-ttu-id="43ee0-123">다음 질문은 위치 데이터베이스를 채우는 방법을 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-123">The following questions can help you determine how to populate the location database.</span></span>

 <span data-ttu-id="43ee0-124">**위치 데이터베이스를 채우는 데 사용할 프로세스는 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="43ee0-124">**What process will you use to populate the location database?**</span></span>

<span data-ttu-id="43ee0-p106">데이터가 어디에 있습니까 그리고 이러한 데이터를 위치 데이터베이스에서 요구하는 형식으로 변환하기 위해 수행해야 할 단계는 무엇입니까? 위치를 CSV 파일을 사용하여 일괄적으로 또는 개별적으로 추가하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="43ee0-p106">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

 <span data-ttu-id="43ee0-127">**위치 매핑이 이미 포함된 타사 데이터베이스가 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="43ee0-127">**Do you have a third party database that already contains a mapping of locations?**</span></span>

<span data-ttu-id="43ee0-128">보조 위치 정보 서비스 옵션을 사용하여 타사 데이터베이스에 연결하면 오프라인 플랫폼을 사용하여 위치를 그룹화하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-128">By using the Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="43ee0-129">이 방법을 사용하면 위치를 네트워크 식별자에게 연결할 수 있을 뿐만 아니라 사용자에게도 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-129">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="43ee0-130">즉, 위치 정보 서비스는 보조 위치 정보 서비스에서 시작된 여러 주소를 비즈니스용 Skype 클라이언트로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-130">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Skype for Business client.</span></span> <span data-ttu-id="43ee0-131">그러면 사용자는 가장 적합한 위치를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-131">The user can then choose the most appropriate location.</span></span>

<span data-ttu-id="43ee0-132">위치 정보 서비스와 통합하려면 타사 데이터베이스가 Lync Server 위치 요청/응답 계획에 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-132">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="43ee0-133">자세한 내용은 ["[MS-E911WS]: E911 지원 프로토콜 사양용 웹 서비스"를 참조하세요.](https://go.microsoft.com/fwlink/p/?linkid=213819)</span><span class="sxs-lookup"><span data-stu-id="43ee0-133">For details, see  ["[MS-E911WS]: Web Service for E911 Support Protocol Specification"](https://go.microsoft.com/fwlink/p/?linkid=213819).</span></span> <span data-ttu-id="43ee0-134">보조 위치 정보 서비스 배포에 대한 자세한 내용은 배포 설명서에서 비즈니스용 [Skype 서버에서](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) 보조 위치 정보 서비스 구성을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="43ee0-134">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="43ee0-135">위치 데이터베이스를 채우는 방법에 대한 자세한 내용은 배포 설명서에서 [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="43ee0-135">For details about populating the location database, see [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.</span></span>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="43ee0-136">위치 데이터베이스 유지 관리</span><span class="sxs-lookup"><span data-stu-id="43ee0-136">Maintaining the Location Database</span></span>

<span data-ttu-id="43ee0-p109">위치 데이터베이스를 채우고 나면 네트워크 구성이 변경되므로 데이터베이스를 업데이트하기 위한 전략을 개발해야 합니다. 다음 질문은 위치 데이터베이스를 유지 관리하는 방법을 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-p109">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

 <span data-ttu-id="43ee0-139">**어떤 방법으로 위치 데이터베이스를 업데이트하시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="43ee0-139">**How will you update the location database?**</span></span>

<span data-ttu-id="43ee0-p110">WAP 추가, 사무실 케이블 재연결(스위치 할당이 달라짐) 및 서브넷 확장 등을 포함하여 위치 데이터베이스를 업데이트해야 하는 몇 가지 시나리오가 있습니다. 각 개별 위치를 직접 업데이트하시겠습니까 아니면 CSV 파일을 사용하여 모든 위치를 일괄적으로 업데이트하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="43ee0-p110">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

 <span data-ttu-id="43ee0-142">**SNMP 응용 프로그램을 사용하여 Lync 클라이언트 MAC 주소를 포트 및 스위치 식별자와 일치시키시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="43ee0-142">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>

<span data-ttu-id="43ee0-143">SNMP 응용 프로그램을 사용할 경우 SNMP 응용 프로그램과 위치 데이터베이스 간 포트 및 스위치 정보를 일치시키기 위한 수동 프로세스를 개발해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-143">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="43ee0-144">SNMP 응용 프로그램에서 데이터베이스에 포함되지 않은 섀시 IP 주소 또는 포트 ID를 반환하면 위치 정보 서비스에서 클라이언트로 위치를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43ee0-144">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>


