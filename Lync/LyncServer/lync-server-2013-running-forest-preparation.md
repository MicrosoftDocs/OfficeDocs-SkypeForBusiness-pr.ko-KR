---
title: 'Lync Server 2013: 포리스트 준비 실행'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df862c99d05ea27a305a9965e9026065ecfe7792
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="4b0a5-102">Lync Server 2013에 대 한 포리스트 준비 실행</span><span class="sxs-lookup"><span data-stu-id="4b0a5-102">Running forest preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b0a5-103">_**마지막으로 수정 된 항목:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="4b0a5-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="4b0a5-104">설치 또는 Lync Server 관리 셸 cmdlet을 사용 하 여 포리스트를 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the forest.</span></span> <span data-ttu-id="4b0a5-105">포리스트를 준비하는 cmdlet은 **Enable-CsAdForest**입니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-105">The cmdlet that prepares the forest is **Enable-CsAdForest**.</span></span>

<span data-ttu-id="4b0a5-106">포리스트를 준비한 후 도메인 준비를 실행하기 전에 전역 설정이 복제되었는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-106">After you prepare the forest, you must verify that global settings have been replicated before running domain preparation.</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a><span data-ttu-id="4b0a5-107">설치 프로그램을 사용하여 포리스트를 준비하려면</span><span class="sxs-lookup"><span data-stu-id="4b0a5-107">To use Setup to prepare the forest</span></span>

1.  <span data-ttu-id="4b0a5-108">포리스트 루트 도메인에 대해 Enterprise Admins 그룹의 구성원으로 도메인에 가입한 컴퓨터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-108">Log on to a computer that is joined to a domain as a member of the Enterprise Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="4b0a5-109">Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 배포 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="4b0a5-110">**Active Directory 준비**를 클릭한 다음 배포 상태가 확인될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="4b0a5-111">**3단계: 현재 포리스트 준비**에서 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-111">At **Step 3: Prepare Current Forest**, click **Run**.</span></span>

5.  <span data-ttu-id="4b0a5-112">**포리스트 준비** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-112">On the **Prepare Forest** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4b0a5-113">포리스트 준비에서는 Lync Server 2013에 대 한 유니버설 그룹을 배치할 위치를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-113">Forest Preparation allows you to choose where to place the Universal Groups for Lync Server 2013.</span></span> <span data-ttu-id="4b0a5-114">조직의 요구 사항에 맞는 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-114">Choose a location that is consistent with the requirements of your organization.</span></span>

    
    </div>

6.  <span data-ttu-id="4b0a5-115">**명령 실행** 페이지에서 **작업 상태: 완료됨**을 찾은 다음 **로그 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-115">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="4b0a5-116">**동작** 열 아래에 있는 **포리스트 준비**를 확장 하 고 각 작업 끝에 있는 \*\* \<성공\> \*\* 실행 결과를 찾아서 포리스트 준비가 성공적으로 완료 되었는지 확인 한 다음 로그를 닫고 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-116">Under the **Action** column, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="4b0a5-p103">도메인 준비를 실행하기 전에 포리스트 루트 도메인 컨트롤러의 **Active Directory 사이트 및 서비스** 스냅인에 나열된 모든 도메인 컨트롤러로 Active Directory 복제가 완료될 때까지 기다리거나 복제를 적용합니다. 몇 분 내에 사이트 내부에서 복제가 발생하도록 모든 Active Directory 사이트의 도메인 컨트롤러 간에 복제를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-p103">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation. Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a><span data-ttu-id="4b0a5-119">cmdlet을 사용하여 포리스트를 준비하려면</span><span class="sxs-lookup"><span data-stu-id="4b0a5-119">To use cmdlets to prepare the forest</span></span>

1.  <span data-ttu-id="4b0a5-120">포리스트 루트 도메인에서 Domain Admins 그룹의 구성원으로 도메인에 가입한 컴퓨터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-120">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="4b0a5-121">Lync Server Core 구성 요소는 다음과 같이 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-121">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="4b0a5-122">Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 Lync Server 배포 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-122">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="4b0a5-123">Microsoft Visual C++ 재배포 가능 파일을 설치하라는 메시지가 표시되면 **예**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-123">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="4b0a5-124">Lync server 2013 설치 대화 상자에 Lync Server 파일을 설치할 위치를 묻는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-124">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="4b0a5-125">기본 위치를 선택하거나 **찾아보기**를 클릭하여 원하는 위치를 선택한 후에 **설치**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-125">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="4b0a5-126">사용권 계약 페이지에서 **동의함**을 선택한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-126">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="4b0a5-127">설치 관리자가 Lync Server 2013 핵심 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-127">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="4b0a5-128">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="4b0a5-129">를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-129">Run:</span></span>
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    <span data-ttu-id="4b0a5-130">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-130">For example:</span></span>
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    <span data-ttu-id="4b0a5-p106">GroupDomain 매개 변수를 지정하지 않을 경우 기본값은 로컬 도메인입니다. 기본 도메인이 아닌 도메인에서 이전에 유니버설 그룹이 만들어진 경우 GroupDomain 매개 변수를 명시적으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-p106">If you do not specify the GroupDomain parameter, the default value is the local domain. If universal groups were created previously in a domain that is not the default domain, you must specify the GroupDomain parameter explicitly.</span></span>

5.  <span data-ttu-id="4b0a5-133">도메인 준비를 실행하기 전에 포리스트 루트 도메인 컨트롤러의 **Active Directory 사이트 및 서비스** 스냅인에 나열된 모든 도메인 컨트롤러로 Active Directory 복제가 완료될 때까지 기다리거나 복제를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-133">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span>

6.  <span data-ttu-id="4b0a5-p107">포리스트 준비가 성공적으로 완료되었는지 확인합니다. 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-p107">Verify that forest preparation was successful. Run:</span></span>
    
        Get-CsAdForest 
    
    <span data-ttu-id="4b0a5-136">이 cmdlet은 포리스트 준비가 성공적으로 완료 된 경우 **LC\_\_FORESTSETTINGS STATE\_READY** 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0a5-136">This cmdlet returns a value of **LC\_FORESTSETTINGS\_STATE\_READY** if forest preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4b0a5-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b0a5-137">See Also</span></span>


[<span data-ttu-id="4b0a5-138">Cmdlet을 사용 하 여 Lync Server 2013에 대 한 포리스트 준비 되돌리기</span><span class="sxs-lookup"><span data-stu-id="4b0a5-138">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[<span data-ttu-id="4b0a5-139">Lync Server 2013에 대 한 포리스트 준비</span><span class="sxs-lookup"><span data-stu-id="4b0a5-139">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

