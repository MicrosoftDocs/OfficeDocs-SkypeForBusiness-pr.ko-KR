---
title: 'Lync Server 2013: 백업 및 복원에 대 한 모범 사례'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fc2aac99251c0b2e5bc950b3dc11e8e2044b440
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a><span data-ttu-id="caea6-102">Lync Server 2013의 백업 및 복원에 대 한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="caea6-102">Best practices for backup and restoration for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="caea6-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="caea6-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="caea6-104">이 섹션에는 두 가지 유형의 모범 사례가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-104">This section includes two types of best practices:</span></span>

  - <span data-ttu-id="caea6-105">백업 및 복원 모범 사례</span><span class="sxs-lookup"><span data-stu-id="caea6-105">Best practices for backup and restoration.</span></span>

  - <span data-ttu-id="caea6-106">재해의 영향을 최소화 하기 위한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="caea6-106">Best practices for minimizing the impact of a disaster.</span></span>

<div>

## <a name="best-practices-for-backup-and-restoration"></a><span data-ttu-id="caea6-107">백업 및 복원 모범 사례</span><span class="sxs-lookup"><span data-stu-id="caea6-107">Best Practices for Backup and Restoration</span></span>

<span data-ttu-id="caea6-108">백업 및 복원 프로세스를 원활 하 게 수행 하려면 데이터를 백업 또는 복원할 때 다음과 같은 모범 사례를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-108">To facilitate your backup and restoration process, apply the following best practices when you back up or restore your data:</span></span>

  - <span data-ttu-id="caea6-109">적절한 간격으로 백업을 정기적으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-109">Perform regular backups at appropriate intervals.</span></span> <span data-ttu-id="caea6-110">가장 단순하고 가장 일반적으로 사용되는 백업 유형 및 순환 계획은 전체 SQL Server 데이터베이스의 전체 야간 백업입니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-110">The simplest and most commonly used backup type and rotation schedule is a full, nightly backup of the entire SQL Server database.</span></span> <span data-ttu-id="caea6-111">복원 해야 하는 경우 복원 프로세스에는 하나의 백업만 필요 하며 하루 이상의 데이터는 손실 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-111">Then, if restoration is necessary, the restoration process requires only one backup, and no more than a day’s data should be lost.</span></span>

  - <span data-ttu-id="caea6-112">Cmdlet 또는 Lync Server 제어판을 사용 하 여 구성을 변경 하는 경우에는 **내보내기-csconfiguration** cmdlet을 사용 하 여 변경 후 토폴로지 구성 파일 (Xds)의 스냅숏 백업을 수행 하 여 데이터베이스를 복원 해야 하는 경우 변경 내용이 손실 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-112">If you use cmdlets or the Lync Server Control Panel to make configuration changes, use the **Export-CsConfiguration** cmdlet to take a snapshot backup of the topology configuration file (Xds.mdf) after you make the changes, so that you won't lose the changes if you need to restore your databases.</span></span> <span data-ttu-id="caea6-113">이 구성은 XML 형식으로 백업 되 고 ZIP 파일로 압축 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-113">Note that this configuration is backed up in XML format and compressed as a ZIP file.</span></span>

  - <span data-ttu-id="caea6-114">Lync Server 백업에 사용할 공유 폴더에 백업 된 데이터를 모두 저장할 충분 한 디스크 공간이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-114">Make sure that the shared folder you plan to use for backing up Lync Server has sufficient disk space to hold all the backed up data.</span></span>

  - <span data-ttu-id="caea6-115">Lync Server 사용량이 보통 낮을 때 백업을 예약 하 여 서버 성능 및 사용자 환경을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-115">Schedule backups when Lync Server usage is typically low, to improve server performance and user experience.</span></span>

  - <span data-ttu-id="caea6-116">데이터를 백업 하는 위치가 안전한 지 확인 합니다 (원격 위치 권장).</span><span class="sxs-lookup"><span data-stu-id="caea6-116">Make sure that the location where you back up data is secure (we recommend a remote location).</span></span>

  - <span data-ttu-id="caea6-117">데이터를 복원 해야 하는 경우를 대비 하 여 사용할 수 있는 위치에 백업 파일을 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-117">Keep the backup files where they will be available, in case you need to restore the data.</span></span>

  - <span data-ttu-id="caea6-118">조직에서 지원 되는 복원 프로세스의 주기적인 테스트를 계획 하 고 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-118">Plan for and schedule periodic testing of the restoration processes that are supported by your organization.</span></span>

  - <span data-ttu-id="caea6-119">백업 및 복원 프로세스를 미리 확인 하 여 예상 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-119">Validate your backup and restoration processes in advance to make sure that they work as expected.</span></span>

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a><span data-ttu-id="caea6-120">재해 영향을 최소화하기 위한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="caea6-120">Best Practices for Minimizing the Impact of a Disaster</span></span>

