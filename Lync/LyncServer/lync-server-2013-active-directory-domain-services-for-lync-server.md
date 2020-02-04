---
title: 'Lync Server 2013: Lync Server 용 Active Directory 도메인 서비스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ac4b4da954fd792559d2160ce457aec91cb0ac6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="3fa73-102">Lync Server 2013의 Active Directory 도메인 서비스</span><span class="sxs-lookup"><span data-stu-id="3fa73-102">Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fa73-103">_**마지막으로 수정한 주제:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="3fa73-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="3fa73-104">Active Directory 도메인 서비스는 Windows Server 2003, Windows Server 2008, Windows Server 2012 및 Windows Server 2012 R2 네트워크에 대 한 디렉터리 서비스로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-104">Active Directory Domain Services functions as the directory service for Windows Server 2003, Windows Server 2008, Windows Server 2012, and Windows Server 2012 R2 networks.</span></span> <span data-ttu-id="3fa73-105">Active Directory 도메인 서비스는 Microsoft Lync Server 2013 보안 인프라가 빌드되는 기반 역할도 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-105">Active Directory Domain Services also serves as the foundation on which the Microsoft Lync Server 2013 security infrastructure is built.</span></span> <span data-ttu-id="3fa73-106">이 섹션의 목적은 Lync Server 2013에서 Active Directory 도메인 서비스를 사용 하 여 IM, 웹 회의, 미디어, 음성에 대 한 신뢰할 수 있는 환경을 만드는 방법을 설명 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-106">The purpose of this section is to describe how Lync Server 2013 uses Active Directory Domain Services to create a trustworthy environment for IM, Web conferencing, media, and voice.</span></span> <span data-ttu-id="3fa73-107">Active Directory 도메인 서비스에 대 한 Lync Server 확장에 대 한 자세한 내용과 Active Directory 도메인 서비스의 환경 준비에 대 한 자세한 내용은 배포 설명서에서 [Lync server 2013에 대 한 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-active-directory-domain-services.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3fa73-107">For details about Lync Server extensions to Active Directory Domain Services and about preparing your environment for Active Directory Domain Services, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span> <span data-ttu-id="3fa73-108">Windows Server 네트워크용 Active Directory 도메인 서비스의 역할에 대 한 자세한 내용은 사용 중인 운영 체제 버전에 대 한 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3fa73-108">For details about the role of Active Directory Domain Services in Windows Server networks, see the documentation for the version of the operating system you are using.</span></span>

<span data-ttu-id="3fa73-109">Lync Server 2013는 Active Directory 도메인 서비스를 사용 하 여 다음을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-109">Lync Server 2013 uses Active Directory Domain Services to store:</span></span>

  - <span data-ttu-id="3fa73-110">전역 설정 포리스트에서 Lync Server 2013을 실행 하는 모든 서버에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-110">Global settings that all servers running Lync Server 2013 in a forest require.</span></span>

  - <span data-ttu-id="3fa73-111">포리스트에서 Lync Server 2013을 실행 하는 모든 서버의 역할을 식별 하는 서비스 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-111">Service information that identifies the roles of all servers running Lync Server 2013 in a forest.</span></span>

  - <span data-ttu-id="3fa73-112">일부 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="3fa73-112">Some user settings.</span></span>

<div>

## <a name="active-directory-infrastructure"></a><span data-ttu-id="3fa73-113">Active Directory 인프라</span><span class="sxs-lookup"><span data-stu-id="3fa73-113">Active Directory Infrastructure</span></span>

<span data-ttu-id="3fa73-114">Active Directory의 인프라 요구 사항에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-114">Infrastructure requirements for Active Directory include the following:</span></span>

  - <span data-ttu-id="3fa73-115">도메인 컨트롤러에 대 한 운영 체제 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3fa73-115">Operating system requirements for domain controllers</span></span>

  - <span data-ttu-id="3fa73-116">도메인 및 포리스트 기능 수준 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3fa73-116">Domain and forest functional level requirements</span></span>

  - <span data-ttu-id="3fa73-117">글로벌 카탈로그 도메인 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3fa73-117">Global catalog domain requirements</span></span>

