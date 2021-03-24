---
title: 비즈니스용 Skype 서버의 서비스 관리
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
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: 이 문서에서는 비즈니스용 Skype 서버 토폴로지에서 실행되는 서비스를 관리하는 방법을 설명합니다.
ms.openlocfilehash: d0669eab34795de3241c954f2eda593eda474193
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104384"
---
# <a name="manage-services-for-skype-for-business-server"></a><span data-ttu-id="27a05-103">비즈니스용 Skype 서버의 서비스 관리</span><span class="sxs-lookup"><span data-stu-id="27a05-103">Manage services for Skype for Business Server</span></span>

<span data-ttu-id="27a05-104">이 문서에서는 비즈니스용 Skype 서버 토폴로지에서 실행되는 서비스를 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-104">This article describes how to manage services running in a Skype for Business Server topology.</span></span>
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="27a05-105">비즈니스용 Skype 서버를 실행하는 컴퓨터 목록 보기</span><span class="sxs-lookup"><span data-stu-id="27a05-105">View a list of computers running Skype for Business Server</span></span>
<span data-ttu-id="27a05-106"><a name="view_list"> </a></span><span class="sxs-lookup"><span data-stu-id="27a05-106"><a name="view_list"> </a></span></span>

<span data-ttu-id="27a05-107">비즈니스용 Skype 서버 제어판을 사용하여 토폴로지에서 비즈니스용 Skype 서버를 실행하는 모든 컴퓨터의 목록을 보고 각 컴퓨터의 서비스 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-107">You can use Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business Server in your topology and see the service status of each.</span></span> <span data-ttu-id="27a05-108">컴퓨터, 풀 또는 사이트에 따라 목록을 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-108">You can sort the list by computer, pool, or site.</span></span> 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="27a05-109">비즈니스용 Skype 서버를 실행하는 컴퓨터의 목록을 표시</span><span class="sxs-lookup"><span data-stu-id="27a05-109">To view a list of computers running Skype for Business Server</span></span>

1. <span data-ttu-id="27a05-110">비즈니스용 Skype 서버에 대해 미리 정의한 관리 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-110">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="27a05-111">비즈니스용 Skype 서버에서 사용할 수 있는 미리 정의한 관리 역할에 대한 자세한 내용은 **Planning for Role-Based Access Control을 참조하세요.**</span><span class="sxs-lookup"><span data-stu-id="27a05-111">For details about the predefined administrative roles available in Skype for Business Server, see **Planning for Role-Based Access Control**.</span></span>   
2. <span data-ttu-id="27a05-112">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>   
3. <span data-ttu-id="27a05-113">왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-113">In the left navigation bar, click **Topology** and then click **Status**.</span></span>   
4. <span data-ttu-id="27a05-114">**상태** 페이지에서 다음을 필요한 대로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-114">On the **Status** page, do any of the following as needed:</span></span>
   - <span data-ttu-id="27a05-115">**컴퓨터**, **풀** 또는 **사이트** 열 머리글을 클릭한 다음 위쪽 화살표나 아래쪽 화살표를 클릭하여 목록을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-115">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span> 
   - <span data-ttu-id="27a05-116">**새로 고침** 을 클릭하여 최신 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-116">Click **Refresh** to view the most up-to-date list.</span></span>  
   - <span data-ttu-id="27a05-117">검색 필드에 컴퓨터 이름을 입력하여 특정 컴퓨터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-117">Search for a specific computer by typing the computer name in the search field.</span></span>
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a><span data-ttu-id="27a05-118">비즈니스용 Skype 서버에서 실행 중인 서비스 상태 보기</span><span class="sxs-lookup"><span data-stu-id="27a05-118">View the status of services running on a Skype for Business server</span></span>
<span data-ttu-id="27a05-119"><a name="view-status"> </a></span><span class="sxs-lookup"><span data-stu-id="27a05-119"><a name="view-status"> </a></span></span>

<span data-ttu-id="27a05-120">비즈니스용 Skype 서버 제어판을 사용하여 비즈니스용 Skype 서버 토폴로지의 특정 컴퓨터에서 실행 중인 모든 서비스를 보고 각 서비스의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-120">You can use Skype for Business Server Control Panel to view all the services that are running on a specific computer in your Skype for Business Server topology and see the status of each service.</span></span>
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="27a05-121">컴퓨터에서 실행되는 서비스 상태를 보려면</span><span class="sxs-lookup"><span data-stu-id="27a05-121">To view the status of services running on a computer</span></span>

