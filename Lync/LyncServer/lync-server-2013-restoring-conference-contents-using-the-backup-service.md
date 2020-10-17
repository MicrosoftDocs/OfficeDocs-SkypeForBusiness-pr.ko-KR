---
title: 'Lync Server 2013: 백업 서비스를 사용 하 여 전화 회의 내용 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 252cdf6713db7fcb3c4658cc4adb0eb51905c1ff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511455"
---
# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="39f3c-102">Lync Server 2013에서 백업 서비스를 사용 하 여 전화 회의 내용 복원</span><span class="sxs-lookup"><span data-stu-id="39f3c-102">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39f3c-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="39f3c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="39f3c-p101">프런트 엔드 풀의 파일 저장소에 저장된 회의 정보가 사용할 수 없는 상태가 되면 풀에 있는 사용자가 자신의 회의 데이터를 보유할 수 있도록 이 정보를 복원해야 합니다. 회의 데이터가 손실된 프런트 엔드 풀이 다른 프런트 엔드 풀과 쌍으로 연결된 경우 백업 서비스를 사용하여 데이터를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39f3c-p101">If the conference information stored in the file store of a Front End pool becomes unavailable. you must restore this information so that users homed on the pool retain their conference data. If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="39f3c-p102">또한 전체 풀이 실패한 경우에도 이 작업을 수행해야 하며 해당 사용자를 백업 풀로 장애 조치(failover)해야 합니다. 이러한 사용자를 원래 풀로 다시 장애 조치(failover)한 경우 이 절차에 따라 해당 회의 콘텐츠를 다시 원래 풀에도 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39f3c-p102">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool. When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="39f3c-109">Pool1이 Pool2와 쌍으로 연결되었고 Pool1의 회의 데이터가 손실되었다고 가정해보십시오.</span><span class="sxs-lookup"><span data-stu-id="39f3c-109">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="39f3c-110">다음 cmdlet을 사용 하 여 백업 서비스를 호출 하 여 콘텐츠를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39f3c-110">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="39f3c-p104">회의 콘텐츠를 복원할 때는 크기에 따라 시간이 오래 걸릴 수 있습니다. 다음 cmdlet을 사용해서 프로세스 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39f3c-p104">Restoring the conference contents may take some time, depending on their size. You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="39f3c-113">이 cmdlet이 데이터 회의 모듈에 대해 정상 상태 값을 반환하면 처리가 완료된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="39f3c-113">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

