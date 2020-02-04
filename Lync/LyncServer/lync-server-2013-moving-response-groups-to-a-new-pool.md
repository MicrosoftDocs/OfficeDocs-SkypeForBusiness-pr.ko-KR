---
title: 'Lync Server 2013: 응답 그룹을 새 풀로 이동'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96740d8937f1548952d41d5674ef3e66cd29e2b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a><span data-ttu-id="f60a7-102">Lync Server 2013에서 응답 그룹을 새 풀로 이동</span><span class="sxs-lookup"><span data-stu-id="f60a7-102">Moving response groups to a new pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f60a7-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f60a7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f60a7-104">Lync Server 2013에는 FQDN (정규화 된 도메인 이름)이 다른 경우에도 한 풀의 응답 그룹을 다른 풀로 이동 하기 위한 새로운 cmdlet 지원이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-104">Lync Server 2013 introduces new cmdlet support for moving response groups from one pool to another pool, even when the fully qualified domain name (FQDN) is different.</span></span>

<span data-ttu-id="f60a7-105">한 프런트 엔드 풀의 응답 그룹을 다른 FQDN을 사용 하는 다른 프런트 엔드 풀로 이동 하려면 다음 절차의 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-105">Use the steps in the following procedure to move response groups from one Front End pool to another Front End pool with a different FQDN.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f60a7-106">공존 환경에서 Lync Server 2013&nbsp;프런트 엔드 풀 간에만 응답 그룹을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-106">In a coexistence environment, you can move response groups only between Lync Server 2013&nbsp;Front End pools.</span></span>



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a><span data-ttu-id="f60a7-107">다른 FQDN을 사용 하 여 응답 그룹을 풀로 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="f60a7-107">To move response groups to a pool with a different FQDN</span></span>

1.  <span data-ttu-id="f60a7-108">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f60a7-109">원본 풀에서 응답 그룹을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-109">Export the response groups in the source pool.</span></span> <span data-ttu-id="f60a7-110">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-110">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    <span data-ttu-id="f60a7-111">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-111">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    <span data-ttu-id="f60a7-112">내보내는 동안 원본 풀에서 응답 그룹을 제거 하려면 – RemoveExportedConfiguration 매개 변수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-112">To remove the response groups from the source pool during the export, include the –RemoveExportedConfiguration parameter.</span></span> <span data-ttu-id="f60a7-113">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-113">For example:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  <span data-ttu-id="f60a7-114">응답 그룹을 대상 풀로 가져오고 대상 풀을 새 담당자로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-114">Import the response groups to the destination pool and assign the destination pool as the new owner.</span></span> <span data-ttu-id="f60a7-115">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-115">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    <span data-ttu-id="f60a7-116">또한 응답 그룹 응용 프로그램 수준 설정을 원본 풀에서 대상 풀로 복사 하려는 경우 – ReplaceExistingRgsSettings 매개 변수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-116">If you also want to copy the Response Group application-level settings from the source pool to the destination pool, include the –ReplaceExistingRgsSettings parameter.</span></span> <span data-ttu-id="f60a7-117">풀 당 하나의 응용 프로그램 수준 설정 집합을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-117">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="f60a7-118">원본 풀의 응용 프로그램 수준 설정을 대상 풀로 복사 하는 경우 원본 풀의 설정이 대상 풀에 대 한 설정을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-118">If you copy the application-level settings from the source pool to the destination pool, the settings from the source pool replace the settings for the destination pool.</span></span> <span data-ttu-id="f60a7-119">원본 풀의 응용 프로그램 수준 설정을 복사 하지 않으면 대상 풀의 기존 설정이 가져온 응답 그룹에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-119">If you do not copy the application-level settings from the source pool, the existing settings from the destination pool apply to the imported response groups.</span></span>
    
    <span data-ttu-id="f60a7-120">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-120">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f60a7-121">응용 프로그램 수준 설정에는 기본 음악 보존 구성, 기본 음악 대기 오디오 파일, 에이전트 ringback 유예 기간 및 통화 컨텍스트 구성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-121">Application-level settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="f60a7-122">이러한 구성 설정을 보려면 <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-122">To view these configuration settings, run the <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="f60a7-123">이 cmdlet에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-help CsRgsConfiguration</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f60a7-123">For details about this cmdlet, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="f60a7-124">다음을 수행 하 여 가져온 응답 그룹 구성을 표시 하 여 가져오기가 성공적으로 수행 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-124">Verify that the import was successful by displaying the imported response group configuration by doing the following:</span></span>
    
      - <span data-ttu-id="f60a7-125">모든 워크플로를 가져왔는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-125">Verify that all the workflows were imported.</span></span> <span data-ttu-id="f60a7-126">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-126">At the command line, type the following:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="f60a7-127">모든 큐를 가져왔는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-127">Verify that all the queues were imported.</span></span> <span data-ttu-id="f60a7-128">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-128">At the command line, type the following:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="f60a7-129">모든 에이전트 그룹을 가져왔는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-129">Verify that all the agent groups were imported.</span></span> <span data-ttu-id="f60a7-130">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-130">At the command line, type the following:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="f60a7-131">모든 비즈니스 시간을 가져왔는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-131">Verify that all the hours of business were imported.</span></span> <span data-ttu-id="f60a7-132">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-132">At the command line, type the following:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - <span data-ttu-id="f60a7-133">모든 공휴일 집합을 가져왔는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-133">Verify that all the holiday sets were imported.</span></span> <span data-ttu-id="f60a7-134">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-134">At the command line, type the following:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  <span data-ttu-id="f60a7-135">응답 그룹 중 하나에 호출을 배치 하 고 통화가 올바르게 처리 되었는지 확인 하 여 가져오기가 성공적으로 수행 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-135">Verify that the import was successful by placing a call to one of the response groups and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="f60a7-136">대상 풀의 에이전트 그룹에 로그인 할 수 있는 공식 에이전트 그룹의 구성원 인 에이전트를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-136">Request agents who are members of formal agent groups to sign in to their agent groups in the destination pool.</span></span>

7.  <span data-ttu-id="f60a7-137">이전에 원본 풀에서 응답 그룹을 제거 하지 않은 경우 원본 풀에서 응답 그룹을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-137">If you did not previously remove response groups from the source pool, remove the response groups from the source pool.</span></span> <span data-ttu-id="f60a7-138">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-138">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    <span data-ttu-id="f60a7-139">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f60a7-139">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