1. <span data-ttu-id="27a05-122">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="27a05-123">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="27a05-124">왼쪽 탐색 표시줄에서 **토폴로지** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-124">In the left navigation bar, click **Topology**.</span></span> 
4. <span data-ttu-id="27a05-125">상태 **페이지에서** 필요한 경우 목록을 정렬하거나 검색하여 관심 있는 컴퓨터를 찾은 다음 컴퓨터 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-125">On the **Status** page, sort or search the list, as required, to find the computer you're interested in, and then click the computer name.</span></span>
5. <span data-ttu-id="27a05-126">다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-126">Do any of the following:</span></span>
   - <span data-ttu-id="27a05-127">컴퓨터에서 실행되는 서비스의 최신 상태를 보려면 **서비스 상태 가져오기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-127">To see the latest status of services running on the computer, click **Get service status**.</span></span>
   - <span data-ttu-id="27a05-128">컴퓨터에서 실행되는 특정 서비스 목록 및 각 서비스의 상태를 보려면 **속성** 을 클릭합니다. 목록으로 돌아오려면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-128">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a><span data-ttu-id="27a05-129">Windows Powershell cmdlet을 통해 서비스 상태 보기</span><span class="sxs-lookup"><span data-stu-id="27a05-129">Viewing service status with Windows Powershell cmdlets</span></span>

