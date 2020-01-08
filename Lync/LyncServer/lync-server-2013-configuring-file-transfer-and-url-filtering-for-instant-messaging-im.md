---
title: IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a9e39799815a86bc255b9aa58627df94eb3f81
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a>Lync Server 2013에서 IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

지능형 IM 필터 도구는 사용자 환경에 대 한 성능 저하를 최소화 하 여 Lync Server 2013 배포를 가장 일반적인 바이러스 형태의 확산 으로부터 보호 합니다. 지능형 IM 필터를 사용 하 여 필터를 구성 하 여 회사 방화벽 외부의 알 수 없는 끝점에서 원하지 않거나 위험한 인스턴트 메시지를 차단 합니다. 특정 접두 번호와 특정 확장명의 파일에 대 한 하이퍼링크를 포함 하는 인스턴트 메시지와 같이 차단 되어야 하는 항목을 결정 하는 데 사용할 조건을 지정 하 여 필터를 구성 합니다.

지능형 IM 필터는 다음을 제공 합니다.

  - 향상 된 URL 필터링.

  - 향상 된 파일 전송 필터링.

지능형 IM 필터 구성에는 다음이 포함 됩니다.

  - URL 필터링 구성

  - 파일 전송 필터링 구성

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a>인스턴트 메시지에 필터링 옵션을 적용 하는 방법

지능형 IM 메시지 필터 도구를 배포 하기 전에 메시지가 하나의 Lync Server 2013 서버에서 다른 사용자에 게 라우팅될 때 필터링 옵션이 적용 되는 방식을 이해 해야 합니다. 이러한 필터링 옵션이 적용 되는 방식에 따라 서버가 단일 조직에 있든 조직 경계를 넘어 지에 관계 없이 일관성이 있습니다. 이 일관성은 사용자 지정 된 알림 및 경고 텍스트를 메시지에 삽입 하 고 서버에서 보내는 방식에 적용 됩니다.

<div>


> [!NOTE]
> 인스턴트 메시지 필터는 메시지에서 Url을 처리 하는 데 필요한 CPU 리소스의 양을 늘립니다. 이러한 CPU 수요 증가는 Lync Server의 성능에도 영향을 줍니다.



</div>

Lync Server 제어판의 **메신저 대화 및 현재 상태** 그룹에 있는 **URL 필터** 페이지를 사용 하 여 일부 또는 전체 하이퍼링크를 차단 하거나 경고를 구성할 수 있습니다. **하이퍼링크 접두사** 옵션 **보내기 경고 메시지**를 선택 하면 하이퍼링크를 포함 하는 인스턴트 메시지의 시작 부분에 경고가 삽입 됩니다.

인스턴트 메시지가 한 서버에서 다른 서버로 이동 하면 다음과 같은 일반적인 지침이 적용 됩니다.

  - 서버에서 인스턴트 메시지를 차단 하는 경우 ( **Url 필터** 페이지에서 **파일 확장명으로 url 차단** 확인란을 선택 했거나 **하이퍼링크 접두사** 옵션 **차단 하이퍼링크**를 선택한 경우) 클라이언트에 오류 메시지가 반환 됩니다. 이후 서버는이 메신저 대화를 받을 수 없습니다.

  - 서버 (Server1)가 활성 하이퍼링크를 포함 하는 인스턴트 메시지에 경고를 추가 하는 경우,이 인스턴트 메시지를 수신 하는 후속 서버 (Server2)는 메신저 대화에 표시 된이 활성 하이퍼링크에 따라 다른 작업을 수행 하 고 다음을 차단할 수 있습니다. 인스턴트 메시지를 표시 하거나 경고를 추가 합니다. 이 URL에 대 한 경고만 추가 하도록 Server2를 구성한 경우 Server1이 추가한 이전의 경고가 제거 되 고, Server2에 구성 된 경고가 인스턴트 메시지의 시작 부분에 추가 됩니다.

<div>


> [!NOTE]
> 혼합 환경에서 Lync Server 2013을 실행 하는 경우 SP1이 포함 된 Live Communications Server 2005는 지능형 IM 필터 응용 프로그램을 사용 하는 데 필요한 최소 버전입니다. 지능형 IM 필터는 SP1 없이 실시간 통신 서버 2005에서 지원 되지 않습니다.



