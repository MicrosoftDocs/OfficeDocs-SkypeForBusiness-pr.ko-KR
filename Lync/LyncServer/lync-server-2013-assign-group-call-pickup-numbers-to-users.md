---
title: 'Lync Server 2013: 사용자에 게 그룹 통화 픽업 번호 할당'
description: 'Lync Server 2013: 사용자에 게 그룹 통화 픽업 번호를 할당 합니다.'
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
ms.openlocfilehash: d550b4556af427e11e99ffb26fb2a6c34d019490
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566134"
---
# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a>Lync Server 2013의 사용자에 게 그룹 통화 픽업 번호 할당

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-01-30_

통화 대기 번호 표에 그룹 통화 픽업 그룹 번호를 추가한 후에는 사용자에 게 그룹을 할당할 수 있습니다. SEFAUtil (보조 확장 기능 활성화) 리소스 키트 도구를 사용 하 여 사용자에 게 통화 픽업 그룹을 할당 합니다.

<div>


> [!NOTE]  
> 하이브리드 배포에서는 온라인 상태인 사용자에 게 그룹 통화 픽업 그룹을 할당 하지 마십시오. 홈 온라인 상태인 사용자는 그룹 통화 픽업에 참가할 수 없습니다. 즉, 다른 사용자가 해당 통화에 응답할 수 없으며 다른 사용자에 게 전화를 걸 수 있습니다.



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a>그룹 통화 픽업 그룹을 사용자에 게 할당 하려면

1.  관리자 권한으로 SEFAUtil 도구를 설치한 컴퓨터에 로그온 합니다.

2.  명령줄에서 다음을 실행합니다.
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    예를 들면 다음과 같습니다.
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 사용자에 대 한 그룹 통화 픽업 사용 설정](lync-server-2013-enable-group-call-pickup-for-users.md)  
[Lync Server 2013의 사용자에 대 한 그룹 통화 픽업 사용 안 함](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

