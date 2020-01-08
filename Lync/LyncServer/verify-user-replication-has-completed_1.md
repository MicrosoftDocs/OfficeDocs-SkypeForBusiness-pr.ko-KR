---
title: 사용자 복제가 완료되었는지 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13f4fbd2e0d0236f9dc404ffa84ab2f0ce385e2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="06b8a-102">사용자 복제가 완료되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="06b8a-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06b8a-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="06b8a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="06b8a-104">**CsLegacyUser** cmdlet을 실행 하는 경우에는 AD DS (Active Directory 도메인 서비스) 간 사용자 정보로 인해 오류가 발생 하 고 초기 복제가 완료 되지 않아 Lync Server 2013 데이터베이스가 동기화 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b8a-104">When running the **Move-CsLegacyUser** cmdlet, you may experience a failure due to user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases being out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="06b8a-105">Lync Server를 성공적으로 완료 하는 데 걸리는 시간 2013 사용자 복제기 서비스의 초기 동기화는 Lync Server 2013 풀을 호스팅하는 Active Directory 포리스트에서 호스팅되는 도메인 컨트롤러 수에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="06b8a-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="06b8a-106">Lync server 2013 사용자 복제기 서비스 초기 동기화 프로세스는 Lync Server 2013 프런트 엔드 서버가 처음으로 시작 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b8a-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="06b8a-107">이후 동기화는 사용자 복제기 간격을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b8a-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="06b8a-108">**CsLegacyUser** cmdlet을 실행 하기 전에 사용자 복제가 완료 되었는지 확인 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b8a-108">Complete the following steps to verify user replication has completed before running the **Move-CsLegacyUser** cmdlet.</span></span>

<div>

## <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="06b8a-109">사용자 복제가 완료 되었는지 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="06b8a-109">To verify that user replication has completed</span></span>

1.  <span data-ttu-id="06b8a-110">Lync Server 2013 프런트 엔드 서버에서 **시작** 메뉴를 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b8a-110">From the Lync Server 2013 Front End server, click the **Start** menu, and then click **Run**.</span></span>

2.  <span data-ttu-id="06b8a-111">**Eventvwr** 을 입력 한 다음 **확인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b8a-111">Enter **eventvwr.exe** and then click **OK**.</span></span>

3.  <span data-ttu-id="06b8a-112">이벤트 뷰어에서 **응용 프로그램 및 서비스 로그** 를 클릭 하 여 확장 한 다음 Lync Server를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b8a-112">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

4.  <span data-ttu-id="06b8a-113">**작업** 창에서 **현재 로그 필터링**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b8a-113">In the **Actions** pane click **Filter Current Log**.</span></span>

5.  <span data-ttu-id="06b8a-114">**이벤트 원본** 목록에서 **LS 사용자 복제기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b8a-114">From the **Event sources** list, click **LS User Replicator**.</span></span>

6.  <span data-ttu-id="06b8a-115">\*\* \<모든 이벤트 id\> \*\* 에서 **30024** 을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b8a-115">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

7.  <span data-ttu-id="06b8a-116">필터링 된 이벤트 목록의 **일반** 탭에서 사용자 복제가 성공적으로 완료 되었음을 나타내는 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="06b8a-116">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

