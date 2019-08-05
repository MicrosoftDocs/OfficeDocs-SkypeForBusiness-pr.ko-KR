---
title: 비즈니스용 Skype 서버에서 포리스트 준비에의 한 변경 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: 이 섹션에서는 포리스트 준비 단계에서 만든 전역 설정 및 개체와 유니버설 서비스 및 관리 그룹에 대해 설명 합니다.
ms.openlocfilehash: ece4a9bd1db5f43b52a96265dee41ee3a0a30b22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196815"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a><span data-ttu-id="721f3-103">비즈니스용 Skype 서버에서 포리스트 준비에의 한 변경 사항</span><span class="sxs-lookup"><span data-stu-id="721f3-103">Changes made by forest preparation in Skype for Business Server</span></span>

<span data-ttu-id="721f3-104">이 섹션에서는 포리스트 준비 단계에서 만든 전역 설정 및 개체와 유니버설 서비스 및 관리 그룹에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="721f3-105">Active Directory 전역 설정 및 개체</span><span class="sxs-lookup"><span data-stu-id="721f3-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="721f3-106">전역 설정을 구성 컨테이너에 저장 하는 경우 (모든 새로운 비즈니스용 Skype Server 배포의 경우) 포리스트 준비는 기존 서비스 컨테이너를 사용 하 고 Configuration\Services에 **RTC 서비스** 개체를 추가 합니다. 오브젝트가.</span><span class="sxs-lookup"><span data-stu-id="721f3-106">If you store global settings in the Configuration container (as is the case for all new Skype for Business Server deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\Services object.</span></span> <span data-ttu-id="721f3-107">RTC 서비스 개체에서 포리스트 준비는 msRTCSIP-GlobalContainer 유형의 **전역 설정** 개체를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="721f3-108">전역 설정 개체에는 비즈니스용 Skype 서버 배포에 적용 되는 모든 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-108">The global settings object holds all the settings that apply to the Skype for Business Server deployment.</span></span> <span data-ttu-id="721f3-109">시스템 컨테이너에 전역 설정을 저장 하는 경우 포리스트 준비에서는 루트 도메인 시스템 컨테이너 아래에 Microsoft 컨테이너를 사용 하 고 System\Microsoft 개체 아래에 RTC Service 개체를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\Microsoft object.</span></span>

<span data-ttu-id="721f3-110">또한 포리스트 준비는 프로시저가 실행 되는 루트 도메인에 대 한 새 **MsRTCSIP 도메인** 개체를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="721f3-111">Active Directory 유니버설 서비스 및 관리 그룹</span><span class="sxs-lookup"><span data-stu-id="721f3-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="721f3-112">포리스트 준비는 사용자가 지정 하는 도메인을 기반으로 유니버설 그룹을 만들고 이러한 그룹에 대 한 Ace (액세스 제어 항목)를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-112">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups.</span></span> <span data-ttu-id="721f3-113">이 단계에서는 지정 하는 도메인의 사용자 컨테이너에 유니버설 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-113">This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="721f3-114">유니버설 그룹을 통해 관리자는 전역 설정 및 서비스에 액세스 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-114">Universal groups allow administrators to access and manage global settings and services.</span></span> <span data-ttu-id="721f3-115">포리스트 준비는 다음 유형의 유니버설 그룹을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-115">Forest preparation adds the following types of universal groups:</span></span>

- <span data-ttu-id="721f3-116">**관리 그룹** 이 그룹은 비즈니스용 Skype Server 네트워크의 관리자 역할을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-116">**Administrative groups** These groups define administrator roles for a Skype for Business Server network.</span></span>

- <span data-ttu-id="721f3-117">**인프라 그룹** 이러한 그룹은 비즈니스용 Skype 서버 인프라의 특정 영역에 액세스할 수 있는 권한을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-117">**Infrastructure groups** These groups provide permission to access specific areas of the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="721f3-118">관리 그룹의 구성 요소로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-118">They function as components of administrative groups.</span></span> <span data-ttu-id="721f3-119">이러한 그룹을 수정 하거나 직접 사용자를 추가 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-119">You should not modify these groups or add users directly to them.</span></span>

- <span data-ttu-id="721f3-120">**서비스 그룹** 이러한 그룹은 다양 한 비즈니스용 Skype Server 서비스에 액세스 하는 데 필요한 서비스 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-120">**Service groups** These groups are service accounts that are required to access various Skype for Business Server services.</span></span>

