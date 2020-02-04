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
ms.openlocfilehash: d75e0f1f62ec2594ab8d774dc9d426b8bdd56061
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="infrastructure-and-deployment-cmdlets-in-lync-server-2013"></a>Lync Server 2013의 인프라 및 배포 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-09_

Microsoft Lync Server 2013에 포함 된 인프라 및 배포 cmdlet은 제품의 초기 설정 및 배포에 유용할 수 있습니다. Lync Server를 배포한 후 이러한 cmdlet을 사용 하 여 구성 요소가 예상 대로 작동 하는지 확인 하는 등의 작업을 수행할 수 있습니다. 복제 설정 관리 Lync Server 토폴로지, 정책 및 구성 설정을 백업 및 복원 합니다.

<div>

## <a name="infrastructure-and-deployment-cmdlets"></a>인프라 및 배포 Cmdlet

관리자가 대부분의 인프라 및 배포를 직접 호출 해야 하는 경우는 거의 없습니다. 이는 설치 프로그램이 나 토폴로지 작성기를 실행할 때 이러한 cmdlet이 자동으로 호출 되기 때문입니다. 단 하나의 주요 예외는 Lync Server 토폴로지, 정책 및 구성 설정에 대 한 백업 복사본을 만들 수 있도록 하는 **내보내기-CsConfiguration** cmdlet 일 수 있습니다. 그러나 필요한 경우에는 Lync Server 관리 셸에서 또는 스크립트 내 에서도 인프라 및 배포 cmdlet을 실행할 수 있습니다. 스크립트를 사용 하 여 특정 작업을 자동화할 수 있습니다. 다음은 인프라 및 배포와 직접 관련 된 cmdlet의 목록입니다.

**[Lync Server 2013의 Active Directory cmdlet](lync-server-2013-active-directory-cmdlets.md)**

  - <span></span>  
    [Disable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398785(v=OCS.15))

  - <span></span>  
    [Enable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg412764(v=OCS.15))

  - <span></span>  
    [Get-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398453(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [사용 안 함-CsAdForest](https://technet.microsoft.com/en-us/library/Gg398122(v=OCS.15))

  - <span></span>  
    [Enable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg425713(v=OCS.15))

  - <span></span>  
    [Get-CsAdForest](https://technet.microsoft.com/en-us/library/Gg412995(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg413070(v=OCS.15))

  - <span></span>  
    [Install-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg398681(v=OCS.15))

**[Lync Server 2013의 복제 cmdlet](lync-server-2013-replication-cmdlets.md)**

  - <span></span>  
    [Debug-CsInterPoolReplication](https://technet.microsoft.com/en-us/library/JJ619185(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsManagementStoreReplication-호출](https://technet.microsoft.com/en-us/library/Gg413060(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsManagementStoreReplicationStatus](https://technet.microsoft.com/en-us/library/Gg399052(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [-CsReplica 사용](https://technet.microsoft.com/en-us/library/Gg425965(v=OCS.15))

  - <span></span>  
    [테스트-CsReplica](https://technet.microsoft.com/en-us/library/JJ205289(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398548(v=OCS.15))

  - <span></span>  
    [New-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg399059(v=OCS.15))

  - <span></span>  
    [Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg425738(v=OCS.15))

  - <span></span>  
    [Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398540(v=OCS.15))

**[토폴로지 cmdlet jn Lync Server 2013](lync-server-2013-topology-cmdlets.md)**

  - <span></span>  
    [Get-CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [가져오기-CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))

  - <span></span>  
    [집합-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))

  - <span></span>  
    [Get-CsTopology](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))

  - <span></span>  
    [게시-CsTopology](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))

  - <span></span>  
    [테스트-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [수출-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))

  - <span></span>  
    [가져오기-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsComputer 사용 안 함](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))

  - <span></span>  
    [사용-CsComputer](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))

  - <span></span>  
    [Get-CsComputer](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))

  - <span></span>  
    [테스트-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))

**[Lync Server 2013의 백업 및 고가용성 cmdlet](lync-server-2013-backup-and-high-availability-cmdlets.md)**

  - [Get-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205087(v=OCS.15))

  - [제거-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ204903(v=OCS.15))

  - [Set-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205006(v=OCS.15))

<!-- end list -->

  - [Get-CsBackupServiceStatus](https://technet.microsoft.com/en-us/library/JJ205032(v=OCS.15))

<!-- end list -->

  - [CsBackupServiceSync-호출](https://technet.microsoft.com/en-us/library/JJ205374(v=OCS.15))

<!-- end list -->

  - [Debug-CsIntraPoolReplication](https://technet.microsoft.com/en-us/library/JJ205103(v=OCS.15))

<!-- end list -->

  - [Backup-CsPool](https://technet.microsoft.com/en-us/library/JJ204955(v=OCS.15))

<!-- end list -->

  - [Get-CsPoolBackupRelationship](https://technet.microsoft.com/en-us/library/JJ204745(v=OCS.15))

<!-- end list -->

  - [Get-CsPoolFabricState](https://technet.microsoft.com/en-us/library/JJ619188(v=OCS.15))

<!-- end list -->

  - [Invoke-CsPoolFailBack](https://technet.microsoft.com/en-us/library/JJ204873(v=OCS.15))

<!-- end list -->

  - [Invoke-CsPoolFailOver](https://technet.microsoft.com/en-us/library/JJ205189(v=OCS.15))

<!-- end list -->

  - [Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/en-us/library/JJ204689(v=OCS.15))

<!-- end list -->

  - [CsStorageServiceFlush-호출](https://technet.microsoft.com/en-us/library/JJ619175(v=OCS.15))

<!-- end list -->

  - [동기화-CsUserData](https://technet.microsoft.com/en-us/library/JJ205242(v=OCS.15))

<!-- end list -->

  - [-CsUserStoreBackupData 제거](https://technet.microsoft.com/en-us/library/JJ205003(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server PowerShell 블로그](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

