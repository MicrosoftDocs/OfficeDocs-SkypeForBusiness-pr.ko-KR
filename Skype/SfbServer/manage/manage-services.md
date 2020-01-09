---
title: 비즈니스용 Skype 용 서비스 관리 서버
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: 이 문서에서는 비즈니스용 Skype 서버 토폴로지에서 실행 되는 서비스를 관리 하는 방법을 설명 합니다.
ms.openlocfilehash: 76628840c37bdb0eb85d58887d8bfdcedd20f27c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991673"
---
# <a name="manage-services-for-skype-for-business-server"></a><span data-ttu-id="6838a-103">비즈니스용 Skype 용 서비스 관리 서버</span><span class="sxs-lookup"><span data-stu-id="6838a-103">Manage services for Skype for Business Server</span></span>

<span data-ttu-id="6838a-104">이 문서에서는 비즈니스용 Skype 서버 토폴로지에서 실행 되는 서비스를 관리 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-104">This article describes how to manage services running in a Skype for Business Server topology.</span></span>
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="6838a-105">비즈니스용 Skype 서버를 실행 하는 컴퓨터 목록 보기</span><span class="sxs-lookup"><span data-stu-id="6838a-105">View a list of computers running Skype for Business Server</span></span>
<span data-ttu-id="6838a-106"><a name="view_list"> </a></span><span class="sxs-lookup"><span data-stu-id="6838a-106"></span></span>

<span data-ttu-id="6838a-107">비즈니스용 Skype Server 제어판을 사용 하 여 토폴로지에서 비즈니스용 Skype Server를 실행 하는 모든 컴퓨터의 목록을 확인 하 고 각각의 서비스 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-107">You can use Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business Server in your topology and see the service status of each.</span></span> <span data-ttu-id="6838a-108">컴퓨터, 풀 또는 사이트를 기준으로 목록을 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-108">You can sort the list by computer, pool, or site.</span></span> 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="6838a-109">비즈니스용 Skype 서버를 실행 하는 컴퓨터의 목록을 보려면</span><span class="sxs-lookup"><span data-stu-id="6838a-109">To view a list of computers running Skype for Business Server</span></span>

1. <span data-ttu-id="6838a-110">비즈니스용 Skype Server의 미리 정의 된 관리 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-110">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="6838a-111">비즈니스용 Skype 서버에서 사용할 수 있는 미리 정의 된 관리 역할에 대 한 자세한 내용은 **역할 기반 액세스 제어 계획**을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6838a-111">For details about the predefined administrative roles available in Skype for Business Server, see **Planning for Role-Based Access Control**.</span></span>   
2. <span data-ttu-id="6838a-112">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>   
3. <span data-ttu-id="6838a-113">왼쪽 탐색 모음에서 **토폴로지** 를 클릭 한 다음 **상태**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-113">In the left navigation bar, click **Topology** and then click **Status**.</span></span>   
4. <span data-ttu-id="6838a-114">**상태** 페이지에서 필요에 따라 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-114">On the **Status** page, do any of the following as needed:</span></span>
   - <span data-ttu-id="6838a-115">**컴퓨터**, **풀**또는 **사이트** 열 머리글을 클릭 한 다음 위쪽 화살표 또는 아래쪽 화살표를 클릭 하 여 목록을 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-115">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span> 
   - <span data-ttu-id="6838a-116">**새로 고침** 을 클릭 하 여 최신 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-116">Click **Refresh** to view the most up-to-date list.</span></span>  
   - <span data-ttu-id="6838a-117">검색 필드에 컴퓨터 이름을 입력 하 여 특정 컴퓨터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-117">Search for a specific computer by typing the computer name in the search field.</span></span>
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a><span data-ttu-id="6838a-118">비즈니스용 Skype 서버에서 실행 중인 서비스의 상태 보기</span><span class="sxs-lookup"><span data-stu-id="6838a-118">View the status of services running on a Skype for Business server</span></span>
<span data-ttu-id="6838a-119"><a name="view-status"> </a></span><span class="sxs-lookup"><span data-stu-id="6838a-119"></span></span>

<span data-ttu-id="6838a-120">비즈니스용 skype Server 제어판을 사용 하 여 비즈니스용 Skype Server 토폴로지의 특정 컴퓨터에서 실행 중인 모든 서비스를 보고 각 서비스의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-120">You can use Skype for Business Server Control Panel to view all the services that are running on a specific computer in your Skype for Business Server topology and see the status of each service.</span></span>
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="6838a-121">컴퓨터에서 실행 중인 서비스의 상태를 보려면</span><span class="sxs-lookup"><span data-stu-id="6838a-121">To view the status of services running on a computer</span></span>

