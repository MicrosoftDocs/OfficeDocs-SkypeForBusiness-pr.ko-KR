---
title: 응답 그룹 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c01ec246ba99d2a2f71a16179d839409e6b57b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="f09ec-102">응답 그룹 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="f09ec-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f09ec-103">_**마지막으로 수정한 주제:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="f09ec-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="f09ec-104">사용자를 Lync Server 2013 풀로 이동한 후에는 응답 그룹을 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="f09ec-105">응답 그룹 마이그레이션에는 에이전트 그룹, 큐, 워크플로, 오디오 파일 복사, 레거시 배포에서 Lync Server 2013 풀로 응답 그룹 연락처 개체 이동 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-105">Migrating response groups includes copying agent groups, queues, workflows, and audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="f09ec-106">레거시 응답 그룹을 마이그레이션한 후에는 응답 그룹에 대 한 호출이 Lync Server 2013 풀의 응답 그룹 응용 프로그램에 의해 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="f09ec-107">응답 그룹에 대 한 호출은 더 이상 레거시 풀에서 처리 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f09ec-108">모든 사용자를 Lync Server 2013 풀로 이동 하기 전에 응답 그룹을 마이그레이션할 수 있지만 모든 사용자를 먼저 이동 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="f09ec-109">특히 응답 그룹 에이전트를 사용 하는 사용자는 Lync Server 2013 풀로 이동할 때까지 새로운 기능을 완전히 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="f09ec-110">응답 그룹을 마이그레이션하기 전에 응답 그룹 응용 프로그램이 포함 된 Lync Server 2013 풀을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="f09ec-111">엔터프라이즈 음성을 배포할 때 응답 그룹 응용 프로그램이 기본적으로 설치 되 고 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="f09ec-112">**Get-CsService – ApplicationServer** cmdlet을 실행 하 여 응답 그룹 응용 프로그램이 설치 되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-112">You can ensure that the Response Group application is installed by running the **Get-CsService–ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f09ec-113">이전 응답 그룹을 마이그레이션하기 전에 Lync Server 2013 풀에서 새 Lync Server 2013 응답 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="f09ec-114">응답 그룹을 레거시 풀에서 Lync Server 2013로 마이그레이션하려면 **CsRgsConfiguration** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="f09ec-115">**CsRgsConfiguration**를 실행 하려면 먼저 WMI (Windows Management Instrumentation) 이전 버전과의 호환성 인터페이스 패키지를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-115">Before you can run **Move-CsRgsConfiguration**, you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package.</span></span> <span data-ttu-id="f09ec-116">OCSWMIBC. msi를 실행 하 여이 응용 프로그램을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-116">Install this application by running OCSWMIBC.msi.</span></span> <span data-ttu-id="f09ec-117">설정 폴더의 설치 미디어에서 OCSWMIBC .msi를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-117">You can find OCSWMIBC.msi on the installation media in the Setup folder.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f09ec-118">응답 그룹 마이그레이션 cmdlet은 전체 풀에 대 한 응답 그룹 구성을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="f09ec-119">마이그레이션할 특정 그룹, 큐 또는 워크플로를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-119">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="f09ec-120">응답 그룹을 마이그레이션한 후에는 공식 에이전트가 응답 그룹에 로그인 및 로그 아웃 하는 데 사용 하는 URL을 업데이트 하 고 Lync Server 제어판 또는 Lync Server Management Shell cmdlet을 사용 하 여 모든 에이전트 그룹, 큐 및 워크플로가 이동 되었는지 확인 해야 합니다. 함.</span><span class="sxs-lookup"><span data-stu-id="f09ec-120">After you migrate the response groups, you need to update the URL that formal agents use to sign into and out of their response groups, and use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="f09ec-121">응답 그룹을 마이그레이션하면 Office Communications Server 2007 R2 응답 그룹이 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-121">When you migrate response groups, the Office Communications Server 2007 R2 response groups are not removed.</span></span> <span data-ttu-id="f09ec-122">Office Communications Server 2007 R2 응답 그룹을 제거 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="f09ec-122">Do not remove Office Communications Server 2007 R2 response groups.</span></span> <span data-ttu-id="f09ec-123">Office Communications Server 2007 R2 응답 그룹을 제거 하면 Lync Server 2013의 응답 그룹이 작동을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-123">If you remove an Office Communications Server 2007 R2 response group, the response groups in Lync Server 2013 stop working.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f09ec-124">풀을 해제할 때까지 이전 배포에서 데이터를 제거 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-124">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="f09ec-125">또한 마이그레이션한 후 즉시 응답 그룹을 내보낼 것을 적극 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-125">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="f09ec-126">Office Communications Server 2007 R2 응답 그룹이 제거 되 면 백업에서 응답 그룹을 복원 하 여 Lync Server 2013 응답 그룹을 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-126">If an Office Communications Server 2007 R2 response group gets removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="f09ec-127">**CsRgsConfiguration** cmdlet을 실행 하는 경우 롤백 목적으로 에이전트 그룹, 큐, 워크플로 및 오디오 파일이 레거시 풀에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-127">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="f09ec-128">그러나 레거시 풀로 롤백해야 하는 경우에는 요청 **이동 Applicationendpoint** cmdlet을 실행 하 여 연락처 개체를 레거시 풀로 다시 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-128">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f09ec-129">풀을 해제할 때까지 레거시 풀에서 응답 그룹 데이터를 삭제 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-129">We recommend that you don't delete any response group data from the legacy pool until you decommission the pool.</span></span>



