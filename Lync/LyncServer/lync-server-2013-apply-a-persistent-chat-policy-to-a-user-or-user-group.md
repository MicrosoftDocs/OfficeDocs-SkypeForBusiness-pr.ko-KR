---
title: 'Lync Server 2013: 사용자 또는 사용자 그룹에 영구 채팅 정책 적용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Apply a Persistent Chat policy to a user or user group
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48184652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 726fe9a5fa20a52f770cd5bab475de5731562989
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a>Lync Server 2013에서 사용자 또는 사용자 그룹에 영구 채팅 정책 적용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-06_

사용자가 Lync Server 2013을 사용할 수 있도록 설정 된 경우 특정 사용자에 게 적절 한 정책을 적용 하 여 영구 채팅 서버에 대 한 사용을 설정 하거나 해제할 수 있습니다.

<div>


> [!NOTE]  
> 영구 채팅 서버를 구성 하 고 사용 하려면 먼저 토폴로지 작성기를 사용 하 여 토폴로지에 영구 채팅 서버 지원을 추가한 다음 토폴로지를 게시 해야 합니다. 자세한 내용은 배포 설명서의 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013에서 배포에 영구 채팅 서버 추가</A> 를 참조 하세요.<BR>영구 채팅 서버 구성 설정을 구성 하려면 배포 설명서의 <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync Server 2013에서 영구 채팅 서버 옵션을 전역적으로 또는 영구 채팅 서버 풀에 구성을</A> 참조 하세요.



</div>

이 항목의 절차를 사용 하 여 하나 이상의 사용자 계정 또는 사용자 그룹에 이전에 만든 영구 채팅 사용자 정책을 적용 합니다.

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>사용자 계정에 영구 채팅 사용자 정책을 적용 하려면

1.  CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  **시작** 메뉴에서 Lync Server 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭하고 구성할 사용자 계정을 검색합니다.

4.  검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.

5.  **Lync Server 사용자 편집** 의 **영구 채팅 정책**에서 적용 하려는 영구 채팅 사용자 정책을 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > 자동 설정은 기본 유효 정책을 적용 합니다. <STRONG> &lt;&gt; </STRONG> 이러한 설정은 서버에 의해 자동으로 적용됩니다.

    
    </div>

6.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

