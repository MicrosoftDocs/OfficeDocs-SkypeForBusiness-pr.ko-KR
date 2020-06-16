---
title: XMPP 게이트웨이 액세스 정책 및 인증서 구성
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: d7353d6bfdd4c045d9d592ababf92f2aaaec2365
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>XMPP 게이트웨이 액세스 정책 및 인증서 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-15_

XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP). An XMPP configuration allows Lync users access to XMPP domain users by:

  - IM 및 현재 상태 – 개인 간에만

  - Lync 클라이언트에서 XMPP 페더레이션 연락처 만들기

When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains. You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with. Once the policies are in place, you need to configure the XMPP Gateway certificates.

<div>


> [!NOTE]  
> XMPP 게이트웨이 마이그레이션을 시작 하려면 Lync Server 2013 XMPP 게이트웨이를 배포 하 고 사용자가 Lync Server 2013 XMPP 게이트웨이를 사용할 수 있도록 액세스 정책을 구성 해야 합니다. 다음 단계를 수행 하기 전에 모든 사용자를 Lync Server 2013 배포로 이동 해야 합니다. 자세한 내용은 <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway In Lync Server 2013</A>을 참조 하십시오.



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a>사용자가 Lync Server 2013 XMPP 게이트웨이를 사용할 수 있도록 외부 액세스 정책 구성

1.  Lync Server 제어판을 엽니다.

2.  왼쪽 탐색 모음에서 **Federation and External Access(페더레이션 및 외부 액세스)** 를 클릭하고 **외부 액세스 정책**을 클릭합니다.

3.  **새로 만들기**를 클릭하고 **사용자 정책**을 클릭합니다.

4.  외부 액세스 사용자 정책의 이름을 입력합니다.

5.  외부 액세스 사용자 정책에 대한 설명을 입력합니다.

6.  **페더레이션 사용자와의 통신 사용**을 선택합니다.

7.  Select **Enable communications with XMPP federated users(XMPP 페더레이션 사용자와의 통신 사용)** 을 선택합니다.

8.  **커밋**을 클릭하여 사이트 또는 사용자 정책에 대한 변경 내용을 저장합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

