---
title: 'Lync Server 2013: 컴퓨터, 사용자 또는 InetOrgPerson 컨테이너에서 사용 권한 상속이 비활성화 됨'
description: 'Lync Server 2013: 컴퓨터, 사용자 또는 InetOrgPerson 컨테이너에서 사용 권한 상속이 사용 되지 않도록 설정 되었습니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a619ccd00e328ccef2e3b9eef4d64b190bdbdfd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545164"
---
# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="7e836-103">Lync Server 2013의 컴퓨터, 사용자 또는 InetOrgPerson 컨테이너에서 사용 권한 상속이 비활성화 됨</span><span class="sxs-lookup"><span data-stu-id="7e836-103">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e836-104">_**마지막으로 수정 된 항목:** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="7e836-104">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="7e836-105">잠긴 Active Directory 도메인 서비스에서 사용자 및 컴퓨터 개체는 사용 권한 상속이 사용 하지 않도록 설정 된 특정 Ou (조직 구성 단위)에 포함 되는 경우가 많고, 관리 위임을 보호 하 고 Gpo (그룹 정책 개체)를 사용 하 여 보안 정책을 적용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-105">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="7e836-106">도메인 준비 및 서버 정품 인증 Lync Server 2013에 필요한 Ace (액세스 제어 항목)를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-106">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="7e836-107">사용 권한 상속이 사용 하지 않도록 설정 된 경우 Lync Server 보안 그룹은 이러한 Ace를 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-107">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="7e836-108">이러한 사용 권한이 상속 되지 않으면 Lync Server 보안 그룹은 설정에 액세스할 수 없으며 다음과 같은 두 가지 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-108">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="7e836-109">사용자, InetOrgPersons 및 연락처를 관리 하 고 서버를 운영 하려면 Lync Server 보안 그룹에 각 사용자의 속성 집합, RTC (실시간 통신), RTC 사용자 검색 및 공용 정보에 대 한 도메인 준비 절차에 따라 설정 된 Ace가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-109">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="7e836-110">사용 권한 상속이 비활성화되면 보안 그룹이 이러한 ACE를 상속하지 못하며 서버나 사용자를 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-110">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="7e836-111">서버 및 풀을 검색 하려면 Lync Server를 실행 하는 서버가 Microsoft 컨테이너 및 서버 개체를 포함 하는 컴퓨터 관련 개체에서 정품 인증을 통해 설정 된 Ace를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-111">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="7e836-112">사용 권한 상속이 비활성화되면 보안 그룹, 서버 및 풀이 이러한 ACE를 상속하지 않으므로 이러한 ACE를 활용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-112">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="7e836-113">이러한 문제를 해결 하기 위해 Lync Server에서는 **부여-CsOuPermission** cmdlet을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-113">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="7e836-114">이 cmdlet은 지정 된 컨테이너와 조직 단위 및 컨테이너 또는 조직 단위 내의 개체에 대해 필요한 Lync Server Ace를 직접 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-114">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="7e836-115">도메인 준비 실행 후 사용자, InetOrgPerson 및 연락처 개체에 대한 사용 권한 설정</span><span class="sxs-lookup"><span data-stu-id="7e836-115">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="7e836-116">사용 권한 상속이 비활성화된 경우 잠겨 있는 Active Directory 환경에서는 도메인 준비 중에 도메인 내의 사용자 또는 InetOrgPerson 개체를 보유하는 컨테이너나 조직 구성 단위에 대해 필요한 ACE가 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-116">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="7e836-117">이 상황에서는 사용 권한 상속이 비활성화된 사용자 또는 InetOrgPerson 개체가 있는 각 컨테이너나 OU에 대해 **Grant-CsOuPermission** cmdlet를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-117">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="7e836-118">중앙 포리스트 토폴로지가 있는 경우 대화 상대 개체를 보유하는 컨테이너나 OU에 대해서도 이 절차를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-118">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="7e836-119">중앙 포리스트 토폴로지에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync Server 2013에서 지 원하는 Active Directory 토폴로지](lync-server-2013-supported-active-directory-topologies.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7e836-119">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="7e836-120">ObjectType 매개 변수는 개체 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-120">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="7e836-121">OU 매개 변수는 조직 구성 단위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-121">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="7e836-122">이 cmdlet는 지정된 컨테이너나 OU 및 컨테이너 내의 사용자 또는 InetOrgPerson 개체에 대해 필요한 ACE를 직접 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-122">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="7e836-123">이 명령이 실행 되는 OU에 User 또는 InetOrgPerson 개체가 있는 하위 Ou가 있으면 해당 권한이 해당 개체에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-123">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="7e836-124">각 하위 OU에서 개별적으로이 명령을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-124">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="7e836-125">이것은 Lync 호스팅 배포 (예: 상위 OU = OCS 테 넌 트, DC = CONTOSO, DC = LOCAL 및 child OU = Tenant1, OU = OCS 테 넌 트, dc = LOCAL)와 같은 일반적인 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-125">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="7e836-126">이 cmdlet를 실행하려면 Domain Admins 그룹의 구성원 자격과 동등한 사용자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-126">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="7e836-127">인증 된 사용자 Ace도 잠긴 환경에서 제거 된 경우에는 [Lync Server 2013에서 인증 된 사용자 사용 권한을 제거](lync-server-2013-authenticated-user-permissions-are-removed.md) 하거나 Enterprise Admins 그룹의 구성원 인 계정을 사용 하 여 포리스트 루트 도메인의 관련 컨테이너나 ou에 대 한 읽기 액세스 ace를이 계정에 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-127">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="7e836-128">**사용자, InetOrgPerson 및 연락처 개체에 대해 필요한 ACE를 설정하려면**</span><span class="sxs-lookup"><span data-stu-id="7e836-128">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="7e836-129">Domain Admins 그룹의 구성원이거나 이와 동등한 사용자 권한을 가진 계정을 사용하여 도메인에 가입된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-129">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="7e836-130">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-130">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7e836-131">을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-131">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="7e836-132">Domain 매개 변수를 지정하지 않는 경우에는 로컬 도메인이 기본값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-132">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="7e836-133">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-133">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="7e836-134">로그 파일에서 **\<Success\>** 각 작업의 끝에 있는 실행 결과를 찾아서 사용 권한이 설정 되었는지 확인 한 다음 로그 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-134">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="7e836-135">또는 다음 명령을 실행하여 사용 권한이 설정되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-135">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="7e836-136">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-136">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="7e836-137">도메인 준비 실행 후 컴퓨터 개체에 대한 사용 권한 설정</span><span class="sxs-lookup"><span data-stu-id="7e836-137">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="7e836-138">사용 권한 상속이 비활성화된 경우 잠겨 있는 Active Directory 환경에서는 도메인 준비 중에 도메인 내의 컴퓨터 개체를 보유하는 컨테이너나 OU에 대해 필요한 ACE가 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-138">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="7e836-139">이러한 상황에서는 사용 권한 상속이 사용 하지 않도록 설정 된 Lync Server를 실행 하는 컴퓨터가 있는 각 컨테이너 또는 OU에서 **Grant-CsOuPermission** cmdlet을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-139">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="7e836-140">ObjectType 매개 변수는 개체 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-140">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="7e836-141">이 절차는 지정된 컨테이너에 대해 필요한 ACE를 직접 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-141">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="7e836-142">이 cmdlet를 실행하려면 Domain Admins 그룹의 구성원 자격과 동등한 사용자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-142">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="7e836-143">인증 된 사용자 Ace도 제거 된 경우에는 [Lync Server 2013에서 인증 된 사용자 사용 권한을 제거](lync-server-2013-authenticated-user-permissions-are-removed.md) 하거나 Enterprise Admins 그룹의 구성원 인 계정을 사용 하 여 포리스트 루트 도메인의 관련 컨테이너에 대해이 계정에 대 한 읽기 액세스 ace를 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-143">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="7e836-144">**컴퓨터 개체에 대해 필요한 ACE를 설정하려면**</span><span class="sxs-lookup"><span data-stu-id="7e836-144">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="7e836-145">Domain Admins 그룹의 구성원이거나 이와 동등한 사용자 권한을 가진 계정을 사용하여 도메인 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-145">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="7e836-146">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7e836-147">을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-147">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="7e836-148">Domain 매개 변수를 지정하지 않는 경우에는 로컬 도메인이 기본값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-148">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="7e836-149">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-149">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="7e836-150">예제 로그 파일 C: \\ 로그OUPermissions.xml에서는 \\ **\<Success\>** 각 작업 끝에 있는 실행 결과를 찾아서 오류가 없는지 확인 한 다음 로그를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-150">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="7e836-151">다음 cmdlet를 실행하여 사용 권한을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-151">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="7e836-152">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-152">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e836-153">잠긴 Active Directory 환경의 포리스트 루트 도메인에서 도메인 준비를 실행 하는 경우 Lync Server에 Active Directory 스키마 및 구성 컨테이너에 대 한 액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-153">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="7e836-154">인증 된 기본 사용자 권한이 AD DS의 스키마 또는 구성 컨테이너에서 제거 된 경우에는 schema &nbsp; Admins 그룹의 구성원 (스키마 컨테이너) 또는 Enterprise Admins 그룹 (구성 컨테이너)만 지정 된 컨테이너에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-154">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="7e836-155">Setup.exe, Lync Server 관리 셸 cmdlet 및 Lync Server 제어판에는 이러한 컨테이너에 대 한 액세스 권한이 필요 하기 때문에 설치를 실행 하는 사용자에 게 Schema Admins 및 Enterprise Admins 그룹 멤버 자격에 해당 하는 사용자 권한이 없으면 설치 및 관리 도구의 설치가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-155">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="7e836-156">이 문제를 해결하려면 RTCUniversalGlobalWriteGroup 그룹에 해당 스키마 및 구성 컨테이너에 대한 읽기/쓰기 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e836-156">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

