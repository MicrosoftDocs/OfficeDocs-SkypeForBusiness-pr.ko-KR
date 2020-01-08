---
title: 'Lync Server 2013: 사용자 용 그룹 통화 픽업 사용 안 함'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76b7e0d17b91accdab0f1590d9fc505dec42f430
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="cd5fc-102">Lync Server 2013에서 사용자에 대 한 그룹 통화 픽업 기능을 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="cd5fc-102">Disable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd5fc-103">_**마지막으로 수정한 주제:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="cd5fc-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="cd5fc-104">다음 절차를 사용 하 여 사용자에 대 한 그룹 통화 픽업 기능을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5fc-104">Use the following procedure to disable Group Call Pickup for a user.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cd5fc-105">사용자의 그룹 통화 픽업 기능을 사용 하지 않도록 설정 하면 사용자에 게 할당 된 통화 픽업 그룹 번호가 보존 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd5fc-105">When you disable Group Call Pickup for a user, the call pickup group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="cd5fc-106">이후 해당 사용자의 그룹 통화 픽업을 다시 사용 하도록 설정 하려면/enablegrouppickup 매개 변수를 사용 하 여 통화 픽업 그룹 번호를 다시 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5fc-106">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the call pickup group number again with the /enablegrouppickup parameter.</span></span>



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a><span data-ttu-id="cd5fc-107">사용자의 그룹 통화 픽업를 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="cd5fc-107">To disable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="cd5fc-108">관리자 권한으로 SEFAUtil 도구를 설치한 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5fc-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="cd5fc-109">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5fc-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    <span data-ttu-id="cd5fc-110">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cd5fc-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cd5fc-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd5fc-111">See Also</span></span>


[<span data-ttu-id="cd5fc-112">Lync Server 2013에서 사용자에 게 그룹 통화 픽업 번호 할당</span><span class="sxs-lookup"><span data-stu-id="cd5fc-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="cd5fc-113">Lync Server 2013에서 사용자의 그룹 통화 픽업 사용 설정</span><span class="sxs-lookup"><span data-stu-id="cd5fc-113">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

