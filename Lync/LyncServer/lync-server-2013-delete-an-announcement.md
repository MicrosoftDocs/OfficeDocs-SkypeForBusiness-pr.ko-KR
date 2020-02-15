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
ms.openlocfilehash: 0a7c21a6b44d31514cc9addc800b2ae0812a5ad3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-announcement-in-lync-server-2013"></a>Lync Server 2013에서 알림 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

다음 절차에 따라 지정 되지 않은 번호에 대 한 통화에 사용 되는 알림을 삭제 합니다.

<div>

## <a name="to-delete-an-announcement"></a>알림을 삭제 하려면

1.  Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  조직의 모든 알림을 나열 합니다. 명령줄에서 다음을 실행합니다.
    
        Get-CsAnnouncement

4.  결과 목록에서 삭제 하려는 알림을 찾은 다음 GUID를 복사 합니다. 그런 다음 명령줄에서 다음을 실행 합니다.
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    예:
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    <div>
    

    > [!NOTE]  
    > 더 많은 옵션에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">csannouncement</A> 및 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-csannouncement</A>를 참조 하십시오.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 알림 만들기](lync-server-2013-create-an-announcement.md)  


[CsAnnouncement-사후 알림](https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement)  
[Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