</div>

<div>

## <a name="url-filtering"></a>URL 필터링

Url은 해당 하이퍼링크 접두사에 따라 필터링 됩니다. 다음 예는 유효한 접두사입니다.

  - www\*.

  - ftp.

  - http

URL 필터링을 수행 하도록 인스턴트 메시지 필터를 구성 하지 않으면 인스턴트 메시지에 포함 된 모든 Url이 서버를 통해 수정 되지 않은 상태로 전달 됩니다. URL 필터링을 수행 하도록 인스턴트 메시지 필터를 구성 하면 **Url 편집 필터** 또는 **새 url 필터** 대화 상자에서 선택한 옵션에 따라 인스턴트 메시지의 url이 필터링 됩니다.

  - **Url 필터**   사용이 옵션은 전역 배포 또는 선택한 사이트에 대 한 URL 필터링을 사용 하도록 설정 합니다.

  - **파일 확장명**   을 사용 하 여 url 차단 **메신저 대화 필터는 파일** **형식 확장명** 아래에 확장명이 나열 된 파일을 포함 하는 활성 인트라넷 또는 인터넷 URL을 차단 합니다. URL이 차단 되 면 보낸 사람에 게 오류 메시지가 표시 됩니다. 이 옵션을 선택 하면 **파일 형식 확장명**아래에 정의 된 모든 파일 확장명에 대해 다른 모든 필터링 옵션 보다 우선적으로 적용 됩니다.
    
    <div>
    

    > [!IMPORTANT]
    > 파일 확장명 필터링은 표준 파일 이름으로 제한 됩니다. 다른 이름에 포함 된 파일 확장명에는 필터링이 작동 하지 않을 수 있습니다.

    
    </div>

인스턴트 메시지 대화에서 하이퍼링크를 처리 하는 방법을 구성 하려면 **하이퍼링크 접두사**에서 다음 옵션 중 하나를 선택 합니다.

  - ****   메시지의 url을 필터링 하지 마세요. 서버를 통해 전송 됩니다. 이 옵션을 선택 하면 **허용 메시지** 상자가 표시 됩니다. **허용 메시지** 상자에서 하이퍼링크를 포함 하는 각 인스턴트 메시지의 시작 부분에 삽입할 알림을 지정 합니다. 이 알림 메시지는 65535 자를 초과할 수 없습니다.

  - **블록 하이퍼링크**   액티브 하이퍼링크를 포함 하는 인스턴트 메시지 배달이 Lync Server에 의해 차단 되 고 보낸 사람에 게 오류 메시지가 표시 됩니다.

  - **경고 메시지**   보내기 Lync Server는 인스턴트 메시지에 활성 하이퍼링크를 허용 하지만 경고가 표시 됩니다. 이 옵션을 선택 하면 **경고 메시지** 상자가 나타납니다. **경고 메시지** 상자에서 유효한 하이퍼링크가 포함 된 인스턴트 메시지에 포함할 경고를 입력 해야 합니다. 예를 들어이 경고는 알 수 없는 링크를 클릭 했을 때 발생할 수 있는 위험에 대해 명시 하거나 조직의 관련 정책 및 요구 사항을 지칭 합니다. 이 경고는 65535 자를 초과할 수 없습니다.

