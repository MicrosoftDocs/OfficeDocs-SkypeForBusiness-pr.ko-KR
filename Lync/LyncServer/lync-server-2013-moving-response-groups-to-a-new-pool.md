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
ms.openlocfilehash: 41d739ae79998fe3dbf3acadba2b2f480a960a30
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a><span data-ttu-id="29b6d-102">Lync Server 2013의 새 풀로 응답 그룹 이동</span><span class="sxs-lookup"><span data-stu-id="29b6d-102">Moving response groups to a new pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29b6d-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="29b6d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="29b6d-104">Lync Server 2013에는 FQDN (정규화 된 도메인 이름)이 다를 때를 포함 하 여 한 풀에서 다른 풀로 응답 그룹을 이동 하기 위한 새로운 cmdlet 지원이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-104">Lync Server 2013 introduces new cmdlet support for moving response groups from one pool to another pool, even when the fully qualified domain name (FQDN) is different.</span></span>

<span data-ttu-id="29b6d-105">다음 절차의 단계에 따라 한 프런트 엔드 풀의 응답 그룹을 다른 FQDN을 사용 하는 다른 프런트 엔드 풀로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-105">Use the steps in the following procedure to move response groups from one Front End pool to another Front End pool with a different FQDN.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="29b6d-106">동시 사용 환경에서는 Lync Server 2013&nbsp;프런트 엔드 풀 간에만 응답 그룹을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-106">In a coexistence environment, you can move response groups only between Lync Server 2013&nbsp;Front End pools.</span></span>



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a><span data-ttu-id="29b6d-107">다른 FQDN의 풀로 응답 그룹을 이동하려면</span><span class="sxs-lookup"><span data-stu-id="29b6d-107">To move response groups to a pool with a different FQDN</span></span>

1.  <span data-ttu-id="29b6d-108">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="29b6d-p101">원본 풀에서 응답 그룹을 내보내고 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-p101">Export the response groups in the source pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    <span data-ttu-id="29b6d-111">예시는 다음과 같습니다:</span><span class="sxs-lookup"><span data-stu-id="29b6d-111">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    <span data-ttu-id="29b6d-p102">내보내기 중에 원본 풀에서 응답 그룹을 제거하려면 -RemoveExportedConfiguration 매개 변수를 포함합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-p102">To remove the response groups from the source pool during the export, include the –RemoveExportedConfiguration parameter. For example:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  <span data-ttu-id="29b6d-p103">응답 그룹을 대상 풀로 가져오고 대상 풀을 새 소유자로 할당합니다. 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-p103">Import the response groups to the destination pool and assign the destination pool as the new owner. At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    <span data-ttu-id="29b6d-116">또한 원본 풀에서 대상 풀로 응답 그룹 응용 프로그램 수준 설정을 복사 하려면-ReplaceExistingRgsSettings 매개 변수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-116">If you also want to copy the Response Group application-level settings from the source pool to the destination pool, include the –ReplaceExistingRgsSettings parameter.</span></span> <span data-ttu-id="29b6d-117">풀당 응용 프로그램 수준 설정 집합을 한 개만 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-117">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="29b6d-118">원본 풀에서 대상 풀로 응용 프로그램 수준 설정을 복사하는 경우 원본 풀의 설정이 대상 풀의 설정을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-118">If you copy the application-level settings from the source pool to the destination pool, the settings from the source pool replace the settings for the destination pool.</span></span> <span data-ttu-id="29b6d-119">원본 풀에서 응용 프로그램 수준 설정을 복사하지 않는 경우에는 대상 풀의 기존 설정이 가져온 응답 그룹에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-119">If you do not copy the application-level settings from the source pool, the existing settings from the destination pool apply to the imported response groups.</span></span>
    
    <span data-ttu-id="29b6d-120">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-120">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="29b6d-121">응용 프로그램 수준 설정에는 기본 대기 음악 구성, 기본 대기 음악 오디오 파일, 에이전트 되걸기 유예 기간 및 호출 컨텍스트 구성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-121">Application-level settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="29b6d-122">이러한 구성 설정을 보려면 <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-122">To view these configuration settings, run the <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="29b6d-123">이 cmdlet에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">export-csrgsconfiguration</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="29b6d-123">For details about this cmdlet, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="29b6d-124">다음 절차에 따라 가져온 응답 그룹 구성을 표시하여 가져오기가 성공적으로 수행되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-124">Verify that the import was successful by displaying the imported response group configuration by doing the following:</span></span>
    
      - <span data-ttu-id="29b6d-p106">모든 워크플로를 가져왔는지 확인합니다. 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-p106">Verify that all the workflows were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="29b6d-p107">모든 큐를 가져왔는지 확인합니다. 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-p107">Verify that all the queues were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="29b6d-p108">모든 에이전트 그룹을 가져왔는지 확인합니다. 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-p108">Verify that all the agent groups were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - <span data-ttu-id="29b6d-p109">모든 업무 시간을 가져왔는지 확인합니다. 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-p109">Verify that all the hours of business were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - <span data-ttu-id="29b6d-p110">모든 휴일을 가져왔는지 확인합니다. 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-p110">Verify that all the holiday sets were imported. At the command line, type the following:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  <span data-ttu-id="29b6d-135">응답 그룹 중 하나로 전화를 걸고 통화가 올바르게 처리되는지 확인하여 가져오기가 성공적으로 수행되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-135">Verify that the import was successful by placing a call to one of the response groups and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="29b6d-136">
공식 에이전트 그룹의 구성원인 에이전트에게 대상 풀의 에이전트 그룹에 로그인하도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-136">Request agents who are members of formal agent groups to sign in to their agent groups in the destination pool.</span></span>

7.  <span data-ttu-id="29b6d-p111">원본 풀에서 이전에 응답 그룹을 제거하지 않은 경우 응답 그룹을 원본 풀에서 제거합니다. 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-p111">If you did not previously remove response groups from the source pool, remove the response groups from the source pool. At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    <span data-ttu-id="29b6d-139">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="29b6d-139">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

