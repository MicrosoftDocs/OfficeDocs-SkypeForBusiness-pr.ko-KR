---
title: 'Lync Server 2013: 영구 채팅에 대 한 사이트 정책 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site policy for Persistent Chat
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48183470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0762a7a74e8a88c2ca67e78e5cf2a9f1b032fa15
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501875"
---
# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a>Lync Server 2013에서 영구 채팅에 대 한 사이트 정책 만들기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-06_

배포한 각 사이트에 대해 사이트별 영구 채팅 정책을 만들 수 있습니다.

사이트 정책의 구성은 사이트 정책에 포함되는 특정 사이트에 한해 글로벌 정책을 다시 정의합니다.

<div>


> [!NOTE]  
> 영구 채팅 서버를 구성 하 고 사용 하려면 먼저 토폴로지 작성기를 사용 하 여 토폴로지에 영구 채팅 서버 지원을 추가한 다음 토폴로지를 게시 해야 합니다. 자세한 내용은 배포 설명서의 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013에서 배포에 영구 채팅 서버 추가</A> 를 참조 하십시오.<BR>영구 채팅 서버 구성 설정을 구성 하려면 배포 설명서에서 <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync server 2013의 전역 또는 영구 채팅 서버 풀에 대해 영구 채팅 서버 옵션 구성</A> 을 참조 하십시오.



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>사이트에 대 한 영구 채팅 정책을 만들려면

1.  CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator role 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.

2.  **시작** 메뉴에서 Lync Server 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **영구 채팅**을 클릭하고 **영구적 채팅 정책**을 클릭합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > Windows PowerShell cmdlet을 사용할 수도 있습니다. 자세한 내용은 배포 설명서에서 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성을</A> 참조 하십시오.

    
    </div>

4.  **새로 만들기**를 클릭하고 **사이트 정책**을 클릭합니다.

5.  **사이트 선택**에서 정책을 적용할 사이트를 클릭합니다.

6.  **새 영구적 채팅 정책**에서 다음을 수행합니다.
    
      - **이름**에서 새 사이트 정책의 이름을 지정합니다(예: Redmond).
    
      - **설명**에서 사이트 정책에 대한 자세한 설명을 입력합니다(예: Redmond용 채팅방 정책).
    
      - 사이트 정책을 통해 제어 되지 않는 모든 사이트에 대해 영구 채팅을 제어 하려면 **영구 채팅 사용** 확인란을 선택 하거나 선택을 취소 합니다.

7.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

