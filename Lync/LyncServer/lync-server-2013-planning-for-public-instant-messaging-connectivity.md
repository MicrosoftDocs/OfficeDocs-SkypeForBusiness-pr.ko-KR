---
title: 'Lync Server 2013: 공용 인스턴트 메시징 연결 계획'
description: 'Lync Server 2013: 공용 인스턴트 메시징 연결을 계획 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a020a291a39d78aea9271926c99b508a8cd9827
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549294"
---
# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a>Lync Server 2013의 공용 인스턴트 메시징 연결 계획

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-07_

공용 인스턴트 메시징 연결은 페더레이션 클래스 이며 내부 및 외부 Lync Server 2013 사용자가 다음 중 하나에서 연락처를 추가할 수 있도록 구성 됩니다.

  - 메신저 대화 상대

  - Yahoo\! 연락처만

  - 북아메리카 온라인 (AOL) 연락처

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012 년 9 월 1 일부 터 신규 또는 갱신 계약에 대 한 Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 (PIC USL)를 더 이상 사용할 수 없습니다. 활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다. 서비스 종료 날짜까지 메신저 AOL 및 Yahoo!의 6 월 2014 일 종료 날짜 이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</P>
> <LI>
> <P>PIC USL은 Lync Server 또는 Office Communications Server가 Yahoo!과 페더레이션 하는 데 필요한 사용자별 구독 라이선스 (매달)입니다. 메신저로. 이 서비스를 제공 하는 Microsoft의 기능은 갱신 되지 않을 기본 규약 인 Yahoo!을 지원 합니다.</P>
> <LI>
> <P>이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다. Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Lync 사용자가 IM 및 음성을 통해 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</P></LI></UL>



</div>

이 페더레이션 클래스를 사용 하려면 다음과 같은 계획 고려 사항을 충족 해야 합니다.

  - Windows Live Messenger 사용자는 인스턴트 메시징과 함께 Lync Server 2013 사용자와 피어 투 피어 오디오/시각적 통신을 할 수 있습니다. 에 지 서버는 특정 포트 및 프로토콜 요구 사항을 충족 해야 합니다. 자세한 내용은 [Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 확인](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)을 참조 하십시오.

  - Yahoo 인스턴트 메시징의 경우에는 페더레이션을 제공 하는 일반에 지 서버를 계획 및 배포 하는 데 주로 사용 되는 것과는 다른 고유한 요구 사항이 없습니다.

  - 아메리카 온라인에서 액세스에 지 서비스에 할당 된에 지 서버 인증서에는 클라이언트 EKU (확장 된 키 사용)가 있어야 합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [인증서 요약-Lync Server 2013의 공용 인스턴트 메시징 연결](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [포트 요약-Lync Server 2013의 공용 인스턴트 메시징 연결](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [Lync Server 2013의 DNS 요약-공용 인스턴트 메시징 연결](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))

</div>

</div>

<span> </span>

</div>

</div>

</div>

