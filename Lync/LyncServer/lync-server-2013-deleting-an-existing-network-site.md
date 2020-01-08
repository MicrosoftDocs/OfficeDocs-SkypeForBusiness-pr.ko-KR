---
title: 'Lync Server 2013: 기존 네트워크 사이트 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772d653e0bde803f47a5742a4f3824bdef01c3f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a>Lync Server 2013에서 기존 네트워크 사이트 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

네트워크 사이트는 CAC (통화 허용 제어) 또는 향상 된 9-1-1 배포의 각 영역 내에서 구성 된 사무실 또는 위치입니다. Lync Server 2013 제어판을 사용 하 여 사이트를 구성 하 고 지역을 연결할 수 있습니다. 예를 들어 북미, 레드먼드, Vancouver와 같은 네트워크 사이트에 북아메리카 네트워크 지역이 연결 되어 있을 수 있습니다. 사이트에 대 한 모든 사이트에 대해 CAC 네트워크 사이트를 만들어야 하는 경우에도 해당 사이트가 대역폭 제한 없이 구성 되어야 합니다. Lync Server 제어판에서 네트워크 사이트를 만들고, 수정 하 고, 삭제할 수 있습니다. 다음 절차를 사용 하 여 기존 네트워크 사이트를 삭제 합니다. 네트워크 사이트를 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 사이트 만들기 또는 수정을](lync-server-2013-creating-or-modifying-network-sites.md) 참조 하세요.

<div>

## <a name="to-delete-a-network-site"></a>네트워크 사이트를 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **사이트**를 클릭 합니다.

4.  **사이트** 페이지에서 삭제 하려는 사이트를 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 한 번에 여러 사이트를 삭제할 수 있습니다. 이 작업을 수행 하려면 ctrl 키를 누른 채 여러 사이트를 선택 합니다. 또는 모든 사이트를 선택 하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택을</STRONG> 클릭 합니다.

    
    </div>

5.  **편집** 메뉴에서 **삭제**를 클릭 합니다.

6.  **확인**을 클릭합니다.
    
    <div>
    

    > [!WARNING]  
    > 네트워크 서브넷과 연결 된 네트워크 사이트는 제거할 수 없습니다. 서브넷과 연결 된 사이트를 제거 하려고 하면 오류 메시지가 표시 됩니다. 사이트가 서브넷과 연결 되어 있는지 확인 하려면 사이트를 클릭 한 다음 <STRONG>편집</STRONG> 메뉴에서 <STRONG>자세한 정보 표시</STRONG> 를 클릭 합니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

