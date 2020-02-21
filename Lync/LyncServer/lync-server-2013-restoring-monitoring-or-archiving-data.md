---
title: 'Lync Server 2013: 모니터링 또는 보관 데이터 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e44bf1fe66aa7c03caea2ba367f425f1094a9a4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a><span data-ttu-id="e4968-102">Lync Server 2013에서 모니터링 또는 보관 데이터 복원</span><span class="sxs-lookup"><span data-stu-id="e4968-102">Restoring monitoring or archiving data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4968-103">_**마지막으로 수정 된 항목:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="e4968-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="e4968-104">장애 발생 후 Lync Server를 실행 하 고 실행할 때는 모니터링 및 보관 데이터를 복원 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-104">Restoring monitoring and archiving data is not required to get Lync Server up and running after a failure.</span></span> <span data-ttu-id="e4968-105">그러나 모니터링 및 보관 데이터가 조직에 중요 한 경우 데이터베이스를 다시 만든 후에 데이터를 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-105">However, if monitoring and archiving data is critical to your organization, you will want to restore the data after you re-create the databases.</span></span>

<span data-ttu-id="e4968-106">다음 절차에서는 SQL Server Management Studio를 사용 하 여 보관 또는 모니터링 데이터를 복원 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-106">The following procedure describes how to use SQL Server Management Studio to restore archiving or monitoring data.</span></span>

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a><span data-ttu-id="e4968-107">백업 파일로부터 모니터링 또는 보관 데이터를 복원하려면</span><span class="sxs-lookup"><span data-stu-id="e4968-107">To restore monitoring or archiving data from a backup file</span></span>

1.  <span data-ttu-id="e4968-108">로컬 컴퓨터에서 Administrators 그룹의 구성원 또는 이와 동등한 사용자 권한을 가진 그룹으로 복원 중인 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-108">Log on to the server that you are restoring as a member of the Administrators group on the local computer or a group with equivalent user rights.</span></span>

2.  <span data-ttu-id="e4968-109">SQL Server Management Studio 열기: **시작**, **모든 프로그램**, **Microsoft SQL Server 2012** 또는 **microsoft sql server 2008 R2**를 차례로 클릭 한 다음 **SQL server Management Studio**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-109">Open SQL Server Management Studio: click **Start**, click **All Programs**, click **Microsoft SQL Server 2012** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>

3.  <span data-ttu-id="e4968-110">**서버에 연결**에서 최소한 서버 이름 및 인증 정보를 제공하여 SQL Server 인스턴스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-110">In **Connect to Server**, connect to the SQL Server instance by providing at least the name of the server and the authentication information.</span></span>

4.  <span data-ttu-id="e4968-111">**개체 탐색기**에서 **데이터베이스**를 마우스 오른쪽 단추로 클릭한 후 **데이터베이스 복원**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-111">In **Object Explorer**, right-click **Databases**, and then click **Restore Database**.</span></span>

5.  <span data-ttu-id="e4968-112">**페이지 선택** 아래에서 **일반**을 클릭한 후 **데이터베이스**에서 다음과 같이 데이터베이스 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-112">Under **Select a page**, click **General**, and then in **To database** select the database name as follows:</span></span>
    
      - <span data-ttu-id="e4968-113">보관 데이터베이스의 경우에는 **Lcslog**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-113">For an Archiving database, select **LcsLog**.</span></span>
    
      - <span data-ttu-id="e4968-114">CDR(통화 정보 기록) 데이터베이스에 대해 **LcsCDR**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-114">For a call detail recording (CDR) database, select **LcsCDR**.</span></span>
    
      - <span data-ttu-id="e4968-115">QoE(체감 품질) 데이터베이스에 대해 **QoEMetrics**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-115">For a Quality of Experience (QoE) database, select **QoEMetrics**.</span></span>

6.  <span data-ttu-id="e4968-116">**장치**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-116">Click **From device**.</span></span>

7.  <span data-ttu-id="e4968-117">**복원에 사용할 백업 세트 선택**에서 백업 파일을 클릭한 후 **복원**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-117">Under **Select the backup sets to restore**, click the backup file, and then click **Restore**.</span></span>

8.  <span data-ttu-id="e4968-118">**페이지 선택**에서 **옵션**을 클릭하고 데이터 파일 경로 및 로그 경로가 올바른 폴더에 있는지 확인한 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-118">Under **Select a page**, click **Options**, verify that the data file path and log path are in the correct folder, and then click **OK**.</span></span>

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a><span data-ttu-id="e4968-119">Acl (액세스 제어 목록)이 올바른지 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="e4968-119">To make sure that access control lists (ACLs) are correct</span></span>

1.  <span data-ttu-id="e4968-120">**데이터베이스**를 확장하고, 보관 또는 모니터링 데이터베이스를 확장하고, **보안**을 확장한 후 **사용자**를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-120">Expand **Databases**, expand the archiving or monitoring database, expand **Security**, and then expand **Users**.</span></span>

2.  <span data-ttu-id="e4968-121">도메인 그룹 RTCComponentUniversalServices가 사용자로 존재하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-121">Verify that the domain group RTCComponentUniversalServices exists as a user.</span></span>

3.  <span data-ttu-id="e4968-122">**사용자**에 RTCComponentUniversalServices이 없는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-122">If RTCComponentUniversalServices does not exist under **Users**, do the following:</span></span>
    
    1.  <span data-ttu-id="e4968-123">**사용자**를 마우스 오른쪽 단추로 클릭한 다음 **새 사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-123">Right-click **Users**, and then click **New User**.</span></span>
    
    2.  <span data-ttu-id="e4968-124">**로그인 이름**에 누락 된 그룹 이름 RTCComponentUniversalServices을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-124">In **Login name**, type the missing group name, RTCComponentUniversalServices.</span></span>
    
    3.  <span data-ttu-id="e4968-125">**데이터베이스 역할 멤버 자격** 아래에서 **ServerRole** 권한을 선택한 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-125">Under **Database role membership**, select the **ServerRole** permission, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e4968-126">보관 또는 모니터링 서비스를 다시 시작할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e4968-126">You do not need to restart the archiving or monitoring service.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