1. <span data-ttu-id="6838a-122">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="6838a-123">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="6838a-124">왼쪽 탐색 모음에서 **토폴로지**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-124">In the left navigation bar, click **Topology**.</span></span> 
4. <span data-ttu-id="6838a-125">**상태** 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 원하는 컴퓨터를 찾은 다음 컴퓨터 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-125">On the **Status** page, sort or search the list, as required, to find the computer you're interested in, and then click the computer name.</span></span>
5. <span data-ttu-id="6838a-126">다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-126">Do any of the following:</span></span>
   - <span data-ttu-id="6838a-127">컴퓨터에서 실행 중인 서비스의 최신 상태를 보려면 **서비스 상태 가져오기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-127">To see the latest status of services running on the computer, click **Get service status**.</span></span>
   - <span data-ttu-id="6838a-128">컴퓨터에서 실행 되는 특정 서비스 목록과 각 서비스의 상태를 확인 하려면 **속성**을 클릭 한 다음 **닫기를** 클릭 하 여 목록으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-128">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a><span data-ttu-id="6838a-129">Windows Powershell cmdlet을 사용 하 여 서비스 상태 보기</span><span class="sxs-lookup"><span data-stu-id="6838a-129">Viewing service status with Windows Powershell cmdlets</span></span>

<span data-ttu-id="6838a-130">Windows PowerShell 및 **Get CsWindowsService** cmdlet을 사용 하 여 서비스 상태를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-130">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="6838a-131">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-131">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6838a-132">원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6838a-132">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="6838a-133">이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-133">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-service-status"></a><span data-ttu-id="6838a-134">서비스 상태를 보려면</span><span class="sxs-lookup"><span data-stu-id="6838a-134">To view service status</span></span>

<span data-ttu-id="6838a-135">컴퓨터에서 서비스 상태를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음과 유사한 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-135">To view service status on a computer, type a command similar to the following in the Skype for Business Server Management Shell and then press Enter:</span></span>
  
