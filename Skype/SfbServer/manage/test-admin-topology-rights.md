---
title: 비즈니스용 Skype 서버에서 관리 토폴로지 권한 테스트
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
description: 비즈니스용 Skype 서버에서 토폴로지 권한을 테스트 하는 방법
ms.openlocfilehash: 1664a7e7d2b202b596a882e4b393cc15220806c9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817314"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a><span data-ttu-id="516e0-103">비즈니스용 Skype 서버에서 관리 토폴로지 권한 테스트</span><span class="sxs-lookup"><span data-stu-id="516e0-103">Testing admin topology rights in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="516e0-104">확인 일정</span><span class="sxs-lookup"><span data-stu-id="516e0-104">Verification schedule</span></span>|<span data-ttu-id="516e0-105">최초 비즈니스용 Skype 서버 배포 이후.</span><span class="sxs-lookup"><span data-stu-id="516e0-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="516e0-106">필요한 경우 사용 권한 관련 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="516e0-107">테스트 도구</span><span class="sxs-lookup"><span data-stu-id="516e0-107">Testing tool</span></span>|<span data-ttu-id="516e0-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="516e0-108">Windows PowerShell</span></span>|
|<span data-ttu-id="516e0-109">권한이 필요 함</span><span class="sxs-lookup"><span data-stu-id="516e0-109">Permissions required</span></span>|<span data-ttu-id="516e0-110">비즈니스용 Skype Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br/><br/><span data-ttu-id="516e0-111">Windows PowerShell의 원격 인스턴스를 사용 하는 경우 사용자는 테스트-CsSetupPermission cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="516e0-112">이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="516e0-113">Get-CsAdminRole \| 위치-개체 {$ _. Cmdlet-"테스트-CsSetupPermission"} 일치</span><span class="sxs-lookup"><span data-stu-id="516e0-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsSetupPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="516e0-114">설명</span><span class="sxs-lookup"><span data-stu-id="516e0-114">Description</span></span>

<span data-ttu-id="516e0-115">기본적으로 도메인 관리자만 비즈니스용 Skype 서버 토폴로지를 사용 하도록 설정 하 고 비즈니스용 Skype 서버 인프라를 크게 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-115">By default, only domain administrators can enable a Skype for Business Server topology and make large changes to the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="516e0-116">이 문제는 도메인 관리자와 비즈니스용 Skype 서버 관리자가 한 곳에서 동일 하 게 작동 하는 동안에는 문제가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-116">This won't be a problem as long as your domain administrators and your Skype for Business Server administrators are one and the same.</span></span> <span data-ttu-id="516e0-117">대부분의 조직에서 비즈니스용 Skype 서버 관리자는 전체 도메인에 대 한 관리 권한을 보유 하 고 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-117">In many organizations, Skype for Business Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="516e0-118">기본적으로이는 RTCUniversalServerAdmins 그룹의 구성원으로 정의 된 이러한 관리자가 비즈니스용 Skype 서버 토폴로지 변경 내용을 만들 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-118">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Skype for Business Server topology changes.</span></span> <span data-ttu-id="516e0-119">RTCUniversalServerAdmins 그룹의 구성원에 게 토폴로지 변경 권한을 부여 하려면 [부여-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) cmdlet을 사용 하 여 필요한 Active Directory 권한을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-119">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>
 
<span data-ttu-id="516e0-120">테스트-CsSetupPermission cmdlet은 비즈니스용 Skype Server를 설치 하는 데 필요한 사용 권한이 나 해당 구성 요소 중 하나가 지정 된 Active Directory 컨테이너에 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-120">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Skype for Business Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="516e0-121">사용 권한이 할당 되지 않은 경우에는 허용-CsSetupPermission cmdlet을 실행 하 여 RTCUniversalServerAdmins 그룹의 구성원에 게 비즈니스용 Skype 서버를 설치 하 고 사용할 수 있는 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-121">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Skype for Business Server.</span></span>

## <a name="running-the-test"></a><span data-ttu-id="516e0-122">테스트 실행</span><span class="sxs-lookup"><span data-stu-id="516e0-122">Running the test</span></span>

<span data-ttu-id="516e0-123">Active Directory 컨테이너에 대 한 설정 권한이 할당 되었는지 확인 하려면 테스트-CsSetupPermission 권한 cmdlet을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-123">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="516e0-124">검사할 컨테이너의 고유 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-124">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="516e0-125">예를 들어이 명령은 컨테이너 ou = CsServers, dc = litwareinc, dc = com에 대 한 설정 권한을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-125">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

<span data-ttu-id="516e0-126">자세한 내용은 [테스트-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="516e0-126">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="516e0-127">성공 또는 실패 확인</span><span class="sxs-lookup"><span data-stu-id="516e0-127">Determining success or failure</span></span>

<span data-ttu-id="516e0-128">테스트-CsSetupPermission 권한 값이 Active Directory 컨테이너에 이미 설정 되어 있는 것으로 확인 되 면 cmdlet은 True를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-128">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="516e0-129">False</span><span class="sxs-lookup"><span data-stu-id="516e0-129">True</span></span> 

<span data-ttu-id="516e0-130">권한이 설정 되지 않은 경우 테스트-CsSetupPermission은 False 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-130">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="516e0-131">일반적으로이 값은 많은 경고 메시지에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-131">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="516e0-132">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-132">For example:</span></span>

<span data-ttu-id="516e0-133">경고: ACE (액세스 제어 항목) atl-cs-001\RTCUniversalServerAdmins 허용 ExtendedRight; 않아야 않아야 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="516e0-133">WARNING: Access control entry (ACE) atl-cs-001\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span> 

<span data-ttu-id="516e0-134">경고: "CN = Computers, DC = litwareinc, DC = com" 개체의 Ace (액세스 제어 항목)가 준비 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-134">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="516e0-135">해제</span><span class="sxs-lookup"><span data-stu-id="516e0-135">False</span></span> 

<span data-ttu-id="516e0-136">경고: "테스트-CsSetupPermission" 처리가 경고와 함께 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-136">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="516e0-137">이 실행 중에 "2" 경고가 기록 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-137">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="516e0-138">경고: 자세한 결과는 "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html"에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-138">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="516e0-139">테스트가 실패할 수 있는 이유</span><span class="sxs-lookup"><span data-stu-id="516e0-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="516e0-140">드문 경우이 아니지만 일반적으로 지정 된 Active Directory 컨테이너에 대해 설정 권한이 할당 되지 않는다는 테스트-CsSetupPermission 권한이 실패할 경우</span><span class="sxs-lookup"><span data-stu-id="516e0-140">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="516e0-141">이러한 권한은 부여-CsSetupPermission cmdlet을 사용 하 여 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-141">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="516e0-142">예를 들어이 명령은 도메인 litwareinc.com의 컴퓨터 컨테이너에 대 한 설치 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="516e0-142">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

<span data-ttu-id="516e0-143">자세한 내용은 [테스트-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="516e0-143">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>
