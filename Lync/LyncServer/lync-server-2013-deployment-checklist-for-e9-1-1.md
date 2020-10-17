---
title: 'Lync Server 2013: E9-1-1에 대 한 배포 검사 목록'
description: 'Lync Server 2013: E9-1-1에 대 한 배포 검사 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c93762e2acef5e065249ced17bfa0eab2f159e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568360"
---
# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="12ffd-103">Lync Server 2013의 E9-1-1에 대 한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="12ffd-103">Deployment checklist for E9-1-1 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12ffd-104">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="12ffd-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="12ffd-105">향상 된 9-1-1 (E9-1-1)을 효과적으로 계획 하려면 다음 배포 요구 사항을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-105">To plan effectively for Enhanced 9-1-1 (E9-1-1), be sure to include the following deployment requirements:</span></span>

  - <span data-ttu-id="12ffd-106">E9-1-1 배포를 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="12ffd-106">Prerequisites for deploying E9-1-1.</span></span>

  - <span data-ttu-id="12ffd-107">E9-1-1을 배포 하는 데 필요한 단계</span><span class="sxs-lookup"><span data-stu-id="12ffd-107">Steps that are required to deploy E9-1-1.</span></span>

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a><span data-ttu-id="12ffd-108">E9-1-1 배포 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="12ffd-108">Deployment Prerequisites for E9-1-1</span></span>

<span data-ttu-id="12ffd-109">E9-1-1을 배포 하기 전에 먼저 Lync Server 내부 서버 (중앙 관리 저장소, 프런트 엔드 풀 또는 Standard Edition 서버, 하나 이상의 중재 서버 또는 중재 서버 풀 및 Lync Server 클라이언트 포함)를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-109">Before you deploy E9-1-1, you must already have deployed your Lync Server internal servers, including a Central Management store, a Front End pool or a Standard Edition server, one or more Mediation Servers or Mediation Server pools, and Lync Server clients.</span></span> <span data-ttu-id="12ffd-110">또한 E9-1-1 배포에서는 SIP 트렁크가 적격 E9-1-1 서비스 공급자 또는 공중 전화망 (응급 위치 식별 번호) 게이트웨이를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-110">In addition, an E9-1-1 deployment requires a SIP trunk to a qualified E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway to your public switched telephone network (PSTN).</span></span> <span data-ttu-id="12ffd-111">Lync Server에서는 미국 내 에서만 E9-1-1 서비스 공급자를 사용할 지를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-111">Lync Server supports using E9-1-1 service providers only inside the United States.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="12ffd-112">배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="12ffd-112">Deployment Process</span></span>

