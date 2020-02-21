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
ms.openlocfilehash: 7f0aa515e290e6000564fe8eeaae5aaeb381284d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="infrastructure-and-deployment-cmdlets-in-lync-server-2013"></a>Lync Server 2013의 인프라 및 배포 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-09_

Microsoft Lync Server 2013에 포함 된 인프라 및 배포 cmdlet은 제품 초기에 설치 하 고 배포할 때 유용할 수 있습니다. Lync Server를 배포한 후에는 이러한 cmdlet을 사용 하 여 구성 요소가 예상 대로 작동 하는지 확인할 수 있습니다. 복제 설정 관리 Lync Server 토폴로지, 정책 및 구성 설정을 백업 및 복원 합니다.

<div>

## <a name="infrastructure-and-deployment-cmdlets"></a>인프라 및 배포 Cmdlet

관리자는 대부분의 인프라 및 배포를 직접 호출 해야 합니다. 이는 설치 프로그램이 나 토폴로지 작성기를 실행할 때 이러한 cmdlet이 자동으로 호출 되기 때문입니다. 한 가지 중요 한 예외는 Lync Server 토폴로지, 정책 및 구성 설정의 백업 복사본을 만들 수 있도록 하는 **수출-csconfiguration** cmdlet 일 수 있습니다. 그러나 필요한 경우에는 Lync Server 관리 셸 또는 스크립트 내에서 인프라 및 배포 cmdlet을 실행할 수도 있습니다. 스크립트를 사용 하면 특정 작업을 자동화할 수 있습니다. 다음은 인프라 및 배포와 직접 관련 된 cmdlet 목록입니다.

**[Lync Server 2013의 Active Directory cmdlet](lync-server-2013-active-directory-cmdlets.md)**

  - <span></span>  
    [사용 안 함-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))

  - <span></span>  
    [Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))

  - <span></span>  
    [Get-CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [사용 안 함-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))

  - <span></span>  
    [Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))

  - <span></span>  
    [Get-CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))

  - <span></span>  
    [설치-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))

**[Lync Server 2013의 복제 cmdlet](lync-server-2013-replication-cmdlets.md)**

  - <span></span>  
    [디버그-CsInterPoolReplication](https://technet.microsoft.com/library/JJ619185(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Invoke-csmanagementstorereplication-를 호출 합니다.](https://technet.microsoft.com/library/Gg413060(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csmanagementstorereplicationstatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [사용-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))

  - <span></span>  
    [테스트-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))

  - <span></span>  
    [Get-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))

  - <span></span>  
    [Get-csuserreplicatorconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425738(v=OCS.15))

  - <span></span>  
    [Get-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))

**[토폴로지 cmdlet jn Lync Server 2013](lync-server-2013-topology-cmdlets.md)**

  - <span></span>  
    [Get-CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))

  - <span></span>  
    [설정-CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Enable-Enable-cstopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))

  - <span></span>  
    [Enable-cstopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))

  - <span></span>  
    [게시-Enable-cstopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))

  - <span></span>  
    [Enable-cstopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [수출-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))

  - <span></span>  
    [가져오기-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [사용 안 함-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))

  - <span></span>  
    [사용-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))

  - <span></span>  
    [온-CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))

  - <span></span>  
    [테스트-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csnetworkinterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))

**[Lync Server 2013의 백업 및 고가용성 cmdlet](lync-server-2013-backup-and-high-availability-cmdlets.md)**

  - [Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))

  - [Get-csbackupserviceconfiguration을 제거 합니다.](https://technet.microsoft.com/library/JJ204903(v=OCS.15))

  - [Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))

<!-- end list -->

  - [Get-csbackupservicestatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))

<!-- end list -->

  - [Invoke-csbackupservicesync-를 호출 합니다.](https://technet.microsoft.com/library/JJ205374(v=OCS.15))

<!-- end list -->

  - [Debug-csintrapoolreplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))

<!-- end list -->

  - [백업-CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))

<!-- end list -->

  - [Get-cspoolbackuprelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))

<!-- end list -->

  - [Get-cspoolfabricstate](https://technet.microsoft.com/library/JJ619188(v=OCS.15))

<!-- end list -->

  - [Invoke-cspoolfailback-를 호출 합니다.](https://technet.microsoft.com/library/JJ204873(v=OCS.15))

<!-- end list -->

  - [Initialize-cspoolfailover-를 호출 합니다.](https://technet.microsoft.com/library/JJ205189(v=OCS.15))

<!-- end list -->

  - [Get-cspoolupgradereadinessstate](https://technet.microsoft.com/library/JJ204689(v=OCS.15))

<!-- end list -->

  - [Invoke-csstorageserviceflush-를 호출 합니다.](https://technet.microsoft.com/library/JJ619175(v=OCS.15))

<!-- end list -->

  - [동기화-CsUserData](https://technet.microsoft.com/library/JJ205242(v=OCS.15))

<!-- end list -->

  - [CsUserStoreBackupData 제거](https://technet.microsoft.com/library/JJ205003(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server PowerShell 블로그](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

