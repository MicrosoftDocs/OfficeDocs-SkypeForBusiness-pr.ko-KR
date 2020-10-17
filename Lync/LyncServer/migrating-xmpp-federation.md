---
title: XMPP 페더레이션 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0567f5c2173b1c0d476367d5ab9a70f4c630aa82
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527355"
---
# <a name="migrating-xmpp-federation"></a>XMPP 페더레이션 마이그레이션

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

이전 버전의 Lync Server 및 Office Communications Server에서는 XMPP 배포와의 페더레이션을 허용 하기 위해 별도의 서버 역할로 배포할 수 있는 XMPP (extensible messaging and 거점 protocol) 게이트웨이를 제공 했습니다. Lync Server 2013에서는 XMPP 기능을 기능으로 배포할 수 있습니다. XMPP 기능은 Lync server 2013에 지 서버에서 실행 되는 XMPP 프록시 및 Lync Server 2013 프런트 엔드 서버에서 실행 되는 XMPP 게이트웨이와 같은 두 부분으로 설치 됩니다.

마이그레이션 측면에서 Lync Server 사용자 계정을 Lync Server 2013 풀로 이동 하 고 계속 해 서 레거시 XMPP 게이트웨이를 사용할 수 있습니다. 이는 XMPP 페더레이션 파트너가 Lync Server 2013에 구성 되어 있지 않은 경우에만 가능 합니다.

요약 하자면, Lync Server 2010이 Office Communications Server 2007 R2 XMPP 게이트웨이와 함께 배포 되 고 레거시 Lync Server 2010 사용자에 대해 XMPP 페더레이션을 사용 하도록 설정 되어 있는 경우 XMPP 페더레이션을 Lync Server 2013로 마이그레이션하려면 다음을 수행 합니다.

1.  Lync Server 2013 풀을 배포 합니다.

2.  Lync Server 2013에 지 서버를 배포 합니다.

3.  모든 사용자를 Lync Server 2013 풀로 이동

4.  에지 서버에 대한 XMPP 액세스 정책 및 인증서를 만듭니다.

5.  Lync Server 2013에서 XMPP 페더레이션을 사용 하도록 설정 합니다. 

6.  Lync Server 2013 XMPP 게이트웨이를 가리키도록 DNS 항목을 업데이트 합니다.

</div>

<span> </span>

</div>

</div>

</div>

