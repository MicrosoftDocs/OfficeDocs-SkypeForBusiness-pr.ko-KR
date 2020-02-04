---
title: 'Lync Server 2013: 백업 서비스로 전화 회의 내용 복원'
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
ms.openlocfilehash: 873ca354ca592eb6bc317b579a0a6f5008e6a172
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="6d3d7-102">Lync Server 2013에서 백업 서비스로 전화 회의 내용 복원</span><span class="sxs-lookup"><span data-stu-id="6d3d7-102">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d3d7-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6d3d7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6d3d7-104">프런트 엔드 풀의 파일 저장소에 저장 된 회의 정보를 사용할 수 없게 되는 경우</span><span class="sxs-lookup"><span data-stu-id="6d3d7-104">If the conference information stored in the file store of a Front End pool becomes unavailable.</span></span> <span data-ttu-id="6d3d7-105">그룹에 속한 사용자가 회의 데이터를 유지할 수 있도록이 정보를 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-105">you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="6d3d7-106">회의 데이터가 손실 된 프런트 엔드 풀이 다른 프런트 엔드 풀과 쌍을 이루는 경우 백업 서비스를 사용 하 여 데이터를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-106">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="6d3d7-107">전체 풀이 실패 하 고 해당 사용자를 백업 풀로 장애 조치 해야 하는 경우에도이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-107">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="6d3d7-108">이러한 사용자가 원래 풀로 장애 복구 되는 경우이 절차를 사용 하 여 회의 콘텐츠를 원래 풀로 다시 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-108">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="6d3d7-109">Pool1가 Pool2와 쌍을 이루고 있고 Pool1의 컨퍼런스 데이터가 손실 된다고 가정 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-109">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="6d3d7-110">다음 cmdlet을 사용 하 여 백업 서비스를 호출 하 여 콘텐츠를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-110">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="6d3d7-111">회의 콘텐츠는 크기에 따라 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-111">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="6d3d7-112">다음 cmdlet을 사용 하 여 프로세스 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-112">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="6d3d7-113">이 cmdlet은 데이터 컨퍼런스 모듈에 대 한 안정 된 상태 값을 반환 하는 경우에 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d3d7-113">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

