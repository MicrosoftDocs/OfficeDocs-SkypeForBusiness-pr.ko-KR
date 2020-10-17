---
title: 'Lync Server 2013: 스키마 준비 실행'
description: 'Lync Server 2013: 스키마 준비를 실행 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0991bbff7f54f8b8b9eb01fc87f752e00f3dcbfd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569364"
---
# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a><span data-ttu-id="aa627-103">Lync Server 2013에서 Active Directory 스키마 준비 실행</span><span class="sxs-lookup"><span data-stu-id="aa627-103">Running Active Directory schema preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa627-104">_**마지막으로 수정 된 항목:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="aa627-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="aa627-105">설치 또는 Lync Server 관리 셸 cmdlet을 사용 하 여 Active Directory 스키마를 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-105">You can use Setup or Lync Server Management Shell cmdlets to prepare the Active Directory schema.</span></span> <span data-ttu-id="aa627-106">Active Directory 스키마를 확장하는 cmdlet은 **Install-CsAdServerSchema**입니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-106">The cmdlet that extends the Active Directory schema is **Install-CsAdServerSchema**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aa627-107">스키마 준비 cmdlet(<STRONG>Install-CsAdServerSchema</STRONG>)에서는 스키마 마스터에 액세스해야 하며, 이를 위해서는 원격 레지스트리 서비스가 실행되고 원격 레지스트리 키가 사용할 수 있도록 설정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-107">The schema preparation cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) must access the schema master, which requires that the remote registry service is running and that the remote registry key is enabled.</span></span> <span data-ttu-id="aa627-108">스키마 마스터에서 원격 레지스트리 서비스를 사용할 수 없는 경우에는 스키마 마스터에서 로컬로 cmdlet를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-108">If the remote registry service cannot be enabled on the schema master, you can run the cmdlet locally on the schema master.</span></span> <span data-ttu-id="aa627-109">레지스트리 원격 액세스에 대 한 자세한 내용은 Microsoft 기술 자료 문서 314837, "레지스트리에 대 한 원격 액세스를 관리 하는 방법"을 참조 하십시오 <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A> .</span><span class="sxs-lookup"><span data-stu-id="aa627-109">For details about registry remote access, see Microsoft Knowledge Base article 314837, "How to Manage Remote Access to the Registry," at <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span></span>



</div>

<span data-ttu-id="aa627-110">스키마 준비가 완료되면 포리스트 준비를 진행하기 전에 스키마 파티션이 복제되었는지 수동으로 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-110">After you complete schema preparation, manually verify that the schema partition has been replicated before proceeding to forest preparation.</span></span> <span data-ttu-id="aa627-111">자세한 내용은 [Lync Server 2013에서 Active Directory 스키마 복제 확인](lync-server-2013-verifying-schema-replication.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aa627-111">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="aa627-112">설치 프로그램을 사용하여 현재 포리스트의 스키마를 준비하려면</span><span class="sxs-lookup"><span data-stu-id="aa627-112">To use Setup to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="aa627-113">스키마 마스터의 관리자 권한을 가진 Schema Admins 그룹의 구성원으로 포리스트의 서버에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-113">Log on to a server in your forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="aa627-114">Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 배포 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-114">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="aa627-115">Microsoft Visual C++ 재배포 가능 파일을 설치하라는 메시지가 표시되면 **예**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-115">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>

4.  <span data-ttu-id="aa627-116">Lync server 2013 설치 대화 상자에 Lync Server 파일을 설치할 위치를 묻는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-116">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="aa627-117">기본 위치를 선택하거나 **찾아보기**를 클릭하여 원하는 위치를 선택한 후에 **설치**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-117">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>

5.  <span data-ttu-id="aa627-118">사용권 계약 페이지에서 **동의함**을 선택한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-118">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span>

6.  <span data-ttu-id="aa627-119">설치 관리자가 Lync Server 핵심 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-119">The installer installs the Lync Server Core Components.</span></span>

7.  <span data-ttu-id="aa627-120">배포 마법사를 사용할 준비가 되었으면 **Active Directory 준비**를 클릭한 후 배포 상태가 확인될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-120">When the Deployment Wizard is ready, click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

8.  <span data-ttu-id="aa627-121">**1단계: 스키마 준비**에서 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-121">At **Step 1: Prepare Schema**, click **Run**.</span></span>

9.  <span data-ttu-id="aa627-122">**스키마 준비** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-122">On the **Prepare Schema** page, click **Next**.</span></span>

