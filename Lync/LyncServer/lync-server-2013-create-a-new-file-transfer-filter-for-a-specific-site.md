---
title: 'Lync Server 2013: 특정 사이트에 대 한 새 파일 전송 필터 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edaf0afabff9d212cdd3b5353a8e54840979f827
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a>특정 사이트에 대 한 Lync Server 2013에서 새 파일 전송 필터 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-18_

전역 파일 전송 필터를 수정 하는 것 외에도 Lync Server 2013 배포 내의 특정 사이트에 대 한 사용자 지정 파일 전송 필터를 구성할 수 있습니다. 파일 전송 필터링에 대 한 자세한 내용은 [Lync Server 2013에서 IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성을](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)참조 하세요.

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a>특정 사이트에 대 한 파일 전송 필터를 만들려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **메신저 대화 및 현재 상태** 를 클릭 한 다음 **파일 필터**를 클릭 합니다.

4.  **파일 필터** 페이지에서 **새로 만들기**를 클릭 합니다.

5.  **사이트 선택** 대화 상자에서 파일 전송 필터를 만들려는 사이트를 클릭 한 다음 **확인**을 클릭 합니다.

6.  **새 파일 필터**에서 **파일 필터 사용** 확인란을 클릭 합니다.

7.  **파일 전송** 드롭다운 목록 상자에서 **모두 차단** 또는 **특정 파일 형식 차단을**클릭 합니다.

8.  **모두 차단을**클릭 한 경우 10 단계로 건너뜁니다.

9.  **특정 파일 형식 차단을**클릭 한 경우 다음을 수행 합니다.
    
    1.  **선택을** 클릭 하 여 차단 하려는 파일 형식 확장명의 기본 목록을 수정 합니다.
    
    2.  **파일 형식 선택** 대화 상자의 **파일 형식 확장명**아래에 있는 범주에서 확장을 추가 하거나 제거 하 여 차단 하거나 허용 하려는 파일 형식을 선택 합니다.
    
    3.  차단 하려는 파일 형식에 대 한 확장명이 표시 되지 않으면 **목록에 파일 형식 확장명 추가**아래에 있는 텍스트 상자에 확장명을 입력 한 다음 **추가**를 클릭 합니다.
    
    4.  **확인**을 클릭합니다.

10. **커밋**을 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Lync Server 2013에서 새 URL 필터를 만들어 메신저 대화의 하이퍼링크 처리](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[Lync Server 2013의 기본 파일 전송 필터 수정](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Lync Server 2013의 기본 URL 필터 수정](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

