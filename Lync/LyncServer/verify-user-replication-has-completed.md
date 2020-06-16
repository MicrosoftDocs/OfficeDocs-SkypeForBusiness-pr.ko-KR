---
title: 사용자 복제가 완료되었는지 확인
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d883b5446c843ac8b79e2b29d15f8a1c99f0089
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="576f7-102">사용자 복제가 완료되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="576f7-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="576f7-103">_**마지막으로 수정 된 항목:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="576f7-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="576f7-104">**Cslicuser** cmdlet을 실행 하는 경우 초기 복제가 완료 되지 않아 AD DS (Active Directory 도메인 서비스)와 Lync Server 2013 데이터베이스 간의 사용자 정보가 동기화 되지 않아 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="576f7-104">When running the **Move-CsUser** cmdlet, you may experience a failure because user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="576f7-105">Lync Server 2013 사용자 복제기 service의 초기 동기화를 성공적으로 완료 하는 데 걸리는 시간은 Lync Server 2013 풀을 호스트 하는 Active Directory 포리스트에서 호스트 되는 도메인 컨트롤러의 수에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="576f7-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="576f7-106">Lync Server 2013 사용자 복제기 service 초기 동기화 프로세스는 Lync Server 2013 프런트 엔드 서버를 처음 시작할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="576f7-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="576f7-107">그런 후에는 사용자 복제기 간격을 기반으로 동기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="576f7-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="576f7-108">다음 단계를 완료 하 여 **csuser** cmdlet을 실행 하기 전에 사용자 복제가 완료 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="576f7-108">Complete the following steps to verify user replication has completed before running the **Move-CsUser** cmdlet.</span></span>

<div>

## <a name="to-verify-user-replication-has-completed"></a><span data-ttu-id="576f7-109">사용자 복제가 완료되었는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="576f7-109">To verify user replication has completed</span></span>

1.  <span data-ttu-id="576f7-110">토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="576f7-110">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="576f7-111">**시작** 메뉴를 클릭한 후 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="576f7-111">Click the **Start** menu, and then click **Run**.</span></span>

3.  <span data-ttu-id="576f7-112">**eventvwr.exe**를 입력한 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="576f7-112">Enter **eventvwr.exe** and then click **OK**.</span></span>

4.  <span data-ttu-id="576f7-113">이벤트 뷰어에서 **응용 프로그램 및 서비스 로그**를 클릭해서 확장한 후 Lync Server를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="576f7-113">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

5.  <span data-ttu-id="576f7-114">**동작** 창에서 **현재 로그 필터링**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="576f7-114">In the **Actions** pane click **Filter Current Log**.</span></span>

6.  <span data-ttu-id="576f7-115">**이벤트 원본** 목록에서 **LS User Replicator**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="576f7-115">From the **Event sources** list, click **LS User Replicator**.</span></span>

7.  <span data-ttu-id="576f7-116">에서 **\<All Event IDs\>** **30024** 를 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="576f7-116">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

8.  <span data-ttu-id="576f7-117">필터링된 이벤트 목록의 **일반** 탭에서 사용자 복제가 성공적으로 완료되었음을 나타내는 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="576f7-117">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

