---
title: 비즈니스용 Skype 서버에 대 한 Active Directory 준비
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: '요약: 비즈니스용 Skype 서버 설치를 위해 Active Directory 도메인을 준비 하는 방법을 알아봅니다. Microsoft 평가 센터에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 하세요. https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server'
ms.openlocfilehash: 9a17ae327322b364935d0b965676d26fdce2cffb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018179"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a><span data-ttu-id="3f558-104">비즈니스용 Skype 서버에 대 한 Active Directory 준비</span><span class="sxs-lookup"><span data-stu-id="3f558-104">Prepare Active Directory for Skype for Business Server</span></span>
 
<span data-ttu-id="3f558-105">**요약:** 비즈니스용 Skype 서버 설치를 위해 Active Directory 도메인을 준비 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-105">**Summary:** Learn how to prepare your Active Directory domain for an installation of Skype for Business Server.</span></span> <span data-ttu-id="3f558-106">[Microsoft 평가 센터](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="3f558-107">비즈니스용 Skype 서버가 Active Directory와 긴밀 하 게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-107">Skype for Business Server works closely with Active Directory.</span></span> <span data-ttu-id="3f558-108">비즈니스용 Skype 서버에서 작동 하도록 Active Directory 도메인을 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-108">You must prepare the Active Directory domain to work with Skype for Business Server.</span></span> <span data-ttu-id="3f558-109">이 프로세스는 배포 마법사에서 수행 되며 도메인에 대해 한 번만 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-109">This process is accomplished in the Deployment Wizard and is only done once for the domain.</span></span> <span data-ttu-id="3f558-110">이 프로세스는 그룹을 만들고 도메인을 수정 하며 한 번만 수행 하면 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-110">This is because the process creates groups and modifies the domain, and you need to do that only once.</span></span> <span data-ttu-id="3f558-111">순서에 관계 없이 1 ~ 5 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-111">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="3f558-112">그러나 다이어그램에 나와 있는 것 처럼, 1 ~ 5 단계를 순서 대로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-112">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="3f558-113">Active Directory를 준비 하는 과정은 4 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-113">Preparing Active Directory is step 4 of 8.</span></span> <span data-ttu-id="3f558-114">Active Directory 계획에 대 한 자세한 내용은 비즈니스용 [Skype 서버에 대 한 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 또는 [비즈니스용 skype 서버 2019에 대 한 서버 요구 사항을](../../../SfBServer2019/plan/system-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f558-114">For more information about planning for Active Directory, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![개요 다이어그램](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a><span data-ttu-id="3f558-116">Active Directory 준비</span><span class="sxs-lookup"><span data-stu-id="3f558-116">Prepare Active Directory</span></span>

<span data-ttu-id="3f558-117">비즈니스용 Skype 서버가 AD DS (Active Directory 도메인 서비스)와 긴밀 하 게 통합 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-117">Skype for Business Server is tightly integrated with Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="3f558-118">비즈니스용 Skype 서버를 처음 설치 하기 전에 Active Directory를 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-118">Before Skype for Business Server can be installed for the first time, Active Directory must be prepared.</span></span> <span data-ttu-id="3f558-119">**Active Directory 준비** 라는 배포 마법사 섹션에서는 비즈니스용 Skype 서버에서 사용할 active directory 환경을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-119">The section of the Deployment Wizard titled **Prepare Active Directory** prepares the Active Directory environment for use with Skype for Business Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3f558-120">비즈니스용 Skype 서버 사용 (AD DS)을 통해 토폴로지의 모든 서버를 추적 하 고 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-120">Skype for Business Server uses (AD DS) to track and communicate with all of the servers in a topology.</span></span> <span data-ttu-id="3f558-121">비즈니스용 Skype 서버가 올바르게 작동할 수 있도록 이러한 서버의 대부분이 도메인에 가입 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-121">The majority of these servers must be joined to the domain so that Skype for Business Server can work properly.</span></span> <span data-ttu-id="3f558-122">Edge 및 역방향 프록시와 같은 서버는 도메인에 가입 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-122">Keep in mind that servers such as Edge and Reverse Proxy should not be domain joined.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3f558-123">Active Directory 준비 절차는 배포의 각 도메인에 대해 한 번만 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-123">The Prepare Active Directory procedure should be run only once for each domain in the deployment.</span></span> 
  
<span data-ttu-id="3f558-124">**Active Directory를 준비**하기 위한 비디오 단계를 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f558-124">Watch the video steps for **Prepare Active Directory**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a><span data-ttu-id="3f558-125">배포 마법사에서 Active Directory 준비</span><span class="sxs-lookup"><span data-stu-id="3f558-125">Prepare Active Directory from the Deployment Wizard</span></span>

1. <span data-ttu-id="3f558-126">Active Directory 도메인에 대 한 스키마 관리자 자격 증명을 사용 하 여 사용자로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-126">Log on as a user with Schema Admins credentials for the Active Directory domain.</span></span>
    
2. <span data-ttu-id="3f558-127">비즈니스용 Skype 서버 배포 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-127">Open Skype for Business Server Deployment Wizard.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="3f558-128">비즈니스용 Skype 서버 배포 마법사에서 만든 로그 파일을 검토 하려면 배포 마법사가 실행 된 컴퓨터에서 해당 단계를 실행 한 AD DS 사용자의 사용자 디렉터리에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-128">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the AD DS user who ran the step.</span></span> <span data-ttu-id="3f558-129">예를 들어 사용자가 도메인의 도메인 관리자로 로그온 한 경우 로그 파일의 위치는 C:\Users\Administrator.Contoso\AppData\Local\Temp.입니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-129">For example, if the user logged on as the domain administrator in the domain, contoso.local, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span> 
  
3. <span data-ttu-id="3f558-130">**Active Directory 준비** 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-130">Click the **Prepare Active Directory** link.</span></span>
    
4. <span data-ttu-id="3f558-131">**1 단계: 스키마 준비**</span><span class="sxs-lookup"><span data-stu-id="3f558-131">**Step 1: Prepare schema**</span></span>
    
    <span data-ttu-id="3f558-132">a.</span><span class="sxs-lookup"><span data-stu-id="3f558-132">a.</span></span> <span data-ttu-id="3f558-133">1 단계 제목 아래의 드롭다운을 클릭 하 여 액세스할 수 있는 1 단계에 대 한 필수 구성 요소 정보를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-133">Review the prerequisites information for Step 1 which can be accessed by clicking the drop-down under the Step 1 title.</span></span>
    
    <span data-ttu-id="3f558-134">b.</span><span class="sxs-lookup"><span data-stu-id="3f558-134">b.</span></span> <span data-ttu-id="3f558-135">1 단계에서 **실행** 을 클릭 하 여 스키마 준비 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-135">Click **Run** in Step 1 to launch the Prepare Schema wizard.</span></span>
    
    <span data-ttu-id="3f558-136">c.</span><span class="sxs-lookup"><span data-stu-id="3f558-136">c.</span></span> <span data-ttu-id="3f558-137">각 배포에 대해이 절차를 한 번만 실행 하 고 **Next (다음**)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-137">Take note that the procedure should be run only once for each deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="3f558-138">d.</span><span class="sxs-lookup"><span data-stu-id="3f558-138">d.</span></span> <span data-ttu-id="3f558-139">스키마가 준비 되 면 **로그 보기**를 클릭 하 여 로그를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-139">Once the schema has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="3f558-140">e.</span><span class="sxs-lookup"><span data-stu-id="3f558-140">e.</span></span> <span data-ttu-id="3f558-141">**마침을** 클릭 하 여 스키마 준비 마법사를 닫고 Active Directory 준비 단계로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-141">Click **Finish** to close the Prepare Schema wizard, and return to the Prepare Active Directory steps.</span></span>
    
5. <span data-ttu-id="3f558-142">**2 단계: 스키마 파티션 복제 확인**</span><span class="sxs-lookup"><span data-stu-id="3f558-142">**Step 2: Verify replication of schema partition**</span></span>
    
    <span data-ttu-id="3f558-143">a.</span><span class="sxs-lookup"><span data-stu-id="3f558-143">a.</span></span> <span data-ttu-id="3f558-144">도메인에 대 한 도메인 컨트롤러에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-144">Log on to the domain controller for the domain.</span></span>
    
    <span data-ttu-id="3f558-145">b.</span><span class="sxs-lookup"><span data-stu-id="3f558-145">b.</span></span> <span data-ttu-id="3f558-146">**서버 관리자**의 **도구** 드롭다운 메뉴에서 **ADSI 편집** 을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-146">Open **ADSI Edit** from the **Tools** drop-down menu in **Server Manager**.</span></span>
    
    <span data-ttu-id="3f558-147">c.</span><span class="sxs-lookup"><span data-stu-id="3f558-147">c.</span></span> <span data-ttu-id="3f558-148">**동작** 메뉴에서 **연결**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-148">On the **Action** menu, click **Connect to**.</span></span>
    
    <span data-ttu-id="3f558-149">d.</span><span class="sxs-lookup"><span data-stu-id="3f558-149">d.</span></span> <span data-ttu-id="3f558-150">**잘 알려진 명명 컨텍스트를 선택합니다** 아래에 있는 **연결 설정** 대화 상자에서 **스키마**를 선택한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-150">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
    <span data-ttu-id="3f558-151">e.</span><span class="sxs-lookup"><span data-stu-id="3f558-151">e.</span></span> <span data-ttu-id="3f558-152">스키마 컨테이너 아래에서 **CN = ms-RTC-SIP-SchemaVersion**을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-152">Under the schema container, search for **CN=ms-RTC-SIP-SchemaVersion**.</span></span> <span data-ttu-id="3f558-153">이 개체가 존재 하 고, 범위의 **upper** 특성 값이 1150이 고, 범위의 **하위** 특성 값이 3 이면 스키마가 성공적으로 업데이트 되 고 복제 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-153">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, the schema was successfully updated and replicated.</span></span> <span data-ttu-id="3f558-154">이 개체가 없거나 **Range upper** 및가 중 **하위** 특성의 값이 지정 되지 않은 경우 스키마가 수정 되지 않았거나 복제 되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-154">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, the schema was not modified or has not replicated.</span></span>
    
6. <span data-ttu-id="3f558-155">**3 단계: 현재 포리스트 준비**</span><span class="sxs-lookup"><span data-stu-id="3f558-155">**Step 3: Prepare current forest**</span></span>
    
    <span data-ttu-id="3f558-156">a.</span><span class="sxs-lookup"><span data-stu-id="3f558-156">a.</span></span> <span data-ttu-id="3f558-157">3 단계 제목 아래의 드롭다운을 클릭 하 여 액세스할 수 있는 3 단계에 대 한 필수 구성 요소 정보를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-157">Review the prerequisites information for Step 3 which can be accessed by clicking the drop-down under the Step 3 title.</span></span>
    
    <span data-ttu-id="3f558-158">b.</span><span class="sxs-lookup"><span data-stu-id="3f558-158">b.</span></span> <span data-ttu-id="3f558-159">3 단계에서 **실행** 을 클릭 하 여 현재 포리스트 준비 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-159">Click **Run** in Step 3 to launch the Prepare Current Forest wizard.</span></span>
    
    <span data-ttu-id="3f558-160">c.</span><span class="sxs-lookup"><span data-stu-id="3f558-160">c.</span></span> <span data-ttu-id="3f558-161">이 절차는 배포 당 한 번만 실행 해야 하며, **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-161">Take note that the procedure should be only run once per deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="3f558-162">d.</span><span class="sxs-lookup"><span data-stu-id="3f558-162">d.</span></span> <span data-ttu-id="3f558-163">유니버설 그룹을 만들 도메인을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-163">Specify the domain where the universal groups will be created.</span></span> <span data-ttu-id="3f558-164">서버가 도메인의 일부인 경우 **로컬 도메인**을 선택 하 고 **다음**을 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-164">If the server is part of the domain, you can choose **Local domain**, and click **Next**.</span></span>
    
    <span data-ttu-id="3f558-165">e.</span><span class="sxs-lookup"><span data-stu-id="3f558-165">e.</span></span> <span data-ttu-id="3f558-166">포리스트가 준비 되 면 **로그 보기**를 클릭 하 여 로그를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-166">Once the forest has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="3f558-167">f.</span><span class="sxs-lookup"><span data-stu-id="3f558-167">f.</span></span> <span data-ttu-id="3f558-168">**마침을** 클릭 하 여 현재 포리스트 준비 마법사를 닫고 Active Directory 준비 단계로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-168">Click **Finish** to close the Prepare Current Forest wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="3f558-169">g.</span><span class="sxs-lookup"><span data-stu-id="3f558-169">g.</span></span> <span data-ttu-id="3f558-170">**앱** 페이지에서 **비즈니스용 Skype 서버 관리 셸을** 클릭 하 여 PowerShell을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-170">Click **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="3f558-171">도움말.</span><span class="sxs-lookup"><span data-stu-id="3f558-171">h.</span></span> <span data-ttu-id="3f558-172">Get-CsAdForest **명령을 입력 하 고 enter 키를**누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-172">Type the command Get-CsAdForest, and press **Enter**.</span></span>
    
    <span data-ttu-id="3f558-173">때.</span><span class="sxs-lookup"><span data-stu-id="3f558-173">i.</span></span> <span data-ttu-id="3f558-174">결과가 **LC_FORESTSETTINGS_STATE_READY**이면 그림과 같이 포리스트가 성공적으로 준비 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-174">If the result is **LC_FORESTSETTINGS_STATE_READY**, the forest has successfully been prepared, as shown in the figure.</span></span>
    
     ![포리스트 복제를 확인 합니다.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. <span data-ttu-id="3f558-176">**4 단계: 글로벌 카탈로그 복제 확인**</span><span class="sxs-lookup"><span data-stu-id="3f558-176">**Step 4: Verify replication of the global catalog**</span></span>
    
    <span data-ttu-id="3f558-177">a.</span><span class="sxs-lookup"><span data-stu-id="3f558-177">a.</span></span> <span data-ttu-id="3f558-178">포리스트 준비가 실행된 포리스트의 도메인 컨트롤러(가급적이면 다른 도메인 컨트롤러의 원격 사이트)에서 **Active Directory 사용자 및 컴퓨터**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-178">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="3f558-179">b.</span><span class="sxs-lookup"><span data-stu-id="3f558-179">b.</span></span> <span data-ttu-id="3f558-180">**Active Directory 사용자 및 컴퓨터**에서 포리스트 또는 자식 도메인의 도메인 이름을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-180">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
    <span data-ttu-id="3f558-181">c.</span><span class="sxs-lookup"><span data-stu-id="3f558-181">c.</span></span> <span data-ttu-id="3f558-182">왼쪽 창에서 **사용자** 컨테이너를 클릭 하 고 오른쪽 창에서 유니버설 그룹 **csadministrator** 를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-182">Click the **Users** container on the left side pane, and look for the Universal group **CsAdministrator** in the right side pane.</span></span> <span data-ttu-id="3f558-183">CsAdministrator (Cs로 시작 하는 다른 새 유니버설 그룹 중 하나)가 있는 경우 Active Directory 복제가 정상적으로 수행 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-183">If CsAdministrator (among other new Universal groups that begin with Cs) is present, Active Directory replication has been successful.</span></span>
    
    <span data-ttu-id="3f558-184">d.</span><span class="sxs-lookup"><span data-stu-id="3f558-184">d.</span></span> <span data-ttu-id="3f558-185">그룹이 아직 없으면 복제를 강제로 수행 하거나, 15 분 동안 기다렸다가 오른쪽 창을 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-185">If the groups are not yet present, you can force the replication, or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="3f558-186">그룹이 나타나면 복제가 완료된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-186">When the groups are present, replication is complete.</span></span>
    
8. <span data-ttu-id="3f558-187">**5 단계: 현재 도메인 준비**</span><span class="sxs-lookup"><span data-stu-id="3f558-187">**Step 5: Prepare the current domain**</span></span>
    
    <span data-ttu-id="3f558-188">a.</span><span class="sxs-lookup"><span data-stu-id="3f558-188">a.</span></span> <span data-ttu-id="3f558-189">5 단계에 대 한 필수 구성 요소 정보를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-189">Review the prerequisites information for Step 5.</span></span>
    
    <span data-ttu-id="3f558-190">b.</span><span class="sxs-lookup"><span data-stu-id="3f558-190">b.</span></span> <span data-ttu-id="3f558-191">5 단계에서 **실행** 을 클릭 하 여 현재 도메인 준비 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-191">Click **Run** in Step 5 to launch the Prepare Current Domain wizard.</span></span>
    
    <span data-ttu-id="3f558-192">c.</span><span class="sxs-lookup"><span data-stu-id="3f558-192">c.</span></span> <span data-ttu-id="3f558-193">배포의 각 도메인에 대해이 절차를 한 번만 실행 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-193">Take note that the procedure should only be run once for each domain in the deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="3f558-194">d.</span><span class="sxs-lookup"><span data-stu-id="3f558-194">d.</span></span> <span data-ttu-id="3f558-195">도메인 준비가 완료 되 면 **로그 보기**를 클릭 하 여 로그를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-195">Once the domain has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="3f558-196">e.</span><span class="sxs-lookup"><span data-stu-id="3f558-196">e.</span></span> <span data-ttu-id="3f558-197">**마침을** 클릭 하 여 현재 도메인 준비 마법사를 닫고 Active Directory 준비 단계로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-197">Click **Finish** to close the Prepare Current Domain wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="3f558-198">이 단계는 비즈니스용 Skype 서버 개체가 있는 모든 도메인에서 완료 해야 하며, 그렇지 않으면 서비스가 시작 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-198">These steps must be completed in every domain where Skype for Business Server objects are found, otherwise services might not start.</span></span> <span data-ttu-id="3f558-199">여기에는 사용자, 연락처 개체, 관리 그룹 또는 기타 개체 형식과 같은 모든 유형의 Active Directory 개체가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-199">This includes any type of Active Directory object, such as users, contact objects, administrative groups, or any other type of object.</span></span> <span data-ttu-id="3f558-200">필요한 경우 Get-csuserreplicatorconfiguration-ADDomainNamingContextList를 사용 하 여 비즈니스용 Skype 서버 개체가 있는 도메인만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-200">You can use Set-CsUserReplicatorConfiguration -ADDomainNamingContextList to add only the domains with Skype for Business Server objects, if needed.</span></span>
    
9. <span data-ttu-id="3f558-201">**6 단계: 도메인에서 복제 확인**</span><span class="sxs-lookup"><span data-stu-id="3f558-201">**Step 6: Verify replication in the domain**</span></span>
    
    <span data-ttu-id="3f558-202">a.</span><span class="sxs-lookup"><span data-stu-id="3f558-202">a.</span></span> <span data-ttu-id="3f558-203">**앱** 페이지에서 **비즈니스용 Skype 서버 관리 셸을** 클릭 하 여 PowerShell을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-203">Click the **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="3f558-204">b.</span><span class="sxs-lookup"><span data-stu-id="3f558-204">b.</span></span> <span data-ttu-id="3f558-205">Get-CsAdDomain 명령을 사용 하 여 도메인 내에서 복제를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-205">Use the command Get-CsAdDomain to verify replication within the domain.</span></span>
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > <span data-ttu-id="3f558-206">Domain 매개 변수를 지정하지 않으면 값이 로컬 도메인으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-206">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> 
  
    <span data-ttu-id="3f558-207">Contoso 도메인에 대 한 명령을 실행 하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-207">Example of running the command for the contoso.local domain:</span></span>
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > <span data-ttu-id="3f558-208">GlobalSettingsDomainController 매개 변수를 사용 하 여 전역 설정이 저장 되는 위치를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-208">By using the parameter GlobalSettingsDomainController, you can indicate where global settings are stored.</span></span> <span data-ttu-id="3f558-209">설정이 시스템 컨테이너에 저장 된 경우 (구성 컨테이너로 전역 설정이 마이그레이션되지 않은 업그레이드 배포의 경우) AD DS 포리스트의 루트에 도메인 컨트롤러를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-209">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your AD DS forest.</span></span> <span data-ttu-id="3f558-210">전역 설정이 구성 컨테이너에 있는 경우(설정이 구성 컨테이너로 마이그레이션된 업그레이드 배포 또는 새 배포에서 일반적임) 포리스트에서 도메인 컨트롤러를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-210">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="3f558-211">이 매개 변수를 지정 하지 않으면 cmdlet은 설정이 구성 컨테이너에 저장 된 것으로 가정 하 고 Active Directory의 모든 도메인 컨트롤러를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-211">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="3f558-212">c.</span><span class="sxs-lookup"><span data-stu-id="3f558-212">c.</span></span> <span data-ttu-id="3f558-213">결과가 **LC_DOMAINSETTINGS_STATE_READY**이면 도메인은 성공적으로 복제 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-213">If the result is **LC_DOMAINSETTINGS_STATE_READY**, the domain has successfully replicated.</span></span>
    
10. <span data-ttu-id="3f558-214">**7 단계: 비즈니스용 Skype 서버 제어판에 대 한 관리 액세스를 제공 하는 사용자 추가**</span><span class="sxs-lookup"><span data-stu-id="3f558-214">**Step 7: Add users to provide administrative access to the Skype for Business Server Control Panel**</span></span>
    
    <span data-ttu-id="3f558-215">a.</span><span class="sxs-lookup"><span data-stu-id="3f558-215">a.</span></span> <span data-ttu-id="3f558-216">Domain Admins 그룹 또는 RTCUniversalServerAdmins 그룹의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-216">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
    <span data-ttu-id="3f558-217">b.</span><span class="sxs-lookup"><span data-stu-id="3f558-217">b.</span></span> <span data-ttu-id="3f558-218">**Active Directory 사용자 및 컴퓨터**를 열고 도메인을 확장 한 다음 **사용자** 컨테이너를 클릭 하 고 csadministrator를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-218">Open **Active Directory Users and Computers**, expand your domain, click the **Users** container, right-click CSAdministrator, and choose **Properties**.</span></span>
    
    <span data-ttu-id="3f558-219">c.</span><span class="sxs-lookup"><span data-stu-id="3f558-219">c.</span></span> <span data-ttu-id="3f558-220">**CSAdministrator 속성**에서 **구성원** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-220">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
    <span data-ttu-id="3f558-221">d.</span><span class="sxs-lookup"><span data-stu-id="3f558-221">d.</span></span> <span data-ttu-id="3f558-222">**구성원** 탭에서 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-222">On the **Members** tab, click **Add**.</span></span> <span data-ttu-id="3f558-223">**사용자, 연락처, 컴퓨터, 서비스 계정 또는 그룹 선택**에서 **선택할 개체 이름을 입력**합니다 .를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-223">In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**.</span></span> <span data-ttu-id="3f558-224">CSAdministrators 그룹에 추가할 사용자 이름 또는 그룹 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-224">Type the user name(s) or group name(s) to add to the group CSAdministrators.</span></span> <span data-ttu-id="3f558-225">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-225">Click **OK**.</span></span>
    
    <span data-ttu-id="3f558-226">e.</span><span class="sxs-lookup"><span data-stu-id="3f558-226">e.</span></span> <span data-ttu-id="3f558-227">**구성원** 탭에서 선택한 사용자 또는 그룹이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-227">On the **Members** tab, confirm that the users or groups that you selected are present.</span></span> <span data-ttu-id="3f558-228">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-228">Click **OK**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3f558-229">비즈니스용 Skype 서버 제어판은 역할 기반 액세스 제어 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-229">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="3f558-230">CsAdministrator 그룹의 구성원 자격은 비즈니스용 Skype 서버 제어판을 사용 하는 사용자에 게 모든 구성 기능을 사용할 수 있는 모든 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-230">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all configuration functions available.</span></span> <span data-ttu-id="3f558-231">특정 기능에 대해 디자인된 사용 가능한 다른 역할도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-231">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="3f558-232">사용 가능한 역할에 대 한 자세한 내용은 비즈니스용 [Skype 서버에 대 한 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 또는 [비즈니스용 skype 서버 2019에 대 한 서버 요구 사항을](../../../SfBServer2019/plan/system-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f558-232">For details on the roles available, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="3f558-233">사용자가 관리 그룹의 구성원으로 만들려면 비즈니스용 Skype 서버를 사용 하도록 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-233">Note that users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
    > [!CAUTION]
    > <span data-ttu-id="3f558-234">보안 및 역할 기반 액세스 제어 무결성을 유지 하기 위해 비즈니스용 Skype 서버 배포 관리에서 사용자가 수행 하는 역할을 정의 하는 그룹에 사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-234">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span> 
  
11. <span data-ttu-id="3f558-235">로그 오프 한 다음 Windows에 다시 로그온 하 여 보안 토큰이 새로운 비즈니스용 Skype 서버 보안 그룹으로 업데이트 된 다음 배포 마법사를 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-235">Log off, and then log back on to Windows so that your security token is updated with the new Skype for Business Server security group, and then reopen the Deployment Wizard.</span></span>
    
12. <span data-ttu-id="3f558-236">그림에 표시 된 것 처럼 성공적인 확인을 위해 **Active Directory 준비** 옆에 녹색 체크 표시가 나타나는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f558-236">Verify that you see a green checkmark next to **Prepare Active Directory** to confirm success, as shown in the figure.</span></span>
    
     ![Active Directory 준비 완료](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a><span data-ttu-id="3f558-238">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f558-238">See also</span></span>
 
[<span data-ttu-id="3f558-239">비즈니스용 Skype 서버 2015에 대 한 Active Directory 도메인 서비스</span><span class="sxs-lookup"><span data-stu-id="3f558-239">Active Directory Domain Services for Skype for Business Server 2015</span></span>](../../plan-your-deployment/security/active-directory-domain-services.md)
