---
title: 'Lync Server 2013: 사용자에 게 그룹 통화 픽업 번호 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b437b9da1abaa62d34a177c0188396c30bf7a3e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a><span data-ttu-id="381e6-102">Lync Server 2013의 사용자에 게 그룹 통화 픽업 번호 할당</span><span class="sxs-lookup"><span data-stu-id="381e6-102">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="381e6-103">_**마지막으로 수정 된 항목:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="381e6-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="381e6-104">통화 대기 번호 표에 그룹 통화 픽업 그룹 번호를 추가한 후에는 사용자에 게 그룹을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381e6-104">After you add Group Call Pickup group numbers to the call park orbit table, you can assign the groups to users.</span></span> <span data-ttu-id="381e6-105">SEFAUtil (보조 확장 기능 활성화) 리소스 키트 도구를 사용 하 여 사용자에 게 통화 픽업 그룹을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="381e6-105">Use the secondary extension feature activation (SEFAUtil ) resource kit tool to assign call pickup groups to users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="381e6-106">하이브리드 배포에서는 온라인 상태인 사용자에 게 그룹 통화 픽업 그룹을 할당 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="381e6-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="381e6-107">홈 온라인 상태인 사용자는 그룹 통화 픽업에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="381e6-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="381e6-108">즉, 다른 사용자가 해당 통화에 응답할 수 없으며 다른 사용자에 게 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="381e6-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a><span data-ttu-id="381e6-109">그룹 통화 픽업 그룹을 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="381e6-109">To assign a Group Call Pickup group to a user</span></span>

1.  <span data-ttu-id="381e6-110">관리자 권한으로 SEFAUtil 도구를 설치한 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="381e6-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="381e6-111">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="381e6-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="381e6-112">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="381e6-112">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="381e6-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="381e6-113">See Also</span></span>


[<span data-ttu-id="381e6-114">Lync Server 2013의 사용자에 대 한 그룹 통화 픽업 사용 설정</span><span class="sxs-lookup"><span data-stu-id="381e6-114">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
[<span data-ttu-id="381e6-115">Lync Server 2013의 사용자에 대 한 그룹 통화 픽업 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="381e6-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