<span data-ttu-id="caea6-121">정전 또는 갑작스런 하드웨어 오류와 같은 관리 되지 않는 이벤트로 인 한 치명적인 서비스 중단을 처리 하기 위한 최상의 전략은 문제가 발생 한 것으로 가정 하 고 적절 하 게 계획 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-121">The best strategy for dealing with disastrous service interruptions (caused by unmanageable events such as power outages or sudden hardware failures) is to assume they will happen, and to plan accordingly.</span></span>

<span data-ttu-id="caea6-122">최소화 및 중단을 최소화 한 상태로 Lync services가 비즈니스에 중요 한 경우 [Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)에서 설명 하는 대로 프런트 엔드 서버의 연결 된 풀을 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-122">If Lync services, with a minimum of disruption and outage, are business-critical for your organization, you should consider implementing paired pools of Front End Servers, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="caea6-123">그런 다음 이러한 풀 중 하나에 재해가 발생 하는 경우 관리자가 해당 풀의 사용자를 다른 풀에서 처리 하도록 전환할 수 있으며 최소 가동 중지 시간이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-123">Then, if one of these pools has a disaster, an administrator can switch the users of that pool to be served by the other pool, with a minimum of downtime.</span></span>

<span data-ttu-id="caea6-124">백업 및 복원 전략의 일부로 개발 하는 재해 관리 계획에는 다음이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-124">The disaster management plans that you develop as part of your backup and restoration strategy should include the following:</span></span>

  - <span data-ttu-id="caea6-125">소프트웨어 미디어 및 소프트웨어와 펌웨어 업데이트를 즉시 사용할 수 있도록 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-125">Keeping your software media, and your software and firmware updates, readily available.</span></span>

  - <span data-ttu-id="caea6-126">하드웨어 및 소프트웨어 레코드를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-126">Maintaining hardware and software records.</span></span>

  - <span data-ttu-id="caea6-127">데이터를 정기적으로 백업 하 고 백업 무결성을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-127">Backing up your data regularly and monitoring the integrity of your backups.</span></span>

  - <span data-ttu-id="caea6-128">재해 복구에 대한 직원 교육을 실시하고, 절차를 문서화하고, 재해 복구 시뮬레이션 훈련을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-128">Training your staff in disaster recovery, documenting procedures, and implementing disaster recovery simulation drills.</span></span>

  - <span data-ttu-id="caea6-129">예비 하드웨어를 사용할 수 있도록 유지 하거나 SLA (서비스 수준 계약)가 있는 경우 하드웨어 공급 업체 및 공급자에 게 음성 안내 대체를 사용 하 여 계약 합니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-129">Keeping spare hardware available, or, if you have a service level agreement (SLA), contracting with hardware vendors and suppliers for prompt replacements.</span></span>

  - <span data-ttu-id="caea6-130">트랜잭션 로그 파일(.ldf 파일) 및 데이터베이스 파일(.mdf 파일)의 위치를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="caea6-130">Separating the location of your transaction log files (.ldf files) and database files (.mdf files).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