```PowerShell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

<span data-ttu-id="6838a-136">이 명령은 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-136">This command returns information similar to the following:</span></span>
  
|<span data-ttu-id="6838a-137">**RoleName**</span><span class="sxs-lookup"><span data-stu-id="6838a-137">**RoleName**</span></span>|<span data-ttu-id="6838a-138">**상태**</span><span class="sxs-lookup"><span data-stu-id="6838a-138">**Status**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6838a-139">W3SVC</span><span class="sxs-lookup"><span data-stu-id="6838a-139">{W3SVC}</span></span>  <br/> |<span data-ttu-id="6838a-140">실행</span><span class="sxs-lookup"><span data-stu-id="6838a-140">Running</span></span>  <br/> |
|<span data-ttu-id="6838a-141">{CentralManagement}</span><span class="sxs-lookup"><span data-stu-id="6838a-141">{CentralManagement}</span></span>  <br/> | <span data-ttu-id="6838a-142">실행</span><span class="sxs-lookup"><span data-stu-id="6838a-142">Running</span></span> <br/> |
|<span data-ttu-id="6838a-143">{ClsAgent}</span><span class="sxs-lookup"><span data-stu-id="6838a-143">{ClsAgent}</span></span>  <br/> |<span data-ttu-id="6838a-144">실행</span><span class="sxs-lookup"><span data-stu-id="6838a-144">Running</span></span>  <br/> |
|<span data-ttu-id="6838a-145">{등록자, UserServer, EdgeServer}</span><span class="sxs-lookup"><span data-stu-id="6838a-145">{Registrar, UserServer, EdgeServer}</span></span>  <br/> |<span data-ttu-id="6838a-146">실행</span><span class="sxs-lookup"><span data-stu-id="6838a-146">Running</span></span>  <br/> |
|<span data-ttu-id="6838a-147">{ApplicationServer}</span><span class="sxs-lookup"><span data-stu-id="6838a-147">{ApplicationServer}</span></span>  <br/> |<span data-ttu-id="6838a-148">실행</span><span class="sxs-lookup"><span data-stu-id="6838a-148">Running</span></span>  <br/> |
|<span data-ttu-id="6838a-149">{ConferencingServer}</span><span class="sxs-lookup"><span data-stu-id="6838a-149">{ConferencingServer}</span></span>  <br/> |<span data-ttu-id="6838a-150">실행</span><span class="sxs-lookup"><span data-stu-id="6838a-150">Running</span></span>  <br/> |
|<span data-ttu-id="6838a-151">{MediationServer}</span><span class="sxs-lookup"><span data-stu-id="6838a-151">{MediationServer}</span></span>  <br/> |<span data-ttu-id="6838a-152">실행</span><span class="sxs-lookup"><span data-stu-id="6838a-152">Running</span></span>  <br/> |
   
<span data-ttu-id="6838a-153">자세한 내용은 [CsWindowsService 가져오기](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6838a-153">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).</span></span>
  
## <a name="view-details-about-a-service"></a><span data-ttu-id="6838a-154">서비스에 대 한 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="6838a-154">View details about a service</span></span>
<span data-ttu-id="6838a-155"><a name="view_details"> </a></span><span class="sxs-lookup"><span data-stu-id="6838a-155"></span></span>

<span data-ttu-id="6838a-156">비즈니스용 Skype Server 제어판을 사용 하 여 토폴로지의 특정 컴퓨터에서 실행 중인 각 서비스에 대 한 세부 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-156">You can use Skype for Business Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="6838a-157">각 서비스의 상태와 관련 데이터베이스, 포트, 종속 서비스 등의 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-157">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>
  
### <a name="to-view-details-for-a-service"></a><span data-ttu-id="6838a-158">서비스에 대 한 세부 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="6838a-158">To view details for a service</span></span>

1. <span data-ttu-id="6838a-159">비즈니스용 Skype Server의 미리 정의 된 관리 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-159">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="6838a-160">비즈니스용 Skype 서버에서 사용할 수 있는 미리 정의 된 관리 역할에 대 한 자세한 내용은 **역할 기반 액세스 제어 계획**을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6838a-160">For details about the predefined administrative roles available in Skype for Business Server, see **Planning for Role-Based Access Control**.</span></span>
2. <span data-ttu-id="6838a-161">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-161">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="6838a-162">왼쪽 탐색 모음에서 **토폴로지** 를 클릭 한 다음 **상태**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-162">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="6838a-163">**상태** 페이지에서 목록을 정렬 하거나 검색 한 다음 보려는 컴퓨터를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-163">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>
5. <span data-ttu-id="6838a-164">**속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-164">Click **Properties**.</span></span>
6. <span data-ttu-id="6838a-165">**컴퓨터 세부 정보 보기** 창에서 필요한 경우 서비스 목록을 정렬 하 고 보려는 서비스를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-165">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>
7. <span data-ttu-id="6838a-166">필요에 따라 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-166">Do any of the following as needed:</span></span>
   - <span data-ttu-id="6838a-167">해당 하는 특정 서비스의 최신 상태를 보려면 **서비스 상태 가져오기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-167">To see the latest status of that specific service, click **Get service status**.</span></span>
   - <span data-ttu-id="6838a-168">특정 서비스에 대 한 세부 정보를 보려면 **속성** 을 클릭 한 다음 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-168">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
   - <span data-ttu-id="6838a-169">토폴로지의 모든 컴퓨터 목록으로 돌아가려면 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-169">To return to the list of all computers in your topology, click **Close**.</span></span>
    
## <a name="start-or-stop-skype-for-business-server-services"></a><span data-ttu-id="6838a-170">비즈니스용 Skype 서버 서비스 시작 또는 중지</span><span class="sxs-lookup"><span data-stu-id="6838a-170">Start or stop Skype for Business Server services</span></span>
<span data-ttu-id="6838a-171"><a name="StartStop"> </a></span><span class="sxs-lookup"><span data-stu-id="6838a-171"></span></span>

<span data-ttu-id="6838a-172">비즈니스용 Skype Server 제어판을 사용 하 여 특정 컴퓨터에서 실행 되는 모든 비즈니스용 Skype Server 서비스를 시작 하거나 중지 하거나 특정 서비스를 시작 하거나 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-172">You can use Skype for Business Server Control Panel to start or stop all the Skype for Business Server services running on a specific computer or to start or stop a specific service.</span></span>
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="6838a-173">컴퓨터에서 비즈니스용 Skype 서비스를 모두 시작 하거나 중지 하려면</span><span class="sxs-lookup"><span data-stu-id="6838a-173">To start or stop all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="6838a-174">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="6838a-174">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span> <span data-ttu-id="6838a-175">다음과 같은 명령을 실행 하 여 CsServerAdministrator 또는 CsAdministrator RBAC 역할을 할당 했는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-175">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
   ```PowerShell
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. <span data-ttu-id="6838a-176">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-176">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="6838a-177">왼쪽 탐색 모음에서 **토폴로지** 를 클릭 한 다음 **상태**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-177">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="6838a-178">**상태** 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 시작 하거나 중지할 서비스를 실행 하는 컴퓨터를 찾은 다음 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-178">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="6838a-179">**동작**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-179">Click **Action**.</span></span>
6. <span data-ttu-id="6838a-180">**모든 서비스 시작** 또는 **모든 서비스 중지**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-180">Click **Start All services** or **Stop All services**.</span></span>
    
