---
title: 'Lync Server 2013: 재해 복구 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2d36ec6ad1afb8c41c7c5f614e90e03ce4d9282
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528955"
---
# <a name="disaster-recovery-test-in-lync-server-2013"></a><span data-ttu-id="cb12b-102">Lync Server 2013의 재해 복구 테스트</span><span class="sxs-lookup"><span data-stu-id="cb12b-102">Disaster recovery test in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb12b-103">_**마지막으로 수정 된 항목:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="cb12b-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="cb12b-104">Lync Server 2013 풀 서버에 대 한 시스템 복구를 수행 하 여 문서화 된 재해 복구 프로세스를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-104">Perform a system recovery for a Lync Server 2013 pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="cb12b-105">이 테스트에서는 한 서버에 대 한 전체 하드웨어 오류를 시뮬레이션 하며, 리소스, 계획 및 데이터를 복구에 사용할 수 있도록 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data is available for recovery.</span></span> <span data-ttu-id="cb12b-106">조직에서 매번 다른 서버나 기타 장비의 오류를 테스트할 수 있도록 매월 테스트 초점을 회전 해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span>

<span data-ttu-id="cb12b-107">조직에서 재해 복구 테스트를 수행 하는 일정은 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-107">Note that the schedule by which organizations perform Disaster Recovery testing will vary.</span></span> <span data-ttu-id="cb12b-108">재해 복구 테스트는 무시 되거나 연락이 중단 되지 않도록 하는 것이 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-108">It is very important that disaster recovery testing is not ignored or neglected.</span></span>

<div>


<span data-ttu-id="cb12b-109">Lync Server 2013 토폴로지, 정책 및 구성 설정을 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-109">Export your Lync Server 2013 topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="cb12b-110">즉, 업그레이드, 하드웨어 오류 또는 다른 문제로 인해 데이터가 손실 된 후에이 파일을 중앙 관리 저장소로 복원 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="cb12b-111">다음 명령과 같이 Lync Server 2013 토폴로지, 정책 및 구성 설정을 중앙 관리 저장소나 로컬 컴퓨터로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-111">Import your Lync Server 2013 topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span>

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

<span data-ttu-id="cb12b-112">프로덕션 Lync Server 2013 데이터를 백업 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-112">To back up production Lync Server 2013 data:</span></span>

  - <span data-ttu-id="cb12b-113">표준 SQL Server 백업 프로세스를 사용 하 여 데이터베이스를 파일 또는 테이프 덤프 장치로 덤프 하 여 RTC 및 LCSLog 데이터베이스를 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>

  - <span data-ttu-id="cb12b-114">타사 백업 응용 프로그램을 사용 하 여 데이터를 파일 또는 테이프에 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-114">Use third-party backup application to back up the data to file or to tape.</span></span>

  - <span data-ttu-id="cb12b-115">Export-CsUserData cmdlet을 사용 하 여 전체 RTC 데이터베이스의 XML 내보내기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>

  - <span data-ttu-id="cb12b-116">파일 시스템 백업 또는 타사를 사용 하 여 모임 콘텐츠 및 준수 로그를 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-116">Use the file system backup or third-party to back up meeting content and compliance logs.</span></span>

  - <span data-ttu-id="cb12b-117">Export-CsConfiguration 명령줄 도구를 사용 하 여 Lync Server 2013 설정을 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-117">Use the Export-CsConfiguration command-line tool to back up Lync Server 2013 settings.</span></span>

<span data-ttu-id="cb12b-118">장애 조치 (failover) 절차의 첫 번째 단계에는 프로덕션 풀에서 재해 복구 풀로 사용자를 강제로 이동 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span>

<span data-ttu-id="cb12b-119">이는 프로덕션 풀을 사용 하 여 사용자의 재배치가 허용 되지 않으므로 강제 이동이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="cb12b-120">Lync Server 2013 move user 프로세스는 RTC SQL 데이터베이스의 레코드 업데이트 외에 사용자 계정 개체의 특성을 실제로 변경 하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-120">The Lync Server 2013 move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span>

<span data-ttu-id="cb12b-121">이 데이터는 다음의 두 프로세스를 통해 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-121">This data can be restored through the following two processes:</span></span>

  - <span data-ttu-id="cb12b-122">RTC 데이터베이스는 표준 SQL Server 복원 프로세스를 사용 하 여 프로덕션 SQL Server에서 원본 백업 덤프 장치 로부터 복원 하거나 타사 백업/복원 유틸리티를 사용 하 여 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-122">RTC database can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

  - <span data-ttu-id="cb12b-123">프로덕션 SQL Server 내보내기에서 만든 XML 파일을 사용 하 여 DBIMPEXP.exe 유틸리티로 사용자 연락처 데이터를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-123">User contact data can be restored with the DBIMPEXP.exe utility using the XML file that was created from the production SQL Server export.</span></span>

