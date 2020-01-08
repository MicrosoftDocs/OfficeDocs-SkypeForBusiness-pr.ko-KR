---
title: Lync Server 2013 사이트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1843ac4256e71723abf59fa272155ced2010e72
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a>Lync Server 2013에 대한 Lync Server 사이트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-16_

Lync Server에서 Lync 서버 구성 요소를 포함 하는 네트워크 *사이트* 를 정의 합니다. 사이트는 단일 LAN 또는 고속 광섬유 네트워크로 연결 된 두 대의 네트워크와 같이 고속의 짧은 대기 네트워크로 연결 된 컴퓨터 집합입니다 .이 (가) 있습니다. Lync Server 사이트는 Active Directory 도메인 서비스 사이트 및 Microsoft Exchange Server 사이트와는 별개의 개념을 참조 하세요. Lync Server 사이트는 Active Directory 사이트와 일치 하지 않아도 됩니다.

<div>

## <a name="site-types"></a>사이트 종류

각 사이트는 하나 이상의 프런트 엔드 풀 또는 스탠더드 버전 서버를 포함 하는 *중앙 사이트*이거나 *지점 사이트*입니다. 각 지점 사이트는 정확히 하나의 중앙 사이트와 연결 되며, 지점 사이트의 사용자는 연결 된 중앙 사이트의 서버에서 대부분의 Lync Server 기능을 가져옵니다.

각 지점 사이트에는 다음 중 하나가 포함 됩니다.

  - Lync Server 등록자와 Windows Server에서 실행 되는 중재 서버를 사용 하는 산업 표준 블레이드 서버인 *Survivable Branch 기기 (SBA)*. Survivable Branch 기기에는 PSTN (공용 전환 전화 네트워크) 게이트웨이도 포함 되어 있습니다. Survivable Branch 기기는 25 명에서 1000 사용자 사이의 지점 사이트를 위해 설계 되었습니다.

  - *Survivable Branch 서버 (SBS)*-Windows Server를 실행 하는 서버로,이는 지정 된 하드웨어 요구 사항을 충족 하며 Lync server 등록자와 중재 서버 소프트웨어가 설치 되어 있는 것입니다. 전화 서비스 공급자에 게 PSTN 게이트웨이나 SIP 트렁크에 연결 해야 합니다. Survivable Branch 서버는 1000와 5000 사용자 사이의 지점 사이트를 위해 설계 되었습니다.

  - PSTN 게이트웨이, 선택적으로 *중재 서버*. 이 및 다른 서버 역할에 대 한 자세한 내용은 [Lync server 2013의 서버 역할](lync-server-2013-server-roles.md)을 참조 하세요.

중앙 사이트에 대 한 회복성 있는 WAN (광역 네트워크) 링크가 있는 지사는 세 번째 옵션인 PSTN 게이트웨이, 선택적으로 중재 서버를 사용할 수 있습니다. 복원성이 적은 링크를 가진 지점 사이트는 Survivable Branch 기기 또는 Survivable Branch 서버를 사용 하 여 광역 네트워크 장애가 발생 한 시간에 탄력성을 제공 해야 합니다. 예를 들어 Survivable Branch 기기 또는 Survivable Branch 서버가 배포 된 사이트에서 사용자는 지점 사이트를 중앙 사이트에 연결 하는 WAN이 작동 하지 않는 경우에도 계속 해 서 엔터프라이즈 음성 통화를 걸고 받을 수 있습니다. Survivable Branch 기기, Survivable Branch 서버 및 복원 력에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 엔터프라이즈 음성 복원 계획](lync-server-2013-planning-for-enterprise-voice-resiliency.md) 을 참조 하세요.

</div>

<div>

## <a name="site-topologies"></a>사이트 토폴로지

배포에는 하나 이상의 중앙 사이트가 포함 되어야 하며, 여러 분기 사이트에 0이 포함 될 수 있습니다. 각 지점 사이트는 하나의 중앙 사이트와 관련이 있습니다. 중앙 사이트는 현재 상태, 회의 등 지사 사이트에 로컬로 호스팅되지 않은 지점 사이트에 Lync Server 서비스를 제공 합니다.

여러 사이트가 있는 경우 재해 복구 기능을 사용 하도록 다양 한 사이트에서 프런트 엔드 풀을 함께 연결할 수 있습니다. 자세한 내용은 [Lync Server 2013에서 고가용성 및 재해 복구 지원을](lync-server-2013-high-availability-and-disaster-recovery-support.md)참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 서버 역할](lync-server-2013-server-roles.md)  
[Lync Server 2013의 고가용성 및 재해 복구 지원](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[Lync Server 2013 의 Enterprise Voice 복구 계획](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