<span data-ttu-id="721f3-121">다음 표에서는 관리 그룹에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-121">The following table describes the administrative groups.</span></span>

<span data-ttu-id="721f3-122">**포리스트 준비 중에 만든 관리 그룹**</span><span class="sxs-lookup"><span data-stu-id="721f3-122">**Administrative Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="721f3-123">**관리 그룹**</span><span class="sxs-lookup"><span data-stu-id="721f3-123">**Administrative group**</span></span>|<span data-ttu-id="721f3-124">**설명**</span><span class="sxs-lookup"><span data-stu-id="721f3-124">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="721f3-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="721f3-125">RTCUniversalServerAdmins</span></span>  <br/> |<span data-ttu-id="721f3-126">구성원이 모든 서버 역할, 전역 설정 및 사용자를 비롯 한 서버 및 풀 설정을 관리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span>  <br/> |
|<span data-ttu-id="721f3-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="721f3-127">RTCUniversalUserAdmins</span></span>  <br/> |<span data-ttu-id="721f3-128">구성원이 사용자 설정을 관리 하 고 사용자를 한 서버나 풀에서 다른 서버로 이동할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-128">Allows members to manage user settings and move users from one server or pool to another.</span></span>  <br/> |
|<span data-ttu-id="721f3-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="721f3-129">RTCUniversalReadOnlyAdmins</span></span>  <br/> |<span data-ttu-id="721f3-130">구성원이 서버, 풀 및 사용자 설정을 읽을 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-130">Allows members to read server, pool, and user settings.</span></span>  <br/> |

<span data-ttu-id="721f3-131">다음 표에서는 인프라 그룹에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-131">The following table describes the infrastructure groups.</span></span>

<span data-ttu-id="721f3-132">**포리스트 준비 중 만들어진 인프라 그룹**</span><span class="sxs-lookup"><span data-stu-id="721f3-132">**Infrastructure Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="721f3-133">**인프라 그룹**</span><span class="sxs-lookup"><span data-stu-id="721f3-133">**Infrastructure group**</span></span>|<span data-ttu-id="721f3-134">**설명**</span><span class="sxs-lookup"><span data-stu-id="721f3-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="721f3-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="721f3-135">RTCUniversalGlobalWriteGroup</span></span>  <br/> |<span data-ttu-id="721f3-136">비즈니스용 Skype 서버의 전역 설정 개체에 대 한 쓰기 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-136">Grants write access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="721f3-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="721f3-137">RTCUniversalGlobalReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="721f3-138">비즈니스용 Skype 서버의 전역 설정 개체에 대 한 읽기 전용 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-138">Grants read-only access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="721f3-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="721f3-139">RTCUniversalUserReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="721f3-140">비즈니스용 Skype Server 사용자 설정에 읽기 전용 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-140">Grants read-only access to Skype for Business Server user settings.</span></span>  <br/> |
|<span data-ttu-id="721f3-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="721f3-141">RTCUniversalServerReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="721f3-142">비즈니스용 Skype 서버 설정에 대 한 읽기 전용 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-142">Grants read-only access to Skype for Business Server settings.</span></span> <span data-ttu-id="721f3-143">이 그룹은 풀 수준 설정에 대 한 액세스 권한이 없으며 개별 서버에만 해당 하는 설정에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span>  <br/> |
|<span data-ttu-id="721f3-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="721f3-144">RTCUniversalSBATechnicians</span></span>  <br/> |<span data-ttu-id="721f3-145">비즈니스용 Skype Server 구성에 읽기 전용 액세스 권한을 부여 하 고, 설치 중에 survivable 분기 기기의 로컬 관리자 그룹에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-145">Grants read-only access to Skype for Business Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span>  <br/> |

<span data-ttu-id="721f3-146">다음 표에서는 서비스 그룹에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-146">The following table describes the service groups.</span></span>

