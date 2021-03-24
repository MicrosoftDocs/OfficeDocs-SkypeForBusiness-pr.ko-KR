---
title: 비즈니스용 Skype 서버에서 서비스 관리
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
description: 서비스 상태를 보고, 서비스를 시작 및 중지하고, 서비스에 대한 세션을 방지하는 방법을 배워야 합니다.
ms.openlocfilehash: 34228a7e1b8cf9ef044d2f1f15c4b1219f795d79
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103184"
---
# <a name="manage-services-in-skype-for-business-server"></a><span data-ttu-id="757e9-103">비즈니스용 Skype 서버에서 서비스 관리</span><span class="sxs-lookup"><span data-stu-id="757e9-103">Manage services in Skype for Business Server</span></span>

<span data-ttu-id="757e9-104">비즈니스용 Skype 서버 제어판을 사용하여 토폴로지에서 비즈니스용 Skype 서버를 실행하는 모든 컴퓨터의 목록을 보고, 서비스 상태를 보고, 서비스를 시작 또는 중지하고, 서비스에 대한 세션을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-104">You can use the Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business Server in your topology, view the status of services, start or stop services, and prevent sessions for services.</span></span>

- [<span data-ttu-id="757e9-105">비즈니스용 Skype 서버를 실행하는 컴퓨터 목록 보기</span><span class="sxs-lookup"><span data-stu-id="757e9-105">View a list of computers running Skype for Business Server</span></span>](#view-a-list-of-computers-running-skype-for-business-server)
- [<span data-ttu-id="757e9-106">비즈니스용 Skype에서 컴퓨터에서 실행 중인 서비스 상태 보기</span><span class="sxs-lookup"><span data-stu-id="757e9-106">View the status of services running on a computer in Skype for Business</span></span>](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [<span data-ttu-id="757e9-107">비즈니스용 Skype 서비스 시작 또는 중지</span><span class="sxs-lookup"><span data-stu-id="757e9-107">Start or stop Skype for Business services</span></span>](#start-or-stop-skype-for-business-services)
- [<span data-ttu-id="757e9-108">서비스에 대한 세션 방지</span><span class="sxs-lookup"><span data-stu-id="757e9-108">Prevent sessions for services</span></span>](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="757e9-109">비즈니스용 Skype 서버를 실행하는 컴퓨터 목록 보기</span><span class="sxs-lookup"><span data-stu-id="757e9-109">View a list of computers running Skype for Business Server</span></span>

<span data-ttu-id="757e9-110">비즈니스용 Skype 서버 제어판을 사용하여 토폴로지에서 비즈니스용 Skype를 실행하는 모든 컴퓨터의 목록을 보고 각 컴퓨터의 서비스 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-110">Use the Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business in your topology and see the service status of each.</span></span> <span data-ttu-id="757e9-111">컴퓨터, 풀 또는 사이트에 따라 목록을 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-111">You can sort the list by computer, pool, or site.</span></span> 

1. <span data-ttu-id="757e9-112">비즈니스용 Skype 서버에 대해 미리 정의한 관리 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-112">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="757e9-113">자세한 내용은 비즈니스용 [Skype 서버의 RBAC(역할 기반 액세스 제어)를 참조하세요.](../../plan-your-deployment/security/role-based-access-control-rbac.md)</span><span class="sxs-lookup"><span data-stu-id="757e9-113">For more information, see [Role-based access control (RBAC) for Skype for Business Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>
2. <span data-ttu-id="757e9-114">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="757e9-115">비즈니스용 Skype 서버 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 관리 도구 설치 [및 열기 를 참조하세요.](../../management-tools/install-and-open-administrative-tools.md)</span><span class="sxs-lookup"><span data-stu-id="757e9-115">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="757e9-116">왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-116">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="757e9-117">상태 페이지에서 필요한 경우 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-117">On the Status page, do either of the following as needed:</span></span>
    - <span data-ttu-id="757e9-118">**컴퓨터**, **풀** 또는 **사이트** 열 머리글을 클릭한 다음 위쪽 화살표나 아래쪽 화살표를 클릭하여 목록을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-118">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span>
    - <span data-ttu-id="757e9-119">**새로 고침** 을 클릭하여 최신 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-119">Click **Refresh** to view the most up-to-date list.</span></span>
    - <span data-ttu-id="757e9-120">검색 필드에 컴퓨터 이름을 입력하여 특정 컴퓨터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-120">Search for a specific computer by typing the computer name in the search field.</span></span>
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a><span data-ttu-id="757e9-121">비즈니스용 Skype에서 컴퓨터에서 실행 중인 서비스 상태 보기</span><span class="sxs-lookup"><span data-stu-id="757e9-121">View the status of services running on a computer in Skype for Business</span></span>

<span data-ttu-id="757e9-122">비즈니스용 Skype 서버 제어판을 사용하여 비즈니스용 Skype 서버 토폴로지의 특정 컴퓨터에서 실행 중인 모든 서비스를 보고 각 서비스의 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-122">Use the Skype for Business Server Control Panel to view all the services that are running on a specific computer in your Skype for Business Server topology and see the status of each service.</span></span>

1. <span data-ttu-id="757e9-123">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="757e9-124">브라우저 창을 열고 관리 URL을 입력하여 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-124">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="757e9-125">비즈니스용 Skype 서버 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 관리 도구 설치 [및 열기 를 참조하세요.](../../management-tools/install-and-open-administrative-tools.md)</span><span class="sxs-lookup"><span data-stu-id="757e9-125">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="757e9-126">왼쪽 탐색 표시줄에서 **토폴로지** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-126">In the left navigation bar, click **Topology**.</span></span>
4. <span data-ttu-id="757e9-127">상태 페이지에서 필요에 따라 목록을 정렬하거나 검색하여 원하는 컴퓨터를 찾은 다음 컴퓨터 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-127">On the Status page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>
5. <span data-ttu-id="757e9-128">다음 중 하나를 합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-128">Do either of the following:</span></span>
    - <span data-ttu-id="757e9-129">컴퓨터에서 실행되는 서비스의 최신 상태를 보려면 **서비스 상태 가져오기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-129">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    - <span data-ttu-id="757e9-130">컴퓨터에서 실행되는 특정 서비스 목록 및 각 서비스의 상태를 보려면 **속성** 을 클릭합니다. 목록으로 돌아오려면 **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-130">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="757e9-131">Cmdlet을 사용하여 Windows PowerShell 상태 보기</span><span class="sxs-lookup"><span data-stu-id="757e9-131">Viewing service status by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="757e9-132">또한 cmdlet 및 Windows PowerShell cmdlet을 사용하여 서비스 Get-CsWindowsService 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-132">You can also view service status by using Windows PowerShell and the Get-CsWindowsService cmdlet.</span></span> <span data-ttu-id="757e9-133">비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-133">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="757e9-134">자세한 내용은 [비즈니스용 Skype 서버 관리 셸을 참조하세요.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="757e9-134">For more information, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>

<span data-ttu-id="757e9-135">**서비스 상태를 보려면**</span><span class="sxs-lookup"><span data-stu-id="757e9-135">**To view service status**</span></span>

<span data-ttu-id="757e9-136">컴퓨터에서 서비스 상태를 확인하려면 비즈니스용 Skype 서버 관리 셸에 다음과 비슷한 명령을 입력한 다음 Enter를 눌러야 합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-136">To view service status on a computer, type a command similar to the following in the Skype for Business Server Management Shell, and then press Enter:</span></span>

```powershell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

<span data-ttu-id="757e9-137">이 명령은 다음과 비슷한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-137">This command returns information similar to the following:</span></span>

```console
RoleName                                  Status
--------                                  ------
{W3SVC}                                   Running
{CentralManagement}                       Running
{ClsAgent}                                Running
{Registrar, UserServer, EdgeServer}       Running
{ApplicationServer}                       Running
{ConferencingServer}                      Running
{MediationServer}                         Running
```

<span data-ttu-id="757e9-138">자세한 내용은 [Get-CsWindowsService를 참조합니다.](/powershell/module/skype/Get-CsWindowsService)</span><span class="sxs-lookup"><span data-stu-id="757e9-138">For details, see [Get-CsWindowsService](/powershell/module/skype/Get-CsWindowsService).</span></span>

## <a name="start-or-stop-skype-for-business-services"></a><span data-ttu-id="757e9-139">비즈니스용 Skype 서비스 시작 또는 중지</span><span class="sxs-lookup"><span data-stu-id="757e9-139">Start or stop Skype for Business services</span></span>

<span data-ttu-id="757e9-140">비즈니스용 Skype 서버 제어판을 사용하여 특정 컴퓨터에서 실행되는 모든 비즈니스용 Skype 서버 서비스를 시작 또는 중지하거나 특정 서비스를 시작 또는 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-140">Use the Skype for Business Server Control Panel to start or stop all the Skype for Business Server services running on a specific computer or to start or stop a specific service.</span></span>

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a><span data-ttu-id="757e9-141">컴퓨터에서 모든 비즈니스용 Skype 서버 서비스 시작 또는 중지</span><span class="sxs-lookup"><span data-stu-id="757e9-141">Start or stop all Skype for Business Server services on a computer</span></span>

1. <span data-ttu-id="757e9-142">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span> <span data-ttu-id="757e9-143">다음과 같은 명령을 실행하여 CsServerAdministrator 또는 CsAdministrator RBAC 역할이 할당되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-143">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>

    ```powershell
    Get-CsAdminRoleAssignment -Identity "kenmyer"`
    ```

2. <span data-ttu-id="757e9-144">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-144">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="757e9-145">비즈니스용 Skype 서버 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 관리 도구 설치 [및 열기 를 참조하세요.](../../management-tools/install-and-open-administrative-tools.md)</span><span class="sxs-lookup"><span data-stu-id="757e9-145">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="757e9-146">왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-146">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="757e9-147">상태 페이지에서 시작하거나 중지할 서비스를 실행 중인 컴퓨터를 찾기 위해 필요한 경우 목록을 정렬하거나 검색한 다음 해당 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-147">On the Status page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="757e9-148">**동작** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-148">Click **Action**.</span></span>
6. <span data-ttu-id="757e9-149">**모든 서비스 시작** 또는 **모든 서비스 중지** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-149">Click **Start All services** or **Stop All services**.</span></span>

### <a name="start-or-stop-a-specific-service"></a><span data-ttu-id="757e9-150">특정 서비스 시작 또는 중지</span><span class="sxs-lookup"><span data-stu-id="757e9-150">Start or stop a specific service</span></span>

1. <span data-ttu-id="757e9-151">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-151">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="757e9-152">브라우저 창을 열고 관리 URL을 입력하여 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-152">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="757e9-153">비즈니스용 Skype 서버 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 관리 도구 설치 [및 열기 를 참조하세요.](../../management-tools/install-and-open-administrative-tools.md)</span><span class="sxs-lookup"><span data-stu-id="757e9-153">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="757e9-154">왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-154">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="757e9-155">상태 페이지에서 시작하거나 중지할 서비스를 실행 중인 컴퓨터를 찾기 위해 필요한 경우 목록을 정렬하거나 검색한 다음 해당 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-155">On the Status page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="757e9-156">**속성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-156">Click **Properties**.</span></span>
6. <span data-ttu-id="757e9-157">필요한 경우 서비스 목록을 정렬하고 시작 또는 중지할 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-157">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>
7. <span data-ttu-id="757e9-158">**동작** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-158">Click **Action**.</span></span>
8. <span data-ttu-id="757e9-159">**서비스 시작** 또는 **서비스 중지** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-159">Click **Start service** or **Stop service**.</span></span>
9. <span data-ttu-id="757e9-160">**닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-160">Click **Close**.</span></span>


## <a name="prevent-sessions-for-services"></a><span data-ttu-id="757e9-161">서비스에 대한 세션 방지</span><span class="sxs-lookup"><span data-stu-id="757e9-161">Prevent sessions for services</span></span>

<span data-ttu-id="757e9-162">비즈니스용 Skype 제어판을 사용하여 특정 컴퓨터에서 실행되는 모든 비즈니스용 Skype 서버 서비스에 대한 새 세션을 차단하거나 특정 서비스에 대한 새 세션을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-162">Use the Skype for Business Control Panel to prevent new sessions for all the Skype for Business Server services running on a specific computer or to prevent new sessions for a specific service.</span></span>

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a><span data-ttu-id="757e9-163">컴퓨터의 모든 비즈니스용 Skype 서버 서비스에 대한 새 세션 방지</span><span class="sxs-lookup"><span data-stu-id="757e9-163">Prevent new sessions for all  Skype for Business Server services on a computer</span></span>

1. <span data-ttu-id="757e9-164">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-164">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="757e9-165">브라우저 창을 열고 관리 URL을 입력하여 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-165">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="757e9-166">비즈니스용 Skype 서버 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 관리 도구 설치 [및 열기 를 참조하세요.](../../management-tools/install-and-open-administrative-tools.md)</span><span class="sxs-lookup"><span data-stu-id="757e9-166">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="757e9-167">왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-167">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="757e9-168">상태 페이지에서 새 세션을 금지할 서비스를 실행 중인 컴퓨터를 찾기 위해 필요한 경우 목록을 정렬하거나 검색한 다음 해당 컴퓨터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-168">On the Status page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>
5. <span data-ttu-id="757e9-169">**동작** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-169">Click **Action**.</span></span>
6. <span data-ttu-id="757e9-170">**모든 서비스에 대한 새 세션 금지** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-170">Click **Prevent new sessions for all services**.</span></span>

### <a name="prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="757e9-171">특정 서비스에 대한 새 세션 방지</span><span class="sxs-lookup"><span data-stu-id="757e9-171">Prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="757e9-172">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-172">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="757e9-173">브라우저 창을 열고 관리 URL을 입력하여 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-173">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="757e9-174">비즈니스용 Skype 서버 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 관리 도구 설치 [및 열기 를 참조하세요.](../../management-tools/install-and-open-administrative-tools.md)</span><span class="sxs-lookup"><span data-stu-id="757e9-174">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="757e9-175">왼쪽 탐색 모음에서 **토폴로지** 를 클릭하고 **상태** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-175">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="757e9-176">**속성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-176">Click **Properties**.</span></span>
5. <span data-ttu-id="757e9-177">필요한 경우 서비스 목록을 정렬하고 새 세션을 금지할 서비스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-177">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
6. <span data-ttu-id="757e9-178">**동작** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-178">Click **Action**.</span></span>
7. <span data-ttu-id="757e9-179">**서비스에 대한 새 세션 금지** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-179">Click **Prevent new sessions for service**.</span></span>
8. <span data-ttu-id="757e9-180">**닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="757e9-180">Click **Close**.</span></span>