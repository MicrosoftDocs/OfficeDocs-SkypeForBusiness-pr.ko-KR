---
title: 'Lync Server 2013: 위치 정책 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d046b344c294475dffcc0a10ee8972475f7e903
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525465"
---
# <a name="deleting-a-location-policy-in-lync-server-2013"></a>Lync Server 2013에서 위치 정책 삭제

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-10_

Lync Server 2013에서는 위치 정책을 사용 하 여 E9-1-1 (고급 9-1-1) 기능 및 사용자 또는 연락처의 위치 설정과 관련 된 설정을 적용할 수 있습니다. 위치 정책은 사용자가 E9-1-1을 사용하도록 설정되어 있는지 여부를 확인하고, 설정된 경우 긴급 통화에 대한 동작을 결정합니다. 예를 들어 위치 정책을 사용하여 긴급 통화 번호(예: 한국의 경우 119), 회사 보안 부서에 자동으로 알림을 제공할지 여부 및 통화를 라우팅할 방법을 정의할 수 있습니다.

Lync Server 2013 제어판의 **네트워크 구성** 그룹에서 위치 정책을 구성할 수 있습니다. Lync Server 제어판에서 위치 정책을 보거나 만들거나 수정 하거나 삭제할 수 있습니다. 위치 정책을 삭제하려면 다음 절차를 따릅니다. 위치 정책을 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 위치 정책 만들기 또는 수정을](lync-server-2013-creating-or-modifying-a-location-policy.md)참조 하십시오.

<div>

## <a name="to-delete-a-location-policy"></a>위치 정책을 삭제하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭한 다음 **위치 정책**을 클릭합니다.

4.  **위치 정책** 페이지에서 삭제할 위치 정책을 선택합니다.
    
    <div>
    

    > [!NOTE]  
    > 한 번에 둘 이상의 위치 정책을 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 채 여러 정책을 선택합니다. 또는 모든 정책을 선택하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택</STRONG>을 클릭합니다.

    
    </div>

5.  **편집** 메뉴에서 **삭제**를 클릭합니다.

6.  **확인**을 클릭합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 전역 위치 정책은 삭제할 수 없습니다. 글로벌 정책을 삭제하려고 하면 경고 메시지가 나타나고 해당 정책이 기본값으로 다시 설정됩니다.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 위치 정책 만들기 또는 수정](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Lync Server 2013에서 위치 정책 정보 보기](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

