---
title: 'Lync Server 2013: 영구 채팅 서버 정책 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8e41342d50a7d056cdb00c328a912bb6dab6378
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a>Lync Server 2013에서 영구 채팅 서버 정책 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-06_

Lync Server 2013 제어판에서 **영구 채팅** 그룹의 **영구 채팅 정책** 페이지를 사용 하 여 전역, 풀, 사이트 또는 사용자 수준에서 정책을 관리할 수 있습니다 (기본 글로벌 정책 구성 및 배포에 대 한 하나 이상의 추가 사용자 및 사이트 정책 만들기 포함). 사용자가 정책에 따라 영구 채팅 서버를 사용할 수 있도록 설정 된 경우에는 해당 Lync 2013 클라이언트에 영구 채팅 서버 환경이 표시 됩니다.

<div>


> [!NOTE]  
> 토폴로지에서 영구 채팅 서버 사이트 정책은 전역, 사용자 풀 또는 사용자 당 사이트 또는 사용자별로 적용 됩니다.



</div>

전역 정책은 영구 채팅 서버를 배포할 때 자동으로 만들어지며, 구성 하는 것은 가능 하지만 삭제할 수는 없습니다. 글로벌 정책은 모든 사용자에게 적용되므로 사용자별로 설정할 필요가 없습니다.

전역 정책과 함께 영구 채팅 서버에 대해 사용자를 사용 하도록 설정 하는 여러 사이트 및 사용자 정책을 만들고 구성할 수 있습니다. 풀 및 사이트 영구 채팅 서버 정책은 전역 영구 채팅 서버 정책 (해당 사이트의 사용자만 해당)을 재정의 합니다. 사용자 정책은 사용자 정책이 지정된 사용자에 대한 전역, 풀 및 사이트 정책을 모두 재정의합니다.

<div>


> [!NOTE]  
> 영구 채팅 서버를 구성 하 고 사용 하려면 먼저 토폴로지 작성기를 사용 하 여 토폴로지에 영구 채팅 서버 지원을 추가한 다음 토폴로지를 게시 해야 합니다. 자세한 내용은 배포 설명서의 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013에서 배포에 영구 채팅 서버 추가</A> 를 참조 하십시오.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 영구 채팅에 대 한 글로벌 정책 구성](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [Lync Server 2013에서 영구 채팅에 대 한 사이트 정책 만들기](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [Lync Server 2013의 영구 채팅에 대 한 사용자 정책 만들기](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [Lync Server 2013의 사용자 또는 사용자 그룹에 영구 채팅 정책 적용](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

