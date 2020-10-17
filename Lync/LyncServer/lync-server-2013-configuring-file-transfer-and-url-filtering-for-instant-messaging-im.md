---
title: IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성
description: IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring file transfer and URL filtering for instant messaging (IM)
ms:assetid: 115a1a2c-599f-474c-a063-52f7144b5246
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520952(v=OCS.15)
ms:contentKeyID: 48183440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92f11c3f3bb924c1d92361c2635bfb37e1f03175
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548354"
---
# <a name="configuring-file-transfer-and-url-filtering-for-instant-messaging-im-in-lync-server-2013"></a>Lync Server 2013에서 IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

지능형 IM 필터 도구는 사용자 환경에 대 한 성능 저하를 최소화 하면서 가장 일반적인 형태의 바이러스 확산을 방지 하기 위해 Lync Server 2013 배포를 보호 하는 데 도움이 됩니다. 지능형 IM 필터를 사용하면 회사 방화벽 외부의 알 수 없는 끝점에서 보낸 잠재적으로 유해하거나 원치 않는 인스턴트 메시지를 차단하도록 필터를 구성할 수 있습니다. 특정 접두사가 포함된 하이퍼링크를 포함하는 인스턴트 메시지 및 특정 확장명의 파일과 같은 차단할 항목을 결정하는 데 사용할 조건을 지정하여 필터를 구성합니다.

지능형 IM 필터는 다음과 같은 기능을 제공합니다.

  - 향상된 URL 필터링

  - 향상된 파일 전송 필터링

지능형 IM 필터 구성에는 다음이 포함됩니다.

  - URL 필터링 구성

  - 파일 전송 필터링 구성

<div>

## <a name="how-filtering-options-are-applied-to-instant-messages"></a>필터링 옵션을 인스턴트 메시지에 적용하는 방법

지능형 IM 메시지 필터 도구를 배포 하기 전에 메시지가 Lync Server 2013 서버 간에 라우팅되는 방식으로 필터링 옵션을 적용 하는 방법을 이해 해야 합니다. 필터링 옵션이 적용되는 방식은 두 서버가 같은 조직에 있는지 또는 서로 다른 조직에 있는지에 관계없이 동일합니다. 이러한 일관성은 사용자 지정 공지 사항이나 경고 텍스트가 메시지에 삽입되고 서버 간에 전송되는 방식에 적용됩니다.

<div>


> [!NOTE]
> 인스턴트 메시지 필터를 사용할 경우 메시지의 URL을 처리하는 데 필요한 CPU 리소스 양이 늘어납니다. 이러한 CPU 수요 증가는 Lync Server의 성능에도 영향을 줍니다.



</div>

Lync Server 제어판의 **IM 및 현재 상태** 그룹에 있는 **URL 필터** 페이지를 사용 하 여 하이퍼링크 일부 또는 전체를 차단 하거나 경고를 구성할 수 있습니다. **하이퍼링크 접두사** 옵션 **경고 메시지 보내기**를 선택하면 하이퍼링크가 포함된 인스턴트 메시지의 시작 부분에 경고가 삽입됩니다.

인스턴트 메시지가 서버 간에 전송될 때 다음과 같은 일반적인 지침이 적용됩니다.

  - **URL 필터** 페이지에서 **파일 확장명이 있는 URL 차단** 확인란을 선택하거나 **하이퍼링크 접두사** 옵션 **하이퍼링크 차단**을 선택하여 서버에서 인스턴트 메시지를 차단하는 경우 오류 메시지가 클라이언트에 반환됩니다. 그러면 후속 서버에서 이 인스턴트 메시지를 받지 않습니다.

  - 서버(서버 1)에서 활성 하이퍼링크가 포함된 인스턴트 메시지에 경고를 추가한 경우 이 인스턴트 메시지를 받는 후속 서버(서버 2)에서는 인스턴트 메시지에 있는 이 활성 하이퍼링크를 기반으로 다른 작업을 계속 수행할 수 있으며 인스턴트 메시지를 차단하거나 경고를 추가할 수 있습니다. 서버 2가 이 URL에 대한 경고를 추가하도록만 구성된 경우에는 서버 1에서 추가한 이전 경고가 제거되고 서버 2에 구성된 경고가 인스턴트 메시지 시작 부분에 추가됩니다.

<div>


