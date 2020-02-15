---
title: 'Lync Server 2013: 인프라 및 배포 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Infrastructure and deployment cmdlets
ms:assetid: 0a6e872a-9f70-4f23-a4a5-8820dbf55370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398153(v=OCS.15)
ms:contentKeyID: 48183364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93d2c35fcc9ebf037eb33e6553cef28b9e1041ec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="infrastructure-and-deployment-cmdlets-in-lync-server-2013"></a><span data-ttu-id="0d0ed-102">Lync Server 2013의 인프라 및 배포 cmdlet</span><span class="sxs-lookup"><span data-stu-id="0d0ed-102">Infrastructure and deployment cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d0ed-103">_**마지막으로 수정 된 항목:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="0d0ed-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="0d0ed-104">Microsoft Lync Server 2013에 포함 된 인프라 및 배포 cmdlet은 제품 초기에 설치 하 고 배포할 때 유용할 수 있습니다. Lync Server를 배포한 후에는 이러한 cmdlet을 사용 하 여 구성 요소가 예상 대로 작동 하는지 확인할 수 있습니다. 복제 설정 관리 Lync Server 토폴로지, 정책 및 구성 설정을 백업 및 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d0ed-104">The infrastructure and deployment cmdlets included in Microsoft Lync Server 2013 can be useful in the initial setup and deployment of the product; after Lync Server has been deployed these cmdlets can then be used to do such things as verify that components are working as expected; manage replication settings; and backup and restore the Lync Server topology, policies, and configuration settings.</span></span>

<div>

## <a name="infrastructure-and-deployment-cmdlets"></a><span data-ttu-id="0d0ed-105">인프라 및 배포 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0d0ed-105">Infrastructure and Deployment Cmdlets</span></span>

<span data-ttu-id="0d0ed-106">관리자는 대부분의 인프라 및 배포를 직접 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d0ed-106">Administrators will rarely need to directly call many of the infrastructure and deployment.</span></span> <span data-ttu-id="0d0ed-107">이는 설치 프로그램이 나 토폴로지 작성기를 실행할 때 이러한 cmdlet이 자동으로 호출 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="0d0ed-107">That is because these cmdlets are automatically invoked when you run Setup or the Topology Builder.</span></span> <span data-ttu-id="0d0ed-108">한 가지 중요 한 예외는 Lync Server 토폴로지, 정책 및 구성 설정의 백업 복사본을 만들 수 있도록 하는 **수출-csconfiguration** cmdlet 일 수 있습니다. 그러나 필요한 경우에는 Lync Server 관리 셸 또는 스크립트 내에서 인프라 및 배포 cmdlet을 실행할 수도 있습니다. 스크립트를 사용 하면 특정 작업을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d0ed-108">(One major exception might be the **Export-CsConfiguration** cmdlet, which enables you to make a backup copy of your Lync Server topology, policies, and configuration settings.) However, and when needed, the infrastructure and deployment cmdlets can also be run from the Lync Server Management Shell or from within a script; using a script enables you to automate certain tasks.</span></span> <span data-ttu-id="0d0ed-109">다음은 인프라 및 배포와 직접 관련 된 cmdlet 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="0d0ed-109">The following is a list of cmdlets that relate directly to infrastructure and deployment:</span></span>

