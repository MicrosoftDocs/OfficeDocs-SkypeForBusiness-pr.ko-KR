---
title: 'Lync Server 2013: 사용자 용 그룹 통화 픽업 사용 안 함'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76b7e0d17b91accdab0f1590d9fc505dec42f430
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a>Lync Server 2013에서 사용자에 대 한 그룹 통화 픽업 기능을 사용 하지 않도록 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-01-30_

다음 절차를 사용 하 여 사용자에 대 한 그룹 통화 픽업 기능을 사용 하지 않도록 설정 합니다.

<div>


> [!NOTE]  
> 사용자의 그룹 통화 픽업 기능을 사용 하지 않도록 설정 하면 사용자에 게 할당 된 통화 픽업 그룹 번호가 보존 되지 않습니다. 이후 해당 사용자의 그룹 통화 픽업을 다시 사용 하도록 설정 하려면/enablegrouppickup 매개 변수를 사용 하 여 통화 픽업 그룹 번호를 다시 지정 해야 합니다.



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a>사용자의 그룹 통화 픽업를 사용 하지 않도록 설정 하려면

1.  관리자 권한으로 SEFAUtil 도구를 설치한 컴퓨터에 로그온 합니다.

2.  명령줄에서 다음을 실행 합니다.
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    예를 들면 다음과 같습니다.
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 사용자에 게 그룹 통화 픽업 번호 할당](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Lync Server 2013에서 사용자의 그룹 통화 픽업 사용 설정](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

