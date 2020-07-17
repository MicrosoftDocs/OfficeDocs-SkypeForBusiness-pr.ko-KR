---
title: 사용자 복제가 완료되었는지 확인
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Cslicuser cmdlet을 실행 하는 경우 초기 복제가 완료 되지 않아 AD DS (Active Directory 도메인 서비스)와 비즈니스용 Skype 서버 2019 데이터베이스 간의 사용자 정보가 동기화 되지 않아 오류가 발생할 수 있습니다. 비즈니스용 Skype 서버 2019 사용자 복제기 service의 초기 동기화를 성공적으로 완료 하는 데 걸리는 시간은 비즈니스용 Skype 서버 2019 풀을 호스트 하는 Active Directory 포리스트에서 호스트 되는 도메인 컨트롤러의 수에 따라 달라 집니다. 비즈니스용 skype 서버 2019 사용자 복제기 service 초기 동기화 프로세스는 비즈니스용 Skype 서버 2019 프런트 엔드 서버를 처음으로 시작할 때 발생 합니다. 그런 후에는 사용자 복제기 간격을 기반으로 동기화 됩니다. 다음 단계를 완료 하 여 CsUser cmdlet을 실행 하기 전에 사용자 복제가 완료 되었는지 확인 합니다.
ms.openlocfilehash: 5aa832216cc5eddce1d80cc9401ec9992c9edbf1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751650"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="57e57-107">사용자 복제가 완료되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="57e57-107">Verify user replication has completed</span></span>

<span data-ttu-id="57e57-108">**Cslicuser** cmdlet을 실행 하는 경우 초기 복제가 완료 되지 않아 AD DS (Active Directory 도메인 서비스)와 비즈니스용 Skype 서버 2019 데이터베이스 간의 사용자 정보가 동기화 되지 않은 경우 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57e57-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="57e57-109">비즈니스용 Skype 서버 2019 사용자 복제기 service의 초기 동기화를 성공적으로 완료 하는 데 걸리는 시간은 비즈니스용 Skype 서버 2019 풀을 호스트 하는 Active Directory 포리스트에서 호스트 되는 도메인 컨트롤러의 수에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="57e57-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="57e57-110">비즈니스용 skype 서버 2019 사용자 복제기 service 초기 동기화 프로세스는 비즈니스용 Skype 서버 2019 프런트 엔드 서버를 처음으로 시작할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e57-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="57e57-111">그 후에는 동기화가 사용자 복제기 간격을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e57-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="57e57-112">다음 단계를 완료 하 여 **csuser** cmdlet을 실행 하기 전에 사용자 복제가 완료 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e57-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="57e57-113">사용자 복제가 완료되었는지 확인하려면</span><span class="sxs-lookup"><span data-stu-id="57e57-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="57e57-114">토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="57e57-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="57e57-115">**시작** 메뉴를 클릭한 후 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57e57-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="57e57-116">**eventvwr.exe**를 입력한 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57e57-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="57e57-117">이벤트 뷰어에서 **응용 프로그램 및 서비스 로그** 를 클릭 하 여 확장 한 다음 비즈니스용 Skype 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e57-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="57e57-118">**동작** 창에서 **현재 로그 필터링**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57e57-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="57e57-119">**이벤트 원본** 목록에서 **LS User Replicator**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57e57-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="57e57-120">에 **\<All Event IDs\>** **30024**를 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57e57-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="57e57-121">필터링 된 이벤트 목록의 **일반** 탭에서 사용자 복제가 성공적으로 완료 되었음을 나타내는 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="57e57-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

