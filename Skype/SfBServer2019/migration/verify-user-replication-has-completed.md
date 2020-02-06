---
title: 사용자 복제가 완료되었는지 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이동-CsUser cmdlet을 실행할 때 AD DS (Active Directory 도메인 서비스)와 비즈니스용 Skype 서버 2019 데이터베이스 간의 사용자 정보가 동기화 되지 않아 오류가 발생할 수 있습니다. 초기 복제가 완료 되지 않았습니다. 비즈니스용 Skype 서버 2019 사용자 복제기 서비스의 초기 동기화가 완료 되는 데 걸리는 시간은 비즈니스용 Skype를 호스트 하는 Active Directory 포리스트에서 호스팅되는 도메인 컨트롤러 수에 따라 달라 집니다. 서버 2019 풀. 비즈니스용 skype Server 2019 사용자 복제기 서비스 초기 동기화 프로세스가 처음으로 비즈니스용 Skype 서버 2019 프런트 엔드 서버를 시작 하면이 문제가 발생 합니다. 이후 동기화는 사용자 복제기 간격을 기준으로 합니다. 다음 단계를 완료 하 여 CsUser cmdlet을 실행 하기 전에 사용자 복제가 완료 되었는지 확인 합니다.
ms.openlocfilehash: 31f4f9f1045367e376d4536df54c32be14580312
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812656"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="03c92-107">사용자 복제가 완료되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="03c92-107">Verify user replication has completed</span></span>

<span data-ttu-id="03c92-108">**이동-csuser** cmdlet을 실행할 때 AD DS (Active Directory 도메인 서비스)와 비즈니스용 Skype 서버 2019 데이터베이스 간의 사용자 정보가 동기화 되지 않은 경우, 초기 복제가 완료 되지 않아 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03c92-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="03c92-109">비즈니스용 Skype 서버 2019 사용자 복제기 서비스의 초기 동기화가 완료 되는 데 걸리는 시간은 비즈니스용 Skype를 호스트 하는 Active Directory 포리스트에서 호스팅되는 도메인 컨트롤러 수에 따라 달라 집니다. 서버 2019 풀.</span><span class="sxs-lookup"><span data-stu-id="03c92-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="03c92-110">비즈니스용 skype Server 2019 사용자 복제기 서비스 초기 동기화 프로세스가 처음으로 비즈니스용 Skype 서버 2019 프런트 엔드 서버를 시작 하면이 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c92-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="03c92-111">그 이후에는 동기화가 사용자 복제기 간격을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c92-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="03c92-112">다음 단계를 완료 하 여 **csuser** cmdlet을 실행 하기 전에 사용자 복제가 완료 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c92-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="03c92-113">사용자 복제가 완료 되었는지 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="03c92-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="03c92-114">도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 토폴로지 작성기가 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c92-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="03c92-115">**시작** 메뉴를 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c92-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="03c92-116">**Eventvwr**을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c92-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="03c92-117">이벤트 뷰어에서 **응용 프로그램 및 서비스 로그** 를 클릭 하 여 확장 한 다음 비즈니스용 Skype 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c92-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="03c92-118">**작업** 창에서 **현재 로그 필터링**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c92-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="03c92-119">**이벤트 원본** 목록에서 **LS 사용자 복제기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c92-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="03c92-120">\*\* \<모든 이벤트 id\>\*\* 에 **30024**를 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03c92-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="03c92-121">필터링 된 이벤트 목록의 **일반** 탭에서 사용자 복제가 성공적으로 완료 되었다는 항목을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="03c92-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

