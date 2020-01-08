---
title: 'Lync Server 2013: 기존 네트워크 지역 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea9d08121a7d62d10b44f97ff46ff8d4a5ca129e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-regions-in-lync-server-2013"></a>Lync Server 2013에서 기존 네트워크 영역 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

네트워크 영역은 여러 지리적 영역에 걸친 네트워크의 다양 한 부분을 상호 구성 합니다. 모든 네트워크 지역은 중앙 사이트와 연결 되어 있어야 합니다. 중앙 사이트는 CAC (call 허용 제어) 대역폭 정책 서비스가 실행 되는 데이터 센터 사이트입니다. Lync Server 제어판을 사용 하 여 네트워크 지역을 구성할 수 있습니다. 네트워크 영역에는 오디오 및 비디오 연결에 인터넷을 통한 대체 경로가 허용 되는지 여부를 결정 하는 설정이 포함 됩니다. Lync Server 제어판에서 네트워크 지역을 만들거나 수정 하거나 삭제할 수 있습니다. 이 항목을 사용 하 여 기존 네트워크 지역을 삭제 합니다. 기존 네트워크 지역을 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 지역 만들기 또는 수정을](lync-server-2013-creating-or-modifying-network-regions.md)참조 하세요.

<div>

## <a name="to-delete-a-network-region"></a>네트워크 지역을 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **지역을**클릭 합니다.

4.  **지역** 페이지에서 삭제 하려는 지역을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 한 번에 여러 지역을 삭제할 수 있습니다. 이 작업을 수행 하려면 ctrl 키를 누른 채 여러 지역을 선택 합니다. 또는 모든 지역을 선택 하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택을</STRONG> 클릭 합니다.

    
    </div>

5.  **편집** 메뉴에서 **삭제**를 클릭 합니다.

6.  **확인**을 클릭합니다.
    
    <div>
    

    > [!WARNING]  
    > 네트워크 사이트와 연결 된 네트워크 지역은 제거할 수 없습니다. 사이트와 연결 된 지역을 제거 하려고 하면 오류 메시지가 표시 됩니다. 영역이 사이트와 연결 되어 있는지 확인 하려면 지역을 선택 하 고 <STRONG>편집</STRONG> 메뉴에서 <STRONG>세부 정보 표시</STRONG> 를 클릭 합니다.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 네트워크 지역 만들기 또는 수정](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