<span data-ttu-id="27a05-130">또한 **Get-CsWindowsService** cmdlet 및 Windows PowerShell 상태도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-130">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="27a05-131">비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-131">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="27a05-132">원격 Windows PowerShell 사용하여 비즈니스용 Skype 서버에 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를 참조하세요.](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="27a05-132">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="27a05-133">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-133">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-service-status"></a><span data-ttu-id="27a05-134">서비스 상태를 보려면</span><span class="sxs-lookup"><span data-stu-id="27a05-134">To view service status</span></span>

<span data-ttu-id="27a05-135">컴퓨터에서 서비스 상태를 확인하려면 비즈니스용 Skype 서버 관리 셸에 다음과 비슷한 명령을 입력한 다음 Enter를 눌러야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-135">To view service status on a computer, type a command similar to the following in the Skype for Business Server Management Shell and then press Enter:</span></span>
  
```PowerShell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

<span data-ttu-id="27a05-136">이 명령은 다음과 비슷한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-136">This command returns information similar to the following:</span></span>
  
|<span data-ttu-id="27a05-137">**RoleName**</span><span class="sxs-lookup"><span data-stu-id="27a05-137">**RoleName**</span></span>|<span data-ttu-id="27a05-138">**상태**</span><span class="sxs-lookup"><span data-stu-id="27a05-138">**Status**</span></span>|
|:-----|:-----|
|<span data-ttu-id="27a05-139">{W3SVC}</span><span class="sxs-lookup"><span data-stu-id="27a05-139">{W3SVC}</span></span>  <br/> |<span data-ttu-id="27a05-140">실행 중</span><span class="sxs-lookup"><span data-stu-id="27a05-140">Running</span></span>  <br/> |
|<span data-ttu-id="27a05-141">{CentralManagement}</span><span class="sxs-lookup"><span data-stu-id="27a05-141">{CentralManagement}</span></span>  <br/> | <span data-ttu-id="27a05-142">실행 중</span><span class="sxs-lookup"><span data-stu-id="27a05-142">Running</span></span> <br/> |
|<span data-ttu-id="27a05-143">{ClsAgent}</span><span class="sxs-lookup"><span data-stu-id="27a05-143">{ClsAgent}</span></span>  <br/> |<span data-ttu-id="27a05-144">실행 중</span><span class="sxs-lookup"><span data-stu-id="27a05-144">Running</span></span>  <br/> |
|<span data-ttu-id="27a05-145">{Registrar, UserServer, EdgeServer}</span><span class="sxs-lookup"><span data-stu-id="27a05-145">{Registrar, UserServer, EdgeServer}</span></span>  <br/> |<span data-ttu-id="27a05-146">실행 중</span><span class="sxs-lookup"><span data-stu-id="27a05-146">Running</span></span>  <br/> |
|<span data-ttu-id="27a05-147">{ApplicationServer}</span><span class="sxs-lookup"><span data-stu-id="27a05-147">{ApplicationServer}</span></span>  <br/> |<span data-ttu-id="27a05-148">실행 중</span><span class="sxs-lookup"><span data-stu-id="27a05-148">Running</span></span>  <br/> |
|<span data-ttu-id="27a05-149">{ConferencingServer}</span><span class="sxs-lookup"><span data-stu-id="27a05-149">{ConferencingServer}</span></span>  <br/> |<span data-ttu-id="27a05-150">실행 중</span><span class="sxs-lookup"><span data-stu-id="27a05-150">Running</span></span>  <br/> |
|<span data-ttu-id="27a05-151">{MediationServer}</span><span class="sxs-lookup"><span data-stu-id="27a05-151">{MediationServer}</span></span>  <br/> |<span data-ttu-id="27a05-152">실행 중</span><span class="sxs-lookup"><span data-stu-id="27a05-152">Running</span></span>  <br/> |
   
<span data-ttu-id="27a05-153">자세한 내용은 [Get-CsWindowsService를 참조합니다.](/powershell/module/skype/get-cswindowsservice.md?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="27a05-153">For details, see [Get-CsWindowsService](/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).</span></span>
  
## <a name="view-details-about-a-service"></a><span data-ttu-id="27a05-154">서비스에 대한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="27a05-154">View details about a service</span></span>
<span data-ttu-id="27a05-155"><a name="view_details"> </a></span><span class="sxs-lookup"><span data-stu-id="27a05-155"><a name="view_details"> </a></span></span>

<span data-ttu-id="27a05-156">비즈니스용 Skype 서버 제어판을 사용하여 토폴로지의 특정 컴퓨터에서 실행되는 각 서비스에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-156">You can use Skype for Business Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="27a05-157">구체적으로 연관된 데이터베이스, 포트 및 종속 서비스 등과 같은 세부 정보 및 각 서비스의 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-157">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>
  
### <a name="to-view-details-for-a-service"></a><span data-ttu-id="27a05-158">서비스에 대한 세부 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="27a05-158">To view details for a service</span></span>

1. <span data-ttu-id="27a05-159">비즈니스용 Skype 서버에 대해 미리 정의한 관리 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-159">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="27a05-160">비즈니스용 Skype 서버에서 사용할 수 있는 미리 정의한 관리 역할에 대한 자세한 내용은 **Planning for Role-Based Access Control을 참조하세요.**</span><span class="sxs-lookup"><span data-stu-id="27a05-160">For details about the predefined administrative roles available in Skype for Business Server, see **Planning for Role-Based Access Control**.</span></span>
2. <span data-ttu-id="27a05-161">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-161">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="27a05-162">왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-162">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="27a05-163">**상태** 페이지에서 목록을 정렬하거나 목록 전체를 검색한 다음 보려는 컴퓨터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-163">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>
5. <span data-ttu-id="27a05-164">**속성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-164">Click **Properties**.</span></span>
6. <span data-ttu-id="27a05-165">**컴퓨터 세부 정보 보기** 창에서 필요한 경우 서비스 목록을 정렬하고 보려는 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-165">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>
7. <span data-ttu-id="27a05-166">필요에 따라 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-166">Do any of the following as needed:</span></span>
   - <span data-ttu-id="27a05-167">특정 서비스의 최신 상태를 보려면 **서비스 상태 가져오기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-167">To see the latest status of that specific service, click **Get service status**.</span></span>
   - <span data-ttu-id="27a05-168">특정 서비스의 세부 정보를 보려면 **속성**, **닫기** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-168">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
   - <span data-ttu-id="27a05-169">토폴로지의 모든 컴퓨터 목록으로 돌아가려면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-169">To return to the list of all computers in your topology, click **Close**.</span></span>
    
## <a name="start-or-stop-skype-for-business-server-services"></a><span data-ttu-id="27a05-170">비즈니스용 Skype 서버 서비스 시작 또는 중지</span><span class="sxs-lookup"><span data-stu-id="27a05-170">Start or stop Skype for Business Server services</span></span>
<span data-ttu-id="27a05-171"><a name="StartStop"> </a></span><span class="sxs-lookup"><span data-stu-id="27a05-171"><a name="StartStop"> </a></span></span>

<span data-ttu-id="27a05-172">비즈니스용 Skype 서버 제어판을 사용하여 특정 컴퓨터에서 실행되는 모든 비즈니스용 Skype 서버 서비스를 시작 또는 중지하거나 특정 서비스를 시작 또는 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-172">You can use Skype for Business Server Control Panel to start or stop all the Skype for Business Server services running on a specific computer or to start or stop a specific service.</span></span>
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="27a05-173">컴퓨터에서 모든 비즈니스용 Skype 서비스를 시작하거나 중지하려면</span><span class="sxs-lookup"><span data-stu-id="27a05-173">To start or stop all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="27a05-174">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-174">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span> <span data-ttu-id="27a05-175">다음과 같은 명령을 실행하여 CsServerAdministrator 또는 CsAdministrator RBAC 역할이 할당되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-175">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
   ```PowerShell
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. <span data-ttu-id="27a05-176">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-176">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="27a05-177">왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-177">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="27a05-178">**상태** 페이지에서 시작하거나 중지할 서비스를 실행 중인 컴퓨터를 찾기 위해 필요한 경우 목록을 정렬하거나 검색한 다음 해당 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-178">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="27a05-179">**동작** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-179">Click **Action**.</span></span>
6. <span data-ttu-id="27a05-180">**모든 서비스 시작** 또는 **모든 서비스 중지** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-180">Click **Start All services** or **Stop All services**.</span></span>
    
### <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="27a05-181">특정 서비스를 시작 또는 중지하려면</span><span class="sxs-lookup"><span data-stu-id="27a05-181">To start or stop a specific service</span></span>

1. <span data-ttu-id="27a05-182">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-182">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="27a05-183">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-183">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="27a05-184">왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-184">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="27a05-185">**상태** 페이지에서 시작하거나 중지할 서비스를 실행 중인 컴퓨터를 찾기 위해 필요한 경우 목록을 정렬하거나 검색한 다음 해당 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-185">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="27a05-186">**속성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-186">Click **Properties**.</span></span>
6. <span data-ttu-id="27a05-187">필요한 경우 서비스 목록을 정렬하고 시작 또는 중지할 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-187">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>
7. <span data-ttu-id="27a05-188">**동작** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-188">Click **Action**.</span></span>
8. <span data-ttu-id="27a05-189">**서비스 시작** 또는 **서비스 중지** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-189">Click **Start service** or **Stop service**.</span></span>
9. <span data-ttu-id="27a05-190">**닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-190">Click **Close**.</span></span>
    
## <a name="prevent-sessions-for-services"></a><span data-ttu-id="27a05-191">서비스에 대한 세션 방지</span><span class="sxs-lookup"><span data-stu-id="27a05-191">Prevent sessions for services</span></span>
<span data-ttu-id="27a05-192"><a name="prevent_session"> </a></span><span class="sxs-lookup"><span data-stu-id="27a05-192"><a name="prevent_session"> </a></span></span>

<span data-ttu-id="27a05-193">비즈니스용 Skype 서버 제어판을 사용하여 특정 컴퓨터에서 실행되는 모든 비즈니스용 Skype 서버 서비스에 대한 새 세션을 방지하거나 특정 비즈니스용 Skype 서버 서비스에 대한 새 세션을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-193">You can use Skype for Business Server Control Panel to prevent new sessions for all the Skype for Business Server services running on a specific computer or to prevent new sessions for a specific Skype for Business Server service.</span></span>
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="27a05-194">컴퓨터에서 모든 비즈니스용 Skype 서비스에 대한 새 세션을 방지하려면</span><span class="sxs-lookup"><span data-stu-id="27a05-194">To prevent new sessions for all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="27a05-195">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="27a05-196">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-196">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="27a05-197">왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-197">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="27a05-198">**상태** 페이지에서 새 세션을 금지할 서비스를 실행 중인 컴퓨터를 찾기 위해 필요한 경우 목록을 정렬하거나 검색한 다음 해당 컴퓨터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-198">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>
5. <span data-ttu-id="27a05-199">**동작** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-199">Click **Action**.</span></span>
6. <span data-ttu-id="27a05-200">**모든 서비스에 대한 새 세션 금지** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-200">Click **Prevent new sessions for all services**.</span></span>
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="27a05-201">특정 서비스에 대한 새 세션을 금지하려면</span><span class="sxs-lookup"><span data-stu-id="27a05-201">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="27a05-202">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-202">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="27a05-203">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-203">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="27a05-204">왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-204">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="27a05-205">**상태** 페이지에서 시작하거나 중지할 서비스를 실행 중인 컴퓨터를 찾기 위해 필요한 경우 목록을 정렬하거나 검색한 다음 해당 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-205">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
5. <span data-ttu-id="27a05-206">**속성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-206">Click **Properties**.</span></span>
6. <span data-ttu-id="27a05-207">필요한 경우 서비스 목록을 정렬하고 새 세션을 금지할 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-207">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
7. <span data-ttu-id="27a05-208">**동작** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-208">Click **Action**.</span></span>
8. <span data-ttu-id="27a05-209">**서비스에 대한 새 세션 금지** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-209">Click **Prevent new sessions for service**.</span></span>
9. <span data-ttu-id="27a05-210">**닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="27a05-210">Click **Close**.</span></span>
