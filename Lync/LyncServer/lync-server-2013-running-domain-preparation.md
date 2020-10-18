---
title: 'Lync Server 2013: 도메인 준비 실행'
description: 'Lync Server 2013: 도메인 준비를 실행 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f2c4ebe94d07ed2d1fd9be013cd8e88204312f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577784"
---
# <a name="running-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="87e4d-103">Lync Server 2013에 대 한 도메인 준비 실행</span><span class="sxs-lookup"><span data-stu-id="87e4d-103">Running domain preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87e4d-104">_**마지막으로 수정 된 항목:** 2013-04-16_</span><span class="sxs-lookup"><span data-stu-id="87e4d-104">_**Topic Last Modified:** 2013-04-16_</span></span>

<span data-ttu-id="87e4d-105">설치 또는 Lync Server 관리 셸 cmdlet을 사용 하 여 도메인을 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-105">You can use Setup or Lync Server Management Shell cmdlets to prepare domains.</span></span> <span data-ttu-id="87e4d-106">도메인을 준비하는 cmdlet은 **Enable-CsAdDomain**입니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-106">The cmdlet that prepares a domain is **Enable-CsAdDomain**.</span></span>

<span data-ttu-id="87e4d-107">도메인 준비는 Lync Server 2013에 대 한 Active Directory 도메인 서비스 준비의 마지막 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-107">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span>

<div>

## <a name="to-use-setup-to-prepare-domains"></a><span data-ttu-id="87e4d-108">설치 프로그램을 사용하여 도메인을 준비하려면</span><span class="sxs-lookup"><span data-stu-id="87e4d-108">To use Setup to prepare domains</span></span>

1.  <span data-ttu-id="87e4d-109">도메인의 서버에 Domain Admins 그룹 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-109">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="87e4d-110">Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 Lync Server 배포 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-110">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="87e4d-111">**Active Directory 준비**를 클릭한 다음 배포 상태가 확인될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-111">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="87e4d-112">**5단계: 현재 도메인 준비**에서 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-112">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

5.  <span data-ttu-id="87e4d-113">**도메인 준비** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-113">On the **Prepare Domain** page, click **Next**.</span></span>

6.  <span data-ttu-id="87e4d-114">**명령 실행** 페이지에서 **작업 상태: 완료됨**을 찾은 다음 **로그 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-114">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="87e4d-115">**동작** 열 아래에 있는 **도메인 준비**를 확장 하 고 **\<Success\>** 각 작업 끝에 있는 실행 결과를 찾아서 도메인 준비가 성공적으로 완료 되었는지 확인 한 다음 로그를 닫고 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-115">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="87e4d-116">Active Directory 복제가 포리스트 루트 도메인 컨트롤러의 Active Directory 사이트 및 서비스 스냅인에 나열된 모든 도메인 컨트롤러로 복제를 완료하거나 적용할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-116">Wait for Active Directory replication to complete or force replication to all the domain controllers listed in the Active Directory Sites and Services snap-in for the forest root domain controller.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a><span data-ttu-id="87e4d-117">cmdlet을 사용하여 도메인을 준비하려면</span><span class="sxs-lookup"><span data-stu-id="87e4d-117">To use cmdlets to prepare the domain</span></span>

1.  <span data-ttu-id="87e4d-118">도메인의 서버에 Domain Admins 그룹 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-118">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="87e4d-119">Lync Server Core 구성 요소는 다음과 같이 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-119">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="87e4d-120">Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 Lync Server 배포 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-120">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="87e4d-121">Microsoft Visual C++ 재배포 가능 파일을 설치하라는 메시지가 표시되면 **예**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-121">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="87e4d-122">Lync server 2013 설치 대화 상자에 Lync Server 파일을 설치할 위치를 묻는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-122">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="87e4d-123">기본 위치를 선택하거나 **찾아보기**를 클릭하여 원하는 위치를 선택한 후에 **설치**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-123">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="87e4d-124">사용권 계약 페이지에서 **동의함**을 선택한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-124">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="87e4d-125">설치 관리자가 Lync Server 2013 핵심 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-125">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="87e4d-126">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-126">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="87e4d-127">을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-127">Run:</span></span>
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    <span data-ttu-id="87e4d-128">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-128">For example:</span></span>
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    <span data-ttu-id="87e4d-129">Domain 매개 변수를 지정하지 않는 경우에는 로컬 도메인이 기본값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-129">If you do not specify the Domain parameter, the default is the local domain.</span></span>

5.  <span data-ttu-id="87e4d-p104">다음을 실행하여 도메인 준비가 성공적으로 완료되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-p104">Verify that domain preparation was successful. Run:</span></span>
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    <span data-ttu-id="87e4d-132">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-132">For example:</span></span>
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="87e4d-133">GlobalSettingsDomainController 매개 변수를 통해 전역 설정이 저장되어 있는 위치를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-133">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="87e4d-134">설정이 시스템 컨테이너에 저장되어 있는 경우(전역 설정이 구성 컨테이너로 마이그레이션되지 않은 업그레이드 배포에서 일반적임) Active Directory 포리스트의 루트에서 도메인 컨트롤러를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-134">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global settings migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="87e4d-135">전역 설정이 구성 컨테이너에 있는 경우(설정이 구성 컨테이너로 마이그레이션된 업그레이드 배포 또는 새 배포에서 일반적임) 포리스트에서 도메인 컨트롤러를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-135">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="87e4d-136">이 매개 변수를 지정 하지 않으면 cmdlet은 설정이 구성 컨테이너에 저장 된 것으로 가정 하 고 AD DS의 모든 도메인 컨트롤러를 참조 합니다 &nbsp; .</span><span class="sxs-lookup"><span data-stu-id="87e4d-136">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>
    
    <span data-ttu-id="87e4d-137">**Domain** 매개 변수를 지정 하지 않을 경우 기본값은 로컬 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-137">If you do not specify the **Domain** parameter, the default is the local domain.</span></span>
    
    <span data-ttu-id="87e4d-138">이 cmdlet은 도메인 준비가 성공적으로 완료 된 경우 \*\*LC \_ domainsettings \_ STATE \_ \*\* 의 가능한 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="87e4d-138">This cmdlet returns a value of **LC\_DOMAINSETTINGS\_STATE\_READY** if domain preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="87e4d-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87e4d-139">See Also</span></span>


[<span data-ttu-id="87e4d-140">Cmdlet을 사용 하 여 Lync Server 2013에 대 한 도메인 준비 되돌리기</span><span class="sxs-lookup"><span data-stu-id="87e4d-140">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[<span data-ttu-id="87e4d-141">Lync Server 2013에 대 한 도메인 준비</span><span class="sxs-lookup"><span data-stu-id="87e4d-141">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

