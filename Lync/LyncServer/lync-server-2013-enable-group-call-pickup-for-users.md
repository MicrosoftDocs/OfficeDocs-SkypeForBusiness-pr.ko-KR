---
title: 'Lync Server 2013: 사용자 용 그룹 통화 픽업 기능 사용'
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
ms.openlocfilehash: 1fc2f513960371d0115b63260d35180f319bd923
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a>Lync Server 2013에서 사용자의 그룹 통화 픽업 사용 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-01-30_

SEFAUtil 리소스 키트 도구를 사용 하 여 사용자 용 그룹 통화 픽업 기능을 사용 하도록 설정 합니다. 그룹 통화 픽업를 사용 하도록 설정 하려면 사용자에 게 통화 공원 궤도 테이블에 GroupPickup 유형의 그룹 번호를 할당 해야 합니다. SEFAUtil를 실행할 때/enablegrouppickup 매개 변수를 사용 하 여 통화 픽업 그룹 번호를 할당 하 고 동시에 그룹 통화 픽업 기능을 사용 하도록 설정 합니다.

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a>사용자에 대 한 그룹 통화 픽업 Pickup 사용

1.  관리자 권한으로 SEFAUtil 도구를 설치한 컴퓨터에 로그온 합니다.

2.  명령줄에서 다음을 실행 합니다.
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    예를 들면 다음과 같습니다.
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 사용자에 게 그룹 통화 픽업 번호 할당](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Lync Server 2013에서 사용자에 대 한 그룹 통화 픽업 기능을 사용 하지 않도록 설정](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

