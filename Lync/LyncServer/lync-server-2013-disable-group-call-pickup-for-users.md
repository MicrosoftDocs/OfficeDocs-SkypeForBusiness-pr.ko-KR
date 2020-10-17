---
title: 'Lync Server 2013: 사용자의 그룹 통화 픽업 사용 안 함'
description: 'Lync Server 2013: 사용자의 그룹 통화 픽업를 사용 하지 않도록 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3f5b4542cf7bb8ea5be524d2695701979ec2987
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568194"
---
# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="1e356-103">Lync Server 2013의 사용자에 대 한 그룹 통화 픽업 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="1e356-103">Disable Group Call Pickup for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e356-104">_**마지막으로 수정 된 항목:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="1e356-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="1e356-105">다음 절차에 따라 사용자에 대 한 그룹 통화 픽업를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-105">Use the following procedure to disable Group Call Pickup for a user.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1e356-106">사용자에 대해 그룹 통화 픽업를 사용 하지 않도록 설정 하면 사용자에 게 할당 된 통화 픽업 그룹 번호가 보존 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-106">When you disable Group Call Pickup for a user, the call pickup group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="1e356-107">이후에 해당 사용자에 대해 그룹 통화 픽업을 다시 사용 하도록 설정 하려면/enablegrouppickup 매개 변수를 사용 하 여 통화 픽업 그룹 번호를 다시 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-107">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the call pickup group number again with the /enablegrouppickup parameter.</span></span>



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a><span data-ttu-id="1e356-108">사용자에 대 한 그룹 통화 픽업를 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1e356-108">To disable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="1e356-109">관리자 권한으로 SEFAUtil 도구를 설치한 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-109">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="1e356-110">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-110">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    <span data-ttu-id="1e356-111">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-111">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1e356-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e356-112">See Also</span></span>


[<span data-ttu-id="1e356-113">Lync Server 2013의 사용자에 게 그룹 통화 픽업 번호 할당</span><span class="sxs-lookup"><span data-stu-id="1e356-113">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="1e356-114">Lync Server 2013의 사용자에 대 한 그룹 통화 픽업 사용 설정</span><span class="sxs-lookup"><span data-stu-id="1e356-114">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

