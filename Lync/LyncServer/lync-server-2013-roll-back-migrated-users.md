---
title: 'Lync Server 2013: 마이그레이션된 사용자 롤백'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbc2c46b462ec50c1f5796a9a6a03cd39f7b44dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a><span data-ttu-id="bd095-102">Lync Server 2013에서 마이그레이션된 사용자 롤백</span><span class="sxs-lookup"><span data-stu-id="bd095-102">Roll back migrated users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd095-103">_**마지막으로 수정 된 항목:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="bd095-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="bd095-104">통합 연락처 저장소 기능을 롤백해야 하는 경우 사용자를 다시 Exchange 2010 또는 Lync Server 2010로 이동 하는 경우에만 연락처를 롤백합니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-104">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="bd095-105">롤백하려면 사용자에 대 한 정책을 사용 하지 않도록 설정한 다음 **invoke-csucsrollback** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-105">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="bd095-106">정책이 사용 하지 않도록 설정 되어 있지 않은 경우 통합 된 연락처 저장소 마이그레이션은 다시 시작 되므로, **invoke-csucsrollback** 단독으로 실행 하는 것 만으로는 영구 롤백을 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-106">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="bd095-107">예를 들어 Exchange 2013이 exchange 2010로 롤백 되 고 사용자의 사서함이 Exchange 2013로 이동 된 경우 통합 연락처 저장소 마이그레이션은 통합 연락처 저장소 보다 7 일 후에 다시 시작 됩니다. 은 사용자 서비스 정책에서 해당 사용자에 대해 계속 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-107">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user’s mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bd095-108">다음 경우에는 <STRONG>csuser</STRONG> p s i c s i c s i c e r t s e r t 사용자의 연락처 저장소가 Exchange 2013에서 Lync Server 2013로 자동 롤백됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-108">The <STRONG>Move-CsUser</STRONG> cmdlet automatically rolls back the user's contact store from Exchange 2013 to Lync Server 2013 in the following situations:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="bd095-109">사용자가 Lync Server 2013에서 Lync Server 2010로 이동 하는 경우</span><span class="sxs-lookup"><span data-stu-id="bd095-109">When users are moved from Lync Server 2013 to Lync Server 2010.</span></span></P>
> <LI>
> <P><span data-ttu-id="bd095-110">사용자가 Lync Online에서 Lync Server 2013 온-프레미스로 이동 하는 경우와 같이 사용자가 크로스 프레미스로 마이그레이션될 때 또는 그 반대의 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-110">When users are migrated cross premises, such as when a user is moved from Lync Online to Lync Server 2013 on-premises, or vice versa.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bd095-p102">백업 데이터베이스에서 통합 연락처 저장소 데이터를 가져올 경우 통합 연락처 저장소 모드가 내보내기와 가져오기 간에 변경되면 통합 연락처 저장소 데이터 및 사용자 데이터가 손상될 수 있습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-p102">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="bd095-113">사용자의 대화 상대가 Exchange 2013로 마이그레이션될 때까지 연락처 목록을 내보낸 다음, 마이그레이션 후 같은 데이터를 가져오면 통합 연락처 저장소 데이터 및 연락처 목록이 손상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-113">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span></P>
> <LI>
> <P><span data-ttu-id="bd095-114">사용자를 Exchange 2013로 마이그레이션하고 마이그레이션 후 마이그레이션을 롤백하는 경우, 마이그레이션 후 데이터를 가져오는 몇 가지 이유로 인해 통합 연락처 저장소 데이터 및 연락처 목록이 손상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-114">If you export userdata after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bd095-115">Exchange 사서함을 Exchange 2013에서 Exchange 2010로 이동 하기 전에 먼저 Exchange 관리자가 lync server 사용자 연락처를 Exchange 2013에서 Lync Server로 롤백 했는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-115">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Lync Server administrator has first rolled back the Lync Server user contacts from Exchange 2013 to Lync Server.</span></span> <span data-ttu-id="bd095-116">통합 연락처 저장소 연락처를 Lync Server로 롤백하려면이 섹션의 뒷부분에 나오는 "Exchange 2013에서 통합 연락처 저장소를 Lync Server 2013로 롤백하는 방법" 절차를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bd095-116">To roll back unified contact store contacts to Lync Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013," later in this section.</span></span>



</div>