<span data-ttu-id="721f3-147">**포리스트 준비 중에 만든 서비스 그룹**</span><span class="sxs-lookup"><span data-stu-id="721f3-147">**Service Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="721f3-148">**서비스 그룹**</span><span class="sxs-lookup"><span data-stu-id="721f3-148">**Service group**</span></span>|<span data-ttu-id="721f3-149">**설명**</span><span class="sxs-lookup"><span data-stu-id="721f3-149">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="721f3-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="721f3-150">RTCHSUniversalServices</span></span>  <br/> |<span data-ttu-id="721f3-151">프런트 엔드 서버 및 Standard Edition 서버를 실행 하는 데 사용 되는 서비스 계정이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="721f3-152">이 그룹은 비즈니스용 Skype Server 전역 설정 및 Active Directory 사용자 개체에 대 한 서버 읽기/쓰기 액세스를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-152">This group allows servers read/write access to Skype for Business Server global settings and Active Directory user objects.</span></span>  <br/> |
|<span data-ttu-id="721f3-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="721f3-153">RTCComponentUniversalServices</span></span>  <br/> |<span data-ttu-id="721f3-154">A/V 회의 서버, 웹 서비스, 중재 서버, 보관 서버, 모니터링 서버를 실행 하는 데 사용 되는 서비스 계정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span>  <br/> |
|<span data-ttu-id="721f3-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="721f3-155">RTCProxyUniversalServices</span></span>  <br/> |<span data-ttu-id="721f3-156">비즈니스용 Skype 서버에 지 서버를 실행 하는 데 사용 되는 서비스 계정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-156">Includes service accounts used to run Skype for Business Server Edge Servers.</span></span>  <br/> |
|<span data-ttu-id="721f3-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="721f3-157">RTCUniversalConfigReplicator</span></span>  <br/> |<span data-ttu-id="721f3-158">비즈니스용 Skype 서버 중앙 관리 저장소 복제에 참가할 수 있는 서버를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-158">Includes servers that can participate in Skype for Business Server Central Management store replication.</span></span>  <br/> |
|<span data-ttu-id="721f3-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="721f3-159">RTCSBAUniversalServices</span></span>  <br/> |<span data-ttu-id="721f3-160">비즈니스용 Skype Server 설정에 읽기 전용 액세스 권한을 부여 하지만, survivable branch 서버 설치 및 survivable branch 기기 배포에 대 한 구성을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-160">Grants read-only access to Skype for Business Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span>  <br/> |

<span data-ttu-id="721f3-161">그런 다음 포리스트 준비는 다음과 같이 해당 인프라 그룹에 서비스 및 관리 그룹을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

- <span data-ttu-id="721f3-162">RTCUniversalServerAdmins는 RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, RTCUniversalUserReadOnlyGroup에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="721f3-163">RTCUniversalUserAdmins는 RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, RTCUniversalUserReadOnlyGroup의 구성원으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="721f3-164">RTCHSUniversalServices, RTCComponentUniversalServices 및 RTCUniversalReadOnlyAdmins는 RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, RTCUniversalUserReadOnlyGroup의 구성원으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="721f3-165">포리스트 준비는 또한 다음과 같은 RBAC (역할 기반 액세스 제어) 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

- <span data-ttu-id="721f3-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="721f3-166">CSAdministrator</span></span>

- <span data-ttu-id="721f3-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="721f3-167">CSArchivingAdministrator</span></span>

- <span data-ttu-id="721f3-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="721f3-168">CSHelpDesk</span></span>

- <span data-ttu-id="721f3-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="721f3-169">CSLocationAdministrator</span></span>

- <span data-ttu-id="721f3-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="721f3-170">CSResponseGroupAdministrator</span></span>

- <span data-ttu-id="721f3-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="721f3-171">CSServerAdministrator</span></span>

- <span data-ttu-id="721f3-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="721f3-172">CSUserAdministrator</span></span>

- <span data-ttu-id="721f3-173">Csviewadministrator</span><span class="sxs-lookup"><span data-stu-id="721f3-173">CSViewOnlyAdministrator</span></span>

- <span data-ttu-id="721f3-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="721f3-174">CSVoiceAdministrator</span></span>

- <span data-ttu-id="721f3-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="721f3-175">CsPersistentChatAdministator</span></span>

- <span data-ttu-id="721f3-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="721f3-176">CsResponseGroupManager</span></span>