<span data-ttu-id="3fa73-118">자세한 내용은 배포 설명서의 [Lync Server 2013에 대 한 Active Directory 인프라 요구 사항을](lync-server-2013-active-directory-infrastructure-requirements.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3fa73-118">For details, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a><span data-ttu-id="3fa73-119">Active Directory 도메인 서비스 준비</span><span class="sxs-lookup"><span data-stu-id="3fa73-119">Active Directory Domain Services Preparation</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3fa73-120">시스템 컨테이너 대신 구성 컨테이너에 전역 설정을 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-120">We recommend that you deploy global settings to the Configuration container instead of the System container.</span></span> <span data-ttu-id="3fa73-121">이는 보안을 강화 하지는 않지만 일부 Active Directory 도메인 서비스 토폴로지의 확장성이 향상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-121">This does not enhance security, but can result in scalability improvements for some Active Directory Domain Services topologies.</span></span> <span data-ttu-id="3fa73-122">Microsoft Office 통신 서버 2007에서 마이그레이션하고 있고 시스템 컨테이너를 사용 하지만 구성 컨테이너를 사용 하려는 경우에는 업그레이드 준비를 수행 하기 전에 시스템 컨테이너에서 설정을 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-122">If you are migrating from Microsoft Office Communications Server 2007 and have used the System container but plan to use the Configuration container, you MUST move the settings in the System container BEFORE you do any upgrade preparations.</span></span> <span data-ttu-id="3fa73-123">시스템 컨테이너 설정을 구성 컨테이너로 마이그레이션하려면의 <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>Office Communications Server 2007 전역 설정 마이그레이션 도구를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3fa73-123">To migrate your System container settings to the Configuration container, see Office Communications Server 2007 Global Settings Migration Tool at <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>.</span></span>



</div>

<span data-ttu-id="3fa73-124">Lync Server 2013을 배포할 때 첫 번째 단계는 Active Directory 도메인 서비스를 준비 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-124">When deploying Lync Server 2013, the first step is to prepare Active Directory Domain Services.</span></span> <span data-ttu-id="3fa73-125">Lync Server 2013에 대 한 Active Directory 도메인 서비스를 준비 하려면 다음 세 단계로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-125">Preparing Active Directory Domain Services for Lync Server 2013 consists of the following three steps:</span></span>

  - <span data-ttu-id="3fa73-126">**스키마 준비**.</span><span class="sxs-lookup"><span data-stu-id="3fa73-126">**Prepare Schema**.</span></span> <span data-ttu-id="3fa73-127">이 작업은 Active Directory 도메인 서비스의 스키마를 확장 하 여 Lync Server 2013에 대 한 클래스 및 특성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-127">This task extends the schema in Active Directory Domain Services to include classes and attributes specific to Lync Server 2013.</span></span> <span data-ttu-id="3fa73-128">스키마 준비에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 Active Directory 스키마 준비 실행](lync-server-2013-running-schema-preparation.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3fa73-128">For details about preparing the schema, see [Running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="3fa73-129">자세한 내용은 [Office Communications Server 2007 R2에서 Lync Server 2013로 마이그레이션을](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3fa73-129">For more information, see [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span></span>

  - <span data-ttu-id="3fa73-130">**포리스트 준비**.</span><span class="sxs-lookup"><span data-stu-id="3fa73-130">**Prepare Forest**.</span></span> <span data-ttu-id="3fa73-131">이 작업은 해당 설정 및 개체에 대 한 액세스를 제어 하는 유니버설 서비스 및 관리 그룹과 함께 포리스트 루트 도메인에 전역 설정과 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-131">This task creates global settings and objects in the forest root domain, along with the universal service and administrative groups that govern access to these settings and objects.</span></span> <span data-ttu-id="3fa73-132">포리스트 준비에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013의 포리스트 준비 실행](lync-server-2013-running-forest-preparation.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3fa73-132">For details about preparing the forest, see [Running forest preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="3fa73-133">**도메인 준비**.</span><span class="sxs-lookup"><span data-stu-id="3fa73-133">**Prepare Domain**.</span></span> <span data-ttu-id="3fa73-134">이 작업은 도메인 내에서 사용자를 호스트 하 고 관리 하는 권한을 부여 하는 유니버설 그룹에 필요한 Ace (액세스 제어 항목)를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-134">This task adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="3fa73-135">이 작업은 Lync Server 2013 및 Lync Server 사용자가 거주 하는 모든 도메인을 실행 하는 서버를 배포 하려는 모든 도메인에서 완료 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-135">This task must be completed in all domains where you want to deploy servers running Lync Server 2013 and any domains where your Lync Server users reside.</span></span> <span data-ttu-id="3fa73-136">도메인을 준비 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013에 대 한 도메인 준비 실행](lync-server-2013-running-domain-preparation.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3fa73-136">For details about preparing the domain, see [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="3fa73-137">Active Directory를 준비 하는 전체 프로세스 및 각 단계를 수행 하는 데 필요한 권한 및 사용 권한은 배포 설명서의 [Lync Server 2013에 대 한 Active directory 인프라 요구 사항을](lync-server-2013-active-directory-infrastructure-requirements.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3fa73-137">For an overview of the complete process for preparing Active Directory and the rights and permissions required to perform each step, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="universal-groups"></a><span data-ttu-id="3fa73-138">유니버설 그룹</span><span class="sxs-lookup"><span data-stu-id="3fa73-138">Universal Groups</span></span>

<span data-ttu-id="3fa73-139">포리스트를 준비 하는 동안 Lync Server 2013는 전역 설정 및 서비스에 액세스 하 고 관리 하는 권한이 있는 Active Directory 도메인 서비스 내에 다양 한 유니버설 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-139">During preparation of the forest, Lync Server 2013 creates various universal groups within Active Directory Domain Services that have permission to access and manage global settings and services.</span></span> <span data-ttu-id="3fa73-140">이러한 유니버설 그룹에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-140">These universal groups include:</span></span>

  - <span data-ttu-id="3fa73-141">**관리 그룹**.</span><span class="sxs-lookup"><span data-stu-id="3fa73-141">**Administrative groups**.</span></span> <span data-ttu-id="3fa73-142">이러한 그룹은 Lync Server 네트워크의 기본 관리자 역할을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-142">These groups define the fundamental administrator roles for a Lync Server network.</span></span> <span data-ttu-id="3fa73-143">포리스트를 준비 하는 동안 이러한 관리자 그룹은 Lync Server 인프라 그룹에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-143">During forest preparation, these administrator groups are added to Lync Server infrastructure groups.</span></span>

  - <span data-ttu-id="3fa73-144">**서비스 그룹**.</span><span class="sxs-lookup"><span data-stu-id="3fa73-144">**Service groups**.</span></span> <span data-ttu-id="3fa73-145">이러한 그룹은 Lync Server에서 제공 하는 다양 한 서비스에 액세스 하는 데 필요한 서비스 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-145">These groups are service accounts that are required to access various services provided by Lync Server.</span></span>

  - <span data-ttu-id="3fa73-146">**인프라 그룹**</span><span class="sxs-lookup"><span data-stu-id="3fa73-146">**Infrastructure groups**.</span></span> <span data-ttu-id="3fa73-147">이러한 그룹은 Lync Server 인프라의 특정 영역에 대 한 액세스 권한을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-147">These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="3fa73-148">관리 그룹의 구성 요소로 작동 하므로이를 수정 하거나 직접 사용자를 추가 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-148">They function as components of administrative groups, and you should not modify them or add users to them directly.</span></span> <span data-ttu-id="3fa73-149">포리스트를 준비 하는 동안 특정 서비스 및 관리 그룹이 해당 인프라 그룹에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-149">During forest preparation, specific service and administration groups are added to the appropriate infrastructure groups.</span></span>

<span data-ttu-id="3fa73-150">Lync Server에 대 한 광고를 준비할 때 생성 되는 특정 유니버설 그룹 및 인프라 그룹에 추가 되는 서비스 및 관리 그룹에 대 한 자세한 내용은 배포 설명서의 [Lync server 2013에서 포리스트 준비에의 한 변경 내용](lync-server-2013-changes-made-by-forest-preparation.md) 에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="3fa73-150">For details about the specific universal groups created when preparing AD for Lync Server, as well as the service and administration groups that get added to the infrastructure groups, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3fa73-151">Lync Server 2013는 windows Server 2012에서 Lync Server 2013를 실행 하는 서버에 대 한 유니버설 그룹과 도메인 컨트롤러용 Windows Server 2003 운영 체제를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-151">Lync Server 2013 supports the universal groups in the Windows Server 2012 for servers running Lync Server 2013, as well as Windows Server 2003 operating systems for domain controllers.</span></span> <span data-ttu-id="3fa73-152">유니버설 그룹의 구성원은 도메인 트리나 포리스트에 있는 모든 도메인의 다른 그룹 및 계정을 포함할 수 있으며, 도메인 트리나 포리스트의 모든 도메인에서 사용 권한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-152">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="3fa73-153">관리자 위임과 통합 된 유니버설 그룹 지원으로 Lync 서버 배포의 관리를 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-153">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="3fa73-154">예를 들어 관리자가 둘 다 관리할 수 있도록 한 도메인을 다른 도메인에 추가할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-154">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>



</div>

</div>

<div>

## <a name="role-based-access-control"></a><span data-ttu-id="3fa73-155">역할 기반 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="3fa73-155">Role-Based Access Control</span></span>

<span data-ttu-id="3fa73-156">유니버설 서비스 및 관리 그룹을 만들고 서비스 및 관리 그룹을 적절 한 유니버설 그룹에 추가 하는 것 외에도 포리스트 준비는 RBAC (역할 기반 액세스 제어) 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-156">In addition to creating universal service and administration groups and adding service and administration groups to the appropriate universal groups, forest preparation also creates Role-Based Access Control (RBAC) groups.</span></span> <span data-ttu-id="3fa73-157">포리스트 준비로 만든 특정 RBAC 그룹에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 포리스트 준비를 통해 변경한 내용을](lync-server-2013-changes-made-by-forest-preparation.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3fa73-157">For details about the specific RBAC groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="3fa73-158">RBAC 그룹에 대 한 자세한 내용은 [Lync Server 2013에 대 한 rbac (역할 기반 액세스 제어](lync-server-2013-role-based-access-control-rbac.md))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3fa73-158">For more information about RBAC groups, see [Role-based access control (RBAC) for Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span></span>

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a><span data-ttu-id="3fa73-159">Ace (액세스 제어 항목) 및 상속</span><span class="sxs-lookup"><span data-stu-id="3fa73-159">Access Control Entries (ACEs) and Inheritance</span></span>

<span data-ttu-id="3fa73-160">포리스트 준비는 개인 Ace를 만들고 자신이 만든 유니버설 그룹에 Ace를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-160">Forest preparation creates both private and public ACEs and, adding ACEs for the universal groups it creates.</span></span> <span data-ttu-id="3fa73-161">Lync Server에서 사용 하는 전역 설정 컨테이너에 특정 개인 Ace를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-161">It creates specific private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="3fa73-162">이 컨테이너는 Lync Server 에서만 사용 되며 전역 설정을 저장 하는 위치에 따라 루트 도메인의 구성 컨테이너 또는 시스템 컨테이너에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-162">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span>

<span data-ttu-id="3fa73-163">도메인 준비 단계에서는 도메인 내에서 사용자를 호스트 하 고 관리할 수 있는 권한을 부여 하는 유니버설 그룹에 필요한 Ace (액세스 제어 항목)를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-163">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="3fa73-164">도메인 준비는 도메인 루트 및 세 가지 기본 제공 컨테이너 (사용자, 컴퓨터 및 도메인 컨트롤러)에 Ace를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-164">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="3fa73-165">포리스트 준비 및 도메인 준비에 의해 만들어지고 추가 된 공개 Ace에 대 한 자세한 내용은 [Lync server 2013에서 포리스트 준비에의 한 변경](lync-server-2013-changes-made-by-forest-preparation.md) 내용과 배포 설명서의 [lync server 2013에서 도메인 준비에](lync-server-2013-changes-made-by-domain-preparation.md) 의 한 변경 사항에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="3fa73-165">For details about the public ACEs created and added by forest preparation and domain preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) and [Changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="3fa73-166">조직에서 보안 위험을 줄일 수 있도록 AD DS (Active Directory 도메인 서비스)를 잠그는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-166">Organizations often lock down Active Directory Domain Services (AD DS) to help mitigate security risks.</span></span> <span data-ttu-id="3fa73-167">그러나 잠겨 있는 Active Directory 환경은 Lync Server 2013에 필요한 권한을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-167">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="3fa73-168">여기에는 컨테이너 및 Ou에서 Ace를 제거 하 고 사용자, 연락처, InetOrgPerson 또는 컴퓨터 개체에 대 한 사용 권한 상속을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-168">This can include removal of ACEs from containers and OUs and disabling of permissions inheritance on User, Contact, InetOrgPerson, or Computer objects.</span></span> <span data-ttu-id="3fa73-169">Active Directory 환경 잠겨 있는 경우에는 컨테이너 및이를 필요로 하는 Ou에 대 한 사용 권한을 수동으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-169">In a locked down Active Directory environment, permissions must be set manually on containers and OUs that require them.</span></span> <span data-ttu-id="3fa73-170">자세한 내용은 배포 설명서의 [Lync Server 2013에서 잠겨진 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3fa73-170">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="server-information"></a><span data-ttu-id="3fa73-171">서버 정보</span><span class="sxs-lookup"><span data-stu-id="3fa73-171">Server Information</span></span>

<span data-ttu-id="3fa73-172">정품 인증 하는 동안 Lync Server 2013는 Active Directory 도메인 서비스의 다음 세 위치에 서버 정보를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-172">During activation, Lync Server 2013 publishes server information to the three following locations in Active Directory Domain Services:</span></span>

  - <span data-ttu-id="3fa73-173">Lync Server 2013이 설치 되어 있는 물리적 컴퓨터에 해당 하는 각 Active Directory 컴퓨터 개체의 SCP (서비스 연결 지점)입니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-173">A service connection point (SCP) on each Active Directory computer object corresponding to a physical computer on which Lync Server 2013 is installed.</span></span>

  - <span data-ttu-id="3fa73-174">**MsRTCSIP** 클래스의 컨테이너에서 만들어진 서버 개체</span><span class="sxs-lookup"><span data-stu-id="3fa73-174">Server objects created in the container of the **msRTCSIP-Pools** class.</span></span>

  - <span data-ttu-id="3fa73-175">토폴로지 작성기에 지정 된 신뢰할 수 있는 서버</span><span class="sxs-lookup"><span data-stu-id="3fa73-175">Trusted servers specified in Topology Builder.</span></span>

</div>

<div>

## <a name="service-connection-points"></a><span data-ttu-id="3fa73-176">서비스 연결 지점</span><span class="sxs-lookup"><span data-stu-id="3fa73-176">Service Connection Points</span></span>

<span data-ttu-id="3fa73-177">Active Directory 도메인 서비스의 각 Lync Server 2013 개체에는 RTC Services 라는 SCP가 있으며, 여기에는 각 컴퓨터를 식별 하는 다양 한 특성이 포함 되어 있으며 제공 하는 서비스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-177">Each Lync Server 2013 object in Active Directory Domain Services has an SCP called RTC Services, which in turn contains a number of attributes that identify each computer and specify the services that it provides.</span></span> <span data-ttu-id="3fa73-178">중요 한 SCP 특성 중에는 *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*및 *serviceBindingInformation*가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-178">Among the more important SCP attributes are *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*, and *serviceBindingInformation*.</span></span> <span data-ttu-id="3fa73-179">타사 자산 관리 응용 프로그램은 이러한 특성과 다른 SCP 특성에 대해 쿼리 하 여 배포에서 서버 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-179">Third-party asset management applications can retrieve server information across a deployment by querying against these and other SCP attributes.</span></span>

</div>

<div>

## <a name="active-directory-server-objects"></a><span data-ttu-id="3fa73-180">Active Directory 서버 개체</span><span class="sxs-lookup"><span data-stu-id="3fa73-180">Active Directory Server Objects</span></span>

<span data-ttu-id="3fa73-181">각 Lync Server 2013 서버 역할에는 해당 특성이 해당 역할에서 제공 하는 서비스를 정의 하는 해당 Active Directory 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-181">Each Lync Server 2013 server role has a corresponding Active Directory object whose attributes define the services provided by that role.</span></span> <span data-ttu-id="3fa73-182">또한 스탠더드 버전 서버를 정품 인증 하거나 Enterprise Edition 풀을 만들 때 Lync Server 2013에서 **MsRTCSIP 풀** 컨테이너에 새 **msRTCSIP 풀** 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-182">Also, when a Standard Edition server is activated, or when an Enterprise Edition pool is created, Lync Server 2013 creates a new **msRTCSIP-Pool** object in the **msRTCSIP-Pools** container.</span></span> <span data-ttu-id="3fa73-183">**MsRTCSIP** 클래스는 풀의 FQDN (정규화 된 도메인 이름)을 풀의 프런트 엔드 및 백 엔드 구성 요소 간 연결과 함께 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-183">The **msRTCSIP-Pool** class specifies the fully qualified domain name (FQDN) of the pool, along with the association between the front-end and back-end components of the pool.</span></span> <span data-ttu-id="3fa73-184">(스탠더드 버전 서버는 한 컴퓨터에서 앞 및 뒤 끝을 collocated 논리적 풀로 간주 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="3fa73-184">(A Standard Edition server is regarded as a logical pool whose front and back ends are collocated on a single computer.)</span></span>

</div>

<div>

## <a name="trusted-servers"></a><span data-ttu-id="3fa73-185">신뢰할 수 있는 서버</span><span class="sxs-lookup"><span data-stu-id="3fa73-185">Trusted Servers</span></span>

<span data-ttu-id="3fa73-186">Lync Server 2013에서 신뢰 하는 서버는 토폴로지 작성기를 실행 하 고 토폴로지를 게시할 때 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-186">In Lync Server 2013, trusted servers are the ones specified when you run Topology Builder and publish your topology.</span></span> <span data-ttu-id="3fa73-187">모든 서버 정보를 포함 하 여 게시 된 토폴로지가 중앙 관리 저장소에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-187">The published topology, including all the server information, is stored in the Central Management store.</span></span> <span data-ttu-id="3fa73-188">중앙 관리 저장소에 정의 된 서버만 신뢰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-188">Only servers defined in the Central Management store are trusted.</span></span> <span data-ttu-id="3fa73-189">Lync Server 2013에서 신뢰할 수 있는 서버는 다음 조건에 맞는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-189">In Lync Server 2013, a trusted server is one that meets the following criteria:</span></span>

  - <span data-ttu-id="3fa73-190">중앙 관리 저장소에 저장 된 토폴로지에서 서버의 FQDN이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-190">The FQDN of the server occurs in the topology stored in Central Management store.</span></span>

  - <span data-ttu-id="3fa73-191">서버는 신뢰할 수 있는 CA에서 유효한 인증서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-191">The server presents a valid certificate from a trusted CA.</span></span> <span data-ttu-id="3fa73-192">자세한 내용은 [Lync Server 2013의 인증서 인프라 요구 사항을](lync-server-2013-certificate-infrastructure-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3fa73-192">For details, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span></span>

<span data-ttu-id="3fa73-193">이러한 조건 중 하나라도 없으면 서버를 신뢰할 수 없고 연결이 거부 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-193">If either of these criteria is missing, the server is not trusted and connection with it is refused.</span></span> <span data-ttu-id="3fa73-194">이 double 요구 사항은 rogue 서버에서 유효한 서버의 FQDN을 사용 하려고 시도 하는 공격 가능성을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-194">This double requirement prevents a possible, if unlikely, attack in which a rogue server attempts to take over a valid server’s FQDN.</span></span>

<span data-ttu-id="3fa73-195">또한 lync server 2013 서버와 통신 하기 위해 Microsoft Office Communications Server 2007 R2 및 Microsoft Office Communications Server 2007 배포를 사용 하기 위해 Lync Server 2013는 포리스트를 준비 하는 동안 컨테이너를 만듭니다. 목록 보관 이전 릴리스에 대 한 신뢰할 수 있는 서버</span><span class="sxs-lookup"><span data-stu-id="3fa73-195">Additionally, to enable Microsoft Office Communications Server 2007 R2 and Microsoft Office Communications Server 2007 deployments to communicate with Lync Server 2013 servers, Lync Server 2013 creates containers during forest preparation for holding lists of trusted servers for previous releases.</span></span> <span data-ttu-id="3fa73-196">다음 표에서는 이전 배포와의 호환성을 사용 하도록 만들어진 컨테이너에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-196">The following table describes the containers created to enable compatibility with previous deployments.</span></span>

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a><span data-ttu-id="3fa73-197">이전 릴리스와의 호환성을 위해 신뢰할 수 있는 서버 목록과 해당 Active Directory 컨테이너</span><span class="sxs-lookup"><span data-stu-id="3fa73-197">Trusted Server Lists and Their Active Directory Containers for Compatibility with Previous Releases</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3fa73-198">신뢰 된 서버 목록</span><span class="sxs-lookup"><span data-stu-id="3fa73-198">Trusted server list</span></span></th>
<th><span data-ttu-id="3fa73-199">Active Directory 컨테이너</span><span class="sxs-lookup"><span data-stu-id="3fa73-199">Active Directory container</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fa73-200">스탠더드 버전 서버 및 엔터프라이즈 풀 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="3fa73-200">Standard Edition servers and Enterprise pool Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="3fa73-201">RTC 서비스/전역 설정</span><span class="sxs-lookup"><span data-stu-id="3fa73-201">RTC Service/Global Settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fa73-202">회의 서버</span><span class="sxs-lookup"><span data-stu-id="3fa73-202">Conferencing Servers</span></span></p></td>
<td><p><span data-ttu-id="3fa73-203">RTC 서비스/신뢰할 수 있는 MCUs</span><span class="sxs-lookup"><span data-stu-id="3fa73-203">RTC Service/Trusted MCUs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fa73-204">웹 구성 요소 서버</span><span class="sxs-lookup"><span data-stu-id="3fa73-204">Web Components Servers</span></span></p></td>
<td><p><span data-ttu-id="3fa73-205">RTC 서비스/TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="3fa73-205">RTC Service/TrustedWebComponentsServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fa73-206">중재 서버 및 Communicator Web Access 서버, 응용 프로그램 서버, 체감 품질를 사용 하는 등록 기관, A/V 회의 서비스 (타사 SIP 서버 이기도)</span><span class="sxs-lookup"><span data-stu-id="3fa73-206">Mediation Servers and Communicator Web Access Servers, Application Server, Registrar with QoE, A/V Conferencing Service (also 3rd-party SIP servers)</span></span></p></td>
<td><p><span data-ttu-id="3fa73-207">RTC 서비스/신뢰할 수 있는 서비스</span><span class="sxs-lookup"><span data-stu-id="3fa73-207">RTC Service/Trusted Services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fa73-208">프록시 서버</span><span class="sxs-lookup"><span data-stu-id="3fa73-208">Proxy Servers</span></span></p></td>
<td><p><span data-ttu-id="3fa73-209">Lync Server 2013는 프록시 서버에 대 한 이전 버전과의 호환성을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-209">Lync Server 2013 does not support backward compatibility for proxy servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3fa73-210">이전 릴리스의 신뢰 하는 서버를 지원 하려면 모범 사례 분석기 도구를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa73-210">To support trusted servers of previous releases, you must run the best practices analyzer tool.</span></span> <span data-ttu-id="3fa73-211">모범 사례 분석기를 실행 하는 방법에 대 [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633)한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3fa73-211">For details about running the best practices analyzer, see [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

