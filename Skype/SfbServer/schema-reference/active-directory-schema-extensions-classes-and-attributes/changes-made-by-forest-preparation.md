---
title: 비즈니스용 Skype 서버에서 포리스트 준비로 변경한 내용
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: 이 섹션에서는 포리스트 준비 단계를 통해 만들어지는 전역 설정과 개체, 유니버설 서비스 및 관리 그룹에 대해 설명합니다.
ms.openlocfilehash: 4e8032cb91b012c710dc509708a813d55825f7a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831918"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a><span data-ttu-id="0d201-103">비즈니스용 Skype 서버에서 포리스트 준비로 변경한 내용</span><span class="sxs-lookup"><span data-stu-id="0d201-103">Changes made by forest preparation in Skype for Business Server</span></span>

<span data-ttu-id="0d201-104">이 섹션에서는 포리스트 준비 단계를 통해 만들어지는 전역 설정과 개체, 유니버설 서비스 및 관리 그룹에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="0d201-105">Active Directory 전역 설정 및 개체</span><span class="sxs-lookup"><span data-stu-id="0d201-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="0d201-106">모든 새 비즈니스용 Skype 서버 배포의 경우처럼 구성 컨테이너에 전역 설정을 저장하는 경우 포리스트 준비에서는 기존 서비스 컨테이너를 사용하고 Configuration\Services 개체 아래에 **RTC 서비스** 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-106">If you store global settings in the Configuration container (as is the case for all new Skype for Business Server deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\Services object.</span></span> <span data-ttu-id="0d201-107">포리스트 준비에서는 RTC Service 개체 아래에 msRTCSIP-GlobalContainer 유형의 **Global Settings** 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="0d201-108">전역 설정 개체에는 비즈니스용 Skype 서버 배포에 적용되는 모든 설정이 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-108">The global settings object holds all the settings that apply to the Skype for Business Server deployment.</span></span> <span data-ttu-id="0d201-109">System 컨테이너에 전역 설정을 저장하는 경우 포리스트 준비에서는 루트 도메인 System 컨테이너 아래의 Microsoft 컨테이너와 System\Microsoft 개체 아래의 RTC Service 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\Microsoft object.</span></span>

<span data-ttu-id="0d201-110">또한 포리스트 준비에서는 절차가 실행되는 루트 도메인에 대한 새로운 **msRTCSIP-Domain** 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="0d201-111">Active Directory 유니버설 서비스 및 관리 그룹</span><span class="sxs-lookup"><span data-stu-id="0d201-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="0d201-p102">포리스트 준비에서는 지정한 도메인을 기반으로 유니버설 그룹을 만들고 이러한 그룹에 대한 ACE(액세스 제어 항목)를 추가합니다. 이 단계에서 유니버설 그룹은 지정하는 도메인의 User 컨테이너에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-p102">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups. This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="0d201-p103">유니버설 그룹에서는 관리자가 전역 설정 및 서비스를 액세스하고 관리할 수 있습니다. 포리스트를 준비하면 다음 유형의 유니버설 그룹이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-p103">Universal groups allow administrators to access and manage global settings and services. Forest preparation adds the following types of universal groups:</span></span>

- <span data-ttu-id="0d201-116">**관리 그룹** 이러한 그룹은 비즈니스용 Skype 서버 네트워크에 대한 관리자 역할을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-116">**Administrative groups** These groups define administrator roles for a Skype for Business Server network.</span></span>

- <span data-ttu-id="0d201-117">**인프라 그룹** 이러한 그룹은 비즈니스용 Skype 서버 인프라의 특정 영역에 액세스할 수 있는 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-117">**Infrastructure groups** These groups provide permission to access specific areas of the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="0d201-118">이 그룹은 관리 그룹의 구성 요소로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-118">They function as components of administrative groups.</span></span> <span data-ttu-id="0d201-119">이러한 그룹을 수정하거나 여기에 사용자를 직접 추가해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-119">You should not modify these groups or add users directly to them.</span></span>

- <span data-ttu-id="0d201-120">**서비스 그룹** 이러한 그룹은 다양한 비즈니스용 Skype 서버 서비스에 액세스하는 데 필요한 서비스 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-120">**Service groups** These groups are service accounts that are required to access various Skype for Business Server services.</span></span>

<span data-ttu-id="0d201-121">다음 표에서는 관리 그룹에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-121">The following table describes the administrative groups.</span></span>

<span data-ttu-id="0d201-122">**포리스트 준비 중에 생성되는 관리 그룹**</span><span class="sxs-lookup"><span data-stu-id="0d201-122">**Administrative Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="0d201-123">**관리 그룹**</span><span class="sxs-lookup"><span data-stu-id="0d201-123">**Administrative group**</span></span>|<span data-ttu-id="0d201-124">**설명**</span><span class="sxs-lookup"><span data-stu-id="0d201-124">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0d201-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0d201-125">RTCUniversalServerAdmins</span></span>  <br/> |<span data-ttu-id="0d201-126">구성원이 모든 서버 역할, 전역 설정 및 사용자를 포함하여 서버 및 풀 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span>  <br/> |
|<span data-ttu-id="0d201-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="0d201-127">RTCUniversalUserAdmins</span></span>  <br/> |<span data-ttu-id="0d201-128">구성원이 사용자 설정을 관리하고 한 서버 또는 풀에서 다른 서버 또는 풀로 사용자를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-128">Allows members to manage user settings and move users from one server or pool to another.</span></span>  <br/> |
|<span data-ttu-id="0d201-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="0d201-129">RTCUniversalReadOnlyAdmins</span></span>  <br/> |<span data-ttu-id="0d201-130">구성원이 서버, 풀 및 사용자 설정을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-130">Allows members to read server, pool, and user settings.</span></span>  <br/> |

<span data-ttu-id="0d201-131">다음 표에서는 인프라 그룹에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-131">The following table describes the infrastructure groups.</span></span>

<span data-ttu-id="0d201-132">**포리스트 준비 중에 생성되는 인프라 그룹**</span><span class="sxs-lookup"><span data-stu-id="0d201-132">**Infrastructure Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="0d201-133">**인프라 그룹**</span><span class="sxs-lookup"><span data-stu-id="0d201-133">**Infrastructure group**</span></span>|<span data-ttu-id="0d201-134">**설명**</span><span class="sxs-lookup"><span data-stu-id="0d201-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0d201-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="0d201-135">RTCUniversalGlobalWriteGroup</span></span>  <br/> |<span data-ttu-id="0d201-136">비즈니스용 Skype 서버의 전역 설정 개체에 대한 쓰기 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-136">Grants write access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="0d201-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="0d201-137">RTCUniversalGlobalReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="0d201-138">비즈니스용 Skype 서버의 전역 설정 개체에 대한 읽기 전용 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-138">Grants read-only access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="0d201-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="0d201-139">RTCUniversalUserReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="0d201-140">비즈니스용 Skype 서버 사용자 설정에 대한 읽기 전용 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-140">Grants read-only access to Skype for Business Server user settings.</span></span>  <br/> |
|<span data-ttu-id="0d201-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="0d201-141">RTCUniversalServerReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="0d201-142">비즈니스용 Skype 서버 설정에 대한 읽기 전용 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-142">Grants read-only access to Skype for Business Server settings.</span></span> <span data-ttu-id="0d201-143">이 그룹은 풀 수준 설정에는 액세스할 수 없고 개별 서버와 관련된 설정에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span>  <br/> |
|<span data-ttu-id="0d201-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="0d201-144">RTCUniversalSBATechnicians</span></span>  <br/> |<span data-ttu-id="0d201-145">비즈니스용 Skype 서버 구성에 대한 읽기 전용 액세스 권한을 부여하며 설치 중에 Survivable Branch Appliance의 Local Administrators 그룹에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-145">Grants read-only access to Skype for Business Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span>  <br/> |

<span data-ttu-id="0d201-146">다음 표에서는 서비스 그룹에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-146">The following table describes the service groups.</span></span>

<span data-ttu-id="0d201-147">**포리스트 준비 중에 생성되는 서비스 그룹**</span><span class="sxs-lookup"><span data-stu-id="0d201-147">**Service Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="0d201-148">**서비스 그룹**</span><span class="sxs-lookup"><span data-stu-id="0d201-148">**Service group**</span></span>|<span data-ttu-id="0d201-149">**설명**</span><span class="sxs-lookup"><span data-stu-id="0d201-149">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0d201-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="0d201-150">RTCHSUniversalServices</span></span>  <br/> |<span data-ttu-id="0d201-151">프런트 엔드 서버 및 Standard Edition 서버를 실행하기 위해 사용되는 서비스 계정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="0d201-152">이 그룹은 서버에서 비즈니스용 Skype 서버 전역 설정 및 Active Directory 사용자 개체에 대한 읽기/쓰기 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-152">This group allows servers read/write access to Skype for Business Server global settings and Active Directory user objects.</span></span>  <br/> |
|<span data-ttu-id="0d201-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="0d201-153">RTCComponentUniversalServices</span></span>  <br/> |<span data-ttu-id="0d201-154">A/V 회의 서버, 웹 서비스, 중재 서버, 보관 서버 및 모니터링 서버를 실행하는 데 사용되는 서비스 계정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span>  <br/> |
|<span data-ttu-id="0d201-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="0d201-155">RTCProxyUniversalServices</span></span>  <br/> |<span data-ttu-id="0d201-156">비즈니스용 Skype 서버 에지 서버를 실행하기 위해 사용되는 서비스 계정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-156">Includes service accounts used to run Skype for Business Server Edge Servers.</span></span>  <br/> |
|<span data-ttu-id="0d201-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="0d201-157">RTCUniversalConfigReplicator</span></span>  <br/> |<span data-ttu-id="0d201-158">비즈니스용 Skype 서버 중앙 관리 저장소 복제에 참여할 수 있는 서버를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-158">Includes servers that can participate in Skype for Business Server Central Management store replication.</span></span>  <br/> |
|<span data-ttu-id="0d201-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="0d201-159">RTCSBAUniversalServices</span></span>  <br/> |<span data-ttu-id="0d201-160">비즈니스용 Skype 서버 설정에 대한 읽기 전용 액세스 권한을 부여하지만, Survivable Branch Server 및 Survivable Branch Appliance 배포를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-160">Grants read-only access to Skype for Business Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span>  <br/> |

<span data-ttu-id="0d201-161">그런 다음 포리스트 준비에서는 다음과 같이 해당 인프라 그룹에 서비스 및 관리 그룹을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

- <span data-ttu-id="0d201-162">RTCUniversalServerAdmins는 RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup 및 RTCUniversalUserReadOnlyGroup에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="0d201-163">RTCUnversalUserAdmins는 RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup 및 RTCUniversalUserReadOnlyGroup의 구성원으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="0d201-164">RTCHSUniversalServices, RTCComponentUniversalServices 및 RTCUniversalReadOnlyAdmins는 RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup 및 RTCUniversalUserReadOnlyGroup의 구성원으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="0d201-165">또한 포리스트 준비에서는 다음과 같은 RBAC(역할 기반 액세스 제어) 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

- <span data-ttu-id="0d201-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="0d201-166">CSAdministrator</span></span>

- <span data-ttu-id="0d201-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="0d201-167">CSArchivingAdministrator</span></span>

- <span data-ttu-id="0d201-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="0d201-168">CSHelpDesk</span></span>

- <span data-ttu-id="0d201-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="0d201-169">CSLocationAdministrator</span></span>

- <span data-ttu-id="0d201-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="0d201-170">CSResponseGroupAdministrator</span></span>

- <span data-ttu-id="0d201-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="0d201-171">CSServerAdministrator</span></span>

- <span data-ttu-id="0d201-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="0d201-172">CSUserAdministrator</span></span>

- <span data-ttu-id="0d201-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="0d201-173">CSViewOnlyAdministrator</span></span>

- <span data-ttu-id="0d201-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="0d201-174">CSVoiceAdministrator</span></span>

- <span data-ttu-id="0d201-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="0d201-175">CsPersistentChatAdministator</span></span>

- <span data-ttu-id="0d201-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="0d201-176">CsResponseGroupManager</span></span>

<span data-ttu-id="0d201-177">RBAC 역할 및 각 역할에 허용되는 작업에 대한 자세한 내용은 계획 설명서에서 [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0d201-177">For details about RBAC roles and the tasks allowed for each, see [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) in the Planning documentation.</span></span>

<span data-ttu-id="0d201-178">포리스트 준비에서는 개인 및 공용 ACE를 모두 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="0d201-179">비즈니스용 Skype 서버에서 사용하는 전역 설정 컨테이너에 개인 AES를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-179">It creates private ACEs on the global settings container used by Skype for Business Server.</span></span> <span data-ttu-id="0d201-180">이 컨테이너는 비즈니스용 Skype 서버에서만 사용하며 전역 설정을 저장하는 위치에 따라 루트 도메인의 구성 컨테이너 또는 시스템 컨테이너에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-180">This container is used only by Skype for Business Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="0d201-181">아래 표에 포리스트 준비에서 만들어지는 공용 ACE가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

<span data-ttu-id="0d201-182">**포리스트 준비에서 만들어지는 공용 ACE**</span><span class="sxs-lookup"><span data-stu-id="0d201-182">**Public ACEs created by Forest Preparation**</span></span>


| <span data-ttu-id="0d201-183">**ACE**</span><span class="sxs-lookup"><span data-stu-id="0d201-183">**ACE**</span></span>                                                                 | <span data-ttu-id="0d201-184">**RTCUniversalGlobalReadOnlyGroup**</span><span class="sxs-lookup"><span data-stu-id="0d201-184">**RTCUniversalGlobalReadOnlyGroup**</span></span> |
|:------------------------------------------------------------------------|:------------------------------------|
| <span data-ttu-id="0d201-185">루트 도메인 시스템 컨테이너 읽기(상속되지) **\\**\*</span><span class="sxs-lookup"><span data-stu-id="0d201-185">Read root domain System Container (not inherited) **\\**\*</span></span> <br/>        | <span data-ttu-id="0d201-186">X 키</span><span class="sxs-lookup"><span data-stu-id="0d201-186">X</span></span>  <br/>                            |
| <span data-ttu-id="0d201-187">구성의 DisplaySpecifiers 컨테이너 읽기(상속되지)</span><span class="sxs-lookup"><span data-stu-id="0d201-187">Read Configuration's DisplaySpecifiers container (not inherited)</span></span>  <br/> | <span data-ttu-id="0d201-188">X 키</span><span class="sxs-lookup"><span data-stu-id="0d201-188">X</span></span>  <br/>                            |

> [!NOTE]
> <span data-ttu-id="0d201-189"><strong>\\</strong>\*상속되지 않은 AES는 이러한 컨테이너에서 자식 개체에 대한 액세스 권한을 부여하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-189"><strong>\\</strong>\*ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="0d201-190">상속된 AES는 이러한 컨테이너 아래에 있는 자식 개체에 대한 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-190">ACEs that are inherited grant access to child objects under these containers.</span></span>

<span data-ttu-id="0d201-191">구성 명명 컨텍스트 아래의 구성 컨테이너에서 포리스트 준비는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

- <span data-ttu-id="0d201-192">사용자, 연락처 및 InetOrgPersons에 대한 언어 표시 지정(예: CN=user-Display,CN=409,CN=DisplaySpecifiers)의 adminContextMenu 및 adminPropertyPages 특성 아래에 **RTC property** 페이지의 항목 **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** 를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="0d201-193">**Extended-Rights** 아래에 User 및 Contact 클래스에 적용되는 **controlAccessRight** 유형의 **RTCPropertySet** 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

- <span data-ttu-id="0d201-194">**Extended-Rights** 아래에 User, Contact, OU 및 DomainDNS 클래스에 적용되는 **controlAccessRight** 유형의 **RTCUserSearchPropertySet** 개체를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

- <span data-ttu-id="0d201-195">각 언어 OU(조직 구성 단위) 표시 지정자(예: CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers)의 **extraColumns** 특성 아래에 **msRTCSIP-PrimaryUserAddress** 를 추가하고, 기본 표시(예: CN=default-Display, CN=409,CN=DisplaySpecifiers)의 **extraColumns** 특성 값을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="0d201-196">Users, Contacts 및 InetOrgPerson 개체에 대한 각 언어 표시 지정자(예: 영어인 경우 CN=user-Display,CN=409,CN=DisplaySpecifiers)의 **attributeDisplayNames** 특성 아래에 **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** 및 **msRTCSIP-UserEnabled** 필터링 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0d201-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>


