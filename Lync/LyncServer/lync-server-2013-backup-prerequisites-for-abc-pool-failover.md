---
title: 'Lync Server 2013: ABC 풀 장애 조치 (failover)에 대 한 백업 선행 조건'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7cdb228b0a748c830aa488e7b058bf8664360d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a><span data-ttu-id="26948-102">Lync Server 2013에서 ABC 풀 장애 조치 (failover)에 대 한 백업 선행 조건</span><span class="sxs-lookup"><span data-stu-id="26948-102">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26948-103">_**마지막으로 수정한 주제:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="26948-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="26948-104">ABC 풀 장애 조치 절차를 사용 하 여 최대한 활용할 수 있으려면 다음과 같이 재난 및 장애 조치 (failover)가 발생 하기 전에 특정 백업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26948-104">To get the maximum benefit from using the ABC pool failover procedure, you must perform certain backups before the disaster and failover happen:</span></span>

  - <span data-ttu-id="26948-105">**CsLISConfiguration** cmdlet을 사용 하 여 풀 A의 LIS (위치 정보 서비스) 구성 데이터를 정기적으로 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26948-105">You must regularly back up the Location Information Service (LIS) configuration data from pool A by using the **Export-CsLISConfiguration** cmdlet.</span></span>
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - <span data-ttu-id="26948-106">**Export-CsRgsConfiguration** cmdlet을 사용 하 여 풀 A의 응답 그룹 구성 데이터를 정기적으로 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26948-106">You must regularly back up the Response Group configuration data in pool A by using the **Export-CsRgsConfiguration** cmdlet.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <span data-ttu-id="26948-107">일반적으로 매일 백업을 수행 하는 것이 좋지만 많은 양의 변경 내용이 있는 경우에는 백업을 더 자주 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26948-107">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="26948-108">재해가 발생 한 경우 손실 될 수 있는 정보의 양은 백업의 빈도 및 변경 빈도 및 볼륨에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="26948-108">The amount of information that you can lose in the event of a disaster depends on the frequency of your backups, as well as on the frequency and volume of changes.</span></span>
    
    <span data-ttu-id="26948-109">응답 그룹 응용 프로그램은 풀 당 하나의 응용 프로그램 수준 설정 집합만 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26948-109">The Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="26948-110">이러한 설정은 **Get-CsRgsConfiguration** cmdlet을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26948-110">These settings can be accessed through the **Get-CsRgsConfiguration** cmdlets.</span></span> <span data-ttu-id="26948-111">설정에는 기본 음악 보관 구성, 기본 음악 오디오 파일, 에이전트 링 뒤로 유예 기간, 호출 컨텍스트 구성 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26948-111">The settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ring-back grace period, and the call context configuration.</span></span> <span data-ttu-id="26948-112">이러한 설정은 **ReplaceExistingSettings** 매개 변수를 사용 하 여 **가져오기-CsRgsConfiguration** cmdlet을 통해 하나의 풀로 전송할 수 있지만,이 작업은 대상 풀의 모든 응용 프로그램 수준 설정 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="26948-112">These settings can be transferred from one pool to another through the **Import-CsRgsConfiguration** cmdlet by using the **ReplaceExistingSettings** parameter, but this operation will override any application-level settings in the destination pool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="26948-113">별도의 위치에서 응답 그룹 응용 프로그램을 구성 하는 데 사용 된 모든 원본 오디오 파일의 백업 복사본을 보관 합니다 (즉, 기록 또는 보관 된 파일의 경우).</span><span class="sxs-lookup"><span data-stu-id="26948-113">In a separate location, keep a backup copy of all the original audio files that have been used to configure the Response Group application (that is, any recordings or music-on-hold files).</span></span>

    
    </div>
    
    <span data-ttu-id="26948-114">풀의 통화 파킹에 대해 업로드 된 사용자 지정 음악 보관 파일이 있는 경우 다른 위치에 복사본을 보관 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26948-114">If you have any customized music-on-hold files that have been uploaded for Call Park in a pool, you should keep a copy of these in another location.</span></span> <span data-ttu-id="26948-115">이러한 파일은 Lync Server 2013 재해 복구 프로세스의 일부로 백업 되지 않으며 풀에 업로드 된 파일이 손상 되거나 손상 되거나 지워진 경우 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26948-115">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26948-116">통화 공원 응용 프로그램은 하나의 설정 집합과 사용자 지정 된 음악/보류 오디오 파일을 풀 당 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26948-116">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="26948-117">이러한 설정은 <STRONG>CsCpsConfiguration</STRONG> cmdlet을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26948-117">These settings can be accessed through the <STRONG>Get-CsCpsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="26948-118">통화 공원에 대 한 재해 복구 메커니즘은 백업 풀의 통화 공원 응용 프로그램을 사용 하기 때문에 재해가 발생할 경우 주 풀의 설정이 백업 되거나 보존 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26948-118">Because the disaster recovery mechanism for Call Park relies on the Call Park application of the backup pool, the settings of the primary pool are not backed up or preserved if a disaster occurs.</span></span> <span data-ttu-id="26948-119">기본 풀이 손실 되는 경우 이러한 설정을 복구할 수 없으며 새 풀을 배포 하 여 기본 풀을 대체 하는 경우에는 통화 공원 설정 및 사용자 지정 된 음악 대기 오디오 파일을 다시 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26948-119">If the primary pool is lost, these settings cannot be recovered, and when a new pool is deployed to replace the primary pool, the Call Park settings and any customized music-on-hold audio file would need to be reconfigured.</span></span>

    
    </div>

  - <span data-ttu-id="26948-120">지정 하지 않은 번호 음성 기능의 일부로 알림을 구성 하는 경우 초기 구성 중에 사용 되는 원본 오디오 파일의 복사본을 다른 위치에 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="26948-120">If you configure any announcements as part of the Unassigned Number Voice Feature, we recommend that you keep in another location a copy of any original audio file used during the initial configuration.</span></span> <span data-ttu-id="26948-121">이 작업을 수행 하지 않은 경우에는 오디오 파일을 가져온 서버 또는 풀의 파일 저장소에 구성 된 오디오 파일의 복사본을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26948-121">If you did not do that, you can get a copy of the configured audio files in the file store of the server or pool to which the audio files were imported.</span></span> <span data-ttu-id="26948-122">이러한 파일은 Lync Server 2013 재해 복구 프로세스의 일부로 백업 되지 않으며 풀에 업로드 된 파일이 손상 되거나 손상 되거나 지워진 경우 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26948-122">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="26948-123">서버 또는 풀의 파일 저장소에서 지정 하지 않은 번호 음성 기능을 구성 하는 데 사용 된 모든 오디오 파일을 복사 하려면 다음을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26948-123">To copy all the audio files used to configure the Unassigned Number Voice Feature from the file store of a server or a pool, use:</span></span>
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - <span data-ttu-id="26948-124">풀에 데이터베이스를 모니터링 하 고 보관 하는 경우에는 SQL Server 관리 도구를 사용 하 여 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26948-124">If you have Monitoring and Archiving databases in a pool, you should use SQL Server management tools to back them up.</span></span> <span data-ttu-id="26948-125">ABC 장애 조치 (failover) 절차에서 모니터링 및 보관 데이터베이스는 Lync Server 백업 서비스를 통해 백업 되지 않기 때문에 그룹 A에 collocated 경우 보존 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26948-125">In the ABC failover procedure, Monitoring and Archiving databases are not preserved if they are collocated in pool A, because these databases are not backed up through Lync Server Backup Service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