<span data-ttu-id="0d0ed-110">**[Lync Server 2013의 Active Directory cmdlet](lync-server-2013-active-directory-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="0d0ed-110">**[Active Directory cmdlets in Lync Server 2013](lync-server-2013-active-directory-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-111">[사용 안 함-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-111">[Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-112">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-112">[Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-113">[Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-113">[Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0d0ed-114">[사용 안 함-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-114">[Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-115">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-115">[Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-116">[Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-116">[Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0d0ed-117">[Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-117">[Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-118">[설치-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-118">[Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))</span></span>

<span data-ttu-id="0d0ed-119">**[Lync Server 2013의 복제 cmdlet](lync-server-2013-replication-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="0d0ed-119">**[Replication cmdlets in Lync Server 2013](lync-server-2013-replication-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-120">[디버그-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-120">[Debug-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0d0ed-121">[Invoke-csmanagementstorereplication-를 호출 합니다.](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-121">[Invoke-CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0d0ed-122">[Get-csmanagementstorereplicationstatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-122">[Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0d0ed-123">[사용-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-123">[Enable-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-124">[테스트-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-124">[Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0d0ed-125">[Get-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-125">[Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-126">[Get-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-126">[New-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-127">[Get-csuserreplicatorconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-127">[Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-128">[Get-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-128">[Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))</span></span>

<span data-ttu-id="0d0ed-129">**[토폴로지 cmdlet jn Lync Server 2013](lync-server-2013-topology-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="0d0ed-129">**[Topology cmdlets jn Lync Server 2013](lync-server-2013-topology-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-130">[Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-130">[Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0d0ed-131">[Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-131">[Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-132">[설정-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-132">[Set-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0d0ed-133">[Enable-Enable-cstopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-133">[Enable-CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-134">[Enable-cstopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-134">[Get-CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-135">[게시-Enable-cstopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-135">[Publish-CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-136">[Enable-cstopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-136">[Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0d0ed-137">[수출-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-137">[Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-138">[가져오기-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-138">[Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0d0ed-139">[Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-139">[Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0d0ed-140">[사용 안 함-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-140">[Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-141">[사용-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-141">[Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-142">[온-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-142">[Get-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0d0ed-143">[테스트-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-143">[Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0d0ed-144">[Get-csnetworkinterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-144">[Get-CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))</span></span>

<span data-ttu-id="0d0ed-145">**[Lync Server 2013의 백업 및 고가용성 cmdlet](lync-server-2013-backup-and-high-availability-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="0d0ed-145">**[Backup and high availability cmdlets in Lync Server 2013](lync-server-2013-backup-and-high-availability-cmdlets.md)**</span></span>

  - <span data-ttu-id="0d0ed-146">[Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-146">[Get-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))</span></span>

  - <span data-ttu-id="0d0ed-147">[Get-csbackupserviceconfiguration을 제거 합니다.](https://technet.microsoft.com/library/JJ204903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-147">[Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))</span></span>

  - <span data-ttu-id="0d0ed-148">[Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-148">[Set-CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0d0ed-149">[Get-csbackupservicestatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-149">[Get-CsBackupServiceStatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0d0ed-150">[Invoke-csbackupservicesync-를 호출 합니다.](https://technet.microsoft.com/library/JJ205374(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-150">[Invoke-CsBackupServiceSync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0d0ed-151">[Debug-csintrapoolreplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-151">[Debug-CsIntraPoolReplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0d0ed-152">[백업-CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-152">[Backup-CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0d0ed-153">[Get-cspoolbackuprelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-153">[Get-CsPoolBackupRelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0d0ed-154">[Get-cspoolfabricstate](https://technet.microsoft.com/library/JJ619188(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-154">[Get-CsPoolFabricState](https://technet.microsoft.com/library/JJ619188(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0d0ed-155">[Invoke-cspoolfailback-를 호출 합니다.](https://technet.microsoft.com/library/JJ204873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-155">[Invoke-CsPoolFailBack](https://technet.microsoft.com/library/JJ204873(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0d0ed-156">[Initialize-cspoolfailover-를 호출 합니다.](https://technet.microsoft.com/library/JJ205189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-156">[Invoke-CsPoolFailOver](https://technet.microsoft.com/library/JJ205189(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0d0ed-157">[Get-cspoolupgradereadinessstate](https://technet.microsoft.com/library/JJ204689(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-157">[Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/library/JJ204689(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0d0ed-158">[Invoke-csstorageserviceflush-를 호출 합니다.](https://technet.microsoft.com/library/JJ619175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-158">[Invoke-CsStorageServiceFlush](https://technet.microsoft.com/library/JJ619175(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0d0ed-159">[동기화-CsUserData](https://technet.microsoft.com/library/JJ205242(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-159">[Sync-CsUserData](https://technet.microsoft.com/library/JJ205242(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="0d0ed-160">[CsUserStoreBackupData 제거](https://technet.microsoft.com/library/JJ205003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0d0ed-160">[Remove-CsUserStoreBackupData](https://technet.microsoft.com/library/JJ205003(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0d0ed-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d0ed-161">See Also</span></span>


[<span data-ttu-id="0d0ed-162">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="0d0ed-162">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