> [!NOTE]
> 혼합 환경에서 Lync Server 2013을 실행 하는 경우에는 지능형 IM 필터 응용 프로그램을 사용 하는 데 필요한 최소 버전은 s p 1이 포함 된 Live Communications Server 2005입니다. SP1이 없는 Live Communications Server 2005에서는 지능형 IM 필터가 지원되지 않습니다.



</div>

<div>

## <a name="url-filtering"></a>URL 필터링

URL은 해당 하이퍼링크 접두사에 따라 필터링됩니다. 다음은 유효한 접두사의 예입니다.

  - www \* .

  - ftp.

  - http

URL 필터링을 수행하도록 인스턴트 메시지 필터를 구성하지 않은 경우 인스턴트 메시지에 포함된 모든 URL이 수정되지 않은 상태로 서버를 통해 전달됩니다. URL 필터링을 수행하도록 인스턴트 메시지 필터를 구성한 경우에는 **URL 필터 편집** 또는 **새 URL 필터** 대화 상자에서 선택한 옵션에 따라 인스턴트 메시지의 URL이 필터링됩니다.

  - **URL 필터 사용**     이 옵션은 전역 배포 또는 선택한 사이트에 URL 필터링을 사용 하도록 설정 합니다.

  - **파일 확장명**     을 사용 하 여 url 차단 인스턴트 메시지 필터는 파일 **형식 확장명** 에 나열 된 확장명을 가진 파일을 포함 하는 모든 활성 인트라넷 또는 인터넷 URL을 블록 **편집** 대화 상자에 차단 합니다. URL이 차단 되 면 보낸 사람에 게 오류 메시지가 표시 됩니다. 이 옵션을 선택 하면 **파일 형식 확장명**에 정의 된 모든 파일 확장명에 대해 block으로 사용 되는 모든 필터링 옵션 보다 우선 합니다.
    
    <div>
    

    > [!IMPORTANT]
    > 표준 파일 이름의 파일 확장명만 필터링할 수 있습니다. 다른 이름에 포함된 파일 확장명에는 필터링이 적용되지 않을 수 있습니다.

    
    </div>

인스턴트 메시지 대화에서 하이퍼링크가 처리되는 방식을 구성하려면 **하이퍼링크 접두사** 아래에서 다음 옵션 중 하나를 선택합니다.

  - **필터링**     안 함 메시지의 Url은 서버를 통해 전송 됩니다. 이 옵션을 선택 하면 **허용 메시지** 상자가 나타납니다. **허용 메시지** 상자에서 하이퍼링크를 포함 하는 각 인스턴트 메시지의 시작 부분에 삽입 하려는 알림을 지정 합니다. 이 메시지는 최대 65535 자까지 구성 될 수 있습니다.

  - **하이퍼링크 차단**     액티브 하이퍼링크를 포함 하는 인스턴트 메시지 배달은 Lync Server에 의해 차단 되며 보낸 사람에 게 오류 메시지가 표시 됩니다.

  - **경고 메시지 보내기**     Lync Server에서는 인스턴트 메시지에 대 한 활성 하이퍼링크를 허용 하지만 경고는 포함 되어 있습니다. 이 옵션을 선택하면 **경고 메시지** 상자가 나타납니다. **경고 메시지** 상자에 유효한 하이퍼링크가 포함된 인스턴트 메시지에 포함할 경고를 입력해야 합니다. 예를 들어 이 경고는 알 수 없는 링크를 클릭할 경우의 잠재적 위험을 알리거나 조직의 관련 정책 및 요구 사항을 나타낼 수 있습니다. 경고는 최대 65535자까지 가능합니다.

