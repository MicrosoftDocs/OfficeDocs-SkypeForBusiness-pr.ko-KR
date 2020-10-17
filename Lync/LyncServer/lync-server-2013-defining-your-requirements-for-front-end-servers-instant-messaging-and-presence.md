---
title: 'Lync Server 2013: 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 요구 사항 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54629a270fcba5f6237deaaa1146108e16bafef7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504335"
---
# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Lync Server 2013의 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 요구 사항 정의

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-07_

IM(인스턴트 메시징) 및 현재 상태를 계획하는 데 수행되는 작업 중 주요 작업은 사용자를 위해 충분한 프런트 엔드 서버를 제공하는 것입니다.

<div>

## <a name="enabling-communication-with-external-users"></a>외부 사용자와 통신 사용

사용자가 외부 사용자와 정보를 교환할 수 있도록 하 여 Lync Server에 대 한 투자의 이점을 대폭 증대 시킬 수도 있습니다. 외부 사용자에는 다음이 포함될 수 있습니다.

  - **원격 사용자**     조직의 사용자가 방화벽 외부에서 작업 중 이며 해당 랩톱이 나 기타 Lync Server 장치를 사용 하는 경우

  - **페더레이션 사용자**     회사의 사용자는 Lync Server를 실행 하는 사람과 함께 작업 합니다. 조직의 사용자가 이러한 사용자에게 쉽게 연결할 수 있도록 하려면 이러한 회사와 페더레이션 관계를 만들면 됩니다.

  - **공개 사용자**     Internet services, Yahoo 및 AOL의 Windows Live 네트워크에서 제공 하는 IM 서비스와 같은 공용 IM 서비스 사용자 \! 및 Google 대화 기능과 같은 XMPP (Extensible Messaging And 현재 상태 프로토콜)를 사용 하는 공급자 및 서버 사용자입니다.
    
    <div>
    

    > [!NOTE]  
    > Windows Live, AOL, Yahoo! 등의 공용 IM 연결에는 별도의 라이선스가 필요할 수도 있습니다.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>2012 년 9 월 1 일, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 신규 또는 갱신 동의를 위해 더 이상 구매할 수 없습니다. 활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다. 서비스 종료 날짜까지 메신저 AOL 및 Yahoo!의 6 월 2014 일 종료 날짜 이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</P>
    > <LI>
    > <P>PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!을 페더레이션 하는 데 필요한 사용자별 구독 라이선스입니다. 메신저로. 이 서비스를 제공 하는 Microsoft의 기능은 기본 규약에 따라 세로 맞춤에 사용 되는 Yahoo!에 대 한 지원을 받을 수 있습니다.</P>
    > <LI>
    > <P>이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다. Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</P></LI></UL>

    
    </div>

이러한 시나리오를 일부 또는 모두 사용 하도록 설정 하려면 Lync Server 배포와 외부 사용자 간의 보안 통신을 사용 하도록 설정 하는 데 도움이 되는에 지 서버를 배포 해야 합니다. 조직의 원격 사용자와 페더레이션 조직의 사용자는 IM을 사용하여 서로의 현재 상태를 확인하고 통신할 수 있습니다. 외부 사용자와의 통신을 사용 하는 방법에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md) 을 참조 하십시오.

</div>

<div>

## <a name="archiving-im-content"></a>IM 콘텐츠 보관

Lync Server에서는 조직이 규정 준수 규정을 따라야 하는 경우 사용할 수 있는 기능을 제공 합니다. 보관을 사용 하 여 조직의 모든 사용자 또는 지정한 특정 사용자에 대 한 IM 메시지의 콘텐츠를 보관할 수 있습니다. 자세한 내용은 계획 설명서의 [Lync Server 2013에서 보관 계획](lync-server-2013-planning-for-archiving.md) 을 참조 하십시오.

Microsoft Exchange Server 2013도 배포 된 경우에는 Exchange 데이터 보관을 Lync Server 데이터 보관 기능과 통합 하 고 단일 도구를 사용 하 여 두 가지 유형의 보관 데이터를 검색할 수 있습니다. 자세한 내용은 microsoft [Exchange server 2013 보관을 사용 하도록 Microsoft Lync Server 2013 구성을](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

