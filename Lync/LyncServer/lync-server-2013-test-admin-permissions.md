---
title: 'Lync Server 2013: 관리자 권한 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d12707cbbd03181b5606c835d50bb2f173f10da
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-admin-permissions-in-lync-server-2013"></a><span data-ttu-id="4a0ee-102">Lync Server 2013의 관리자 권한 테스트</span><span class="sxs-lookup"><span data-stu-id="4a0ee-102">Test admin permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a0ee-103">_**마지막으로 수정 된 항목:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="4a0ee-103">_**Topic Last Modified:** 2014-08-18_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a0ee-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="4a0ee-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="4a0ee-105">초기 Lync Server 배포 후</span><span class="sxs-lookup"><span data-stu-id="4a0ee-105">After initial Lync Server deployment.</span></span> <span data-ttu-id="4a0ee-106">사용 권한 관련 문제가 발생 하는 경우 필요에 따라</span><span class="sxs-lookup"><span data-stu-id="4a0ee-106">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a0ee-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="4a0ee-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="4a0ee-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a0ee-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a0ee-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="4a0ee-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="4a0ee-110">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="4a0ee-111">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우, 사용자에 게는 CsOUPermission cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="4a0ee-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="4a0ee-113">설명</span><span class="sxs-lookup"><span data-stu-id="4a0ee-113">Description</span></span>

<span data-ttu-id="4a0ee-114">Lync Server 2013 1을 설치할 때 설치 프로그램에서 수행 하는 작업의 RTCUniversalUserAdmins 그룹에는 사용자, 컴퓨터, 연락처, 응용 프로그램 연락처 및 InetOrg persons를 관리 하는 데 필요한 Active Directory 사용 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-114">When you install Lync Server 2013 one of the tasks that were performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="4a0ee-115">사용 하지 않도록 설정 되어 있는 경우 Active Directory 설치 프로그램에서 해당 사용 권한 상속을 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-115">If you have disabled permission inheritance in Active Directory setup won't be able to assign those permissions.</span></span> <span data-ttu-id="4a0ee-116">따라서 RTCUniversalUserAdmins 그룹의 구성원은 Lync Server 엔터티를 관리할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-116">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Lync Server entities.</span></span> <span data-ttu-id="4a0ee-117">이러한 관리 권한은 도메인 관리자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-117">Those management privileges will only be available to domain administrators.</span></span>

<span data-ttu-id="4a0ee-118">테스트-CsOUPermission cmdlet은 사용자, 컴퓨터 및 기타 개체를 관리 하는 데 필요한 권한이 Active Directory 컨테이너에 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-118">The Test-CsOUPermission cmdlet verifies that the required permissions that are needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="4a0ee-119">이러한 사용 권한을 설정 하지 않은 경우에는 [부여-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) cmdlet을 실행 하 여이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-119">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) cmdlet.</span></span>

<span data-ttu-id="4a0ee-120">RTCUniversalUserAdmins 그룹의 구성원 에게만 사용 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-120">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="4a0ee-121">이 cmdlet을 사용 하 여 임의의 사용자 또는 그룹에 사용 권한을 부여할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-121">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="4a0ee-122">다른 사용자나 그룹에 사용자 관리 권한을 부여 하려면 해당 사용자 또는 그룹을 RTCUniversalUserAdmins 그룹에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-122">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span>

<span data-ttu-id="4a0ee-123">OU 사용 권한에 대 한 자세한 내용은 [Lync Server 2013의 컴퓨터, 사용자 또는 InetOrgPerson 컨테이너에서 권한 상속을 사용 하지 않도록 설정](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)문서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-123">For more information on OU permissions, see the article [Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="4a0ee-124">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="4a0ee-124">Running the test</span></span>

<span data-ttu-id="4a0ee-125">컨테이너에 대 한 관리 권한이 설정 되어 있는지 확인 하려면 테스트-CsOUPermission cmdlet을 실행 하 고 컨테이너의 고유 이름과 확인 하려는 사용 권한 유형을 순서 대로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="4a0ee-126">예를 들어이 명령은 사용자 권한이 OU ou = Redmond, dc = litwareinc, dc = com에 설정 되어 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

<span data-ttu-id="4a0ee-127">단일 명령을 사용 하 여 여러 사용 권한을 확인 하려면 각 사용 권한 형식을 큰따옴표로 묶어서 묶고 해당 형식을 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="4a0ee-128">예를 들어 다음 명령은 사용자, 컴퓨터 및 연락처 사용 권한을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

<span data-ttu-id="4a0ee-129">자세한 내용은 [CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-129">For more information, see the help topic for the [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="4a0ee-130">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="4a0ee-130">Determining success or failure</span></span>

<span data-ttu-id="4a0ee-131">필요한 사용 권한이 이미 설정 된 경우에는 테스트-CsOUPermission이 한 단어 응답을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-131">If the required permissions have already been set then Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="4a0ee-132">참</span><span class="sxs-lookup"><span data-stu-id="4a0ee-132">True</span></span>

<span data-ttu-id="4a0ee-133">필요한 사용 권한을 설정 하지 않은 경우에는 테스트-CsOUPermission이 값 False를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-133">If the required permissions are not set then Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="4a0ee-134">이 값을 찾기 위해 잠시 검색 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="4a0ee-135">일반적으로는 몇 가지 관련 경고 내에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="4a0ee-136">예:</span><span class="sxs-lookup"><span data-stu-id="4a0ee-136">For example:</span></span>

<span data-ttu-id="4a0ee-137">경고: ACE (액세스 제어 항목) atl-cs-001\\RTCUniversalUserReadOnlyGroup; 통해 변수가 readproperty로 ContainerInherit; 파일만 bf967aba-0de6-11d0-00aa003049e2; d819615a-4738-3b9b-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="4a0ee-137">WARNING: access control entry (ACE) atl-cs-001\\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span>

<span data-ttu-id="4a0ee-138">경고: 개체 "OU = 북미, DC = atl-cs-001\\DC = LITWAREINC, DC = com"에 대 한 ace (액세스 제어 항목)가 준비 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\\DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="4a0ee-139">False</span><span class="sxs-lookup"><span data-stu-id="4a0ee-139">False</span></span>

<span data-ttu-id="4a0ee-140">경고: "테스트-CsOUPermission" 처리가 경고와 함께 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="4a0ee-141">이 실행 중에 경고 "2"가 기록 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-141">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="4a0ee-142">경고: 자세한 결과는 "C\\: Users\\Admin\\AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de"에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-142">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="4a0ee-143">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="4a0ee-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="4a0ee-144">일반적으로 RTCUniversalUserAdmins 그룹에 지정 된 사용 권한이 할당 되지 않은 것으로 나타내는 CsOUPermission에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-144">If Test-CsOUPermission fails that will usually mean that the specified permission has not been assign to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="4a0ee-145">이 문제를 해결 하 고 필요한 사용 권한을 할당 하려면 부여-CsOUPermission cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="4a0ee-146">예를 들어 다음 명령은 사용자, 연락처 및 inetOrgPersons에 대 한 OU 권한을 RTCUniversalUserAdmins 그룹에 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

<span data-ttu-id="4a0ee-147">자세한 내용은 부여-CsOUPermission cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a0ee-147">For more information, see the help topic for the Grant-CsOUPermission cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

