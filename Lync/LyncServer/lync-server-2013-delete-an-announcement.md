---
title: 'Lync Server 2013: 알림 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an announcement
ms:assetid: 26ea7149-4470-4c22-9bab-8a4065aca44e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687998(v=OCS.15)
ms:contentKeyID: 49733588
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95f425a461d628ccf7da6021c20b578f639fe605
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516195"
---
# <a name="delete-an-announcement-in-lync-server-2013"></a><span data-ttu-id="3cc64-102">Lync Server 2013에서 알림 삭제</span><span class="sxs-lookup"><span data-stu-id="3cc64-102">Delete an announcement in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cc64-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3cc64-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3cc64-104">다음 절차에 따라 지정 되지 않은 번호에 대 한 통화에 사용 되는 알림을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cc64-104">Use the following procedure to delete an announcement that is used for calls to unassigned numbers.</span></span>

<div>

## <a name="to-delete-an-announcement"></a><span data-ttu-id="3cc64-105">알림을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="3cc64-105">To delete an announcement</span></span>

1.  <span data-ttu-id="3cc64-106">Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cc64-106">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3cc64-107">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3cc64-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3cc64-108">조직의 모든 알림을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cc64-108">List all the announcements in your organization.</span></span> <span data-ttu-id="3cc64-109">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3cc64-109">At the command line, run:</span></span>
    
        Get-CsAnnouncement

4.  <span data-ttu-id="3cc64-110">결과 목록에서 삭제 하려는 알림을 찾은 다음 GUID를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cc64-110">In the resulting list, locate the announcement you want to delete, and copy the GUID.</span></span> <span data-ttu-id="3cc64-111">그런 다음 명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cc64-111">Then, at the command line, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    <span data-ttu-id="3cc64-112">예제:</span><span class="sxs-lookup"><span data-stu-id="3cc64-112">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3cc64-113">더 많은 옵션에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">csannouncement</A> 및 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-csannouncement</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3cc64-113">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">Get-CsAnnouncement</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3cc64-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3cc64-114">See Also</span></span>


[<span data-ttu-id="3cc64-115">Lync Server 2013에서 알림 만들기</span><span class="sxs-lookup"><span data-stu-id="3cc64-115">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)  


[<span data-ttu-id="3cc64-116">CsAnnouncement-사후 알림</span><span class="sxs-lookup"><span data-stu-id="3cc64-116">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement)  
[<span data-ttu-id="3cc64-117">Get-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="3cc64-117">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

