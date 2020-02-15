---
title: Lync Server 2013 IM 및 현재 상태
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a7713f7b09602aed01ac20e5a76a361e04277a5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a>Lync Server 2013의 IM 및 현재 상태

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-07_

IM (인스턴트 메시징) 및 현재 상태는 Lync Server 배포에 자동으로 설치 됩니다.

*현재 상태* 정보를 사용 하면 사용자가 적절 한 형태의 통신을 사용 하 여 적절 한 시간에 동료에 게 접근 하 여 생산성 높은 작업 환경을 높일 수 있습니다. 사용자의 현재 상태는 가용성, 연락 가능성, 통신, 추가 메모 (예: 위치 및 상태), 사용자에 게 연락 하는 방법을 포함 하는 정보의 모음입니다. Lync Server에는 사진, 위치 정보 및 "사용 가능", "방해 금지" 및 "오른쪽으로 설정"과 같은 기본 상태를 포함 하는 "사용할 수 있음", "작동 안 함" 및 "권한"을 비롯 한 다양 한 현재 상태에 대 한 현재 상태가 표시 됩니다. 관리자는 조직의 특정 현재 상태를 사용자 지정 하 여 정의할 수도 있습니다.

사용자는 연락처 관리 및 사용자 액세스 옵션을 사용 하 여 다른 사용자가 볼 수 있는 정보를 제어 합니다. 사용자는 서로 다른 수준의 대화 상대를 설정할 수 있으며, 각각의 현재 상태 정보를 볼 수 있습니다.

연락처 목록만 살펴보면 사용자는 한 눈에 파악 해야 하는 모든 정보를 쉽게 찾을 수 있습니다. 단순한 색 아이콘은 다른 사용자의 현재 상태를 나타내고 그림과 위치도 표시 됩니다.

Lync Server와 Outlook 및 SharePoint 같은 다른 제품 간의 통합을 사용 하 여 전자 메일 메시지 또는 팀 웹 사이트 등의 연락처 이름이 표시 될 때마다 상태 및 연락처 정보도 표시 됩니다. 또한 Exchange 2013을 배포 하는 경우 Lync Server 및 Exchange 2013에서는 두 제품 중 하나의 클라이언트에서 액세스할 수 있는 통합 연락처 저장소를 공유할 수 있습니다.

Lync Server에서 인스턴트 메시징을 사용 하면 사용자가 적시에 정보를 신속 하 게 파악할 수 있습니다. 원하는 경우 사용자는 MSN/Windows Live, Yahoo\!및 AOL 같은 공용 IM 네트워크의 사용자와 통신할 수도 있습니다. Windows Live, AOL 및 Yahoo와의 공용 IM 연결에는 별도의 라이선스가 필요할 수도 있습니다.\! 또한 Lync Server에는 사용자가 Google 대화와 같은 XMPP 서비스 사용자와 IM 메시지 및 현재 상태 정보를 교환할 수 있도록 XMPP (Extensible Messaging and 현재 상태 프로토콜) 호환성이 포함 되어 있습니다.

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

사용자는 대화 기록을 통해 이전 IM 대화를 추적 하 고 IM 달 전에 통신 했을 수 있는 정보를 검색할 수 있습니다.

영구 채팅 기능을 통해 사용자는 시간에 따라 지속 되는 단체 및 토픽 기반 대화에 참가할 수 있습니다. 대화방에 게시 되는 메시지 (토론 포럼)는 영구적 일 수 있습니다 (즉, 시간에 따라 사용 가능). 다른 위치 및 부서에서 동시에 온라인 상태가 아닌 사용자도 참가할 수 있도록 합니다.

조직이 규정 준수 규정을 따라야 하는 경우에는 메시지 보관 기능을 배포 하 여 조직의 모든 사용자 또는 지정한 특정 사용자에 대 한 인스턴트 메시지 콘텐츠를 보관할 수 있습니다. Exchange 2013도 배포 하는 경우 IM 보관 사서함을 Exchange의 원본 위치 유지 기능과 통합 하 여 준수에 대 한 단일 관리 환경을 제공할 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

