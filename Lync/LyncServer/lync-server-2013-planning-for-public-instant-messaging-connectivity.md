---
title: 'Lync Server 2013: 공용 인스턴트 메시징 연결 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4432484fbd6056d51a38090a18dbe106851d7c0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a>Lync Server 2013에서 공용 인스턴트 메시징 연결 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-10-07_

공용 인스턴트 메시징 연결은 페더레이션 클래스 이며, 내부 및 외부 Lync Server 2013 사용자가 다음 중 한 곳에서 연락처를 추가할 수 있도록 구성 되었습니다.

  - Messenger 연락처

  - Yahoo\! 상대가

  - 아메리카 온라인 (AOL) 연락처

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 (PIC USL)는 더 이상 신규 또는 갱신 계약을 구매할 수 없습니다. 활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다. 서비스 종료 날짜까지 Messenger. AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜 님이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</P>
> <LI>
> <P>PIC USL은 Lync Server 또는 Office Communications Server가 Yahoo!에 페더레이션 하는 데 필요한 사용자별, 월별 구독 라이선스입니다. 받으려면. 이 서비스를 제공 하는 Microsoft의 기능은 갱신 되지 않을 기본 규약 인 Yahoo!의 지원으로 부과 됩니다.</P>
> <LI>
> <P>이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다. Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Skype 페더레이션은이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 통해 수백만 명에 게 연락할 수 있도록 합니다.</P></LI></UL>



</div>

이 페더레이션 클래스에는 다음과 같은 계획 고려 사항이 필요 합니다.

  - Windows Live Messenger 사용자는 인스턴트 메시지 외에도 Lync Server 2013 사용자와 피어 투 피어 오디오/시각적 통신을 할 수 있습니다. Edge 서버는 특정 포트 및 프로토콜 요구 사항을 충족 해야 합니다. 자세한 내용은 [Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항을 확인](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)하세요.

  - Yahoo 인스턴트 메시징에는 페더레이션을 제공 하는 일반 Edge 서버의 계획 및 배포에 일반적으로 사용 되는 것이 아닌 고유한 요구 사항이 없습니다.

  - 아메리카 온라인에서 액세스에 지 서비스에 할당 된 Edge 서버 인증서에는 EKU (클라이언트 확장 키 사용)가 있어야 합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [인증서 요약-Lync Server 2013의 공개 인스턴트 메시지 연결](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [포트 요약-Lync Server 2013의 공개 인스턴트 메시지 연결](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [DNS 요약-Lync Server 2013의 공개 인스턴트 메시지 연결](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))

</div>

</div>

<span> </span>

</div>

</div>

</div>

