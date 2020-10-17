---
title: 영구 채팅 서버에 대 한 이전 버전과의 호환성을 실행 합니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c96b2ad99ce403df32cc224d854c34160bd6c613
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518095"
---
# <a name="run-backward-compatibility-for-persistent-chat-server"></a>영구 채팅 서버에 대 한 이전 버전과의 호환성을 실행 합니다.

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

Lync Server 2013, 영구 채팅 서버 끝점은 영구 채팅 서버 풀을 가리키는 간단한 URL을 만드는 방법을 제공 합니다. 이 기능은 레거시 클라이언트를 Lync 2013, 영구 채팅을 실행 하는 컴퓨터에 연결 하려고 할 때 수동 구성에 간단한 URL을 입력할 수 있기 때문에 (Microsoft Office Communications Server 2007 R2 그룹 채팅 서버 또는 Lync Server 2010, 그룹 채팅)에 유용 합니다. 이 끝점은 영구 채팅에서 사용 되지 않으며 레거시 클라이언트에만 필요 합니다. 이 기능은 대화방을 마이그레이션할 수 있지만 조직 전체에 Lync 2013 클라이언트를 배포 하지 않은 중간 기간에 유용 합니다. Lync 2010 그룹 채팅 (클라이언트)을 실행 하는 사용자는 계속 해 서 영구 채팅 서버 백 엔드 서버에 연결할 수 있습니다.

여러 영구 채팅 서버 끝점을 만들 필요는 없습니다. 각 영구 채팅 서버 풀에 대해 하나만 필요 합니다. 관리자는 여러 끝점 (풀 당 하나)을 만들 수 있지만 레거시 클라이언트는 한 번에 하나의 풀에만 연결 되도록 구성할 수 있습니다. 일반 또는 메인스트림 시나리오에서는 레거시 배포가 하나의 풀에 불과합니다. 일반적으로 새 배포는 해당 풀을 새 Lync Server 2013로 마이그레이션하고 새로운 영구 채팅 서버 풀을 더 추가할 수 있습니다.

주요 시나리오에서는 일반적으로 다음 패턴을 따릅니다.

  - Lync Server 2010, 그룹 채팅 풀을 하나씩 사용 하 여 사용자를 관리 하 고, Lync 2010 그룹 채팅 클라이언트는 잘 알려진 사용자 (기본 sip: ocschat@ .com 또는 이와 유사한 것)를 통해 해당 풀에 연결 \<domainName\> 합니다. 사용자가 SIP 사용이 가능한 Active Directory 도메인 서비스이 고 조회 서비스에서 들어오는 요청을 받을 수 있도록 등록 합니다.

  - 이후에 Lync Server 2013 영구 채팅 서버와 영구 채팅 서버 풀을 설치 합니다.

  - 사용자가 일반적으로 오프라인인 시간 중에는(예: 주말) 다음을 수행합니다.
    
      - Lync Server 2010, 그룹 채팅을 해제 합니다.
    
      - Lync Server 2010, 그룹 채팅 풀의 데이터를 Lync Server 2013 영구 채팅 서버 풀로 마이그레이션합니다.
    
      - Active Directory 도메인 서비스에서 잘 알려진 사용자를 삭제 합니다.
    
      - 이전에 삭제한 잘 알려진 사용자와 동일한 SIP URI를 사용하여 새로운 *레거시 끝점*을 만듭니다.
    
      - Lync Server 2013, 영구 채팅 서버를 시작 합니다.

  - 사용자는 Lync 2010 그룹 채팅 (클라이언트)을 사용 하 여 다시 로그온 하 고 구성을 변경할 필요 없이 자신의 데이터에 연결 합니다.

  - 나중에 Lync Server 2010, 그룹 채팅을 해제할 수 있습니다. 따라서 Lync Server 2013, 영구 채팅 서버를 배포 하 고 새 Lync Server 2013 영구 채팅 서버 풀을 설치할 수 있습니다.

Lync Server 2010, 그룹 채팅을 Lync Server 2013, 영구 채팅 서버로 마이그레이션하는 방법에 대 한 자세한 내용은 [Lync server 2010, 그룹 채팅 또는 Office Communications server 2007 R2 그룹 채팅에서 Lync server 2013, 영구 채팅 서버로 마이그레이션을](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)참조 하십시오.

이전 버전과의 호환성을 실행 하려면 레거시 그룹 채팅 풀 클라이언트에서 사용할 수 있는 영구 채팅 서버 풀을 가리키는 영구 채팅 서버 끝점을 만들려면 다음을 수행 합니다.

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

다음으로, 해당 SIP 주소를 대화 상대 개체로 사용 하도록 영구 채팅 클라이언트를 구성 합니다. 특정 영구 채팅 서버 풀에 대 한 **get-cspersistentchatendpoint** cmdlet을 사용 하 여 SIP 주소를 만듭니다.

Windows PowerShell 명령줄 인터페이스를 사용 하 여 영구 채팅 서버 끝점을 추가 하려면 다음 예를 고려해 야 합니다. 여기에서는 풀의 FQDN(정규화된 도메인 이름)이 "pcpool.contoso.com"인 "contoso.com" 토폴로지에서 연락처 개체의 이름이 "persistentchat"로 지정되도록 연락처 개체를 구성합니다.

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅에서 Lync Server 2013, 영구 채팅 서버로 마이그레이션](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

