---
title: 'Lync Server 2013: 백업 서비스 구성 및 모니터링'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65fbbf4db9e15eac2d29fcde6bd126355c794a95
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="7cb07-102">Lync Server 2013에서 백업 서비스 구성 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="7cb07-102">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cb07-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7cb07-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7cb07-104">다음 Lync Server 관리 셸 명령을 사용 하 여 백업 서비스를 구성 하 고 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-104">You can use the following Lync Server Management Shell commands to configure and monitor the Backup Service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7cb07-105">RTCUniversalServerAdmins 그룹은 기본적으로 <STRONG>Get-CsBackupServiceStatus</STRONG>를 실행할 수 있는 사용 권한을 보유한 유일한 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-105">The RTCUniversalServerAdmins group is the only group that has permissions to run <STRONG>Get-CsBackupServiceStatus</STRONG> by default.</span></span> <span data-ttu-id="7cb07-106">이 cmdlet을 사용하려면 이 그룹의 구성원으로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-106">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="7cb07-107">또는 <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet을 사용하여 이 명령에 대한 액세스 권한을 다른 그룹(예: CSAdministrator)에 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-107">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="7cb07-108">백업 서비스 구성을 보려면</span><span class="sxs-lookup"><span data-stu-id="7cb07-108">To see the Backup Service configuration</span></span>

<span data-ttu-id="7cb07-109">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-109">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="7cb07-110">SyncInterval의 기본값은 2분입니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-110">The default for SyncInterval is two minutes.</span></span>

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="7cb07-111">백업 서비스의 동기화 간격을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="7cb07-111">To set the Backup Service sync interval</span></span>

<span data-ttu-id="7cb07-112">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-112">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="7cb07-113">예를 들어 다음 명령은 간격을 3분으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-113">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7cb07-114">이 cmdlet을 사용하여 백업 서비스의 기본 동기화 간격을 변경할 수 있지만, 절대적으로 필요한 경우를 제외하고는 변경해서는 안 됩니다. 동기화 간격은 백업 서비스 성능과 RPO(복구 지점 목표)에 상당한 영향을 미치기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-114">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="7cb07-115">특정 풀의 백업 서비스 상태를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="7cb07-115">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="7cb07-116">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-116">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> <span data-ttu-id="7cb07-117">백업 서비스의 동기화 상태는 풀(P1)에서 백업 풀(P2)로 단방향으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-117">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="7cb07-118">P1에서 P2로의 동기화 상태는 P2에서 P1로의 동기화 상태와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-118">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="7cb07-119">P1에서 P2로의 경우 P1의 모든 변경 내용이 동기화 간격 내에 P2로 완전히 복제되면 백업 서비스는 "안정" 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-119">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="7cb07-120">P1에서 P2로 동기화할 변경 내용이 더 이상 없는 경우 "최종" 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-120">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="7cb07-121">두 상태 모두 cmdlet이 실행되는 시점의 백업 서비스 스냅숏을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-121">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="7cb07-122">반환된 상태가 이후로도 계속 지속됨을 의미하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-122">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="7cb07-123">특히 "최종" 상태는 cmdlet이 실행된 이후 P1에 변경 내용이 전혀 생성되지 않은 경우에만 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-123">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="7cb07-124">이는 <STRONG>Invoke-CsPoolfailover</STRONG> 실행 논리의 일부로 읽기 전용 모드로 전환된 후 P1에서 P2로 장애 조치되는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-124">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the <STRONG>Invoke-CsPoolfailover</STRONG> execution logic.</span></span>



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="7cb07-125">특정 풀의 백업 관계 정보를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="7cb07-125">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="7cb07-126">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-126">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="7cb07-127">백업 서비스의 동기화를 강제로 실행하려면</span><span class="sxs-lookup"><span data-stu-id="7cb07-127">To force a Backup Service sync</span></span>

<span data-ttu-id="7cb07-128">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7cb07-128">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

