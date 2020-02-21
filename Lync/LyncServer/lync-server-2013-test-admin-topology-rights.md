---
title: 'Lync Server 2013: 관리 토폴로지 테스트 권한'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 050ba83b4598fc5ed8ed3d40d0b1aa02ba9356b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a><span data-ttu-id="efff1-102">Lync Server 2013의 관리 토폴로지 테스트 권한</span><span class="sxs-lookup"><span data-stu-id="efff1-102">Test admin topology rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efff1-103">_**마지막으로 수정 된 항목:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="efff1-103">_**Topic Last Modified:** 2016-12-08_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efff1-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="efff1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="efff1-105">초기 Lync Server 배포 후</span><span class="sxs-lookup"><span data-stu-id="efff1-105">After initial Lync Server deployment.</span></span> <span data-ttu-id="efff1-106">사용 권한 관련 문제가 발생 하는 경우 필요에 따라</span><span class="sxs-lookup"><span data-stu-id="efff1-106">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efff1-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="efff1-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="efff1-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="efff1-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efff1-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="efff1-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="efff1-110">Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="efff1-111">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우에는 사용자에 게 테스트-CsSetupPermission cmdlet을 실행할 수 있는 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="efff1-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="efff1-113">설명</span><span class="sxs-lookup"><span data-stu-id="efff1-113">Description</span></span>

<span data-ttu-id="efff1-114">기본적으로 도메인 관리자만 lync server 토폴로지를 사용 하도록 설정 하 고 Lync Server 인프라를 크게 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-114">By default, only domain administrators can enable a Lync Server topology and make large changes to the Lync Server infrastructure.</span></span> <span data-ttu-id="efff1-115">이는 도메인 관리자와 Lync Server 관리자가 1과 동일한 경우에는 문제가 되지 않습니다. 대부분의 조직에서는 Lync Server 관리자가 전체 도메인에 대 한 관리 권한을 보유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-115">This won't be a problem as long as your domain administrators and your Lync Server administrators are one and the same.In many organizations Lync Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="efff1-116">기본적으로 RTCUniversalServerAdmins 그룹의 구성원으로 정의 된 이러한 관리자는 Lync Server 토폴로지를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-116">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Lync Server topology changes.</span></span> <span data-ttu-id="efff1-117">RTCUniversalServerAdmins 그룹의 구성원에 게 토폴로지를 변경할 수 있는 권한을 부여 하려면 [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet을 사용 하 여 필요한 Active Directory 권한을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-117">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>

<span data-ttu-id="efff1-118">테스트-CsSetupPermission cmdlet은 Lync Server 또는 해당 구성 요소 중 하나를 설치 하는 데 필요한 사용 권한이 지정 된 Active Directory 컨테이너에 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-118">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Lync Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="efff1-119">사용 권한이 할당 되지 않은 경우에는 RTCUniversalServerAdmins 그룹의 구성원에 게 Lync Server를 설치 하 고 사용 하도록 설정할 수 있는 권한을 부여 하려면 Grant-CsSetupPermission cmdlet을 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-119">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="efff1-120">부여-CsSetupPermission에서 할당 된 사용 권한의 자세한 목록은 블로그 게시물 <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">부여-cssetuppermission 및 Grant-Cssetuppermission</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="efff1-120">For a detailed list of permissions assigned by Grant-CsSetupPermission, see the blog post <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission and Grant-CsOUPermission</A>.</span></span>



</div>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="efff1-121">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="efff1-121">Running the test</span></span>

<span data-ttu-id="efff1-122">Active Directory 컨테이너에 대해 설치 권한이 할당 되었는지 확인 하려면 테스트-CsSetupPermission cmdlet을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-122">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="efff1-123">확인할 컨테이너의 고유 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-123">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="efff1-124">예를 들어이 명령은 컨테이너 ou = CsServers, dc = litwareinc, dc = com에 대 한 설치 권한을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-124">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

<span data-ttu-id="efff1-125">자세한 내용은 [테스트-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="efff1-125">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="efff1-126">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="efff1-126">Determining success or failure</span></span>

<span data-ttu-id="efff1-127">테스트-CsSetupPermission에서 필요한 사용 권한이 Active Directory 컨테이너에 이미 설정 된 것으로 확인 되 면 cmdlet은 True 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-127">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="efff1-128">참</span><span class="sxs-lookup"><span data-stu-id="efff1-128">True</span></span>

<span data-ttu-id="efff1-129">사용 권한을 설정 하지 않으면 테스트-CsSetupPermission에서 False 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-129">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="efff1-130">일반적으로이 값은 많은 경고 메시지에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-130">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="efff1-131">예:</span><span class="sxs-lookup"><span data-stu-id="efff1-131">For example:</span></span>

<span data-ttu-id="efff1-132">경고: ACE (액세스 제어 항목) atl-cs-001\\RTCUniversalServerAdmins; 통해 ExtendedRight; None None 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="efff1-132">WARNING: Access control entry (ACE) atl-cs-001\\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span>

<span data-ttu-id="efff1-133">경고: "CN = Computers, DC = litwareinc, DC = com" 개체의 Ace (액세스 제어 항목)가 준비 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-133">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="efff1-134">False</span><span class="sxs-lookup"><span data-stu-id="efff1-134">False</span></span>

<span data-ttu-id="efff1-135">경고: "테스트-CsSetupPermission" 처리가 경고와 함께 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-135">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="efff1-136">이 실행 중에 경고 "2"가 기록 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-136">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="efff1-137">경고: 자세한 결과는 "C\\: Users\\Admin\\AppData\\Local\\Temp\\Test-cssetuppermission-1da99ba6-abe2-45e4-8b16-dfd244763118"에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-137">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="efff1-138">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="efff1-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="efff1-139">드문 경우는 아니지만, 일반적으로 테스트-CsSetupPermission에 오류가 발생 하 여 지정 된 Active Directory 컨테이너에 대해 설치 권한이 할당 되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-139">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="efff1-140">이러한 사용 권한은 부여-CsSetupPermission cmdlet을 사용 하 여 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-140">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="efff1-141">예를 들어이 명령은 litwareinc.com 도메인의 컴퓨터 컨테이너에 설치 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="efff1-141">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

<span data-ttu-id="efff1-142">자세한 내용은 [테스트-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="efff1-142">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