### <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="6838a-181">특정 서비스를 시작 하거나 중지 하려면</span><span class="sxs-lookup"><span data-stu-id="6838a-181">To start or stop a specific service</span></span>

1. <span data-ttu-id="6838a-182">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-182">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="6838a-183">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-183">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="6838a-184">왼쪽 탐색 모음에서 **토폴로지** 를 클릭 한 다음 **상태**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-184">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="6838a-185">**상태** 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 시작 하거나 중지할 서비스를 실행 하는 컴퓨터를 찾은 다음 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-185">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="6838a-186">**속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-186">Click **Properties**.</span></span>
6. <span data-ttu-id="6838a-187">필요한 경우 서비스 목록을 정렬 하 고 시작 하거나 중지 하려는 서비스를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-187">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>
7. <span data-ttu-id="6838a-188">**동작**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-188">Click **Action**.</span></span>
8. <span data-ttu-id="6838a-189">**서비스 시작** 또는 **서비스 중지**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-189">Click **Start service** or **Stop service**.</span></span>
9. <span data-ttu-id="6838a-190">**닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-190">Click **Close**.</span></span>
    
## <a name="prevent-sessions-for-services"></a><span data-ttu-id="6838a-191">서비스에 대한 세션 방지</span><span class="sxs-lookup"><span data-stu-id="6838a-191">Prevent sessions for services</span></span>
<span data-ttu-id="6838a-192"><a name="prevent_session"> </a></span><span class="sxs-lookup"><span data-stu-id="6838a-192"></span></span>

<span data-ttu-id="6838a-193">비즈니스용 skype Server 제어판을 사용 하 여 특정 컴퓨터에서 실행 중인 모든 비즈니스용 Skype Server services에 대 한 새 세션을 방지 하거나 특정 비즈니스용 Skype Server 서비스에 대 한 새 세션을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-193">You can use Skype for Business Server Control Panel to prevent new sessions for all the Skype for Business Server services running on a specific computer or to prevent new sessions for a specific Skype for Business Server service.</span></span>
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="6838a-194">컴퓨터의 모든 비즈니스용 Skype 서비스에 대해 새 세션을 방지 하려면</span><span class="sxs-lookup"><span data-stu-id="6838a-194">To prevent new sessions for all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="6838a-195">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="6838a-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="6838a-196">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-196">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="6838a-197">왼쪽 탐색 모음에서 **토폴로지** 를 클릭 한 다음 **상태**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-197">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="6838a-198">**상태** 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 새 세션을 방지 하려는 서비스를 실행 하는 컴퓨터를 찾은 다음 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-198">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>
5. <span data-ttu-id="6838a-199">**동작**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-199">Click **Action**.</span></span>
6. <span data-ttu-id="6838a-200">**모든 서비스에 대해 새 세션 금지를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-200">Click **Prevent new sessions for all services**.</span></span>
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="6838a-201">특정 서비스에 대 한 새 세션을 방지 하려면</span><span class="sxs-lookup"><span data-stu-id="6838a-201">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="6838a-202">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="6838a-202">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="6838a-203">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-203">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="6838a-204">왼쪽 탐색 모음에서 **토폴로지** 를 클릭 한 다음 **상태**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-204">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="6838a-205">**상태** 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 시작 하거나 중지할 서비스를 실행 하는 컴퓨터를 찾은 다음 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-205">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
5. <span data-ttu-id="6838a-206">**속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-206">Click **Properties**.</span></span>
6. <span data-ttu-id="6838a-207">필요한 경우 서비스 목록을 정렬 하 고 새 세션을 방지 하려는 서비스를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-207">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
7. <span data-ttu-id="6838a-208">**동작**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-208">Click **Action**.</span></span>
8. <span data-ttu-id="6838a-209">**서비스에 대해 새 세션 금지를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-209">Click **Prevent new sessions for service**.</span></span>
9. <span data-ttu-id="6838a-210">**닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6838a-210">Click **Close**.</span></span>
    

