---
title: 'Lync Server 2013: 채팅방을 위한 추가 기능 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eb6525f67f22e09c4bf7ea40f575b3981e9a55c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a>Lync Server 2013에서 채팅방을 위한 추가 기능 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

Lync Server 2013 제어판에서 **영구 채팅** 페이지의 **추가 기능** 섹션을 사용 하 여 url을 영구 채팅방과 연결할 수 있습니다. 이러한 Url은 Lync 2013 클라이언트에서 대화 확장 창의 대화방에 표시 됩니다. 관리자는 등록 된 추가 기능 목록에 추가 기능을 추가 해야 하며, 사용자가 Lync 2013 클라이언트에서이 업그레이드를 볼 수 있으려면 채팅방 관리자/작성자가 등록 된 추가 기능 중 하 나와 회의실을 연결 하는 것이 필요 합니다.

추가 기능은 채팅방 내 환경을 확장하기 위해 사용됩니다. 일반적인 추가 기능에는 주식 시세 표시기가 채팅방에 게시 되는 경우를 가로채는 Silverlight 응용 프로그램을 가리키는 URL이 포함 될 수 있으며, 확장성 창에 주식 기록이 표시 됩니다. 다른 예로는 "Top of mind" 또는 "Topic of the day"와 같이 몇 가지 공유 컨텍스트를 포함하도록 채팅방에 OneNote 2013 URL을 추가 기능으로 포함하는 것을 들 수 있습니다.

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a>채팅방의 추가 기능을 구성하려면

1.  CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.

2.  **시작** 메뉴에서 Lync Server 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.
    
    <div>
    

    > [!IMPORTANT]  
    > Windows PowerShell cmdlet을 사용할 수도 있습니다. 자세한 내용은 배포 설명서의 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성을</A> 참조 하세요.

    
    </div>

3.  왼쪽 탐색 모음에서 **영구 채팅**을 클릭한 다음 **추가 기능**을 클릭합니다.
    
    여러 영구 채팅 서버 풀 배포의 경우 드롭다운 목록에서 적절 한 풀을 선택 합니다.

4.  **추가 기능** 페이지에서 **새로 만들기**를 클릭합니다.

5.  **서비스 선택**에서 추가 기능을 만들어야 하는 영구 채팅 서버 풀에 해당 하는 서비스를 선택 합니다. 추가 기능은 한 풀에서 다른 풀로 이동하거나 여러 풀 간에 공유할 수 없습니다.

6.  **새 추가 기능**에서 다음을 수행합니다.
    
      - **이름**에 새 추가 기능 이름을 지정합니다.
    
      - **URL**에 추가 기능과 연결할 URL을 지정합니다. URL은 http 및 https 프로토콜로 제한됩니다.

7.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)  


[Windows PowerShell cmdlet으로 영구 채팅 서버 구성](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

