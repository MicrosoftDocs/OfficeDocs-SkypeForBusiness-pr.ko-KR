---
title: 'Lync Server 2013: 사용자가 Enterprise Voice를 사용 하지 않도록 설정'
description: 'Lync Server 2013: 사용자가 Enterprise Voice를 사용할 수 없도록 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d99916444e2b1c984e251f6e6289d88e31a538a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568214"
---
# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013에서 Enterprise Voice에 대 한 사용자 사용 안 함

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

다음 절차에 따라 Lync Server 2013에 대해 사용 하도록 설정 된 사용자 계정에 대해 Enterprise Voice를 사용 하지 않도록 설정 합니다.

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a>Enterprise Voice에 대 한 사용자 계정을 사용 하지 않도록 설정 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭합니다.

4.  **사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기**를 클릭합니다.

5.  테이블에서 Enterprise Voice를 사용 하도록 설정 하려는 사용자 계정을 클릭 합니다.

6.  **편집** 메뉴에서 **세부 정보 표시**를 클릭합니다.

7.  **Lync Server 사용자 편집** 페이지의 **전화 통신** 아래에서 **Enterprise Voice**를 제외한 아무 옵션이나 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 사용자가 Lync를 사용 하 여 오디오 또는 비디오 통화를 수행 하지 못하도록 제한 하려면 <STRONG>전화 통신</STRONG>아래에서 <STRONG>오디오/비디오 사용 안 함을</STRONG>클릭 합니다.

    
    </div>

8.  **커밋**을 클릭합니다.

이제 사용자가 Enterprise Voice 기능을 사용할 수 없습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 Enterprise Voice를 사용할 수 있도록 사용자 설정](lync-server-2013-enable-users-for-enterprise-voice.md)  


[Lync Server 2013의 사용자에 대 한 Enterprise Voice 관리](lync-server-2013-managing-enterprise-voice-for-users.md)  
[Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

