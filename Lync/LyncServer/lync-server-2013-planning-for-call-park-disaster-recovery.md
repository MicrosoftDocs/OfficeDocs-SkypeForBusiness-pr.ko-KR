---
title: 'Lync Server 2013: 통화 대기 재해 복구 계획'
description: 'Lync Server 2013: 통화 대기 재해 복구 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1d05503f1d8c30f4dd4446a995442d5e2500dbc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554284"
---
# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="38885-103">Lync Server 2013의 통화 대기 재해 복구 계획</span><span class="sxs-lookup"><span data-stu-id="38885-103">Planning for Call Park disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38885-104">_**마지막으로 수정 된 항목:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="38885-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="38885-105">이 섹션에서는 재해 복구를 위해 통화 대기 응용 프로그램을 준비 하는 몇 가지 방법과 재해 복구 프로세스에 대 한 일부 고려 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="38885-105">This section describes some ways to prepare the Call Park application for disaster recovery and some considerations for the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a><span data-ttu-id="38885-106">통화 대기 재해 복구 준비</span><span class="sxs-lookup"><span data-stu-id="38885-106">Preparing for Call Park Disaster Recovery</span></span>

<span data-ttu-id="38885-107">재해 복구 절차를 준비하고 수행할 때 다음 사항에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="38885-107">Keep the following in mind when preparing for and carrying out disaster recovery procedures.</span></span>

  - <span data-ttu-id="38885-108">용량 계획을 수행할 때 재해 복구를 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="38885-108">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="38885-109">재해 복구 용량의 경우 페어링 된 풀의 각 풀은 두 풀에서 통화 대기 서비스의 작업 부하를 처리할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38885-109">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of the Call Park services in both pools.</span></span> <span data-ttu-id="38885-110">통화 대기 용량 계획에 대 한 자세한 내용은 [Lync Server 2013에서 통화 대기에 대 한 용량 계획](lync-server-2013-capacity-planning-for-call-park.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="38885-110">For details about Call Park capacity planning, see [Capacity planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span></span>

  - <span data-ttu-id="38885-111">재해 복구 중에 장애 조치(failover) 프로세스의 일부로서 백업 풀로 리디렉션된 사용자는 백업 풀에서 실행 중인 통화 대기 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="38885-111">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park service running in the backup pool.</span></span> <span data-ttu-id="38885-112">따라서 재해 복구 중 통화 대기를 지원 하려면 기본 풀과 백업 풀에서 모두 통화 대기 응용 프로그램을 배포 하 고 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38885-112">Therefore, support for Call Park during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

  - <span data-ttu-id="38885-113">각 풀에는 해당 풀에 있는 사용자에 대해 통화 대기에 사용할 유효한 파킹된 통화 번호 범위가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38885-113">Each pool must have a valid range of orbit numbers for users who are homed in that pool to use for parking calls.</span></span>

  - <span data-ttu-id="38885-114">통화 대기를 위해 업로드 된 보류 중인 사용자 지정 음악의 별도 백업 복사본을 항상 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="38885-114">Always keep a separate backup copy of any customized music on hold that has been uploaded for Call Park.</span></span> <span data-ttu-id="38885-115">이러한 파일은 Lync Server 2013 재해 복구 프로세스의 일부로 백업 되지 않으며, 풀에 업로드 된 파일이 손상 되거나 손상 되거나 지워진 경우 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38885-115">These files are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a><span data-ttu-id="38885-116">통화 대기 재해 복구 고려 사항</span><span class="sxs-lookup"><span data-stu-id="38885-116">Call Park Disaster Recovery Considerations</span></span>

<span data-ttu-id="38885-117">통화 대기 응용 프로그램 구성 설정의 집합과 사용자 지정 된 단일 음악 오디오 파일을 풀 당 하나만 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38885-117">You can define only one set of Call Park application configuration settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="38885-118">이러한 설정에는 시간 제한 임계값, 대기 음악, 최대 호출 받기 시도 횟수 및 시간 제한 URI가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="38885-118">These settings include the timeout threshold, music on hold, maximum call pickup attempts, and timeout URI.</span></span> <span data-ttu-id="38885-119">이러한 구성 설정을 보려면 **Get-CsCpsConfiguration** cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="38885-119">To view these configuration settings, run the **Get-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="38885-120">**New-cscpsconfiguration** cmdlet에 대 한 자세한 내용은 [get-new-cscpsconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="38885-120">For details about the **Get-CsCpsConfiguration** cmdlet, see [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span></span>

<span data-ttu-id="38885-121">재해 복구 중에 통화 대기는 백업 풀의 통화 대기 응용 프로그램을 사용 하므로 기본 풀의 설정이 백업 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38885-121">During disaster recovery, Call Park uses the Call Park application in the backup pool, so settings in the primary pool are not backed up.</span></span> <span data-ttu-id="38885-122">기본 풀을 복구할 수 없고 기본 풀을 대체 하기 위해 새 풀을 배포 하는 경우 기본 풀의 설정이 손실 되며, 새 풀에서 통화 대기 설정 및 사용자 지정 된 모든 음악 오디오 파일을 다시 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38885-122">If the primary pool can't be recovered and you deploy a new pool to replace the primary pool, the settings from the primary pool are lost, and you need to reconfigure the Call Park settings and any customized music-on-hold audio files in the new pool.</span></span>

<span data-ttu-id="38885-123">기본 풀을 대체 하기 위해 다른 FQDN (정규화 된 도메인 이름)을 사용 하 여 새 풀을 배포 하는 경우 기본 풀과 연결 된 모든 통화 대기 궤도 범위를 새 풀의 FQDN으로 다시 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38885-123">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Call Park orbit ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="38885-124">궤도 범위를 새 풀에 다시 할당 하려면 Lync Server 제어판 또는 **get-cscallparkorbit** cmdlet 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38885-124">To reassign orbit ranges to the new pool, you can use either Lync Server Control Panel or the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="38885-125">**Get-cscallparkorbit** cmdlet에 대 한 자세한 내용은 [get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="38885-125">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

