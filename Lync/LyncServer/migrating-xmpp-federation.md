---
title: XMPP 페더레이션 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b72dabd60ea42a84fcf9b15d1d739bc063ddf1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a>XMPP 페더레이션 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

이전 버전의 Lync Server 및 Office Communications Server에서는 XMPP 배포와 페더레이션 할 수 있는 별도의 서버 역할로 배포할 수 있는 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 게이트웨이를 제공 했습니다. Lync Server 2013에서는 XMPP 기능을 기능으로 배포할 수 있습니다. XMPP 기능은 Lync Server 2013 Edge 서버에서 실행 되는 XMPP 프록시로, Lync Server 2013 프런트 엔드 서버에서 실행 되는 XMPP 게이트웨이 등 두 가지 부분으로 설치 됩니다.

마이그레이션 측면에서 Lync Server 사용자 계정은 Lync Server 2013 풀로 이동 하 고 계속 해 서 레거시 XMPP 게이트웨이를 사용할 수 있습니다. 이는 XMPP 페더레이션 파트너가 Lync Server 2013에서 구성 되지 않은 경우에만 가능 합니다.

요약 하자면, Lync Server 2010이 Office Communications Server 2007 R2 XMPP 게이트웨이와 함께 배포 된 경우 레거시 Lync Server 2010 사용자에 대해 xmpp 페더레이션을 사용할 수 있도록 설정 되어 있는 경우 XMPP 페더레이션을 Lync Server 2013로 마이그레이션합니다.

1.  Lync Server 2013 풀을 배포 합니다.

2.  Lync Server 2013 Edge 서버를 배포 합니다.

3.  모든 사용자를 Lync Server 2013 풀로 이동

4.  Edge 서버용 XMPP 액세스 정책 및 인증서를 만듭니다.

5.  Lync Server 2013에서 XMPP 페더레이션을 사용 하도록 설정 합니다. 

6.  Lync Server 2013 XMPP 게이트웨이를 가리키도록 DNS 항목을 업데이트 합니다.

</div>

<span> </span>

</div>

</div>

</div>

