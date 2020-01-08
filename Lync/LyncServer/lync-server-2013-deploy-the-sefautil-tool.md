---
title: 'Lync Server 2013: SEFAUtil 도구 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0783ab251359582d232d558da2161a149dea5117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a><span data-ttu-id="37711-102">Lync Server 2013에서 SEFAUtil 도구 배포</span><span class="sxs-lookup"><span data-stu-id="37711-102">Deploy the SEFAUtil tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37711-103">_**마지막으로 수정한 주제:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="37711-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="37711-104">그룹 통화 픽업을 배포 하 고 관리 하려면 SEFAUtil 리소스 키트 도구를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37711-104">To deploy and manage Group Call Pickup, you need to use the SEFAUtil resource kit tool.</span></span> <span data-ttu-id="37711-105">이 도구는 Lync Server 2013 리소스 키트 도구의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="37711-105">The tool is part of the Lync Server 2013 resource kit tools.</span></span> <span data-ttu-id="37711-106">SEFAUtil를 설치 하기 전에 토폴로지에 신뢰할 수 있는 응용 프로그램 풀이 있어야 하 고, SEFAUtil를 신뢰할 수 있는 응용 프로그램으로 지정 하 고, 토폴로지를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37711-106">Before you can install SEFAUtil, you must have a trusted application pool in your topology, specify SEFAUtil as a trusted application, and enable the topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="37711-107">Microsoft 통합 커뮤니케이션 관리 API (c) 3.0 Core SDK는 SEFAUtil 도구를 실행할 컴퓨터에 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37711-107">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span>



</div>

<span data-ttu-id="37711-108">배포의 모든 프런트 엔드 풀에서 SEFAUtil를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37711-108">You can run the SEFAUtil in any Front End pool in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="37711-109">SEFAUtil를 실행 하는 방법에 대 한 자세한 내용은 Technet 블로그 문서 "SEFAutil 실행을 얻는 방법"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37711-109">For more details about running SEFAUtil, see the Technet blog article, "How to get SEFAutil running?"</span></span> <span data-ttu-id="37711-110"><A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>.</span><span class="sxs-lookup"><span data-stu-id="37711-110">at <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>.</span></span>



</div>

<div>

## <a name="to-deploy-sefautil"></a><span data-ttu-id="37711-111">SEFAUtil 배포</span><span class="sxs-lookup"><span data-stu-id="37711-111">To deploy SEFAUtil</span></span>

1.  <span data-ttu-id="37711-112">Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="37711-112">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="37711-113">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="37711-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="37711-114">SEFAUtil 도구는 신뢰할 수 있는 응용 프로그램 풀의 일부인 컴퓨터 에서만 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37711-114">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="37711-115">필요한 경우 SEFAUtil를 실행할 계획의 프런트 엔드 풀에 대해 신뢰할 수 있는 응용 프로그램 풀을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="37711-115">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="37711-116">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="37711-116">At the command line, run:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  <span data-ttu-id="37711-117">SEFAUtil 도구를 신뢰할 수 있는 응용 프로그램으로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="37711-117">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="37711-118">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="37711-118">At the command line, run:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="37711-119">필요한 경우 다른 포트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37711-119">You can use a different port if needed.</span></span>

    
    </div>

5.  <span data-ttu-id="37711-120">변경 내용이 포함 된 토폴로지를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="37711-120">Enable the topology with your changes.</span></span> <span data-ttu-id="37711-121">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="37711-121">At the command line, run:</span></span>
    
        Enable-CsTopology

6.  <span data-ttu-id="37711-122">3 단계에서 만든 신뢰할 수 있는 응용 프로그램 풀에 있는 프런트 엔드 서버에 Lync Server 2013 리소스 키트 도구를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="37711-122">Install the Lync Server 2013 resource kit tools on a Front End Server that is in the trusted application pool that you created in step 3.</span></span>

7.  <span data-ttu-id="37711-123">다음과 같이 SEFAUtil 도구가 올바르게 실행 되 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="37711-123">Verify that the SEFAUtil tool is running correctly, as follows:</span></span>
    
    1.  <span data-ttu-id="37711-124">Windows 명령 프롬프트에서 관리자 권한으로 도구를 실행 하 여 배포에 있는 사용자의 착신 전환 설정을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="37711-124">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="37711-125">이 도구는 명령줄 \ Files\Microsoft Lync Server 2013 \ Reskit에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37711-125">The tool is located at \Program Files\Microsoft Lync Server 2013\Reskit.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="37711-126">사용자의 착신 전환 설정을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="37711-126">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="37711-127">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="37711-127">At the command line, run:</span></span>
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        <span data-ttu-id="37711-128">사용자의 착신 전환 설정이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37711-128">The call forwarding settings for the user will be displayed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

