---
title: 'Lync Server 2013: 포리스트 준비로 인 한 변경 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e31e088d34bae2e136d86751c71f45754dc9db07
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a><span data-ttu-id="c6800-102">Lync Server 2013에서 포리스트 준비로 인 한 변경 사항</span><span class="sxs-lookup"><span data-stu-id="c6800-102">Changes made by forest preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6800-103">_**마지막으로 수정 된 항목:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="c6800-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="c6800-104">이 섹션에서는 포리스트 준비 단계를 통해 만들어지는 전역 설정과 개체, 유니버설 서비스 및 관리 그룹에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

<div>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="c6800-105">Active Directory 전역 설정 및 개체</span><span class="sxs-lookup"><span data-stu-id="c6800-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="c6800-106">전역 설정을 구성 컨테이너에 저장 하는 경우 (모든 새 Lync Server 2013 배포의 경우) 포리스트 준비에서는 기존 서비스 컨테이너를 사용 하 고 구성\\서비스 개체 아래에 **RTC 서비스** 개체를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-106">If you store global settings in the Configuration container (as is the case for all new Lync Server 2013 deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\\Services object.</span></span> <span data-ttu-id="c6800-107">포리스트 준비에서는 RTC Service 개체 아래에 msRTCSIP-GlobalContainer 유형의 **Global Settings** 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="c6800-108">전역 설정 개체에는 Lync Server 배포에 적용 되는 모든 설정이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-108">The global settings object holds all the settings that apply to the Lync Server deployment.</span></span> <span data-ttu-id="c6800-109">시스템 컨테이너에 전역 설정을 저장 하는 경우 포리스트 준비에서는 루트 도메인 시스템 컨테이너 아래의 Microsoft 컨테이너와 시스템\\microsoft 개체 아래에 RTC 서비스 개체를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\\Microsoft object.</span></span>

<span data-ttu-id="c6800-110">또한 포리스트 준비에서는 절차가 실행되는 루트 도메인에 대한 새로운 **msRTCSIP-Domain** 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="c6800-111">Active Directory 유니버설 서비스 및 관리 그룹</span><span class="sxs-lookup"><span data-stu-id="c6800-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="c6800-p102">포리스트 준비에서는 지정한 도메인을 기반으로 유니버설 그룹을 만들고 이러한 그룹에 대한 ACE(액세스 제어 항목)를 추가합니다. 이 단계에서 유니버설 그룹은 지정하는 도메인의 User 컨테이너에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-p102">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups. This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="c6800-p103">유니버설 그룹에서는 관리자가 전역 설정 및 서비스를 액세스하고 관리할 수 있습니다. 포리스트를 준비하면 다음 유형의 유니버설 그룹이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-p103">Universal groups allow administrators to access and manage global settings and services. Forest preparation adds the following types of universal groups:</span></span>

  - <span data-ttu-id="c6800-116">**관리 그룹**   이러한 그룹은 Lync Server 네트워크에 대 한 관리자 역할을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-116">**Administrative groups**   These groups define administrator roles for a Lync Server network.</span></span>

  - <span data-ttu-id="c6800-117">**인프라 그룹**   이러한 그룹은 Lync Server 인프라의 특정 영역에 액세스할 수 있는 권한을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-117">**Infrastructure groups**   These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="c6800-118">이 그룹은 관리 그룹의 구성 요소로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-118">They function as components of administrative groups.</span></span> <span data-ttu-id="c6800-119">이러한 그룹을 수정하거나 여기에 사용자를 직접 추가해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-119">You should not modify these groups or add users directly to them.</span></span>

  - <span data-ttu-id="c6800-120">**서비스 그룹**   이러한 그룹은 다양 한 Lync Server 서비스에 액세스 하는 데 필요한 서비스 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-120">**Service groups**   These groups are service accounts that are required to access various Lync Server services.</span></span>

<span data-ttu-id="c6800-121">다음 표에서는 관리 그룹에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-121">The following table describes the administrative groups.</span></span>

### <a name="administrative-groups-created-during-forest-preparation"></a><span data-ttu-id="c6800-122">포리스트 준비 중에 생성되는 관리 그룹</span><span class="sxs-lookup"><span data-stu-id="c6800-122">Administrative Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6800-123">관리 그룹</span><span class="sxs-lookup"><span data-stu-id="c6800-123">Administrative group</span></span></th>
<th><span data-ttu-id="c6800-124">설명</span><span class="sxs-lookup"><span data-stu-id="c6800-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6800-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c6800-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="c6800-126">구성원이 모든 서버 역할, 전역 설정 및 사용자를 포함하여 서버 및 풀 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6800-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="c6800-127">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="c6800-128">구성원이 사용자 설정을 관리하고 한 서버 또는 풀에서 다른 서버 또는 풀로 사용자를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-128">Allows members to manage user settings and move users from one server or pool to another.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6800-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="c6800-129">RTCUniversalReadOnlyAdmins</span></span></p></td>
<td><p><span data-ttu-id="c6800-130">구성원이 서버, 풀 및 사용자 설정을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-130">Allows members to read server, pool, and user settings.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c6800-131">다음 표에서는 인프라 그룹에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-131">The following table describes the infrastructure groups.</span></span>

### <a name="infrastructure-groups-created-during-forest-preparation"></a><span data-ttu-id="c6800-132">포리스트 준비 중에 생성되는 인프라 그룹</span><span class="sxs-lookup"><span data-stu-id="c6800-132">Infrastructure Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6800-133">인프라 그룹</span><span class="sxs-lookup"><span data-stu-id="c6800-133">Infrastructure group</span></span></th>
<th><span data-ttu-id="c6800-134">설명</span><span class="sxs-lookup"><span data-stu-id="c6800-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6800-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="c6800-135">RTCUniversalGlobalWriteGroup</span></span></p></td>
<td><p><span data-ttu-id="c6800-136">Lync Server에 대 한 전역 설정 개체에 대 한 쓰기 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-136">Grants write access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6800-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c6800-137">RTCUniversalGlobalReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c6800-138">Lync Server에 대 한 전역 설정 개체에 대 한 읽기 전용 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-138">Grants read-only access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6800-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c6800-139">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c6800-140">Lync Server 사용자 설정에 대 한 읽기 전용 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-140">Grants read-only access to Lync Server user settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6800-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c6800-141">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="c6800-142">Lync Server 설정에 대 한 읽기 전용 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-142">Grants read-only access to Lync Server settings.</span></span> <span data-ttu-id="c6800-143">이 그룹은 풀 수준 설정에는 액세스할 수 없고 개별 서버와 관련된 설정에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6800-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="c6800-144">RTCUniversalSBATechnicians</span></span></p></td>
<td><p><span data-ttu-id="c6800-145">Lync Server 구성에 대 한 읽기 전용 액세스 권한을 부여 하 고 설치 중에 sba (survivable 분기 기기의 로컬 관리자 그룹에 위치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-145">Grants read-only access to Lync Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c6800-146">다음 표에서는 서비스 그룹에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-146">The following table describes the service groups.</span></span>

### <a name="service-groups-created-during-forest-preparation"></a><span data-ttu-id="c6800-147">포리스트 준비 중에 생성되는 서비스 그룹</span><span class="sxs-lookup"><span data-stu-id="c6800-147">Service Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6800-148">서비스 그룹</span><span class="sxs-lookup"><span data-stu-id="c6800-148">Service group</span></span></th>
<th><span data-ttu-id="c6800-149">설명</span><span class="sxs-lookup"><span data-stu-id="c6800-149">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6800-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="c6800-150">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="c6800-151">프런트 엔드 서버 및 Standard Edition 서버를 실행 하는 데 사용 되는 서비스 계정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="c6800-152">이 그룹은 서버가 Lync Server 전역 설정 및 Active Directory 사용자 개체에 대 한 읽기/쓰기 액세스를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-152">This group allows servers read/write access to Lync Server global settings and Active Directory user objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6800-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="c6800-153">RTCComponentUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="c6800-154">A/V 회의 서버, 웹 서비스, 중재 서버, 보관 서버 및 모니터링 서버를 실행 하는 데 사용 되는 서비스 계정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6800-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="c6800-155">RTCProxyUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="c6800-156">Lync Server에 지 서버를 실행 하는 데 사용 되는 서비스 계정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-156">Includes service accounts used to run Lync Server Edge Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6800-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="c6800-157">RTCUniversalConfigReplicator</span></span></p></td>
<td><p><span data-ttu-id="c6800-158">Lync Server 중앙 관리 저장소 복제에 참가할 수 있는 서버를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-158">Includes servers that can participate in Lync Server Central Management store replication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6800-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="c6800-159">RTCSBAUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="c6800-160">Lync Server 설정에 대 한 읽기 전용 액세스 권한을 부여 하지만 sba (survivable 분기 서버 및 sba (survivable branch 기기 배포의 설치를 위한 구성을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-160">Grants read-only access to Lync Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c6800-161">그런 다음 포리스트 준비에서는 다음과 같이 해당 인프라 그룹에 서비스 및 관리 그룹을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

  - <span data-ttu-id="c6800-162">RTCUniversalServerAdmins는 RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup 및 RTCUniversalUserReadOnlyGroup에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="c6800-163">RTCUnversalUserAdmins는 RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup 및 RTCUniversalUserReadOnlyGroup의 구성원으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="c6800-164">RTCHSUniversalServices, RTCComponentUniversalServices 및 RTCUniversalReadOnlyAdmins는 RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup 및 RTCUniversalUserReadOnlyGroup의 구성원으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="c6800-165">또한 포리스트 준비에서는 다음과 같은 RBAC(역할 기반 액세스 제어) 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

  - <span data-ttu-id="c6800-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="c6800-166">CSAdministrator</span></span>

  - <span data-ttu-id="c6800-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="c6800-167">CSArchivingAdministrator</span></span>

  - <span data-ttu-id="c6800-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="c6800-168">CSHelpDesk</span></span>

  - <span data-ttu-id="c6800-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="c6800-169">CSLocationAdministrator</span></span>

  - <span data-ttu-id="c6800-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="c6800-170">CSResponseGroupAdministrator</span></span>

  - <span data-ttu-id="c6800-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="c6800-171">CSServerAdministrator</span></span>

  - <span data-ttu-id="c6800-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="c6800-172">CSUserAdministrator</span></span>

  - <span data-ttu-id="c6800-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="c6800-173">CSViewOnlyAdministrator</span></span>

  - <span data-ttu-id="c6800-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="c6800-174">CSVoiceAdministrator</span></span>

  - <span data-ttu-id="c6800-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="c6800-175">CsPersistentChatAdministator</span></span>

  - <span data-ttu-id="c6800-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="c6800-176">CsResponseGroupManager</span></span>

<span data-ttu-id="c6800-177">각 항목에 대해 허용 되는 RBAC 역할 및 작업에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 역할 기반 액세스 제어 계획](lync-server-2013-planning-for-role-based-access-control.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c6800-177">For details about RBAC roles and the tasks allowed for each, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="c6800-178">포리스트 준비에서는 개인 및 공용 ACE를 모두 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="c6800-179">Lync Server에서 사용 하는 전역 설정 컨테이너에 개인 Ace를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-179">It creates private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="c6800-180">이 컨테이너는 Lync Server 에서만 사용 되며 전역 설정을 저장 하는 위치에 따라 루트 도메인의 구성 컨테이너나 시스템 컨테이너에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-180">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="c6800-181">아래 표에 포리스트 준비에서 만들어지는 공용 ACE가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

### <a name="public-aces-created-by-forest-preparation"></a><span data-ttu-id="c6800-182">포리스트 준비에서 만들어지는 공용 ACE</span><span class="sxs-lookup"><span data-stu-id="c6800-182">Public ACEs created by Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6800-183">ACE</span><span class="sxs-lookup"><span data-stu-id="c6800-183">ACE</span></span></th>
<th><span data-ttu-id="c6800-184">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="c6800-184">RTCUniversalGlobalReadOnlyGroup</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6800-185">루트 도메인 System 컨테이너 읽기(상속되지 않음)<strong>\*</strong></span><span class="sxs-lookup"><span data-stu-id="c6800-185">Read root domain System Container (not inherited)<strong>\*</strong></span></span></p></td>
<td><p><span data-ttu-id="c6800-186">X</span><span class="sxs-lookup"><span data-stu-id="c6800-186">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6800-187">구성의 DisplaySpecifiers 컨테이너 읽기(상속되지 않음)</span><span class="sxs-lookup"><span data-stu-id="c6800-187">Read Configuration’s DisplaySpecifiers container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="c6800-188">X</span><span class="sxs-lookup"><span data-stu-id="c6800-188">X</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c6800-189"><STRONG>\*</STRONG>상속 되지 않은 Ace는 이러한 컨테이너의 하위 개체에 대 한 액세스 권한을 부여 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-189"><STRONG>\*</STRONG>ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="c6800-190">상속 된 Ace는 이러한 컨테이너 아래의 자식 개체에 대 한 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-190">ACEs that are inherited grant access to child objects under these containers.</span></span>



</div>

<span data-ttu-id="c6800-191">구성 명명 컨텍스트 아래의 구성 컨테이너에서 포리스트 준비는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

  - <span data-ttu-id="c6800-192">사용자, 연락처 및 InetOrgPersons에 대한 언어 표시 지정(예: CN=user-Display,CN=409,CN=DisplaySpecifiers)의 adminContextMenu 및 adminPropertyPages 특성 아래에 **RTC property** 페이지의 항목 **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** 를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="c6800-193">**Extended-Rights** 아래에 User 및 Contact 클래스에 적용되는 **controlAccessRight** 유형의 **RTCPropertySet** 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

  - <span data-ttu-id="c6800-194">**Extended-Rights** 아래에 User, Contact, OU 및 DomainDNS 클래스에 적용되는 **controlAccessRight** 유형의 **RTCUserSearchPropertySet** 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

  - <span data-ttu-id="c6800-195">각 언어 OU(조직 구성 단위) 표시 지정자(예: CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers)의 **extraColumns** 특성 아래에 **msRTCSIP-PrimaryUserAddress**를 추가하고, 기본 표시(예: CN=default-Display, CN=409,CN=DisplaySpecifiers)의 **extraColumns** 특성 값을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="c6800-196">Users, Contacts 및 InetOrgPerson 개체에 대한 각 언어 표시 지정자(예: 영어인 경우 CN=user-Display,CN=409,CN=DisplaySpecifiers)의 **attributeDisplayNames** 특성 아래에 **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** 및 **msRTCSIP-UserEnabled** 필터링 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c6800-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

