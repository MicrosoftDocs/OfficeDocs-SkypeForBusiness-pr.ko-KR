---
title: 비즈니스용 Skype 서버에서 관리자 권한 테스트
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
description: 비즈니스용 Skype 서버에서 관리자 권한을 테스트하는 방법
ms.openlocfilehash: 535911c26bac5e3f1dadb2c8d59cffe82dc20c7a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122402"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="e5d66-103">비즈니스용 Skype 서버에서 관리자 권한 테스트</span><span class="sxs-lookup"><span data-stu-id="e5d66-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="e5d66-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="e5d66-104">Verification schedule</span></span>|<span data-ttu-id="e5d66-105">초기 비즈니스용 Skype 서버 배포 후</span><span class="sxs-lookup"><span data-stu-id="e5d66-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="e5d66-106">사용 권한 관련 문제가 발생하는 경우 필요한 경우</span><span class="sxs-lookup"><span data-stu-id="e5d66-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="e5d66-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="e5d66-107">Testing tool</span></span>|<span data-ttu-id="e5d66-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5d66-108">Windows PowerShell</span></span>|
|<span data-ttu-id="e5d66-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="e5d66-109">Permissions required</span></span>|<span data-ttu-id="e5d66-110">비즈니스용 Skype 서버 관리 셸을 사용하여 로컬로 실행할 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="e5d66-111">원격 응용 Windows PowerShell 사용하여 실행할 경우 사용자에게 Test-CsOUPermission cmdlet을 실행할 수 있는 권한이 있는 RBAC 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="e5d66-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 표시하기 위해 이 cmdlet 프롬프트에서 Windows PowerShell 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="e5d66-113">Get-CsAdminRole Where-Object \| {$_를 사용합니다. Cmdlet -match "Test-CsOUPermission"}</span><span class="sxs-lookup"><span data-stu-id="e5d66-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="e5d66-114">설명</span><span class="sxs-lookup"><span data-stu-id="e5d66-114">Description</span></span>

<span data-ttu-id="e5d66-115">비즈니스용 Skype 서버를 설치할 때 설치 프로그램에서 수행한 작업 중 하나는 RTCUniversalUserAdmins 그룹에 사용자, 컴퓨터, 연락처, 응용 프로그램 연락처 및 InetOrg 사용자를 관리하는 데 필요한 Active Directory 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="e5d66-116">Active Directory에서 사용 권한 상속을 사용하지 않도록 설정한 경우 설치 프로그램이 해당 권한을 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="e5d66-117">따라서 RTCUniversalUserAdmins 그룹의 구성원은 비즈니스용 Skype 서버 엔터티를 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="e5d66-118">이러한 관리 권한은 도메인 관리자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="e5d66-119">이 Test-CsOUPermission cmdlet은 사용자, 컴퓨터 및 기타 개체를 관리하는 데 필요한 사용 권한이 Active Directory 컨테이너에 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="e5d66-120">이러한 사용 권한이 설정되지 않은 경우 [Grant-CsOUPermission cmdlet을](/powershell/module/skype/Grant-CsOUPermission)실행하여 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="e5d66-121">이 Grant-CsOUPermission RTCUniversalUserAdmins 그룹의 구성원에게만 권한을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="e5d66-122">이 cmdlet을 사용하여 임의의 사용자 또는 그룹에 사용 권한을 부여할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="e5d66-123">다른 사용자 또는 그룹에 사용자 관리 권한을 부여하려면 해당 사용자 또는 그룹을 RTCUniversalUserAdmins 그룹에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="e5d66-124">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="e5d66-124">Running the test</span></span>

<span data-ttu-id="e5d66-125">관리 권한이 컨테이너에 대해 설정되어 있는지 확인하려면 Test-CsOUPermission cmdlet을 실행하고 그 다음에 컨테이너의 고유 이름과 확인할 사용 권한 유형별로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="e5d66-126">예를 들어 다음 명령은 OU ou=Redmond,dc=litwareinc,dc=com에 대한 사용자 권한이 설정되어 있는지 여부를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="e5d66-127">단일 명령을 사용하여 여러 사용 권한을 확인하려면 각 사용 권한 유형을 따오기 표시로 묶은 다음 각 사용 권한 유형을 각 유형에 각 묶은 다음 각 사용 권한을 각 유형에 각 묶어 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="e5d66-128">예를 들어 다음 명령은 사용자, 컴퓨터 및 연락처 권한을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="e5d66-129">자세한 내용은 [cmdlet의 도움말 Test-CsOUPermission 참조하세요.](/powershell/module/skype/test-csoupermission)</span><span class="sxs-lookup"><span data-stu-id="e5d66-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e5d66-130">성공 또는 실패 결정</span><span class="sxs-lookup"><span data-stu-id="e5d66-130">Determining success or failure</span></span>

<span data-ttu-id="e5d66-131">필요한 사용 권한이 이미 설정된 경우 Test-CsOUPermission 한 단어 응답이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="e5d66-132">True</span><span class="sxs-lookup"><span data-stu-id="e5d66-132">True</span></span>

<span data-ttu-id="e5d66-133">필요한 사용 권한이 설정되지 않은 경우 Test-CsOUPermission False 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="e5d66-134">이 값을 찾으기 위해 잠시 검색해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="e5d66-135">일반적으로 함께 제공되는 여러 경고 안에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="e5d66-136">예:</span><span class="sxs-lookup"><span data-stu-id="e5d66-136">For example:</span></span>

<span data-ttu-id="e5d66-137">경고: ACE(액세스 제어 항목) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="e5d66-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="e5d66-138">경고: "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" 개체의 AC(액세스 제어 항목)가 준비되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="e5d66-139">False</span><span class="sxs-lookup"><span data-stu-id="e5d66-139">False</span></span> 

<span data-ttu-id="e5d66-140">경고: "Test-CsOUPermission" 처리가 경고로 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="e5d66-141">이 실행 중에 "2" 경고가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="e5d66-142">경고: 자세한 결과는 "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html"에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e5d66-143">테스트가 실패한 이유</span><span class="sxs-lookup"><span data-stu-id="e5d66-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="e5d66-144">오류가 Test-CsOUPermission 경우 일반적으로 지정된 권한이 RTCUniversalUserAdmins 그룹에 할당되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="e5d66-145">이 문제를 해결하고 cmdlet을 사용하여 필요한 권한을 할당할 Grant-CsOUPermission 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="e5d66-146">예를 들어 다음 명령은 사용자, 연락처 및 inetOrgPersons에 대한 OU 권한을 RTCUniversalUserAdmins 그룹에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e5d66-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="e5d66-147">자세한 내용은 [cmdlet의 도움말 Test-CsOUPermission 참조하세요.](/powershell/module/skype/test-csoupermission)</span><span class="sxs-lookup"><span data-stu-id="e5d66-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](/powershell/module/skype/test-csoupermission).</span></span>