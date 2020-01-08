---
title: 'Lync Server 2013: 사용자에 게 그룹 통화 픽업 번호 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e919b1fb4ee225eba1c5317ff1f3049791075bcc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a><span data-ttu-id="a7b8c-102">Lync Server 2013에서 사용자에 게 그룹 통화 픽업 번호 할당</span><span class="sxs-lookup"><span data-stu-id="a7b8c-102">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7b8c-103">_**마지막으로 수정한 주제:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="a7b8c-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="a7b8c-104">통화 공원 표에 그룹 통화 픽업 그룹 번호를 추가한 후에는 그룹을 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7b8c-104">After you add Group Call Pickup group numbers to the call park orbit table, you can assign the groups to users.</span></span> <span data-ttu-id="a7b8c-105">SEFAUtil (보조 확장 기능 활성화) 리소스 키트 도구를 사용 하 여 사용자에 게 통화 픽업 그룹을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7b8c-105">Use the secondary extension feature activation (SEFAUtil ) resource kit tool to assign call pickup groups to users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a7b8c-106">하이브리드 배포의 경우 그룹 통화 픽업 그룹을 온라인 상태인 사용자에 게 할당 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a7b8c-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="a7b8c-107">홈 인터넷에 연결 된 사용자는 그룹 통화 픽업에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7b8c-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="a7b8c-108">즉, 다른 사용자가 해당 통화에 대 한 응답을 받을 수 없으며 다른 사용자에 게 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7b8c-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a><span data-ttu-id="a7b8c-109">그룹 통화 픽업 그룹을 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="a7b8c-109">To assign a Group Call Pickup group to a user</span></span>

1.  <span data-ttu-id="a7b8c-110">관리자 권한으로 SEFAUtil 도구를 설치한 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7b8c-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="a7b8c-111">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7b8c-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="a7b8c-112">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a7b8c-112">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a7b8c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7b8c-113">See Also</span></span>


[<span data-ttu-id="a7b8c-114">Lync Server 2013에서 사용자의 그룹 통화 픽업 사용 설정</span><span class="sxs-lookup"><span data-stu-id="a7b8c-114">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
[<span data-ttu-id="a7b8c-115">Lync Server 2013에서 사용자에 대 한 그룹 통화 픽업 기능을 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="a7b8c-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

