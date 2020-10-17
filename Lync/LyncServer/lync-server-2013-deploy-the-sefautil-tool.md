---
title: 'Lync Server 2013: SEFAUtil 도구 배포'
description: 'Lync Server 2013: SEFAUtil 도구를 배포 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 311f14f33dff30b388836a7f02483c4afe5da1b1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558614"
---
# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a><span data-ttu-id="77d7d-103">Lync Server 2013에서 SEFAUtil 도구 배포</span><span class="sxs-lookup"><span data-stu-id="77d7d-103">Deploy the SEFAUtil tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77d7d-104">_**마지막으로 수정 된 항목:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="77d7d-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="77d7d-105">그룹 통화 픽업를 배포 하 고 관리 하려면 SEFAUtil 리소스 키트 도구를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-105">To deploy and manage Group Call Pickup, you need to use the SEFAUtil resource kit tool.</span></span> <span data-ttu-id="77d7d-106">이 도구는 Lync Server 2013 resource kit 도구의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-106">The tool is part of the Lync Server 2013 resource kit tools.</span></span> <span data-ttu-id="77d7d-107">SEFAUtil을 설치 하려면 토폴로지에서 신뢰할 수 있는 응용 프로그램 풀이 있어야 하 고, SEFAUtil을 신뢰할 수 있는 응용 프로그램으로 지정 하 고, 토폴로지를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-107">Before you can install SEFAUtil, you must have a trusted application pool in your topology, specify SEFAUtil as a trusted application, and enable the topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="77d7d-108">Microsoft 통합 커뮤니케이션 관리 API (SEFAUtil MA) 3.0 Core SDK는이 도구를 실행 하려는 컴퓨터에 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-108">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span>



</div>

<span data-ttu-id="77d7d-109">배포의 모든 프런트 엔드 풀에서 SEFAUtil를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-109">You can run the SEFAUtil in any Front End pool in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77d7d-110">SEFAUtil을 실행 하는 방법에 대 한 자세한 내용은 Technet 블로그 문서, "SEFAutil 실행 방법 확인"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="77d7d-110">For more details about running SEFAUtil, see the Technet blog article, "How to get SEFAutil running?"</span></span> <span data-ttu-id="77d7d-111">에서 <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A></span><span class="sxs-lookup"><span data-stu-id="77d7d-111">at <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A>.</span></span>



</div>

<div>

## <a name="to-deploy-sefautil"></a><span data-ttu-id="77d7d-112">SEFAUtil을 배포 하려면</span><span class="sxs-lookup"><span data-stu-id="77d7d-112">To deploy SEFAUtil</span></span>

1.  <span data-ttu-id="77d7d-113">Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-113">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="77d7d-114">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="77d7d-115">SEFAUtil 도구는 트러스트 된 응용 프로그램 풀에 속하는 컴퓨터 에서만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-115">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="77d7d-116">필요한 경우 SEFAUtil를 실행할 프런트 엔드 풀에 대해 신뢰할 수 있는 응용 프로그램 풀을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-116">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="77d7d-117">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-117">At the command line, run:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  <span data-ttu-id="77d7d-118">SEFAUtil 도구를 신뢰할 수 있는 응용 프로그램으로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-118">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="77d7d-119">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-119">At the command line, run:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="77d7d-120">필요한 경우 다른 포트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-120">You can use a different port if needed.</span></span>

    
    </div>

5.  <span data-ttu-id="77d7d-121">변경 내용을 적용 하 여 토폴로지를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-121">Enable the topology with your changes.</span></span> <span data-ttu-id="77d7d-122">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-122">At the command line, run:</span></span>
    
        Enable-CsTopology

6.  <span data-ttu-id="77d7d-123">3 단계에서 만든 신뢰할 수 있는 응용 프로그램 풀에 있는 프런트 엔드 서버에 Lync Server 2013 resource kit 도구를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-123">Install the Lync Server 2013 resource kit tools on a Front End Server that is in the trusted application pool that you created in step 3.</span></span>

7.  <span data-ttu-id="77d7d-124">다음과 같이 SEFAUtil 도구가 제대로 실행 되 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-124">Verify that the SEFAUtil tool is running correctly, as follows:</span></span>
    
    1.  <span data-ttu-id="77d7d-125">관리자 권한으로 Windows 명령 프롬프트에서 도구를 실행 하 여 배포에 포함 된 사용자의 착신 전환 설정을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-125">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="77d7d-126">이 도구는 버전 \ Files\Microsoft Lync Server 2013 \ Reskit에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-126">The tool is located at \Program Files\Microsoft Lync Server 2013\Reskit.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="77d7d-127">사용자의 착신 전환 설정을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-127">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="77d7d-128">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-128">At the command line, run:</span></span>
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        <span data-ttu-id="77d7d-129">사용자에 대 한 착신 전환 설정이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77d7d-129">The call forwarding settings for the user will be displayed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

