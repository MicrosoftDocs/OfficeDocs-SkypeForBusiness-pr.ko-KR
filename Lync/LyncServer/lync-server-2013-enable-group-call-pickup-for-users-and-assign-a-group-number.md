---
title: 'Lync Server 2013: 사용자에 대 한 그룹 통화 픽업 사용 및 그룹 번호 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edba55fcfdedc04eb2d8a8356c3d295c381d7c70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528745"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a>Lync Server 2013의 사용자에 대 한 그룹 통화 픽업 사용 설정 및 그룹 번호 할당

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-01-30_

통화 대기 번호 표에 통화 픽업 그룹 번호를 추가한 후에는 그룹 번호를 사용자에 게 할당 하 고 그룹 통화 픽업을 사용 하도록 설정 합니다. SEFAUtil (보조 확장 기능 활성화) 리소스 키트 도구를 사용 하 여 그룹 번호를 할당 하 고 그룹 통화 픽업 기능을 사용 하도록 설정 합니다.

<div>


> [!NOTE]  
> 하이브리드 배포에서는 온라인 상태인 사용자에 게 그룹 통화 픽업 그룹을 할당 하지 마십시오. 홈 온라인 상태인 사용자는 그룹 통화 픽업에 참가할 수 없습니다. 즉, 다른 사용자가 해당 통화에 응답할 수 없으며 다른 사용자에 게 전화를 걸 수 있습니다.



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>그룹 번호를 할당 하 고 사용자에 대 한 그룹 통화 픽업 기능을 사용 하도록 설정 하려면

1.  관리자 권한으로 SEFAUtil 도구를 설치한 컴퓨터에 로그온 합니다.

2.  명령줄에서 다음을 실행합니다.
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    예를 들어 사용자에 게 그룹 번호 199을 할당 하려면 다음을 수행 합니다.
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 사용자에 대 한 그룹 통화 픽업 사용 안 함](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