<span data-ttu-id="12ffd-113">다음 표에서는 E9-1-1 배포 프로세스에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-113">The following table provides an overview of the E9-1-1 deployment process.</span></span> <span data-ttu-id="12ffd-114">배포 단계에 대 한 자세한 내용은 배포 설명서의 [Configure 다기능 9-1-1 In Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="12ffd-114">For details about deployment steps, see [Configure Enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12ffd-115">단계</span><span class="sxs-lookup"><span data-stu-id="12ffd-115">Phase</span></span></th>
<th><span data-ttu-id="12ffd-116">단계</span><span class="sxs-lookup"><span data-stu-id="12ffd-116">Steps</span></span></th>
<th><span data-ttu-id="12ffd-117">역할</span><span class="sxs-lookup"><span data-stu-id="12ffd-117">Roles</span></span></th>
<th><span data-ttu-id="12ffd-118">배포 설명서</span><span class="sxs-lookup"><span data-stu-id="12ffd-118">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12ffd-119">음성 용도, 경로 및 트렁크 구성 구성</span><span class="sxs-lookup"><span data-stu-id="12ffd-119">Configure voice usages, routes, and trunk configurations</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="12ffd-120">새 PSTN 사용 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-120">Create a new PSTN usage record.</span></span> <span data-ttu-id="12ffd-121">이 이름은 위치 정책의 <strong>PSTN 사용</strong> 설정에 사용 되는 이름과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-121">This is the same name that is used for the <strong>PSTN Usage</strong> setting in the location policy.</span></span></p></li>
<li><p><span data-ttu-id="12ffd-122">이전 단계에서 만든 PSTN 사용 레코드에 대 한 음성 경로를 만들거나 할당 한 다음 gateway 특성을 E9-1-1 SIP 트렁크 또는 ELIN gateway로 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-122">Create or assign a voice route to the PSTN usage record created in the previous step and then point the gateway attribute to the E9-1-1 SIP trunk or ELIN gateway.</span></span></p></li>
<li><p><span data-ttu-id="12ffd-123">SIP 트렁크 E9-1-1 서비스 공급자의 경우 SIP를 통해 E9-1-1 통화를 처리할 트렁크를 설정 하 여 <strong>get-cstrunkconfiguration-EnablePIDFLOSupport</strong> cmdlet을 사용 하 여 pidf-로 데이터를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-123">For a SIP trunk E9-1-1 service provider, set the trunk that will be handling E9-1-1 calls over the SIP to pass PIDF-LO data by using the <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> cmdlet.</span></span></p></li>
<li><p><span data-ttu-id="12ffd-124">SIP 트렁크 E9-1-1 서비스 공급자의 경우 E9-1-1 서비스 공급자의 SIP 트렁크에서 처리 하지 않는 통화에 대해 로컬 PSTN 경로를 만들거나 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-124">Optionally, for a SIP trunk E9-1-1 service provider, create or assign a local PSTN route for calls that are not handled by the E9-1-1 service provider’s SIP trunk.</span></span> <span data-ttu-id="12ffd-125">E9-1-1 서비스 공급자에 대 한 연결을 사용할 수 없는 경우이 경로가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-125">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> <span data-ttu-id="12ffd-126">E9-1-1 서비스 공급자가 지 원하는 경우 911 다이얼 문자열을 국내/지역 긴급 통화 응답 센터 (i/o) 번호로 변환 하는 트렁크 구성 규칙을 게이트웨이에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-126">If supported by your E9-1-1 service provider, assign a trunk configuration rule to the gateway that translates the 911 dial string into the direct inward dialing (DID) number of the national/regional Emergency Call Response Center (ECRC).</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="12ffd-127">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="12ffd-127">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="12ffd-128"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Lync Server 2013에서 E9-1-1 음성 경로 구성</a></span><span class="sxs-lookup"><span data-stu-id="12ffd-128"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configure an E9-1-1 voice route in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12ffd-129">위치 정책을 만들고 사용자 및 서브넷에 할당</span><span class="sxs-lookup"><span data-stu-id="12ffd-129">Create location policies and assign them to users and subnets</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="12ffd-130">전역 위치 정책을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-130">Review the global location policy.</span></span></p></li>
<li><p><span data-ttu-id="12ffd-131">사용자 수준 범위로 위치 정책을 만듭니다. 또는 조직에 응급 용도가 서로 다른 사이트가 둘 이상 있는 경우 네트워크 수준 범위를 사용 하 여 위치 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-131">Create a location policy with a user-level scope; or, if the organization has more than one site with different emergency usages, create a location policy with a network-level scope.</span></span></p></li>
<li><p><span data-ttu-id="12ffd-132">네트워크 사이트에 위치 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-132">Assign the location policy to network sites.</span></span></p></li>
<li><p><span data-ttu-id="12ffd-133">네트워크 사이트에 적절 한 서브넷을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-133">Add the appropriate subnets to the network site.</span></span></p></li>
<li><p><span data-ttu-id="12ffd-134">반드시 위치 정책을 사용자 정책에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-134">(Optional) Assign the location policy to user policies.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="12ffd-135">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="12ffd-135">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="12ffd-136">CSLocationAdmin (위치 정책 만들기 제외)</span><span class="sxs-lookup"><span data-stu-id="12ffd-136">CSLocationAdmin (except for creating Location Policies)</span></span></p></td>
<td><p><span data-ttu-id="12ffd-137"><a href="lync-server-2013-create-location-policies.md">Lync Server 2013의 위치 정책 만들기</a></span><span class="sxs-lookup"><span data-stu-id="12ffd-137"><a href="lync-server-2013-create-location-policies.md">Create location policies in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="12ffd-138"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Lync Server 2013에서 네트워크 사이트에 위치 정책 추가</a></span><span class="sxs-lookup"><span data-stu-id="12ffd-138"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Add a location policy to a network site in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="12ffd-139"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Lync Server 2013에서 E9-1-1에 대 한 네트워크 사이트와 서브넷 연결</a></span><span class="sxs-lookup"><span data-stu-id="12ffd-139"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associate subnets with network sites for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12ffd-140">위치 데이터베이스 구성</span><span class="sxs-lookup"><span data-stu-id="12ffd-140">Configure the location database</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="12ffd-141">데이터베이스를 위치에 대한 네트워크 요소 매핑으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-141">Populate the database with a mapping of network elements to locations.</span></span></p></li>
<li><p><span data-ttu-id="12ffd-142">ELIN 게이트웨이의 경우에는 CompanyName 열에 Elin를 추가 &lt; &gt; 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-142">For ELIN gateways, add the ELINs to the &lt;CompanyName&gt; column.</span></span></p></li>
<li><p><span data-ttu-id="12ffd-143">주소 유효성 검사를 위해 E9-1-1 서비스 공급자에 대 한 연결을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-143">Configure the connection to the E9-1-1 service provider for validating addresses.</span></span></p></li>
<li><p><span data-ttu-id="12ffd-144">E9-1-1 서비스 공급자를 사용 하 여 주소 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-144">Validate the addresses with the E9-1-1 service provider.</span></span></p></li>
<li><p><span data-ttu-id="12ffd-145">업데이트된 데이터베이스를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-145">Publish the updated database.</span></span></p></li>
<li><p><span data-ttu-id="12ffd-146">ELIN 게이트웨이의 경우 PSTN 캐리어의 ALI (자동 위치 식별) 데이터베이스에 Elin을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-146">For ELIN gateways, upload the ELINs to your PSTN carrier's Automatic Location Identification (ALI) database.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="12ffd-147">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="12ffd-147">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="12ffd-148">CSLocationAdmin</span><span class="sxs-lookup"><span data-stu-id="12ffd-148">CSLocationAdmin</span></span></p></td>
<td><p><span data-ttu-id="12ffd-149"><a href="lync-server-2013-configure-the-location-database.md">Lync Server 2013에서 위치 데이터베이스 구성</a></span><span class="sxs-lookup"><span data-stu-id="12ffd-149"><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12ffd-150">고급 기능 구성 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="12ffd-150">Configure Advanced Features (optional)</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="12ffd-151">SNMP 응용 프로그램에 대 한 URL을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-151">Configure the URL for the SNMP application.</span></span></p></li>
<li><p><span data-ttu-id="12ffd-152">보조 위치 정보 서비스의 위치에 대 한 URL을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ffd-152">Configure the URL for the location of the Secondary Location Information service.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="12ffd-153">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="12ffd-153">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="12ffd-154"><a href="lync-server-2013-configure-an-snmp-application.md">Lync Server 2013에서 SNMP 응용 프로그램 구성</a></span><span class="sxs-lookup"><span data-stu-id="12ffd-154"><a href="lync-server-2013-configure-an-snmp-application.md">Configure an SNMP application in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="12ffd-155"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Lync Server 2013에서 보조 위치 정보 서비스 구성</a></span><span class="sxs-lookup"><span data-stu-id="12ffd-155"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

