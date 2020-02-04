---
title: XMPP 게이트웨이 액세스 정책 및 인증서 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49733882
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b1aab41b1a9af8c7b8df888dcb3a0c8621fa44e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>XMPP 게이트웨이 액세스 정책 및 인증서 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-15_

XMPP federation는 XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜)를 기반으로 외부 배포를 정의 합니다. XMPP 구성은 다음을 수행 하 여 Lync 사용자가 XMPP 도메인 사용자에 액세스할 수 있도록 합니다.

  - IM 및 현재 상태 – 사용자에만 해당

  - Lync 클라이언트에서 XMPP 페더레이션 대화 만들기

XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) 페더레이션 파트너 지원에 대 한 정책을 구성할 때 정책은 XMPP 페더레이션 도메인의 사용자에 게 적용 되지만 SIP (세션 초기화 프로토콜) 서비스 공급자의 사용자에 게는 적용 되지 않습니다. (예: Windows Live) 또는 SIP 페더레이션 도메인 사용자가 연락처를 추가 하 고 통신 하는 데 사용할 각 XMPP 페더레이션 도메인에 대해 XMPP 페더레이션 파트너를 구성 합니다. 정책이 설정 되 면 XMPP 게이트웨이 인증서를 구성 해야 합니다.

<div>


> [!NOTE]  
> XMPP 게이트웨이 마이그레이션을 시작 하려면 Lync Server 2013 XMPP 게이트웨이를 배포 하 고 Lync Server 2013 XMPP 게이트웨이에 대 한 사용자를 사용 하도록 설정 하는 액세스 정책을 구성 해야 합니다. 이 단계를 수행 하기 전에 모든 사용자가 Lync Server 2013 배포로 이동 해야 합니다. 자세한 내용은 <A href="configure-xmpp-gateway-on-lync-server-2013.md">Lync Server 2013에서 XMPP 게이트웨이 구성을</A>참조 하세요.



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a>Lync Server 2013 XMPP Gateway에 대 한 사용자를 사용할 수 있도록 외부 액세스 정책 구성

1.  Lync Server 제어판을 엽니다.

2.  왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭 한 다음 **외부 액세스 정책을**클릭 합니다.

3.  **새로 만들기** 를 클릭 한 다음 **사용자 정책을**클릭 합니다.

4.  외부 액세스 사용자 정책의 이름을 입력 합니다.

5.  외부 액세스 사용자 정책에 대 한 설명을 입력 합니다.

6.  **페더레이션 사용자와의 통신 사용**을 선택 합니다.

7.  **XMPP 페더레이션 사용자와 통신 사용을**선택 합니다.

8.  **커밋을** 클릭 하 여 사이트 또는 사용자 정책의 변경 내용을 저장 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

