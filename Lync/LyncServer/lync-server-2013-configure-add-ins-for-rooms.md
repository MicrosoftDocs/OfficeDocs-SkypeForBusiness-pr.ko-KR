---
title: 'Lync Server 2013: 대화방에 대 한 추가 기능 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8779e770ca96cbfc34bbbc1f1897df1f5eb9ea03
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523055"
---
# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a>Lync Server 2013에서 대화방에 대 한 추가 기능 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

Lync Server 2013 제어판에서는 **영구** 채팅 페이지의 **추가 기능** 섹션을 사용 하 여 url을 영구 채팅방과 연결할 수 있습니다. 이러한 Url은 대화 확장 창의 대화방에 있는 Lync 2013 클라이언트에 표시 됩니다. 관리자가 등록 된 추가 기능 목록에 추가 기능을 추가 하 고, 사용자가 Lync 2013 클라이언트에서이 업그레이드를 볼 수 있도록 대화방 관리자/작성자가 등록 된 추가 기능 중 하 나와 대화방을 연결 해야 합니다.

추가 기능은 방 내의 환경을 확장하는 데 사용됩니다. 일반적인 추가 기능에는 주식 시세 표시를 대화방에 게시할 때 가로채기를 가로채는 Silverlight 응용 프로그램을 가리키는 URL을 포함할 수 있으며,이를 통해 확장성 창에 주식 기록을 표시할 수도 있습니다. 다른 예로는 "Top of mind" 또는 "Topic of the day"와 같이 몇 가지 공유 컨텍스트를 포함하도록 채팅방에 OneNote 2013 URL을 추가 기능으로 포함하는 것을 들 수 있습니다.

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a>채팅방의 추가 기능을 구성하려면

1.  CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.

2.  **시작** 메뉴에서 Lync Server 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.
    
    <div>
    

    > [!IMPORTANT]  
    > Windows PowerShell cmdlet을 사용할 수도 있습니다. 자세한 내용은 배포 설명서에서 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성을</A> 참조 하십시오.

    
    </div>

3.  왼쪽 탐색 모음에서 **영구 채팅**을 클릭하고 **추가 기능**을 클릭합니다.
    
    여러 영구 채팅 서버 풀 배포의 경우 드롭다운 목록에서 적절 한 풀을 선택 합니다.

4.  **추가 기능** 페이지에서 **새로 만들기**를 클릭합니다.

5.  **서비스 선택**에서 추가 기능을 만들어야 하는 영구 채팅 서버 풀에 해당 하는 서비스를 선택 합니다. 추가 기능은 풀 간에 이동하거나 서로 다른 풀 간에 공유할 수 없습니다.

6.  **새 추가 기능**에서 다음을 수행합니다.
    
      - **이름**에서 새 추가 기능의 이름을 지정합니다.
    
      - **URL**에서 추가 기능과 연결할 URL을 지정합니다. http 및 https 프로토콜의 URL만 사용할 수 있습니다.

7.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)  


[Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

