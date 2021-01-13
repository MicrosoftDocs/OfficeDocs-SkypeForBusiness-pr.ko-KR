---
title: 비즈니스용 Skype 서버에서 관리자 토폴로지 권한 테스트
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 비즈니스용 Skype 서버에서 토폴로지 권한을 테스트하는 방법
ms.openlocfilehash: a6bbebd44387911fdb69679a16ab052c673f0b10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832848"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a><span data-ttu-id="06516-103">비즈니스용 Skype 서버에서 관리자 토폴로지 권한 테스트</span><span class="sxs-lookup"><span data-stu-id="06516-103">Testing admin topology rights in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="06516-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="06516-104">Verification schedule</span></span>|<span data-ttu-id="06516-105">초기 비즈니스용 Skype 서버 배포 후.</span><span class="sxs-lookup"><span data-stu-id="06516-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="06516-106">권한 관련 문제가 발생하는 경우 필요한 경우</span><span class="sxs-lookup"><span data-stu-id="06516-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="06516-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="06516-107">Testing tool</span></span>|<span data-ttu-id="06516-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="06516-108">Windows PowerShell</span></span>|
|<span data-ttu-id="06516-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="06516-109">Permissions required</span></span>|<span data-ttu-id="06516-110">비즈니스용 Skype 서버 관리 셸을 사용하여 로컬로 실행할 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06516-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br/><br/><span data-ttu-id="06516-111">원격 응용 Windows PowerShell 사용하여 실행할 경우 사용자에게 Test-CsSetupPermission cmdlet을 실행할 수 있는 권한이 있는 RBAC 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06516-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="06516-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 표시하기 위해 다음 명령 프롬프트에서 Windows PowerShell 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="06516-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="06516-113">Get-CsAdminRole Where-Object \| {$_를 사용합니다. Cmdlets -match "Test-CsSetupPermission"}</span><span class="sxs-lookup"><span data-stu-id="06516-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsSetupPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="06516-114">설명</span><span class="sxs-lookup"><span data-stu-id="06516-114">Description</span></span>

<span data-ttu-id="06516-115">기본적으로 도메인 관리자만 비즈니스용 Skype 서버 토폴로지와 비즈니스용 Skype 서버 인프라를 크게 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06516-115">By default, only domain administrators can enable a Skype for Business Server topology and make large changes to the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="06516-116">도메인 관리자와 비즈니스용 Skype 서버 관리자가 하나인 경우 이 문제는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="06516-116">This won't be a problem as long as your domain administrators and your Skype for Business Server administrators are one and the same.</span></span> <span data-ttu-id="06516-117">대부분의 조직에서 비즈니스용 Skype 서버 관리자는 전체 도메인에 대한 관리 권한을 보유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06516-117">In many organizations, Skype for Business Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="06516-118">기본적으로 이러한 관리자(RTCUniversalServerAdmins 그룹의 구성원으로 정의)는 비즈니스용 Skype 서버 토폴로지 변경을 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06516-118">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Skype for Business Server topology changes.</span></span> <span data-ttu-id="06516-119">RTCUniversalServerAdmins 그룹의 구성원에게 토폴로지 변경 권한을 부여하려면 [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet을 사용하여 필요한 Active Directory 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06516-119">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>
 
<span data-ttu-id="06516-120">이 Test-CsSetupPermission cmdlet은 비즈니스용 Skype 서버 또는 해당 구성 요소 중 하나를 설치하는 데 필요한 사용 권한이 지정된 Active Directory 컨테이너에 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="06516-120">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Skype for Business Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="06516-121">사용 권한이 할당되지 않은 경우 Grant-CsSetupPermission cmdlet을 실행하여 RTCUniversalServerAdmins 그룹의 구성원에게 비즈니스용 Skype 서버를 설치하고 사용하도록 설정할 수 있는 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06516-121">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Skype for Business Server.</span></span>

## <a name="running-the-test"></a><span data-ttu-id="06516-122">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="06516-122">Running the test</span></span>

<span data-ttu-id="06516-123">Active Directory 컨테이너에 대한 설치 권한이 할당되어 있는지 확인하려면 Test-CsSetupPermission cmdlet을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="06516-123">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="06516-124">확인할 컨테이너의 고유 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="06516-124">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="06516-125">예를 들어 다음 명령은 컨테이너 ou=CsServers,dc=litwareinc,dc=com에 대한 설치 권한을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="06516-125">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

<span data-ttu-id="06516-126">자세한 내용은 [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="06516-126">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="06516-127">성공 또는 실패 결정</span><span class="sxs-lookup"><span data-stu-id="06516-127">Determining success or failure</span></span>

<span data-ttu-id="06516-128">Active Directory Test-CsSetupPermission 필요한 권한이 이미 설정되어 있는지 확인하면 cmdlet은 True 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="06516-128">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="06516-129">True</span><span class="sxs-lookup"><span data-stu-id="06516-129">True</span></span> 

<span data-ttu-id="06516-130">권한이 설정되지 않은 경우 Test-CsSetupPermission False 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="06516-130">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="06516-131">이 값은 일반적으로 많은 경고 메시지로 묶입니다.</span><span class="sxs-lookup"><span data-stu-id="06516-131">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="06516-132">예제:</span><span class="sxs-lookup"><span data-stu-id="06516-132">For example:</span></span>

<span data-ttu-id="06516-133">경고: ACE(액세스 제어 항목) atl-cs-001\RTCUniversalServerAdmins; 허용; ExtendedRight; 없음; 없음; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="06516-133">WARNING: Access control entry (ACE) atl-cs-001\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span> 

<span data-ttu-id="06516-134">경고: "CN=Computers,DC=litwareinc,DC=com" 개체의 A AC(액세스 제어 항목)가 준비되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06516-134">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="06516-135">False</span><span class="sxs-lookup"><span data-stu-id="06516-135">False</span></span> 

<span data-ttu-id="06516-136">경고: "Test-CsSetupPermission" 처리가 경고로 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="06516-136">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="06516-137">이 실행 중에 "2" 경고가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="06516-137">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="06516-138">경고: 자세한 결과는 "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html"에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06516-138">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="06516-139">테스트가 실패한 이유</span><span class="sxs-lookup"><span data-stu-id="06516-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="06516-140">예외는 드물지만 예외가 Test-CsSetupPermission 오류가 발생하면 일반적으로 지정된 Active Directory 컨테이너에 대해 설치 권한이 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06516-140">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="06516-141">이러한 사용 권한은 이 cmdlet을 사용하여 할당할 Grant-CsSetupPermission 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06516-141">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="06516-142">예를 들어 다음 명령은 도메인의 Computers 컨테이너에 설치 권한을 litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="06516-142">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

<span data-ttu-id="06516-143">자세한 내용은 [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="06516-143">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>
