---
title: 'Lync Server 2013: 사용자 용 그룹 통화 픽업 기능을 사용 하도록 설정 하 고 그룹 번호 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9523a76eb9cd23dd4c8ee531520341aaf82f508
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a><span data-ttu-id="1410a-102">Lync Server 2013에서 사용자의 그룹 통화 픽업 기능을 사용 하도록 설정 하 고 그룹 번호 지정</span><span class="sxs-lookup"><span data-stu-id="1410a-102">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1410a-103">_**마지막으로 수정한 주제:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="1410a-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="1410a-104">통화 번호 궤도 테이블에 통화 픽업 그룹 번호를 추가한 후에는 그룹 번호를 사용자에 게 할당 하 고 그룹 통화 픽업 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1410a-104">After you add call pickup group numbers to the call park orbit table, you assign the group numbers to users and enable Group Call Pickup for them.</span></span> <span data-ttu-id="1410a-105">보조 확장 기능 활성화 (SEFAUtil) 리소스 키트 도구를 사용 하 여 그룹 번호를 할당 하 고 그룹 통화 픽업 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1410a-105">Use the secondary extension feature activation (SEFAUtil) resource kit tool to assign group numbers and enable Group Call Pickup.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1410a-106">하이브리드 배포의 경우 그룹 통화 픽업 그룹을 온라인 상태인 사용자에 게 할당 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="1410a-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="1410a-107">홈 인터넷에 연결 된 사용자는 그룹 통화 픽업에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1410a-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="1410a-108">즉, 다른 사용자가 해당 통화에 대 한 응답을 받을 수 없으며 다른 사용자에 게 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1410a-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="1410a-109">그룹 번호를 할당 하 고 사용자에 대 한 그룹 통화 픽업 기능을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1410a-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="1410a-110">관리자 권한으로 SEFAUtil 도구를 설치한 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="1410a-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="1410a-111">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1410a-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="1410a-112">예를 들어 사용자에 게 그룹 번호 199를 할당 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1410a-112">For example, to assign group number 199 to a user:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1410a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1410a-113">See Also</span></span>


[<span data-ttu-id="1410a-114">Lync Server 2013에서 사용자에 대 한 그룹 통화 픽업 기능을 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="1410a-114">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

