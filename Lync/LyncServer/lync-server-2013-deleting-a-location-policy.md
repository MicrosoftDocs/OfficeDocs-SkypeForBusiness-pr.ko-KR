---
title: 'Lync Server 2013: 위치 정책 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4766d2b05cef89ab29b9c303c5ba1ec456843669
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a>Lync Server 2013에서 위치 정책 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-10_

Lync Server 2013에서 위치 정책을 사용 하 여 향상 된 9-1-1 (E9--1) 기능 및 사용자 또는 연락처에 대 한 위치 설정에 관련 있는 설정을 적용할 수 있습니다. 위치 정책은 사용자가 E9을 사용할 수 있는지 여부를 결정 합니다 (예를 들어, 긴급 통화의 경우). 예를 들어 위치 정책을 사용 하 여 전화 통화를 구성 하는 번호 (예: 미국 내 911), 회사 보안에서 자동으로 알릴 지 여부, 통화를 라우팅하는 방법 등을 정의할 수 있습니다.

Lync Server 2013 제어판의 **네트워크 구성** 그룹에서 위치 정책을 구성할 수 있습니다. Lync Server 제어판에서 위치 정책을 보고, 만들고, 수정 하 고, 삭제할 수 있습니다. 다음 절차를 사용 하 여 위치 정책을 삭제 합니다. 위치 정책을 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 위치 정책 만들기 또는 수정을](lync-server-2013-creating-or-modifying-a-location-policy.md)참조 하세요.

<div>

## <a name="to-delete-a-location-policy"></a>위치 정책을 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **위치 정책을**클릭 합니다.

4.  **위치 정책** 페이지에서 삭제 하려는 위치 정책을 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > 한 번에 여러 위치 정책을 삭제할 수 있습니다. 이 작업을 수행 하려면 ctrl 키를 누른 채 여러 정책을 선택 합니다. 또는 모든 정책을 선택 하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택을</STRONG> 클릭 합니다.

    
    </div>

5.  **편집** 메뉴에서 **삭제**를 클릭 합니다.

6.  **확인**을 클릭합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 전역 위치 정책은 삭제할 수 없습니다. 글로벌 정책을 삭제 하려고 하면 경고 메시지가 표시 되 고 해당 정책은 해당 기본값으로 다시 설정 됩니다.

    
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

