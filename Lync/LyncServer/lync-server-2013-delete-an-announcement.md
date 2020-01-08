---
title: 'Lync Server 2013: 공지 사항 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an announcement
ms:assetid: 26ea7149-4470-4c22-9bab-8a4065aca44e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687998(v=OCS.15)
ms:contentKeyID: 49733588
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bb942c57394e2141ad4c550ecaf33ae2ef128fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-announcement-in-lync-server-2013"></a>Lync Server 2013에서 공지 사항 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

다음 절차를 사용 하 여 할당 되지 않은 번호로 전화를 거는 데 사용 되는 알림을 삭제 합니다.

<div>

## <a name="to-delete-an-announcement"></a>공지 사항을 삭제 하려면

1.  Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  조직의 모든 공지 사항을 나열 합니다. 명령줄에서 다음을 실행 합니다.
    
        Get-CsAnnouncement

4.  결과 목록에서 삭제 하려는 공지 사항을 찾아 GUID를 복사 합니다. 그런 다음 명령줄에서 다음을 실행 합니다.
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    예를 들면 다음과 같습니다.
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    <div>
    

    > [!NOTE]  
    > 추가 옵션에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">Csannouncement 가져오기</A> 및 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">-csannouncement 제거</A>를 참조 하세요.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 알림 만들기](lync-server-2013-create-an-announcement.md)  


[CsAnnouncement 제거](https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement)  
[다운로드-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

