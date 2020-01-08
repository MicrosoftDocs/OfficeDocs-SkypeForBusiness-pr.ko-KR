---
title: 'Lync Server 2013: 포리스트 준비 실행'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b011623b9091c1c707ae77381dacb99ba4642a21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="c7506-102">Lync Server 2013에 대한 포리스트 준비 실행</span><span class="sxs-lookup"><span data-stu-id="c7506-102">Running forest preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7506-103">_**마지막으로 수정한 주제:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="c7506-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="c7506-104">설치 또는 Lync Server Management Shell cmdlet을 사용 하 여 포리스트를 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the forest.</span></span> <span data-ttu-id="c7506-105">포리스트를 준비 하는 cmdlet은 **-CsAdForest를 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-105">The cmdlet that prepares the forest is **Enable-CsAdForest**.</span></span>

<span data-ttu-id="c7506-106">포리스트를 준비한 후에는 도메인 준비를 실행 하기 전에 전역 설정이 복제 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-106">After you prepare the forest, you must verify that global settings have been replicated before running domain preparation.</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a><span data-ttu-id="c7506-107">설치 프로그램을 사용 하 여 포리스트 준비</span><span class="sxs-lookup"><span data-stu-id="c7506-107">To use Setup to prepare the forest</span></span>

1.  <span data-ttu-id="c7506-108">도메인에 가입 된 컴퓨터에 포리스트 루트 도메인에 대 한 엔터프라이즈 관리자 그룹의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-108">Log on to a computer that is joined to a domain as a member of the Enterprise Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="c7506-109">Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 배포 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="c7506-110">**Active Directory 준비**를 클릭한 다음 배포 상태가 확인될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="c7506-111">**3 단계: 현재 포리스트 준비**에서 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-111">At **Step 3: Prepare Current Forest**, click **Run**.</span></span>

5.  <span data-ttu-id="c7506-112">**포리스트 준비** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-112">On the **Prepare Forest** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c7506-113">포리스트 준비를 통해 Lync Server 2013의 유니버설 그룹을 배치할 위치를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-113">Forest Preparation allows you to choose where to place the Universal Groups for Lync Server 2013.</span></span> <span data-ttu-id="c7506-114">조직의 요구 사항에 맞는 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-114">Choose a location that is consistent with the requirements of your organization.</span></span>

    
    </div>

6.  <span data-ttu-id="c7506-115">**명령 실행** 페이지에서 **작업 상태: 완료됨**을 찾은 다음 **로그 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-115">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="c7506-116">**작업** 열에서 **포리스트**준비를 확장 하 고 각 작업의 끝에서 \*\* \<성공\> \*\* 실행 결과를 찾아 포리스트 준비가 성공적으로 완료 되었는지 확인 하 고 로그를 닫은 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-116">Under the **Action** column, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="c7506-117">도메인 준비를 실행 하기 전에 Active Directory 복제가 완료 되거나 포리스트 루트 도메인 컨트롤러에 대 한 **Active Directory 사이트 및 서비스** 스냅인에 나열 된 모든 도메인 컨트롤러로 복제를 강제로 수행할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-117">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="c7506-118">모든 Active Directory 사이트의 도메인 컨트롤러 간 복제를 강제로 사이트 내에서 몇 분 내에 복제를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-118">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a><span data-ttu-id="c7506-119">Cmdlet을 사용 하 여 포리스트를 준비 하려면</span><span class="sxs-lookup"><span data-stu-id="c7506-119">To use cmdlets to prepare the forest</span></span>

1.  <span data-ttu-id="c7506-120">포리스트 루트 도메인의 Domain Admins 그룹 구성원으로 도메인에 가입한 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-120">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="c7506-121">다음과 같이 Lync Server Core 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-121">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="c7506-122">Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 Lync Server 배포 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-122">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="c7506-123">Microsoft Visual c + + 재배포 가능 패키지를 설치 하 라는 메시지가 표시 되 면 **예**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-123">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="c7506-124">Lync Server 2013 설정 대화 상자에서 Lync Server 파일을 설치할 위치를 묻는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-124">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="c7506-125">기본 위치를 선택 하거나 선택한 위치를 **찾은** 다음 **설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-125">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="c7506-126">사용권 계약 페이지에서 **사용권 계약에 동의**를 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-126">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="c7506-127">설치 관리자가 Lync Server 2013 핵심 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-127">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="c7506-128">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="c7506-129">런</span><span class="sxs-lookup"><span data-stu-id="c7506-129">Run:</span></span>
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    <span data-ttu-id="c7506-130">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-130">For example:</span></span>
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    <span data-ttu-id="c7506-131">GroupDomain 매개 변수를 지정 하지 않으면 로컬 도메인이 기본값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-131">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span> <span data-ttu-id="c7506-132">기본 도메인이 아닌 도메인에서 유니버설 그룹을 만든 경우에는 GroupDomain 매개 변수를 명시적으로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-132">If universal groups were created previously in a domain that is not the default domain, you must specify the GroupDomain parameter explicitly.</span></span>

5.  <span data-ttu-id="c7506-133">도메인 준비를 실행 하기 전에 Active Directory 복제가 완료 되거나 포리스트 루트 도메인 컨트롤러에 대 한 **Active Directory 사이트 및 서비스** 스냅인에 나열 된 모든 도메인 컨트롤러로 복제를 강제로 수행할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-133">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span>

6.  <span data-ttu-id="c7506-134">포리스트 준비가 성공적으로 완료 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-134">Verify that forest preparation was successful.</span></span> <span data-ttu-id="c7506-135">런</span><span class="sxs-lookup"><span data-stu-id="c7506-135">Run:</span></span>
    
        Get-CsAdForest 
    
    <span data-ttu-id="c7506-136">이 cmdlet은 포리스트 준비에 **성공한\_경우\_LC\_FORESTSETTINGS 상태** 에 대 한 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7506-136">This cmdlet returns a value of **LC\_FORESTSETTINGS\_STATE\_READY** if forest preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c7506-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7506-137">See Also</span></span>


[<span data-ttu-id="c7506-138">Lync Server 2013에 대해 Cmdlet을 사용하여 포리스트 준비 되돌리기</span><span class="sxs-lookup"><span data-stu-id="c7506-138">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[<span data-ttu-id="c7506-139">Lync Server 2013에 대한 포리스트 준비</span><span class="sxs-lookup"><span data-stu-id="c7506-139">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