<span data-ttu-id="bd095-117">다음 절차에서는 사용자 연락처를 롤백하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-117">The following procedure describes how to roll back user contacts.</span></span> <span data-ttu-id="bd095-118">온 **-CsUser** cmdlet을 사용 하 여 lync server 2013와 lync server 2010 간에 사용자를 이동 하는 경우, 사용자 이동 **-csuser** cmdlet은 Lync Server 2013에서 lync server 2010로 이동할 때 공동 작업 연락처 저장소가 자동으로 롤백하여 이러한 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-118">If you use the **Move-CsUser** cmdlet to move users between Lync Server 2013 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unifed contact store when it moves users from Lync Server 2013 to Lync Server 2010.</span></span> <span data-ttu-id="bd095-119">**이동-CsUser** 는 통합 연락처 저장소 정책을 사용 하지 않도록 설정 하지 않으므로 사용자가 다시 Lync Server 2013로 이동 하는 경우 통합 연락처 저장소로의 마이그레이션이 반복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-119">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Lync Server 2013.</span></span>

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a><span data-ttu-id="bd095-120">Lync Server 2013에서 Lync Server 2010로 사용자 연락처를 롤백하려면</span><span class="sxs-lookup"><span data-stu-id="bd095-120">To roll back user contacts from Lync Server 2013 to Lync Server 2010</span></span>

1.  <span data-ttu-id="bd095-121">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bd095-p105">사용자가 롤백 후 다시 마이그레이션되지 않도록, 롤백할 사용자의 통합 연락처 저장소를 사용하지 않도록 설정합니다. 이후에 사용자가 다시 마이그레이션되지 않도록 하려는 경우에만 이 단계를 수행합니다. 개별 사용자의 통합 연락처 저장소를 사용하지 않도록 설정하려면 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-p105">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback. (Perform this step only if you want to make sure that users will not remigrate in the future.) To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="bd095-124">예:</span><span class="sxs-lookup"><span data-stu-id="bd095-124">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="bd095-125">Lync server 2013에서 Lync Server 2010로 사용자를 이동 하기 전에 Lync Server에서 지정 된 사용자에 대 한 버디 목록을 롤백합니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-125">Before moving a user from Lync Server 2013 to Lync Server 2010, roll back the Buddy List for the specified users on Lync Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bd095-126">이 단계를 생략할 경우 대화 상대 목록이 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-126">If this step is omitted, the Buddy List will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="bd095-p106">명령줄에 다음을 입력하여 지정된 사용자를 롤백합니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-p106">Roll back the specified users. At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="bd095-129">예:</span><span class="sxs-lookup"><span data-stu-id="bd095-129">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bd095-p107">-Force 옵션을 사용하여 강제로 롤백하는 것은 좋지 않습니다. 이 옵션을 사용할 경우 사용자의 대화 상대가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-p107">We do not recommend using the –Force option to force the rollback. If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a><span data-ttu-id="bd095-132">Exchange 2013에서 Lync Server 2013로 통합 연락처 저장소 연락처를 롤백하려면</span><span class="sxs-lookup"><span data-stu-id="bd095-132">To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013</span></span>

1.  <span data-ttu-id="bd095-133">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bd095-p108">사용자가 롤백 후 다시 마이그레이션되지 않도록, 롤백할 사용자의 통합 연락처 저장소를 사용하지 않도록 설정합니다. 개별 사용자의 통합 연락처 저장소를 사용하지 않도록 설정하려면 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-p108">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback. To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="bd095-136">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-136">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="bd095-p109">명령줄에 다음을 입력하여 지정된 사용자를 롤백합니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-p109">Roll back the specified users. At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="bd095-139">예:</span><span class="sxs-lookup"><span data-stu-id="bd095-139">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bd095-140">먼저 Lync Server 사용자를 롤백하여 Exchange 2013 사서함을 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-140">You must first roll back the Lync Server user, and then move the Exchange 2013 mailbox.</span></span> <span data-ttu-id="bd095-141">Lync Server 롤백이 완료 될 때까지 Exchange 관리자는 Exchange를 롤백할 수 없도록 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-141">The Exchange administrator is blocked from rolling back Exchange until the Lync Server rollback is complete.</span></span> <span data-ttu-id="bd095-142">-Force 옵션을 사용하여 강제로 롤백하는 것은 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-142">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="bd095-143">이 옵션을 사용할 경우 사용자의 대화 상대가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-143">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="bd095-144">사용자를 Lync Server로 롤백하 고 나면 exchange 관리자가 exchange 사용자에서 exchange 2013 2010로 exchange를 롤백할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd095-144">After you roll back the user to Lync Server, the Exchange administrator can roll back the Exchange user from Exchange 2013 to Exchange 2010.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

