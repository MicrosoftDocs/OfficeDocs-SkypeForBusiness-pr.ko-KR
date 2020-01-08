---
title: 'Lync Server 2013: 영구 채팅에 대한 사이트 정책 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a site policy for Persistent Chat
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48183470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be98028bf06c20c82dca98fc3bc20d25e97a94c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a>Lync Server 2013에서 영구 채팅에 대한 사이트 정책 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-06_

배포한 각 사이트에 대해 사이트별 영구 채팅 정책을 만들 수 있습니다.

사이트 정책의 구성은 사이트 정책에 포함되는 특정 사이트에 한해 전역 정책에 우선합니다.

<div>


> [!NOTE]  
> 영구 채팅 서버를 구성 하 고 사용 하려면 먼저 토폴로지 작성기를 사용 하 여 토폴로지에 영구 채팅 서버 지원을 추가한 다음 토폴로지를 게시 해야 합니다. 자세한 내용은 배포 설명서의 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013에서 배포에 영구 채팅 서버 추가</A> 를 참조 하세요.<BR>영구 채팅 서버 구성 설정을 구성 하려면 배포 설명서의 <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync Server 2013에서 영구 채팅 서버 옵션을 전역적으로 또는 영구 채팅 서버 풀에 구성을</A> 참조 하세요.



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>사이트에 대 한 영구 채팅 정책 만들기

1.  CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  **시작** 메뉴에서 Lync Server 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **영구 채팅**을 클릭하고 **영구 채팅 정책**을 클릭합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > Windows PowerShell cmdlet을 사용할 수도 있습니다. 자세한 내용은 배포 설명서의 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성을</A> 참조 하세요.

    
    </div>

4.  **새로 만들기**를 클릭하고 **사이트 정책**을 클릭합니다.

5.  **사이트 선택**에서 정책을 적용할 사이트를 클릭합니다.

6.  **새 영구 채팅 정책**에서 다음을 수행합니다.
    
      - **이름**에서 새 사이트 정책의 이름을 지정합니다(예: Redmond).
    
      - **설명**에서 사이트 정책에 대한 자세한 설명을 입력합니다(예: Redmond용 채팅방 정책).
    
      - 사이트 정책을 통해 제어되지 않는 모든 사이트에 대해 영구 채팅을 제어하려면 **영구 채팅 사용** 확인란을 선택하거나 선택을 취소합니다.

7.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

