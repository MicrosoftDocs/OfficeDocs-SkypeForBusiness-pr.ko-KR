---
title: 'Lync Server 2013: 그룹 통화 픽업 번호 범위 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Group Call Pickup number range
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945629(v=OCS.15)
ms:contentKeyID: 51541475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66b95df76c812b50ff9c220ea208406a5ab7cf2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="3323c-102">Lync Server 2013에서 그룹 통화 픽업 번호 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="3323c-102">Delete a Group Call Pickup number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3323c-103">_**마지막으로 수정한 주제:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="3323c-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="3323c-104">그룹 통화 픽업 번호 범위를 삭제 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3323c-104">Use the following procedure to delete a Group Call Pickup number range.</span></span>

<div>

## <a name="to-delete-a-call-pickup-group-number-range"></a><span data-ttu-id="3323c-105">통화 픽업 그룹 번호 범위를 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="3323c-105">To delete a call pickup group number range</span></span>

1.  <span data-ttu-id="3323c-106">Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="3323c-106">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3323c-107">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3323c-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3323c-108">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3323c-108">At the command line, type:</span></span>
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    <span data-ttu-id="3323c-109">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3323c-109">For example:</span></span>
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3323c-110">추가 옵션에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">제거-CsCallParkOrbit</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3323c-110">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3323c-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3323c-111">See Also</span></span>


[<span data-ttu-id="3323c-112">Lync Server 2013에서 통화 공원 궤도 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="3323c-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[<span data-ttu-id="3323c-113">제거-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="3323c-113">Remove-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[<span data-ttu-id="3323c-114">Get-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="3323c-114">Get-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