**하이퍼링크 차단** 또는 **경고 메시지 보내기**를 선택한 경우 다음 옵션을 사용할 수 있습니다.

  - **로컬 인트라넷 하이퍼링크 제외**     인스턴트 메시지 필터는 인터넷 Url만 차단 합니다. 인트라넷 내의 위치에 대 한 Url은 수정 되지 않은 상태로 서버를 통해 전달 됩니다. 그러나 Lync Server 통과를 실행 하는 개별 서버에 대 한 인트라넷 Url은 인트라넷 영역의 일부분으로 간주 되는 로컬 웹 사이트 유형에 따라 다릅니다. 서버의 인트라넷 영역 설정을 확인 하려면 [Modify the DEFAULT URL filter in The Lync server 2013](lync-server-2013-modify-the-default-url-filter.md)의 "Internet Explorer에서 인트라넷 설정을 구성 하려면" 절차를 참조 하십시오.

  - **이러한 하이퍼링크 접두사 필터링**     차단할 접두사를 선택 하려면 **선택을**클릭 한 다음 **하이퍼링크 접두사 선택**에서 **하이퍼링크 접두사** 목록에 접두사를 추가 합니다.
    
    **href**를 제외한 모든 접두사는 마침표나 콜론 또는 뒤에 마침표가 오는 별표로 끝나야 합니다. 유효한 접두사는 별표 ()를 제외한 유효한 URL 문자 집합에 있는 모든 문자를 포함할 수 있습니다 \* . 유효한 URL 문자 집합은 \# \* +/0123456789 = @ABCDEFGHIJKLMNOPQRSTUVWXYZ ^ \_ \` ABCDEFGHIJKLMNOPQRSTUVWXYZ | ~입니다.

</div>

<div>

## <a name="file-transfer-filtering"></a>파일 전송 필터링

파일 전송 필터링은 인스턴트 메시지와 전화 회의 둘 다에 영향을 줍니다. 전화 회의 경우 이러한 설정은 Office Live Meeting 2007 클라이언트의 참고 파일 기능 및 멀티미디어 재생 기능에 영향을 줍니다.

<div>


> [!NOTE]
> 또한 Lync Server에서는 파일 전송 설정 옵션도 제공 합니다. 이 서버 쪽 옵션은 Lync Server에서 사용할 수 있는 클라이언트 쪽 컨트롤과 함께 제공 됩니다.



</div>

인스턴트 메시지 대화 중에, Office Live Meeting 2007 클라이언트에서 참고 파일 기능을 사용할 때, 그리고 모든 파일 형식의 멀티미디어 재생 기능에 대해 파일 전송을 필터링할 수 있습니다. 다음 옵션을 설정하여 파일 전송을 제어할 수 있습니다.

  - **파일 필터 사용**     이 옵션은 전역 배포 또는 선택한 사이트에 대해 파일 필터링을 사용 하도록 설정 합니다.
    
    파일 필터를 사용하도록 선택한 경우 **파일 전송**에서 다음 옵션 중 하나를 선택할 수 있습니다.
    
      - **특정 파일 형식 차단**     차단할 파일 확장명 목록을 지정 하 여 서버에 의해 필터링 되는 파일 전송 요청을 지정 합니다. 목록의 항목에는 와일드 카드 문자 ()가 아니라 모든 표준 문자를 포함할 수 있습니다 \* . Office Live Meeting 2007 클라이언트에서 유인물 기능을 사용할 수 있지만이 확장명을 포함 하는 모든 파일을 업로드 하거나 다운로드할 수도 없습니다. **Url 필터** 탭에 나열 된 url 필터에 대 한 설정에서 **파일 확장명으로 url 차단** 확인란을 선택한 경우 url 필터는이 목록에서 이러한 확장명을 포함 하는 활성 하이퍼링크를 차단 합니다. 차단할 파일 형식을 선택 하려면 **선택을**클릭 하 고 **파일 형식 선택**에서 **선택한 파일 형식 확장명** 목록에 파일 형식 확장명을 추가 합니다.
    
      - **모두 차단**     서버는 파일 전송 요청을 포함 하는 모든 인스턴트 메시지를 삭제 하 고 요청을 보낸 사람에 게 오류 메시지를 반환 합니다. Office Live Meeting 2007 클라이언트의 유인물 기능이 사용 하지 않도록 설정 되어 있습니다.

<div>


> [!IMPORTANT]
> 표준 파일 이름의 파일 확장명만 필터링할 수 있습니다. 다른 이름에 포함된 파일 확장명에는 필터링이 적용되지 않을 수 있습니다.



</div>

</div>

</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 기본 파일 전송 필터 수정](lync-server-2013-modify-the-default-file-transfer-filter.md)

  - [특정 사이트에 대해 Lync Server 2013에서 새 파일 전송 필터 만들기](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)

  - [Lync Server 2013의 기본 URL 필터 수정](lync-server-2013-modify-the-default-url-filter.md)

  - [Lync Server 2013에서 새 URL 필터 만들기 IM 대화의 하이퍼링크를 처리 하려면](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 IM 및 현재 상태 설정 관리](lync-server-2013-managing-im-and-presence-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