</div>

<span data-ttu-id="f09ec-130">응답 그룹 구성을 마이그레이션하기 위해 사용 하는 절차는 레거시 풀과 Lync Server 2013 풀 사이에 일대일 관계를 사용 하는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-130">The procedure that follows for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="f09ec-131">마이그레이션 및 배포 중에 풀을 통합 하거나 분할할 계획 이라면 어떤 레거시 풀이 어떤 Lync Server 2013 풀에 매핑되는지 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-131">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="f09ec-132">응답 그룹 구성을 마이그레이션하려면</span><span class="sxs-lookup"><span data-stu-id="f09ec-132">To Migrate Response Group Configurations</span></span>

1.  <span data-ttu-id="f09ec-133">설치 미디어의 설치 폴더에서 OCSWMIBC msi.dll을 찾아 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-133">Locate OCSWMIBC.msi in the Setup folder of the installation media and install it.</span></span>

2.  <span data-ttu-id="f09ec-134">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 관리자 권한이 있는 계정을 사용 하 여 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-134">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

3.  <span data-ttu-id="f09ec-135">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-135">Open the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="f09ec-136">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-136">At the command line, type the following:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="f09ec-137">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-137">For example:</span></span>
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  <span data-ttu-id="f09ec-138">Office Communications Server 2007 R2 환경에서 Microsoft Office Communicator 2007 R2에 대 한 응답 그룹 탭을 배포한 경우 Office Communicator 2007 R2 탭 .xml 파일에서 탭을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-138">If you deployed the Response Group tab for Microsoft Office Communicator 2007 R2 in your Office Communications Server 2007 R2 environment, remove the tab from the Office Communicator 2007 R2 tabs.xml file.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f09ec-139">공식 에이전트는 응답 그룹 탭을 사용 하 여 응답 그룹에 로그인 한 후 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-139">Formal agents used the Response Group tab to sign in to their response groups before they could receive calls.</span></span> <span data-ttu-id="f09ec-140">응답 그룹 탭을 배포한 경우 Office Communicator 2007 R2 탭 .xml 파일을 배포 했을 때의 위치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-140">If you deployed the Response Group tab, you chose the location for the Office Communicator 2007 R2 tabs.xml file when you deployed it.</span></span>

    
    </div>

6.  <span data-ttu-id="f09ec-141">상담원에 게 응답 그룹에 로그인 하 고 로그 아웃 해야 하는 업데이트 된 URL을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-141">Provide users with the updated URL that agents need to sign into and out of their response groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f09ec-142">URL은 일반적으로 https://webpoolFQDN/RgsClients/Tab.aspxwebpoolFQDN이 Lync Server 2013에 방금 마이그레이션한 풀과 연결 된 웹 풀의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-142">The URL is typically https://webpoolFQDN/RgsClients/Tab.aspx, where webpoolFQDN is the fully qualified domain name (FQDN) of the web pool that is associated with the pool that you just migrated to Lync Server 2013.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f09ec-143">Lync의 <STRONG>도구</STRONG> 메뉴에서 URL을 사용할 수 있기 때문에 사용자가 lync 2013으로 업그레이드 한 후에는이 단계가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-143">This step is not required after users upgrade to Lync 2013 because the URL is available from the <STRONG>Tools</STRONG> menu in Lync.</span></span>

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="f09ec-144">Lync Server 제어판을 사용 하 여 응답 그룹 마이그레이션을 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="f09ec-144">To Verify Response Group Migration by Using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f09ec-145">Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-145">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="f09ec-146">왼쪽 탐색 창에서 **응답 그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-146">In the left navigation pane, click **Response Groups**.</span></span>

3.  <span data-ttu-id="f09ec-147">**워크플로** 탭에서 Office Communications Server 2007 R2 환경의 모든 워크플로가 목록에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-147">On the **Workflow** tab, verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="f09ec-148">**큐** 탭을 클릭 하 고 Office Communications Server 2007 R2 환경의 모든 큐가 목록에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-148">Click the **Queue** tab, and verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

5.  <span data-ttu-id="f09ec-149">**그룹** 탭을 클릭 하 고 Office Communications Server 2007 R2 환경의 모든 에이전트 그룹이 목록에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-149">Click the **Group** tab, and verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a><span data-ttu-id="f09ec-150">Cmdlet을 사용 하 여 응답 그룹 마이그레이션을 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="f09ec-150">To Verify Response Group Migration by Using Cmdlets</span></span>

1.  <span data-ttu-id="f09ec-151">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-151">Open the Lync Server Management Shell.</span></span>
    
    <span data-ttu-id="f09ec-152">다음 cmdlet에 대 한 자세한 내용을 보려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-152">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

2.  <span data-ttu-id="f09ec-153">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-153">At the command line, type the following:</span></span>
    
        Get-CsRgsAgentGroup

3.  <span data-ttu-id="f09ec-154">Office Communications Server 2007 R2 환경의 모든 에이전트 그룹이 목록에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-154">Verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="f09ec-155">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-155">At the command line, type the following:</span></span>
    
        Get-CsRgsQueue

5.  <span data-ttu-id="f09ec-156">Office Communications Server 2007 R2 환경의 모든 큐가 목록에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-156">Verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

6.  <span data-ttu-id="f09ec-157">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-157">At the command line, type the following:</span></span>
    
        Get-CsRgsWorkflow

7.  <span data-ttu-id="f09ec-158">Office Communications Server 2007 R2 환경의 모든 워크플로가 목록에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f09ec-158">Verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

