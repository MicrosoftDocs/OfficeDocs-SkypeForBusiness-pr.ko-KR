---
title: 'Lync Server 2013: 영구 채팅 서버 기본 데이터베이스에 대해 SQL Server 로그 전달 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ff5f403329c430e18767d9b334982ecccc3898b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521805"
---
# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="12f53-102">영구 채팅 서버 기본 데이터베이스에 대해 Lync Server 2013에서 SQL Server 로그 전달 설정</span><span class="sxs-lookup"><span data-stu-id="12f53-102">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12f53-103">_**마지막으로 수정 된 항목:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="12f53-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="12f53-104">SQL Server Management Studio를 사용 하 여 영구 채팅 서버 보조 로그 전달 데이터베이스 인스턴스에 연결 하 고 SQL Server 에이전트가 실행 중인지 확인해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="12f53-104">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span>

<span data-ttu-id="12f53-105">영구 채팅 기본 데이터베이스 인스턴스에 연결 된 SQL Server Management Studio를 사용 하 여 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-105">Using SQL Server Management Studio connected to the Persistent Chat primary database instance, perform the following steps:</span></span>

1.  <span data-ttu-id="12f53-106">SQL Server 에이전트가 실행 되 고 있는지 확인해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="12f53-106">Be sure that the SQL Server Agent is running.</span></span>

2.  <span data-ttu-id="12f53-107">mgc 데이터베이스를 마우스 오른쪽 단추로 클릭한 후 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-107">Right-click the mgc database, and then click **Properties**.</span></span>

3.  <span data-ttu-id="12f53-108">**페이지 선택** 아래에서 **트랜잭션 로그 전달**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-108">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

4.  <span data-ttu-id="12f53-109">**이 데이터베이스를 로그 전달 구성의 기본 데이터베이스로 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-109">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

5.  <span data-ttu-id="12f53-110">**트랜잭션 로그 백업**에서 **백업 설정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-110">Under **Transaction log backups**, click **Backup Settings**.</span></span>

6.  <span data-ttu-id="12f53-111">**백업 폴더의 네트워크 경로** 상자에 트랜잭션 로그 백업 폴더에 대해 만든 공유의 네트워크 경로를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-111">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>

7.  <span data-ttu-id="12f53-112">백업 폴더가 주 서버에 있는 경우 백업 폴더의 기본 서버에 백업 폴더의 로컬 경로를 입력 하 고 **폴더의 로컬 경로 (예: c: \\ 백업)** 상자를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-112">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\\backup)** box.</span></span> <span data-ttu-id="12f53-113">(백업 폴더가 주 서버에 없는 경우에는이 상자를 비워 둘 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="12f53-113">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="12f53-114">기본 서버의 SQL Server 서비스 계정이 로컬 시스템 계정으로 실행 되는 경우 주 서버에 백업 폴더를 만들고 해당 폴더에 대 한 로컬 경로를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-114">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

8.  <span data-ttu-id="12f53-115">**다음보다 오래된 파일 삭제** 및 **다음 기간 내에 백업이 발생하지 않으면 경고** 매개 변수를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-115">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

9.  <span data-ttu-id="12f53-116">**백업 작업** 아래의 **예약** 상자에 나열된 백업 일정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-116">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="12f53-117">설치 일정을 사용자 지정 하려면 **예약**을 클릭 하 고 필요에 따라 SQL Server 에이전트 일정을 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-117">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>

10. <span data-ttu-id="12f53-118">**압축**에서 **기본 서버 설정 사용**을 선택하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-118">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>

11. <span data-ttu-id="12f53-119">**보조 서버 인스턴스 및 데이터베이스**에서 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-119">Under **Secondary server instances and databases**, click **Add**.</span></span>

12. <span data-ttu-id="12f53-120">**연결** 을 클릭 하 고 보조 서버로 구성한 SQL Server 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-120">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

13. <span data-ttu-id="12f53-121">**보조 데이터베이스** 상자의 목록에서 **mgc** 데이터베이스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-121">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

14. <span data-ttu-id="12f53-122">**보조 데이터베이스 초기화** 탭에서 **예, 기본 데이터베이스의 전체 백업을 생성 하 고 보조 데이터베이스에 복원 합니다 (존재 하지 않는 경우 보조 데이터베이스를 만듭니다)**.</span><span class="sxs-lookup"><span data-stu-id="12f53-122">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>

15. <span data-ttu-id="12f53-p103">**파일 복사** 탭의 **복사한 파일의 대상 폴더: (이 폴더는 일반적으로 보조 서버에 있습니다.)** 상자에 트랜잭션 로그 백업을 복사할 폴더의 경로를 입력합니다. 이 폴더는 대개 보조 서버에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-p103">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>

16. <span data-ttu-id="12f53-125">**복사 작업** 아래 **일정** 상자에 나열된 복사 일정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-125">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="12f53-126">설치 일정을 사용자 지정 하려면 **예약**을 클릭 하 고 필요에 따라 SQL Server 에이전트 일정을 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-126">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="12f53-127">이 일정은 백업 일정과 대략적으로 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-127">This schedule should be approximately the same as the backup schedule.</span></span>

17. <span data-ttu-id="12f53-128">**복원** 탭의 **백업 복원 시 데이터베이스 상태**에서 **복구 안 함 모드** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-128">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>

18. <span data-ttu-id="12f53-129">**최소 다음 기간 동안 백업 복원 지연:** 에서 **0분**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-129">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>

19. <span data-ttu-id="12f53-130">**다음 기간 내에 복원이 발생하지 않으면 경고**에서 경고 임계값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-130">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>

20. <span data-ttu-id="12f53-131">**복원 작업** 아래 **일정** 상자에 나열된 복원 일정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-131">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="12f53-132">설치 일정을 사용자 지정 하려면 **예약**을 클릭 하 고 필요에 따라 SQL Server 에이전트 일정을 조정한 후에 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-132">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="12f53-133">이 일정은 백업 일정과 대략적으로 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-133">This schedule should be approximately the same as the backup schedule.</span></span>

21. <span data-ttu-id="12f53-134">**데이터베이스 속성** 대화 상자에서 **확인**을 클릭하여 구성 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="12f53-134">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

