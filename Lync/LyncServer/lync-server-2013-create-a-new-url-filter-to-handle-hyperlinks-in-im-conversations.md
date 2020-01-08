---
title: 메신저 대화에서 하이퍼링크를 처리 하기 위한 새 URL 필터 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f8f9a06dd80f87f2758269ddd2d468aeae2014d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a>Lync Server 2013에서 새 URL 필터를 만들어 메신저 대화의 하이퍼링크 처리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-26_

전역 URL 필터를 수정 하는 것 외에도 Lync Server 2013 배포 내의 개별 사이트에 대 한 사용자 지정 URL 필터를 구성할 수 있습니다. URL 필터링에 대 한 자세한 내용은 [Lync Server 2013에서 IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성을](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)참조 하세요.

<div>

## <a name="to-create-a-new-url-filter"></a>새 URL 필터를 만들려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **메신저 대화 및 현재 상태**를 클릭 한 다음 **URL 필터**를 클릭 합니다.

4.  **URL 필터** 페이지에서 **새로 만들기**를 클릭 합니다.

5.  **사이트 선택**에서 URL 필터를 만들려는 사이트를 클릭 한 다음 **확인**을 클릭 합니다.

6.  **새 Url 필터** 대화 상자에서 **url 필터 사용** 확인란을 선택 하 여 사이트에 대 한 url 필터링을 사용 하도록 설정 합니다.

7.  파일 **형식 확장명** 아래에 확장명이 나열 된 파일을 포함 하는 활성 URL을 차단 하려면 파일 **확장명으로 url 차단** **확인란을 선택**합니다.

8.  **하이퍼링크 접두사** 드롭다운 목록 상자에서 인스턴트 메시지 대화에서 url을 처리 하는 방법에 해당 하는 옵션을 클릭 합니다.
    
    **허용 메시지** 상자를 사용 하면 보낼 수 있는 하이퍼링크를 보낼 때 경고 메시지가 사용자에 게 전송 됩니다.

9.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[특정 사이트에 대 한 Lync Server 2013에서 새 파일 전송 필터 만들기](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Lync Server 2013의 기본 파일 전송 필터 수정](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Lync Server 2013의 기본 URL 필터 수정](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