<span data-ttu-id="721f3-177">RBAC 역할 및 각에 대해 허용 되는 작업에 대 한 자세한 내용은 계획 설명서의 [역할 기반 액세스 제어](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="721f3-177">For details about RBAC roles and the tasks allowed for each, see [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) in the Planning documentation.</span></span>

<span data-ttu-id="721f3-178">포리스트 준비는 개인 Ace를 모두 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="721f3-179">비즈니스용 Skype 서버에서 사용 하는 전역 설정 컨테이너에 개인 Ace를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-179">It creates private ACEs on the global settings container used by Skype for Business Server.</span></span> <span data-ttu-id="721f3-180">이 컨테이너는 비즈니스용 Skype Server 에서만 사용 되며, 전역 설정을 저장 하는 위치에 따라 루트 도메인의 구성 컨테이너 또는 시스템 컨테이너에 위치 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-180">This container is used only by Skype for Business Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="721f3-181">포리스트 준비로 만든 공개 Ace는 다음 표에 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

<span data-ttu-id="721f3-182">**포리스트 준비로 만든 공개 Ace**</span><span class="sxs-lookup"><span data-stu-id="721f3-182">**Public ACEs created by Forest Preparation**</span></span>


| <span data-ttu-id="721f3-183">**ACE**</span><span class="sxs-lookup"><span data-stu-id="721f3-183">**ACE**</span></span>                                                                 | <span data-ttu-id="721f3-184">**RTCUniversalGlobalReadOnlyGroup**</span><span class="sxs-lookup"><span data-stu-id="721f3-184">**RTCUniversalGlobalReadOnlyGroup**</span></span> |
|:------------------------------------------------------------------------|:------------------------------------|
| <span data-ttu-id="721f3-185">루트 도메인 시스템 컨테이너 읽기 (상속 되지 않음)**\\**\*</span><span class="sxs-lookup"><span data-stu-id="721f3-185">Read root domain System Container (not inherited) **\\**\*</span></span> <br/>        | <span data-ttu-id="721f3-186">축</span><span class="sxs-lookup"><span data-stu-id="721f3-186">X</span></span>  <br/>                            |
| <span data-ttu-id="721f3-187">구성의 DisplaySpecifiers 컨테이너 읽기 (상속 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="721f3-187">Read Configuration's DisplaySpecifiers container (not inherited)</span></span>  <br/> | <span data-ttu-id="721f3-188">축</span><span class="sxs-lookup"><span data-stu-id="721f3-188">X</span></span>  <br/>                            |

> [!NOTE]
> <span data-ttu-id="721f3-189"><strong>\\</strong>\* 상속 되지 않은 Ace는 이러한 컨테이너 아래의 자식 개체에 대 한 액세스를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-189"><strong>\\</strong>\*ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="721f3-190">상속 된 Ace는 이러한 컨테이너 아래에 있는 자식 개체에 대 한 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-190">ACEs that are inherited grant access to child objects under these containers.</span></span>

<span data-ttu-id="721f3-191">구성 컨테이너의 구성 명명 컨텍스트 아래에서 포리스트 준비는 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

- <span data-ttu-id="721f3-192">사용자, 연락처 및 InetOrgPersons에 대 한 언어 표시 지정자의 adminContextMenu 및 adminPropertyPages 특성 아래에 **RTC 속성** 페이지의 **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** 항목을 추가 합니다 (예: CN = 사용자 표시, CN = 409, CN = DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="721f3-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="721f3-193">사용자 및 연락처 클래스에 적용 되는 **확장 권한** 바로 아래에 **Controlaccessright** 의 **RTCPropertySet** 개체를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

- <span data-ttu-id="721f3-194">사용자, 연락처, OU 및 DomainDNS 클래스에 적용 되는 **확장 권한** **바로** 아래에 controltype의 **RTCUserSearchPropertySet** 개체를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="721f3-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

- <span data-ttu-id="721f3-195">각 OU (조직 구성 단위) 표시 지정자의 **extraColumns** 특성 아래에 **msRTCSIP-PrimaryUserAddress** 를 추가 (예: Cn = ORGANIZATIONALUNIT-display, CN = 409, cn = displayspecifiers) 하 고 다음 값을 복사 합니다. 기본 표시의 **extraColumns** 특성 (예: cn = Default-DISPLAY, cn = 409, Cn = displayspecifiers).</span><span class="sxs-lookup"><span data-stu-id="721f3-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="721f3-196">사용자, 연락처에 대 한 각 언어 표시 지정자의 **Attributedisplaynames** 특성 아래에 **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, **msRTCSIP-userenabled** 필터링 특성을 추가 합니다. 및 InetOrgPerson 개체 (예를 들어 영어: CN = 사용자 표시, CN = 409, CN = DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="721f3-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>


