---
title: 'Lync Server 2013: 공지 사항 삭제'
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
ms.openlocfilehash: 91a15057e4785a16e7fc632422573ee02d1d920b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-announcement-in-lync-server-2013"></a><span data-ttu-id="226ce-102">Lync Server 2013에서 공지 사항 삭제</span><span class="sxs-lookup"><span data-stu-id="226ce-102">Delete an announcement in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="226ce-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="226ce-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="226ce-104">다음 절차를 사용 하 여 할당 되지 않은 번호로 전화를 거는 데 사용 되는 알림을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="226ce-104">Use the following procedure to delete an announcement that is used for calls to unassigned numbers.</span></span>

<div>

## <a name="to-delete-an-announcement"></a><span data-ttu-id="226ce-105">공지 사항을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="226ce-105">To delete an announcement</span></span>

1.  <span data-ttu-id="226ce-106">Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="226ce-106">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="226ce-107">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="226ce-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="226ce-108">조직의 모든 공지 사항을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="226ce-108">List all the announcements in your organization.</span></span> <span data-ttu-id="226ce-109">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="226ce-109">At the command line, run:</span></span>
    
        Get-CsAnnouncement

4.  <span data-ttu-id="226ce-110">결과 목록에서 삭제 하려는 공지 사항을 찾아 GUID를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="226ce-110">In the resulting list, locate the announcement you want to delete, and copy the GUID.</span></span> <span data-ttu-id="226ce-111">그런 다음 명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="226ce-111">Then, at the command line, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    <span data-ttu-id="226ce-112">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="226ce-112">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="226ce-113">추가 옵션에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">Csannouncement 가져오기</A> 및 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">-csannouncement 제거</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="226ce-113">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">Get-CsAnnouncement</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="226ce-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="226ce-114">See Also</span></span>


[<span data-ttu-id="226ce-115">Lync Server 2013에서 알림 만들기</span><span class="sxs-lookup"><span data-stu-id="226ce-115">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)  


[<span data-ttu-id="226ce-116">CsAnnouncement 제거</span><span class="sxs-lookup"><span data-stu-id="226ce-116">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement)  
[<span data-ttu-id="226ce-117">다운로드-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="226ce-117">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