10. <span data-ttu-id="aa627-123">**명령 실행** 페이지에서 **작업 상태: 완료됨**을 찾은 다음 **로그 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-123">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

11. <span data-ttu-id="aa627-124">**동작** 열 아래에 있는 **스키마 준비**를 확장 하 고 **\<Success\>** 각 작업 끝에 있는 실행 결과를 찾아서 스키마 준비가 성공적으로 완료 되었는지 확인 한 다음 로그를 닫고 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-124">Under the **Action** column, expand **Schema Prep**, look for the **\<Success\>** Execution Result at the end of each task to verify that schema preparation completed successfully, close the log, and then click **Finish**.</span></span>

12. <span data-ttu-id="aa627-125">Active Directory 복제가 완료될 때까지 기다리거나 복제를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-125">Wait for Active Directory replication to complete or force replication.</span></span>

13. <span data-ttu-id="aa627-126">다음 절차에 설명된 대로 스키마 변경 내용이 다른 모든 도메인 컨트롤러에 복제되었는지 수동으로 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-126">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="aa627-127">자세한 내용은 [Lync Server 2013에서 Active Directory 스키마 복제 확인](lync-server-2013-verifying-schema-replication.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aa627-127">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="aa627-128">cmdlet를 사용하여 현재 포리스트의 스키마를 준비하려면</span><span class="sxs-lookup"><span data-stu-id="aa627-128">To use cmdlets to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="aa627-129">스키마 마스터의 관리자 권한을 가진 Schema Admins 그룹의 구성원으로 포리스트의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-129">Log on to a computer in the forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="aa627-130">Lync Server Core 구성 요소는 다음과 같이 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-130">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="aa627-131">Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 Lync Server 배포 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-131">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="aa627-132">Microsoft Visual C++ 재배포 가능 파일을 설치하라는 메시지가 표시되면 **예**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-132">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="aa627-133">Lync server 2013 설치 대화 상자에 Lync Server 파일을 설치할 위치를 묻는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-133">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="aa627-134">기본 위치를 선택하거나 **찾아보기**를 클릭하여 원하는 위치를 선택한 후에 **설치**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-134">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="aa627-135">사용권 계약 페이지에서 **동의함**을 선택한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-135">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="aa627-136">설치 관리자가 Lync Server 2013 핵심 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-136">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="aa627-137">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="aa627-138">을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-138">Run:</span></span>
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    <span data-ttu-id="aa627-139">Ldf 매개 변수를 지정 하지 않은 경우 기본값은 레지스트리에서 읽은 Lync Server 2013 설치 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-139">If you do not specify the Ldf parameter, the default value is the Lync Server 2013 installation path that is read from the registry.</span></span>
    
    <span data-ttu-id="aa627-140">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-140">For example:</span></span>
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  <span data-ttu-id="aa627-141">다음 cmdlet를 사용하여 스키마 준비가 완료되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-141">Use the following cmdlet to verify that schema preparation ran to completion.</span></span>
    
        Get-CsAdServerSchema 
    
    <span data-ttu-id="aa627-142">스키마 준비가 성공적으로 완료 된 경우이 cmdlet은 **스키마 \_ 버전 \_ 상태 \_ CURRENT** 의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-142">This cmdlet returns a value of **SCHEMA\_VERSION\_STATE\_CURRENT** if schema preparation was successful.</span></span>

6.  <span data-ttu-id="aa627-143">Active Directory 복제가 완료될 때까지 기다리거나 복제를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-143">Wait for Active Directory replication to complete or force replication.</span></span>

7.  <span data-ttu-id="aa627-144">다음 절차에 설명된 대로 스키마 변경 내용이 다른 모든 도메인 컨트롤러에 복제되었는지 수동으로 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="aa627-144">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="aa627-145">자세한 내용은 [Lync Server 2013에서 Active Directory 스키마 복제 확인](lync-server-2013-verifying-schema-replication.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aa627-145">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aa627-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa627-146">See Also</span></span>


[<span data-ttu-id="aa627-147">Lync Server 2013에서 Active Directory 스키마 복제 확인</span><span class="sxs-lookup"><span data-stu-id="aa627-147">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)  


[<span data-ttu-id="aa627-148">Lync Server 2013에서 Active Directory 스키마 준비</span><span class="sxs-lookup"><span data-stu-id="aa627-148">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