<span data-ttu-id="cb12b-124">이 데이터를 복원한 후에는 사용자가 재해 복구 Lync Server 2013 풀에 효과적으로 연결 하 고 평소와 같이 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-124">After this data is restored, users can effectively connect to the Disaster Recovery Lync Server 2013 pool, and operate as usual.</span></span>

<span data-ttu-id="cb12b-125">사용자가 재해 복구 Lync Server 2013 풀에 연결할 수 있도록 하려면 DNS 레코드를 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-125">To enable users to connect to the Disaster Recovery Lync Server 2013 pool, a DNS record change will be required.</span></span>

<span data-ttu-id="cb12b-126">프로덕션 Lync Server 2013 풀은 다음의 자동 구성 및 DNS SRV 레코드를 사용 하는 클라이언트에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-126">The production Lync Server 2013 pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

  - <span data-ttu-id="cb12b-127">SRV: \_ sip. \_ ls.\<domain\></span><span class="sxs-lookup"><span data-stu-id="cb12b-127">SRV: \_sip.\_tls.\<domain\></span></span> <span data-ttu-id="cb12b-128">/CNAME: SIP\<domain\></span><span class="sxs-lookup"><span data-stu-id="cb12b-128">/CNAME: SIP.\<domain\></span></span>

  - <span data-ttu-id="cb12b-129">CNAME: SIP\<domain\></span><span class="sxs-lookup"><span data-stu-id="cb12b-129">CNAME: SIP.\<domain\></span></span> <span data-ttu-id="cb12b-130">/cvc-pool-1.\<domain\></span><span class="sxs-lookup"><span data-stu-id="cb12b-130">/cvc-pool-1.\<domain\></span></span>

<span data-ttu-id="cb12b-131">장애 조치 (failover)를 촉진 하기 위해이 CNAME 레코드를 업데이트 하 여 DROCSPool FQDN을 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb12b-131">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

  - <span data-ttu-id="cb12b-132">CNAME: SIP\<domain\></span><span class="sxs-lookup"><span data-stu-id="cb12b-132">CNAME: SIP.\<domain\></span></span> <span data-ttu-id="cb12b-133">/DROCSPool.\<domain\></span><span class="sxs-lookup"><span data-stu-id="cb12b-133">/DROCSPool.\<domain\></span></span>

  - <span data-ttu-id="cb12b-134">호흡.\<domain\></span><span class="sxs-lookup"><span data-stu-id="cb12b-134">Sip.\<domain\></span></span>

  - <span data-ttu-id="cb12b-135">AV.\<domain\></span><span class="sxs-lookup"><span data-stu-id="cb12b-135">AV.\<domain\></span></span>

  - <span data-ttu-id="cb12b-136">fea-webconf-service.\<domain\></span><span class="sxs-lookup"><span data-stu-id="cb12b-136">webconf.\<domain\></span></span>

  - <span data-ttu-id="cb12b-137">OCSServices\<domain\></span><span class="sxs-lookup"><span data-stu-id="cb12b-137">OCSServices.\<domain\></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cb12b-138">관리 절차에 대 한 자세한 내용은 <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">백업 및 복원 Lync Server 2013</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cb12b-138">For detailed administration and management procedures, see <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Backing up and restoring Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cb12b-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb12b-139">See Also</span></span>


[<span data-ttu-id="cb12b-140">Lync Server 2013의 고가용성 및 재해 복구 계획</span><span class="sxs-lookup"><span data-stu-id="cb12b-140">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[<span data-ttu-id="cb12b-141">Lync Server 2013의 백업 및 고가용성 cmdlet</span><span class="sxs-lookup"><span data-stu-id="cb12b-141">Backup and high availability cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[<span data-ttu-id="cb12b-142">가져오기-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="cb12b-142">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="cb12b-143">Lync Server 2013 백업 및 복원</span><span class="sxs-lookup"><span data-stu-id="cb12b-143">Backing up and restoring Lync Server 2013</span></span>](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[<span data-ttu-id="cb12b-144">Lync Server 2013 재해 복구, 고가용성 및 백업 서비스 관리</span><span class="sxs-lookup"><span data-stu-id="cb12b-144">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

