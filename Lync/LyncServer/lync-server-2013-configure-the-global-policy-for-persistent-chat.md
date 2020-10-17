---
title: 'Lync Server 2013: 영구 채팅에 대 한 글로벌 정책 구성'
description: 'Lync Server 2013: 영구 채팅에 대 한 글로벌 정책을 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 830074c31791ee8ff489d9a67af189be609c7f4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544944"
---
# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a>Lync Server 2013에서 영구 채팅에 대 한 글로벌 정책 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-06_

기본 전역 정책을 단독으로 사용 하 여 배포의 모든 사용자에 대해 영구 채팅 설정을 사용 하도록 설정할 수 있습니다. 사이트 및 사용자에 대 한 추가 정책을 지정 하 여 특정 사용자 및 사이트에 대해 영구 채팅을 사용할지 여부를 제어할 수도 있습니다.

글로벌 정책은 삭제할 수 없습니다. 글로벌 정책을 삭제하려고 하면 구성이 기본값으로 다시 설정됩니다.

<div>


> [!NOTE]  
> 영구 채팅 서버를 구성 하 고 사용 하려면 먼저 토폴로지 작성기를 사용 하 여 토폴로지에 영구 채팅 서버 지원을 추가한 다음 토폴로지를 게시 해야 합니다. 자세한 내용은 배포 설명서의 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013에서 배포에 영구 채팅 서버 추가</A> 를 참조 하십시오.<BR>영구 채팅 서버 구성 설정을 구성 하려면 배포 설명서에서 <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Lync server 2013의 전역 또는 영구 채팅 서버 풀에 대해 영구 채팅 서버 옵션 구성</A> 을 참조 하십시오.



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a>영구 채팅에 대 한 글로벌 정책을 구성 하려면

1.  CsPersistentChatAdministrator, CsAdministrator 또는 CsUserAdministrator role 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.

2.  **시작** 메뉴에서 Lync Server 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 작업 설명서에서 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md) 를 참조 하십시오.
    
    <div>
    

    > [!IMPORTANT]  
    > Windows PowerShell cmdlet을 사용할 수도 있습니다. 자세한 내용은 배포 설명서에서 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성을</A> 참조 하십시오.

    
    </div>

3.  Lync Server 제어판에서 **영구 채팅**을 클릭 하 고 **영구 채팅 정책을**클릭 합니다.

4.  정책 목록에서 **전역**을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.

5.  **영구적 채팅 정책 편집 - 전역**에서 다음을 수행합니다.
    
      - **이름**에서 글로벌 정책의 새 이름을 지정합니다(기본값인 "전역"을 사용하지 않으려는 경우).
    
      - **설명**에 사용자 정책에 대 한 자세한 정보를 제공 합니다 (예:: centralsitename에 대 한 글로벌 정책).
    
      - 사이트 정책 또는 사용자 정책을 통해 제어 되지 않는 모든 사이트 및 사용자에 대해 영구 채팅을 제어 하려면 **영구 채팅 사용** 확인란을 선택 하거나 선택을 취소 합니다.

6.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

