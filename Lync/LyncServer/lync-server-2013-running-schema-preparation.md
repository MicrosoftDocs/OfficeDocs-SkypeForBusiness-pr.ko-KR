---
title: 'Lync Server 2013: 스키마 준비 실행'
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
ms.openlocfilehash: 06b02981e9baa589801839c8fd8c871ae35b0dde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a><span data-ttu-id="a0a97-102">Lync Server 2013에서 Active Directory 스키마 준비 실행</span><span class="sxs-lookup"><span data-stu-id="a0a97-102">Running Active Directory schema preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0a97-103">_**마지막으로 수정한 주제:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="a0a97-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="a0a97-104">설치 또는 Lync Server Management Shell cmdlet을 사용 하 여 Active Directory 스키마를 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the Active Directory schema.</span></span> <span data-ttu-id="a0a97-105">Active Directory 스키마를 확장 하는 cmdlet은 **설치-CsAdServerSchema**입니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-105">The cmdlet that extends the Active Directory schema is **Install-CsAdServerSchema**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a0a97-106">스키마 준비 cmdlet (<STRONG>설치-CsAdServerSchema</STRONG>)는 스키마 마스터에 액세스 해야 하며,이는 원격 레지스트리 서비스가 실행 중이 고 원격 레지스트리 키를 사용 하도록 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-106">The schema preparation cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) must access the schema master, which requires that the remote registry service is running and that the remote registry key is enabled.</span></span> <span data-ttu-id="a0a97-107">스키마 마스터에서 원격 레지스트리 서비스를 사용 하도록 설정할 수 없는 경우 스키마 마스터에서 cmdlet을 로컬로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-107">If the remote registry service cannot be enabled on the schema master, you can run the cmdlet locally on the schema master.</span></span> <span data-ttu-id="a0a97-108">레지스트리 원격 액세스에 대 한 자세한 내용은 Microsoft 기술 자료 문서 314837, "레지스트리에 대 한 원격 액세스 관리 방법"을 참조 <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>하세요.</span><span class="sxs-lookup"><span data-stu-id="a0a97-108">For details about registry remote access, see Microsoft Knowledge Base article 314837, "How to Manage Remote Access to the Registry," at <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span></span>



</div>

<span data-ttu-id="a0a97-109">스키마 준비를 완료 한 후에는 포리스트 준비를 진행 하기 전에 스키마 파티션이 복제 되었는지 수동으로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-109">After you complete schema preparation, manually verify that the schema partition has been replicated before proceeding to forest preparation.</span></span> <span data-ttu-id="a0a97-110">자세한 내용은 [Lync Server 2013에서 Active Directory 스키마 복제 확인](lync-server-2013-verifying-schema-replication.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0a97-110">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="a0a97-111">설치 프로그램을 사용 하 여 현재 포리스트의 스키마를 준비 하려면</span><span class="sxs-lookup"><span data-stu-id="a0a97-111">To use Setup to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="a0a97-112">포리스트의 서버에 스키마 관리자 그룹의 구성원으로 로그온 하 고 스키마 마스터에 대 한 관리자 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-112">Log on to a server in your forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="a0a97-113">Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 배포 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-113">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="a0a97-114">Microsoft Visual c + + 재배포 가능 패키지를 설치 하 라는 메시지가 표시 되 면 **예**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-114">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>

4.  <span data-ttu-id="a0a97-115">Lync Server 2013 설정 대화 상자에서 Lync Server 파일을 설치할 위치를 묻는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-115">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="a0a97-116">기본 위치를 선택 하거나 선택한 위치를 **찾은** 다음 **설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-116">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>

5.  <span data-ttu-id="a0a97-117">사용권 계약 페이지에서 **사용권 계약에 동의**를 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-117">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span>

6.  <span data-ttu-id="a0a97-118">설치 관리자가 Lync Server Core 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-118">The installer installs the Lync Server Core Components.</span></span>

7.  <span data-ttu-id="a0a97-119">배포 마법사가 준비 되 면 **Active Directory 준비**를 클릭 한 다음 배포 상태가 결정 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-119">When the Deployment Wizard is ready, click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

8.  <span data-ttu-id="a0a97-120">**1 단계: 스키마 준비**에서 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-120">At **Step 1: Prepare Schema**, click **Run**.</span></span>

9.  <span data-ttu-id="a0a97-121">**스키마 준비** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-121">On the **Prepare Schema** page, click **Next**.</span></span>

