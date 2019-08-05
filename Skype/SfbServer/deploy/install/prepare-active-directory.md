---
title: 비즈니스용 Skype 서버에 대 한 Active Directory 준비
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: '요약: 비즈니스용 Skype 서버 설치를 위해 Active Directory 도메인을 준비 하는 방법에 대해 알아봅니다. Microsoft 평가 센터에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server하세요.'
ms.openlocfilehash: e15431cf08925920f4f7ec223d9983d3dc3e35c7
ms.sourcegitcommit: 46fb558814cb6bd7d70729eac590afd51fc6606e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2019
ms.locfileid: "36197828"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a><span data-ttu-id="45eb1-104">비즈니스용 Skype 서버에 대 한 Active Directory 준비</span><span class="sxs-lookup"><span data-stu-id="45eb1-104">Prepare Active Directory for Skype for Business Server</span></span>
 
<span data-ttu-id="45eb1-105">**요약:** 비즈니스용 Skype 서버용 설치를 위해 Active Directory 도메인을 준비 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-105">**Summary:** Learn how to prepare your Active Directory domain for an installation of Skype for Business Server.</span></span> <span data-ttu-id="45eb1-106">[Microsoft 평가 센터](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="45eb1-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="45eb1-107">비즈니스용 Skype 서버는 Active Directory와 긴밀 하 게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-107">Skype for Business Server works closely with Active Directory.</span></span> <span data-ttu-id="45eb1-108">비즈니스용 Skype 서버에서 작업 하려면 Active Directory 도메인을 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-108">You must prepare the Active Directory domain to work with Skype for Business Server.</span></span> <span data-ttu-id="45eb1-109">이 프로세스는 배포 마법사에서 수행 되며 도메인에 대해 한 번만 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-109">This process is accomplished in the Deployment Wizard and is only done once for the domain.</span></span> <span data-ttu-id="45eb1-110">이는 프로세스가 그룹을 생성 하 고 도메인을 수정 하므로 한 번만 수행 해야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-110">This is because the process creates groups and modifies the domain, and you need to do that only once.</span></span> <span data-ttu-id="45eb1-111">1 ~ 5 단계는 순서에 관계 없이 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-111">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="45eb1-112">그러나 6, 7, 8 단계를 순서 대로 수행 하 고 다이어그램에 명시 된 대로 1 ~ 5 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-112">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="45eb1-113">Active Directory는 4 단계에서 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-113">Preparing Active Directory is step 4 of 8.</span></span> <span data-ttu-id="45eb1-114">Active Directory 계획에 대 한 자세한 내용은 비즈니스용 [Skype 서버에 대 한 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 또는 비즈니스용 [skype 서버 2019에 대 한 서버 요구](../../../SfBServer2019/plan/system-requirements.md)사항을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45eb1-114">For more information about planning for Active Directory, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![개요 다이어그램](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a><span data-ttu-id="45eb1-116">Active Directory 준비</span><span class="sxs-lookup"><span data-stu-id="45eb1-116">Prepare Active Directory</span></span>

<span data-ttu-id="45eb1-117">비즈니스용 Skype 서버는 AD DS (Active Directory 도메인 서비스)와 긴밀 하 게 통합 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-117">Skype for Business Server is tightly integrated with Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="45eb1-118">비즈니스용 Skype 서버를 처음 설치 하기 전에 Active Directory를 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-118">Before Skype for Business Server can be installed for the first time, Active Directory must be prepared.</span></span> <span data-ttu-id="45eb1-119">**Active Directory 준비** 라는 배포 마법사의 섹션에서는 비즈니스용 Skype Server에서 사용할 active directory 환경을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-119">The section of the Deployment Wizard titled **Prepare Active Directory** prepares the Active Directory environment for use with Skype for Business Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="45eb1-120">토폴로지의 모든 서버를 추적 하 고 통신 하는 데 비즈니스용 Skype 서버 사용 (AD DS).</span><span class="sxs-lookup"><span data-stu-id="45eb1-120">Skype for Business Server uses (AD DS) to track and communicate with all of the servers in a topology.</span></span> <span data-ttu-id="45eb1-121">모든 서버는 비즈니스용 Skype 서버가 제대로 작동할 수 있도록 도메인에 가입 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-121">Every server must be joined to the domain so that Skype for Business Server can work properly.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="45eb1-122">배포의 각 도메인에 대해 Active Directory 준비 절차가 한 번만 실행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-122">The Prepare Active Directory procedure should be run only once for each domain in the deployment.</span></span> 
  
<span data-ttu-id="45eb1-123">**Active Directory를 준비**하기 위한 비디오 단계를 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="45eb1-123">Watch the video steps for **Prepare Active Directory**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a><span data-ttu-id="45eb1-124">배포 마법사에서 Active Directory 준비</span><span class="sxs-lookup"><span data-stu-id="45eb1-124">Prepare Active Directory from the Deployment Wizard</span></span>

1. <span data-ttu-id="45eb1-125">Active Directory 도메인에 대 한 스키마 관리자 자격 증명을 사용 하 여 사용자로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-125">Log on as a user with Schema Admins credentials for the Active Directory domain.</span></span>
    
2. <span data-ttu-id="45eb1-126">비즈니스용 Skype 서버 배포 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-126">Open Skype for Business Server Deployment Wizard.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="45eb1-127">비즈니스용 Skype 서버 배포 마법사에서 만든 로그 파일을 검토 하려는 경우 배포 마법사가 실행 된 컴퓨터에서 해당 단계를 실행 하는 AD DS 사용자의 사용자 디렉터리에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-127">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the AD DS user who ran the step.</span></span> <span data-ttu-id="45eb1-128">예를 들어 사용자가 도메인의 도메인 관리자로 로그온 한 경우 로그 파일은 C:\Users\Administrator.Contoso\AppData\Local\Temp.에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-128">For example, if the user logged on as the domain administrator in the domain, contoso.local, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span> 
  
3. <span data-ttu-id="45eb1-129">**Active Directory 준비** 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-129">Click the **Prepare Active Directory** link.</span></span>
    
4. <span data-ttu-id="45eb1-130">**1 단계: 스키마 준비**</span><span class="sxs-lookup"><span data-stu-id="45eb1-130">**Step 1: Prepare schema**</span></span>
    
    <span data-ttu-id="45eb1-131">에서.</span><span class="sxs-lookup"><span data-stu-id="45eb1-131">a.</span></span> <span data-ttu-id="45eb1-132">1 단계 제목 아래에 있는 드롭다운을 클릭 하 여 액세스할 수 있는 1 단계의 필수 구성 요소 정보를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-132">Review the prerequisites information for Step 1 which can be accessed by clicking the drop-down under the Step 1 title.</span></span>
    
    <span data-ttu-id="45eb1-133">b.</span><span class="sxs-lookup"><span data-stu-id="45eb1-133">b.</span></span> <span data-ttu-id="45eb1-134">1 단계에서 **실행** 을 클릭 하 여 스키마 준비 마법사를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-134">Click **Run** in Step 1 to launch the Prepare Schema wizard.</span></span>
    
    <span data-ttu-id="45eb1-135">c.</span><span class="sxs-lookup"><span data-stu-id="45eb1-135">c.</span></span> <span data-ttu-id="45eb1-136">각 배포에 대해 절차가 한 번만 실행 되어야 한다는 점에 유의 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-136">Take note that the procedure should be run only once for each deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="45eb1-137">a.</span><span class="sxs-lookup"><span data-stu-id="45eb1-137">d.</span></span> <span data-ttu-id="45eb1-138">스키마를 준비한 후에는 **로그 보기**를 클릭 하 여 로그를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-138">Once the schema has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="45eb1-139">z.e.n.works.</span><span class="sxs-lookup"><span data-stu-id="45eb1-139">e.</span></span> <span data-ttu-id="45eb1-140">**마침을** 클릭 하 여 스키마 준비 마법사를 닫고 Active Directory 준비 단계로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-140">Click **Finish** to close the Prepare Schema wizard, and return to the Prepare Active Directory steps.</span></span>
    
5. <span data-ttu-id="45eb1-141">**2 단계: 스키마 파티션 복제 확인**</span><span class="sxs-lookup"><span data-stu-id="45eb1-141">**Step 2: Verify replication of schema partition**</span></span>
    
    <span data-ttu-id="45eb1-142">에서.</span><span class="sxs-lookup"><span data-stu-id="45eb1-142">a.</span></span> <span data-ttu-id="45eb1-143">도메인에 대 한 도메인 컨트롤러에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-143">Log on to the domain controller for the domain.</span></span>
    
    <span data-ttu-id="45eb1-144">b.</span><span class="sxs-lookup"><span data-stu-id="45eb1-144">b.</span></span> <span data-ttu-id="45eb1-145">**서버 관리자**의 **도구** 드롭다운 메뉴에서 **ADSI 편집** 을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-145">Open **ADSI Edit** from the **Tools** drop-down menu in **Server Manager**.</span></span>
    
    <span data-ttu-id="45eb1-146">c.</span><span class="sxs-lookup"><span data-stu-id="45eb1-146">c.</span></span> <span data-ttu-id="45eb1-147">**작업** 메뉴에서 **연결 대상**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-147">On the **Action** menu, click **Connect to**.</span></span>
    
    <span data-ttu-id="45eb1-148">a.</span><span class="sxs-lookup"><span data-stu-id="45eb1-148">d.</span></span> <span data-ttu-id="45eb1-149">**연결 설정** 대화 상자의 **잘 알려진 명명 컨텍스트 선택**에서 **스키마**를 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-149">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
    <span data-ttu-id="45eb1-150">z.e.n.works.</span><span class="sxs-lookup"><span data-stu-id="45eb1-150">e.</span></span> <span data-ttu-id="45eb1-151">스키마 컨테이너 아래에서 **CN = ms-RTC-SIP-SchemaVersion**을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-151">Under the schema container, search for **CN=ms-RTC-SIP-SchemaVersion**.</span></span> <span data-ttu-id="45eb1-152">이 개체가 있고 a/a 2 **상한** 특성의 값이 1150이 고, **range lower** 특성의 값이 3 이면 스키마는 성공적으로 업데이트 되 고 복제 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-152">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, the schema was successfully updated and replicated.</span></span> <span data-ttu-id="45eb1-153">이 개체가 없거나 **Range upper** 및 **range lower** 특성 값이 지정 되지 않은 경우 스키마는 수정 되거나 복제 되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-153">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, the schema was not modified or has not replicated.</span></span>
    
6. <span data-ttu-id="45eb1-154">**3 단계: 현재 포리스트 준비**</span><span class="sxs-lookup"><span data-stu-id="45eb1-154">**Step 3: Prepare current forest**</span></span>
    
    <span data-ttu-id="45eb1-155">에서.</span><span class="sxs-lookup"><span data-stu-id="45eb1-155">a.</span></span> <span data-ttu-id="45eb1-156">3 단계 제목 아래에 있는 드롭다운을 클릭 하 여 액세스할 수 있는 3 단계의 필수 구성 요소 정보를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-156">Review the prerequisites information for Step 3 which can be accessed by clicking the drop-down under the Step 3 title.</span></span>
    
    <span data-ttu-id="45eb1-157">b.</span><span class="sxs-lookup"><span data-stu-id="45eb1-157">b.</span></span> <span data-ttu-id="45eb1-158">3 단계에서 **실행** 을 클릭 하 여 현재 포리스트 준비 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-158">Click **Run** in Step 3 to launch the Prepare Current Forest wizard.</span></span>
    
    <span data-ttu-id="45eb1-159">c.</span><span class="sxs-lookup"><span data-stu-id="45eb1-159">c.</span></span> <span data-ttu-id="45eb1-160">배포 당 절차가 한 번만 실행 되어야 한다는 점에 유의 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-160">Take note that the procedure should be only run once per deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="45eb1-161">a.</span><span class="sxs-lookup"><span data-stu-id="45eb1-161">d.</span></span> <span data-ttu-id="45eb1-162">유니버설 그룹이 생성 될 도메인을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-162">Specify the domain where the universal groups will be created.</span></span> <span data-ttu-id="45eb1-163">서버가 도메인에 속해 있는 경우 **로컬 도메인**을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-163">If the server is part of the domain, you can choose **Local domain**, and click **Next**.</span></span>
    
    <span data-ttu-id="45eb1-164">z.e.n.works.</span><span class="sxs-lookup"><span data-stu-id="45eb1-164">e.</span></span> <span data-ttu-id="45eb1-165">포리스트가 준비 되 면 **로그 보기**를 클릭 하 여 로그를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-165">Once the forest has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="45eb1-166">f.</span><span class="sxs-lookup"><span data-stu-id="45eb1-166">f.</span></span> <span data-ttu-id="45eb1-167">**마침을** 클릭 하 여 현재 포리스트 준비 마법사를 닫고 Active Directory 준비 단계로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-167">Click **Finish** to close the Prepare Current Forest wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="45eb1-168">g.</span><span class="sxs-lookup"><span data-stu-id="45eb1-168">g.</span></span> <span data-ttu-id="45eb1-169">**앱** 페이지에서 **비즈니스용 Skype Server Management Shell** 을 클릭 하 여 PowerShell을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-169">Click **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="45eb1-170">넣기.</span><span class="sxs-lookup"><span data-stu-id="45eb1-170">h.</span></span> <span data-ttu-id="45eb1-171">명령 가져오기-CsAdForest를 입력 하 고 enter \*\*\*\* 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-171">Type the command Get-CsAdForest, and press **Enter**.</span></span>
    
    <span data-ttu-id="45eb1-172">칼럼.</span><span class="sxs-lookup"><span data-stu-id="45eb1-172">i.</span></span> <span data-ttu-id="45eb1-173">결과가 **LC_FORESTSETTINGS_STATE_READY**경우 그림과 같이 포리스트가 성공적으로 준비 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-173">If the result is **LC_FORESTSETTINGS_STATE_READY**, the forest has successfully been prepared, as shown in the figure.</span></span>
    
     ![포리스트 복제를 확인 합니다.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. <span data-ttu-id="45eb1-175">**4 단계: 글로벌 카탈로그의 복제 확인**</span><span class="sxs-lookup"><span data-stu-id="45eb1-175">**Step 4: Verify replication of the global catalog**</span></span>
    
    <span data-ttu-id="45eb1-176">에서.</span><span class="sxs-lookup"><span data-stu-id="45eb1-176">a.</span></span> <span data-ttu-id="45eb1-177">도메인 컨트롤러 (다른 도메인 컨트롤러의 원격 사이트에 있는 경우)에서 포리스트 준비가 실행 되는 포리스트의 **Active Directory 사용자 및 컴퓨터**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-177">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="45eb1-178">b.</span><span class="sxs-lookup"><span data-stu-id="45eb1-178">b.</span></span> <span data-ttu-id="45eb1-179">**Active Directory 사용자 및 컴퓨터**에서 포리스트 또는 자식 도메인의 도메인 이름을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-179">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
    <span data-ttu-id="45eb1-180">c.</span><span class="sxs-lookup"><span data-stu-id="45eb1-180">c.</span></span> <span data-ttu-id="45eb1-181">왼쪽 창에서 **사용자** 컨테이너를 클릭 하 고 오른쪽 창에서 유니버설 그룹 **csadministrator** 를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-181">Click the **Users** container on the left side pane, and look for the Universal group **CsAdministrator** in the right side pane.</span></span> <span data-ttu-id="45eb1-182">CsAdministrator (Cs로 시작 하는 새로운 유니버설 그룹 중 하나)가 있는 경우 Active Directory 복제가 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-182">If CsAdministrator (among other new Universal groups that begin with Cs) is present, Active Directory replication has been successful.</span></span>
    
    <span data-ttu-id="45eb1-183">a.</span><span class="sxs-lookup"><span data-stu-id="45eb1-183">d.</span></span> <span data-ttu-id="45eb1-184">그룹이 아직 표시 되지 않으면 복제를 강제로 수행 하거나, 15 분 동안 기다렸다가 오른쪽 창을 새로 고칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-184">If the groups are not yet present, you can force the replication, or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="45eb1-185">그룹이 있으면 복제가 완료 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-185">When the groups are present, replication is complete.</span></span>
    
8. <span data-ttu-id="45eb1-186">**5 단계: 현재 도메인 준비**</span><span class="sxs-lookup"><span data-stu-id="45eb1-186">**Step 5: Prepare the current domain**</span></span>
    
    <span data-ttu-id="45eb1-187">에서.</span><span class="sxs-lookup"><span data-stu-id="45eb1-187">a.</span></span> <span data-ttu-id="45eb1-188">5 단계에 대 한 필수 구성 요소 정보를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-188">Review the prerequisites information for Step 5.</span></span>
    
    <span data-ttu-id="45eb1-189">b.</span><span class="sxs-lookup"><span data-stu-id="45eb1-189">b.</span></span> <span data-ttu-id="45eb1-190">5 단계에서 **실행** 을 클릭 하 여 현재 도메인 준비 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-190">Click **Run** in Step 5 to launch the Prepare Current Domain wizard.</span></span>
    
    <span data-ttu-id="45eb1-191">c.</span><span class="sxs-lookup"><span data-stu-id="45eb1-191">c.</span></span> <span data-ttu-id="45eb1-192">배포의 각 도메인에 대해이 절차를 한 번만 실행 해야 한다는 점에 유의 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-192">Take note that the procedure should only be run once for each domain in the deployment, and then click **Next**.</span></span>
    
    <span data-ttu-id="45eb1-193">a.</span><span class="sxs-lookup"><span data-stu-id="45eb1-193">d.</span></span> <span data-ttu-id="45eb1-194">도메인을 준비한 후에는 **로그 보기**를 클릭 하 여 로그를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-194">Once the domain has been prepared, you can view the log by clicking **View Log**.</span></span> 
    
    <span data-ttu-id="45eb1-195">z.e.n.works.</span><span class="sxs-lookup"><span data-stu-id="45eb1-195">e.</span></span> <span data-ttu-id="45eb1-196">**마침을** 클릭 하 여 현재 도메인 준비 마법사를 닫고 Active Directory 준비 단계로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-196">Click **Finish** to close the Prepare Current Domain wizard, and return to the Prepare Active Directory steps.</span></span>
    
    <span data-ttu-id="45eb1-197">이 단계는 비즈니스용 Skype 서버 개체가 있는 모든 도메인에서 완료 되어야 하 고, 그렇지 않으면 서비스가 시작 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-197">These steps must be completed in every domain where Skype for Business Server objects are found, otherwise services might not start.</span></span> <span data-ttu-id="45eb1-198">여기에는 사용자, 연락처 개체, 관리 그룹 또는 기타 개체 형식 등 모든 유형의 Active Directory 개체가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-198">This includes any type of Active Directory object, such as users, contact objects, administrative groups, or any other type of object.</span></span> <span data-ttu-id="45eb1-199">필요에 따라 Set-CsUserReplicatorConfiguration-Addomainnaminingcontextlist를 사용 하 여 비즈니스용 Skype 서버 개체가 있는 도메인만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-199">You can use Set-CsUserReplicatorConfiguration -ADDomainNamingContextList to add only the domains with Skype for Business Server objects, if needed.</span></span>
    
9. <span data-ttu-id="45eb1-200">**6 단계: 도메인에서 복제 확인**</span><span class="sxs-lookup"><span data-stu-id="45eb1-200">**Step 6: Verify replication in the domain**</span></span>
    
    <span data-ttu-id="45eb1-201">에서.</span><span class="sxs-lookup"><span data-stu-id="45eb1-201">a.</span></span> <span data-ttu-id="45eb1-202">**앱** 페이지에서 **비즈니스용 Skype Server Management Shell** 을 클릭 하 여 PowerShell을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-202">Click the **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.</span></span>
    
    <span data-ttu-id="45eb1-203">b.</span><span class="sxs-lookup"><span data-stu-id="45eb1-203">b.</span></span> <span data-ttu-id="45eb1-204">명령 가져오기-CsAdDomain을 사용 하 여 도메인 내의 복제를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-204">Use the command Get-CsAdDomain to verify replication within the domain.</span></span>
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > <span data-ttu-id="45eb1-205">Domain 매개 변수를 지정하지 않으면 값이 로컬 도메인으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-205">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> 
  
    <span data-ttu-id="45eb1-206">Contoso. i a 지방 도메인에 대 한 명령을 실행 하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-206">Example of running the command for the contoso.local domain:</span></span>
    
   ```
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > <span data-ttu-id="45eb1-207">GlobalSettingsDomainController 매개 변수를 사용 하 여 전역 설정이 저장 되는 위치를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-207">By using the parameter GlobalSettingsDomainController, you can indicate where global settings are stored.</span></span> <span data-ttu-id="45eb1-208">설정이 시스템 컨테이너에 저장 되는 경우 (구성 컨테이너로 마이그레이션된 전역 설정이 없는 업그레이드 배포의 경우)에는 AD DS 포리스트의 루트에서 도메인 컨트롤러를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-208">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your AD DS forest.</span></span> <span data-ttu-id="45eb1-209">전역 설정이 구성 컨테이너에 있는 경우(설정이 구성 컨테이너로 마이그레이션된 업그레이드 배포 또는 새 배포에서 일반적임) 포리스트에서 도메인 컨트롤러를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-209">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="45eb1-210">이 매개 변수를 지정 하지 않으면 cmdlet이 구성 컨테이너에 저장 된 것으로 간주 하 고 Active Directory의 모든 도메인 컨트롤러를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-210">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="45eb1-211">c.</span><span class="sxs-lookup"><span data-stu-id="45eb1-211">c.</span></span> <span data-ttu-id="45eb1-212">결과가 **LC_DOMAINSETTINGS_STATE_READY**경우 도메인이 성공적으로 복제 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-212">If the result is **LC_DOMAINSETTINGS_STATE_READY**, the domain has successfully replicated.</span></span>
    
10. <span data-ttu-id="45eb1-213">**7 단계: 비즈니스용 Skype Server 제어판에 대 한 관리 액세스를 제공 하는 사용자 추가**</span><span class="sxs-lookup"><span data-stu-id="45eb1-213">**Step 7: Add users to provide administrative access to the Skype for Business Server Control Panel**</span></span>
    
    <span data-ttu-id="45eb1-214">에서.</span><span class="sxs-lookup"><span data-stu-id="45eb1-214">a.</span></span> <span data-ttu-id="45eb1-215">Domain Admins 그룹 또는 RTCUniversalServerAdmins 그룹의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-215">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
    <span data-ttu-id="45eb1-216">b.</span><span class="sxs-lookup"><span data-stu-id="45eb1-216">b.</span></span> <span data-ttu-id="45eb1-217">**Active Directory 사용자 및 컴퓨터**를 열고, 도메인을 확장 하 고, **사용자** 컨테이너를 클릭 하 고, csadministrator를 마우스 오른쪽 단추로 클릭 하 고, **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-217">Open **Active Directory Users and Computers**, expand your domain, click the **Users** container, right-click CSAdministrator, and choose **Properties**.</span></span>
    
    <span data-ttu-id="45eb1-218">c.</span><span class="sxs-lookup"><span data-stu-id="45eb1-218">c.</span></span> <span data-ttu-id="45eb1-219">**CSAdministrator 속성**에서 **구성원** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-219">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
    <span data-ttu-id="45eb1-220">a.</span><span class="sxs-lookup"><span data-stu-id="45eb1-220">d.</span></span> <span data-ttu-id="45eb1-221">**구성원** 탭에서 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-221">On the **Members** tab, click **Add**.</span></span> <span data-ttu-id="45eb1-222">**사용자, 연락처, 컴퓨터, 서비스 계정 또는 그룹 선택**에서 **선택할 개체 이름 입력**을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-222">In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**.</span></span> <span data-ttu-id="45eb1-223">그룹 CSAdministrators에 추가할 사용자 이름 또는 그룹 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-223">Type the user name(s) or group name(s) to add to the group CSAdministrators.</span></span> <span data-ttu-id="45eb1-224">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-224">Click **OK**.</span></span>
    
    <span data-ttu-id="45eb1-225">z.e.n.works.</span><span class="sxs-lookup"><span data-stu-id="45eb1-225">e.</span></span> <span data-ttu-id="45eb1-226">**구성원** 탭에서 선택한 사용자 또는 그룹이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-226">On the **Members** tab, confirm that the users or groups that you selected are present.</span></span> <span data-ttu-id="45eb1-227">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-227">Click **OK**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="45eb1-228">비즈니스용 Skype 서버 제어판은 역할 기반 액세스 제어 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-228">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="45eb1-229">CsAdministrator 그룹의 구성원은 비즈니스용 Skype Server 제어판을 사용 하는 사용자에 게 모든 구성 기능을 사용할 수 있는 모든 권한을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-229">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all configuration functions available.</span></span> <span data-ttu-id="45eb1-230">특정 기능에 대해 디자인된 사용 가능한 다른 역할도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-230">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="45eb1-231">사용 가능한 역할에 대 한 자세한 내용은 비즈니스용 [Skype 서버에 대 한 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 또는 비즈니스용 [skype Server 2019의 서버 요구](../../../SfBServer2019/plan/system-requirements.md)사항을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45eb1-231">For details on the roles available, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="45eb1-232">관리 그룹의 구성원으로 만들려면 비즈니스용 Skype 서버용으로 사용자를 설정 하지 않아도 된다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="45eb1-232">Note that users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
    > [!CAUTION]
    > <span data-ttu-id="45eb1-233">보안 및 역할 기반 액세스 제어 무결성을 유지 하려면 사용자가 비즈니스용 Skype Server 배포 관리에서 수행 하는 역할을 정의 하는 그룹에 사용자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-233">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span> 
  
11. <span data-ttu-id="45eb1-234">로그 오프 한 다음 Windows에 다시 로그온 하 여 보안 토큰이 비즈니스용 Skype 서버 보안 그룹으로 업데이트 된 다음 배포 마법사를 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-234">Log off, and then log back on to Windows so that your security token is updated with the new Skype for Business Server security group, and then reopen the Deployment Wizard.</span></span>
    
12. <span data-ttu-id="45eb1-235">그림에 표시 된 대로 **Active Directory 준비** 옆에 있는 녹색 확인 표시가 표시 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45eb1-235">Verify that you see a green checkmark next to **Prepare Active Directory** to confirm success, as shown in the figure.</span></span>
    
     ![Active Directory 준비를 완료 했습니다.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a><span data-ttu-id="45eb1-237">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45eb1-237">See also</span></span>
 
[<span data-ttu-id="45eb1-238">비즈니스용 Skype Server 2015 Active Directory 도메인 서비스</span><span class="sxs-lookup"><span data-stu-id="45eb1-238">Active Directory Domain Services for Skype for Business Server 2015</span></span>](../../plan-your-deployment/security/active-directory-domain-services.md)
