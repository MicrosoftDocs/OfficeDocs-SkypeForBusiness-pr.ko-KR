---
title: 'Lync Server 2013: 백업 및 고가용성 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup and high availability cmdlets
ms:assetid: 5aff41a3-7a0e-4c51-9d5f-7f08e36bf046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204925(v=OCS.15)
ms:contentKeyID: 48184236
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc28cf323db57623d120b792384074a4b09d3558
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-high-availability-cmdlets-in-lync-server-2013"></a><span data-ttu-id="6b6e5-102">Lync Server 2013의 백업 및 고가용성 cmdlet</span><span class="sxs-lookup"><span data-stu-id="6b6e5-102">Backup and high availability cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b6e5-103">_**마지막으로 수정한 주제:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="6b6e5-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="6b6e5-104">관리자는 백업 및 고가용성 cmdlet을 사용 하 여 Microsoft Lync Server 2013에서 도입 된 풀 백업, 복원 및 고가용성 기능을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b6e5-104">The backup and high availability cmdlets enable administrators to manage the pool backup, restore, and high availability capabilities introduced in Microsoft Lync Server 2013.</span></span>

<div>

## <a name="backup-and-high-availability-cmdlets"></a><span data-ttu-id="6b6e5-105">백업 및 고가용성 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6b6e5-105">Backup and High Availability Cmdlets</span></span>

<span data-ttu-id="6b6e5-106">다음은 Lync Server 토폴로지의 사용 가능성을 백업 하 고 구성 하는 것과 직접 관련 된 cmdlet의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="6b6e5-106">The following is a list of cmdlets that relate directly to backing up and configuring the availability of your Lync Server topology:</span></span>

<span data-ttu-id="6b6e5-107">**백업 및 고가용성 Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="6b6e5-107">**Backup and High Availability Cmdlets**</span></span>

  - <span data-ttu-id="6b6e5-108">[Get-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b6e5-108">[Get-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205087(v=OCS.15))</span></span>

  - <span data-ttu-id="6b6e5-109">[제거-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ204903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b6e5-109">[Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ204903(v=OCS.15))</span></span>

  - <span data-ttu-id="6b6e5-110">[Set-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205006(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b6e5-110">[Set-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205006(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6b6e5-111">[Get-CsBackupServiceStatus](https://technet.microsoft.com/en-us/library/JJ205032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b6e5-111">[Get-CsBackupServiceStatus](https://technet.microsoft.com/en-us/library/JJ205032(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6b6e5-112">[CsBackupServiceSync-호출](https://technet.microsoft.com/en-us/library/JJ205374(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b6e5-112">[Invoke-CsBackupServiceSync](https://technet.microsoft.com/en-us/library/JJ205374(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6b6e5-113">[Debug-CsIntraPoolReplication](https://technet.microsoft.com/en-us/library/JJ205103(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b6e5-113">[Debug-CsIntraPoolReplication](https://technet.microsoft.com/en-us/library/JJ205103(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6b6e5-114">[Backup-CsPool](https://technet.microsoft.com/en-us/library/JJ204955(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b6e5-114">[Backup-CsPool](https://technet.microsoft.com/en-us/library/JJ204955(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6b6e5-115">[Get-CsPoolBackupRelationship](https://technet.microsoft.com/en-us/library/JJ204745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b6e5-115">[Get-CsPoolBackupRelationship](https://technet.microsoft.com/en-us/library/JJ204745(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6b6e5-116">[Get-CsPoolFabricState](https://technet.microsoft.com/en-us/library/JJ619188(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b6e5-116">[Get-CsPoolFabricState](https://technet.microsoft.com/en-us/library/JJ619188(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6b6e5-117">[Invoke-CsPoolFailBack](https://technet.microsoft.com/en-us/library/JJ204873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b6e5-117">[Invoke-CsPoolFailBack](https://technet.microsoft.com/en-us/library/JJ204873(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6b6e5-118">[Invoke-CsPoolFailOver](https://technet.microsoft.com/en-us/library/JJ205189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b6e5-118">[Invoke-CsPoolFailOver](https://technet.microsoft.com/en-us/library/JJ205189(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6b6e5-119">[Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/en-us/library/JJ204689(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b6e5-119">[Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/en-us/library/JJ204689(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6b6e5-120">[CsStorageServiceFlush-호출](https://technet.microsoft.com/en-us/library/JJ619175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b6e5-120">[Invoke-CsStorageServiceFlush](https://technet.microsoft.com/en-us/library/JJ619175(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6b6e5-121">[동기화-CsUserData](https://technet.microsoft.com/en-us/library/JJ205242(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b6e5-121">[Sync-CsUserData](https://technet.microsoft.com/en-us/library/JJ205242(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="6b6e5-122">[-CsUserStoreBackupData 제거](https://technet.microsoft.com/en-us/library/JJ205003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="6b6e5-122">[Remove-CsUserStoreBackupData](https://technet.microsoft.com/en-us/library/JJ205003(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