**하이퍼링크 차단** 또는 **경고 메시지 보내기를**선택 하면 다음 옵션을 사용할 수 있습니다.

  - **로컬 인트라넷 하이퍼링크**   제외 인스턴트 메시지 필터는 인터넷 url만 차단 합니다. 인트라넷 내의 위치에 대 한 Url은 서버를 통해 수정 되지 않은 상태로 전달 됩니다. 그러나 Lync Server 통과를 실행 하는 개별 서버에 대 한 인트라넷 Url은 해당 인트라넷 영역의 일부로 간주 되는 로컬 웹 사이트 종류에 따라 달라 집니다. 서버의 인트라넷 영역 설정을 확인 하려면 [Lync server 2013의 기본 URL 필터 수정](lync-server-2013-modify-the-default-url-filter.md)에서 "Internet Explorer에서 인트라넷 설정을 구성 하려면" 절차를 참조 하세요.

  - **이러한 하이퍼링크 접두사**   를 필터링 하 여 차단 하려는 접두 번호를 선택 하 고 **선택을**클릭 한 다음 **하이퍼링크 접두사 선택**에서 **하이퍼링크 접두사** 목록에 접두사를 추가 합니다.
    
    **Href** 를 제외한 모든 접두사는 마침표 또는 콜론으로 끝나야 하며, 별표 뒤에는 마침표가와 야 합니다. 유효한 접두사는 별표 (\*)를 제외한 유효한 URL 문자 집합에 있는 모든 문자를 포함할 수 있습니다. 유효한 URL 문자 집합: \# \*+/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^\_ \` ABCDEFGHIJKLMNOPQRSTUVWXYZ | ~

</div>

<div>

## <a name="file-transfer-filtering"></a>파일 전송 필터링

필터 전송 필터링은 인스턴트 메시지와 컨퍼런스 모두에 영향을 줍니다. 회의를 위해 이러한 설정은 Office Live Meeting 2007 클라이언트 및 멀티미디어 재생 기능의 유인물 기능에 영향을 줍니다.

<div>


> [!NOTE]
> Lync 서버는 또한 파일 전송 설정 옵션을 제공 합니다. 이 서버 쪽 옵션이 Lync Server에서 사용할 수 있는 클라이언트측 컨트롤 외에도 제공 됩니다.



</div>

인스턴트 메시지 대화 중에는 Office Live Meeting 2007 클라이언트의 유인물 기능을 사용 하는 경우와 모든 파일 형식에 대 한 멀티미디어 재생 기능에 대 한 파일 전송을 필터링 할 수 있습니다. 파일 전송을 제어 하는 다음 옵션을 설정할 수 있습니다.

  - **파일 필터**   사용이 옵션은 전역 배포 또는 선택한 사이트에 대 한 파일 필터링을 사용 하도록 설정 합니다.
    
    파일 필터를 사용 하도록 설정 하는 경우 **파일 전송**에서 다음 옵션 중 하나를 선택할 수 있습니다.
    
      - **특정 파일 형식**   차단 차단할 파일 확장명 목록을 지정 하 여 서버에서 필터링 하는 파일 전송 요청을 지정 합니다. 목록에 있는 항목에는 모든 표준 문자를 포함할 수 있지만 와일드 카드 문자\*()는 포함 되지 않습니다. Office Live Meeting 2007 클라이언트에서 유인물 기능을 사용할 수 있지만,이 확장명을 가진 모든 파일을 업로드 하거나 다운로드할 수 없습니다. **Url** 필터 탭에 나열 된 url 필터의 설정에서 **파일 확장명으로 url 차단** 확인란을 선택 하면 url 필터는 같은 목록을 사용 하 여 이러한 파일 확장명을 포함 하는 활성 하이퍼링크를 차단 합니다. 차단 하려는 파일 형식을 선택 하려면 **선택을**클릭 한 다음 **파일 형식 선택**에서 파일 형식 확장명을 **선택한 파일 형식 확장명** 목록에 추가 합니다.
    
      - **모든 서버 차단**   파일 전송 요청이 포함 된 모든 인스턴트 메시지를 삭제 하 고 요청을 보낸 사람에 게 오류 메시지를 반환 합니다. Office Live Meeting 2007 클라이언트의 유인물 기능을 사용할 수 없습니다.

<div>


> [!IMPORTANT]
> 파일 확장명 필터링은 표준 파일 이름으로 제한 됩니다. 다른 이름에 포함 된 파일 확장명에는 필터링이 작동 하지 않을 수 있습니다.



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 기본 파일 전송 필터 수정](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [특정 사이트에 대 한 Lync Server 2013에서 새 파일 전송 필터 만들기](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [Lync Server 2013의 기본 URL 필터 수정](lync-server-2013-modify-the-default-url-filter.md)

  - [Lync Server 2013에서 새 URL 필터를 만들어 메신저 대화의 하이퍼링크 처리](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 메신저 및 현재 상태 설정 관리](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