10. <span data-ttu-id="a0a97-122">**명령 실행** 페이지에서 **작업 상태: 완료됨**을 찾은 다음 **로그 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-122">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

11. <span data-ttu-id="a0a97-123">**작업** 열에서 **스키마 Prep**을 확장 하 고 각 작업의 끝에 있는 \*\* \<성공\> \*\* 실행 결과를 찾아 스키마 준비가 성공적으로 완료 되었는지 확인 하 고 로그를 닫은 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-123">Under the **Action** column, expand **Schema Prep**, look for the **\<Success\>** Execution Result at the end of each task to verify that schema preparation completed successfully, close the log, and then click **Finish**.</span></span>

12. <span data-ttu-id="a0a97-124">Active Directory 복제가 완료 되거나 강제로 복제 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-124">Wait for Active Directory replication to complete or force replication.</span></span>

13. <span data-ttu-id="a0a97-125">스키마 변경 내용이 다른 모든 도메인 컨트롤러로 복제 되었는지 수동으로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-125">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="a0a97-126">자세한 내용은 [Lync Server 2013에서 Active Directory 스키마 복제 확인](lync-server-2013-verifying-schema-replication.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0a97-126">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="a0a97-127">Cmdlet을 사용 하 여 현재 포리스트의 스키마를 준비 하려면</span><span class="sxs-lookup"><span data-stu-id="a0a97-127">To use cmdlets to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="a0a97-128">포리스트의 컴퓨터에 스키마 관리자 그룹의 구성원으로 로그온 하 고 스키마 마스터에 대 한 관리자 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-128">Log on to a computer in the forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="a0a97-129">다음과 같이 Lync Server Core 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-129">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="a0a97-130">Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 Lync Server 배포 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-130">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="a0a97-131">Microsoft Visual c + + 재배포 가능 패키지를 설치 하 라는 메시지가 표시 되 면 **예**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-131">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="a0a97-132">Lync Server 2013 설정 대화 상자에서 Lync Server 파일을 설치할 위치를 묻는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-132">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="a0a97-133">기본 위치를 선택 하거나 선택한 위치를 **찾은** 다음 **설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-133">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="a0a97-134">사용권 계약 페이지에서 **사용권 계약에 동의**를 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-134">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="a0a97-135">설치 관리자가 Lync Server 2013 핵심 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-135">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="a0a97-136">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="a0a97-137">런</span><span class="sxs-lookup"><span data-stu-id="a0a97-137">Run:</span></span>
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    <span data-ttu-id="a0a97-138">Ldf 매개 변수를 지정 하지 않으면 기본적으로 레지스트리에서 읽은 Lync Server 2013 설치 경로가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-138">If you do not specify the Ldf parameter, the default value is the Lync Server 2013 installation path that is read from the registry.</span></span>
    
    <span data-ttu-id="a0a97-139">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-139">For example:</span></span>
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  <span data-ttu-id="a0a97-140">다음 cmdlet을 사용 하 여 스키마 준비 작업이 완료 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-140">Use the following cmdlet to verify that schema preparation ran to completion.</span></span>
    
        Get-CsAdServerSchema 
    
    <span data-ttu-id="a0a97-141">이 cmdlet은 스키마 준비에 성공한 경우 **현재 스키마\_버전\_상태\_** 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-141">This cmdlet returns a value of **SCHEMA\_VERSION\_STATE\_CURRENT** if schema preparation was successful.</span></span>

6.  <span data-ttu-id="a0a97-142">Active Directory 복제가 완료 되거나 강제로 복제 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-142">Wait for Active Directory replication to complete or force replication.</span></span>

7.  <span data-ttu-id="a0a97-143">스키마 변경 내용이 다른 모든 도메인 컨트롤러로 복제 되었는지 수동으로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a97-143">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="a0a97-144">자세한 내용은 [Lync Server 2013에서 Active Directory 스키마 복제 확인](lync-server-2013-verifying-schema-replication.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0a97-144">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a0a97-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0a97-145">See Also</span></span>


[<span data-ttu-id="a0a97-146">Lync Server 2013에서 Active Directory 스키마 복제 확인</span><span class="sxs-lookup"><span data-stu-id="a0a97-146">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)  


[<span data-ttu-id="a0a97-147">Lync Server 2013에서 Active Directory 스키마 준비</span><span class="sxs-lookup"><span data-stu-id="a0a97-147">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

