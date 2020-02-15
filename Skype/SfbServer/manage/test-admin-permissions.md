---
title: 비즈니스용 Skype 서버에서 관리자 권한 테스트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 비즈니스용 Skype 서버에서 관리자 권한을 테스트 하는 방법
ms.openlocfilehash: 1e06c87dcf0e436d72c510a2bc8d9f2aa2051620
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030161"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="a3b61-103">비즈니스용 Skype 서버에서 관리자 권한 테스트</span><span class="sxs-lookup"><span data-stu-id="a3b61-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="a3b61-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="a3b61-104">Verification schedule</span></span>|<span data-ttu-id="a3b61-105">초기 비즈니스용 Skype 서버 배포 후</span><span class="sxs-lookup"><span data-stu-id="a3b61-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="a3b61-106">사용 권한 관련 문제가 발생 하는 경우 필요에 따라</span><span class="sxs-lookup"><span data-stu-id="a3b61-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="a3b61-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="a3b61-107">Testing tool</span></span>|<span data-ttu-id="a3b61-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3b61-108">Windows PowerShell</span></span>|
|<span data-ttu-id="a3b61-109">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="a3b61-109">Permissions required</span></span>|<span data-ttu-id="a3b61-110">비즈니스용 Skype 서버 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="a3b61-111">Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우, 사용자에 게는 CsOUPermission cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="a3b61-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="a3b61-113">Get-CsAdminRole \| (Where-개체 {$ _) Cmdlet-"테스트-CsOUPermission"}를 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="a3b61-114">설명</span><span class="sxs-lookup"><span data-stu-id="a3b61-114">Description</span></span>

<span data-ttu-id="a3b61-115">비즈니스용 Skype 서버를 설치 하는 경우 설치 프로그램에서 수행 하는 작업 중 하나에서 사용자, 컴퓨터, 연락처, 응용 프로그램 연락처 및 InetOrg를 관리 하는 데 필요한 Active Directory 사용 권한을 RTCUniversalUserAdmins 그룹에 제공 합니다. 사람들이.</span><span class="sxs-lookup"><span data-stu-id="a3b61-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="a3b61-116">Active Directory에서 사용 권한 상속을 사용 하지 않도록 설정한 경우에는 설치 프로그램에서 해당 사용 권한을 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="a3b61-117">따라서 RTCUniversalUserAdmins 그룹의 구성원은 비즈니스용 Skype 서버 엔터티를 관리할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="a3b61-118">이러한 관리 권한은 도메인 관리자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="a3b61-119">테스트-CsOUPermission cmdlet은 사용자, 컴퓨터 및 기타 개체를 관리 하는 데 필요한 권한이 Active Directory 컨테이너에 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="a3b61-120">이러한 사용 권한을 설정 하지 않은 경우에는 [부여-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)을 실행 하 여이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="a3b61-121">RTCUniversalUserAdmins 그룹의 구성원 에게만 사용 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="a3b61-122">이 cmdlet을 사용 하 여 임의의 사용자 또는 그룹에 사용 권한을 부여할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="a3b61-123">다른 사용자나 그룹에 사용자 관리 권한을 부여 하려면 해당 사용자 또는 그룹을 RTCUniversalUserAdmins 그룹에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="a3b61-124">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="a3b61-124">Running the test</span></span>

<span data-ttu-id="a3b61-125">컨테이너에 대 한 관리 권한이 설정 되어 있는지 확인 하려면 테스트-CsOUPermission cmdlet을 실행 하 고 컨테이너의 고유 이름과 확인 하려는 사용 권한 유형을 순서 대로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="a3b61-126">예를 들어이 명령은 사용자 권한이 OU ou = Redmond, dc = litwareinc, dc = com에 설정 되어 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="a3b61-127">단일 명령을 사용 하 여 여러 사용 권한을 확인 하려면 각 사용 권한 형식을 큰따옴표로 묶어서 묶고 해당 형식을 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="a3b61-128">예를 들어 다음 명령은 사용자, 컴퓨터 및 연락처 사용 권한을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="a3b61-129">자세한 내용은 [CsOUPermission cmdlet에 대 한 도움말 항목](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a3b61-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a3b61-130">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="a3b61-130">Determining success or failure</span></span>

<span data-ttu-id="a3b61-131">필요한 사용 권한이 이미 설정 된 경우에는 테스트-CsOUPermission에서 한 단어 응답을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="a3b61-132">참</span><span class="sxs-lookup"><span data-stu-id="a3b61-132">True</span></span>

<span data-ttu-id="a3b61-133">필요한 사용 권한을 설정 하지 않은 경우 테스트-CsOUPermission은 False 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="a3b61-134">이 값을 찾기 위해 잠시 검색 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="a3b61-135">일반적으로는 몇 가지 관련 경고 내에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="a3b61-136">예:</span><span class="sxs-lookup"><span data-stu-id="a3b61-136">For example:</span></span>

<span data-ttu-id="a3b61-137">경고: ACE (액세스 제어 항목) atl-cs-001\RTCUniversalUserReadOnlyGroup; 통해 변수가 readproperty로 ContainerInherit; 파일만 bf967aba-0de6-11d0-00aa003049e2; d819615a-4738-3b9b-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="a3b61-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="a3b61-138">경고: "OU = 북미, DC = atl-cs-001\DC = litwareinc, DC = com" 개체의 Ace (액세스 제어 항목)가 준비 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="a3b61-139">False</span><span class="sxs-lookup"><span data-stu-id="a3b61-139">False</span></span> 

<span data-ttu-id="a3b61-140">경고: "테스트-CsOUPermission" 처리가 경고와 함께 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="a3b61-141">이 실행 중에 경고 "2"가 기록 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="a3b61-142">경고: 자세한 결과는 "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html"에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a3b61-143">테스트가 실패 한 이유</span><span class="sxs-lookup"><span data-stu-id="a3b61-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="a3b61-144">테스트-CsOUPermission에 오류가 발생 하는 경우 일반적으로 지정 된 사용 권한이 RTCUniversalUserAdmins 그룹에 할당 되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="a3b61-145">이 문제를 해결 하 고 필요한 사용 권한을 할당 하려면 부여-CsOUPermission cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="a3b61-146">예를 들어 다음 명령은 사용자, 연락처 및 inetOrgPersons에 대 한 OU 권한을 RTCUniversalUserAdmins 그룹에 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b61-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="a3b61-147">자세한 내용은 [CsOUPermission cmdlet에 대 한 도움말 항목](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a3b61-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span></span>
