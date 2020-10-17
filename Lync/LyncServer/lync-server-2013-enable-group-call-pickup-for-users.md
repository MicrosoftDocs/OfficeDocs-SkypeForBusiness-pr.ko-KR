---
title: 'Lync Server 2013: 사용자에 대해 그룹 통화 픽업 사용 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89d512eea147039a5766193f9ec2a20cf45caaa0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528725"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="4485b-102">Lync Server 2013의 사용자에 대 한 그룹 통화 픽업 사용 설정</span><span class="sxs-lookup"><span data-stu-id="4485b-102">Enable Group Call Pickup for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4485b-103">_**마지막으로 수정 된 항목:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="4485b-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="4485b-104">SEFAUtil resource kit 도구를 사용 하 여 사용자에 대 한 그룹 통화 픽업을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4485b-104">Use the SEFAUtil resource kit tool to enable Group Call Pickup for users.</span></span> <span data-ttu-id="4485b-105">그룹 통화 픽업를 사용 하도록 설정 하려면 사용자에 게 통화 대기 궤도 테이블에서 GroupPickup 유형의 그룹 번호를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4485b-105">Users must be assigned a group number with type GroupPickup in the call park orbit table to have Group Call Pickup enabled.</span></span> <span data-ttu-id="4485b-106">SEFAUtil.exe 실행할 때/enablegrouppickup 매개 변수를 사용 하 여 통화 픽업 그룹 번호를 할당 하 고 동시에 그룹 통화 픽업 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4485b-106">You assign a call pickup group number and enable Group Call Pickup at the same time by using the /enablegrouppickup parameter when you run SEFAUtil.exe.</span></span>

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="4485b-107">사용자에 대 한 그룹 통화 픽업을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="4485b-107">To enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="4485b-108">관리자 권한으로 SEFAUtil 도구를 설치한 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="4485b-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="4485b-109">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4485b-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="4485b-110">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4485b-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4485b-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4485b-111">See Also</span></span>


[<span data-ttu-id="4485b-112">Lync Server 2013의 사용자에 게 그룹 통화 픽업 번호 할당</span><span class="sxs-lookup"><span data-stu-id="4485b-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="4485b-113">Lync Server 2013의 사용자에 대 한 그룹 통화 픽업 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="4485b-113">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

