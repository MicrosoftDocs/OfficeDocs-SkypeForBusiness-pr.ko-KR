---
title: Lync Server 2013 사이트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7193d657ad1e585b1a82ba8e934e5bf99d83e65b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519615"
---
# <a name="lync-server-sites-for-lync-server-2013"></a>Lync Server 2013 용 lync Server 사이트

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-16_

Lync Server에서는 Lync Server 구성 요소를 포함 하는 네트워크의 *사이트* 를 정의 합니다. 사이트는 단일 LAN(Local Area Network)이나 고속 광섬유 네트워크로 연결된 두 개의 네트워크와 같이 고속, 짧은 대기 시간 네트워크로 견고하게 연결된 컴퓨터 집합입니다. Lync Server 사이트는 Active Directory 도메인 서비스 사이트와 Microsoft Exchange Server 사이트와는 별개의 개념입니다. Lync Server 사이트가 Active Directory 사이트와 일치할 필요는 없습니다.

<div>

## <a name="site-types"></a>사이트 유형

각 사이트는 하나 이상의 프런트 엔드 풀 또는 Standard Edition server 또는 *분기 사이트*를 포함 하는 *중앙 사이트*입니다. 각 분기 사이트는 정확히 하나의 중앙 사이트와 연결 되며, 분기 사이트의 사용자는 연결 된 중앙 사이트에 있는 서버에서 대부분의 Lync Server 기능을 가져옵니다.

각 분기 사이트는 다음 중 하나를 포함합니다.

  - Lync Server 등록자 및 Windows Server에서 실행 되는 중재 서버를 사용 하는 업계 표준의 블레이드 서버인 *SBA (Sba (survivable Branch 어플라이언스)* Sba (survivable 분기 기기에는 PSTN (공중 전화망) 게이트웨이도 포함 되어 있습니다. Sba (survivable 분기 어플라이언스는 25 ~ 1000 명의 사용자가 포함 된 분기 사이트용으로 설계 되었습니다.

  - 지정 된 하드웨어 요구 사항을 충족 하 고 Lync Server 등록자 및 중재 서버 소프트웨어가 설치 된 Windows Server를 실행 하는 서버에 해당 하는 *SBS (Sba (survivable Branch server)* 이 서버는 전화 서비스 공급자에 대한 SIP 트렁크 또는 PSTN 게이트웨이에 연결되어야 합니다. 지속 가능 분기 서버는 사용자가 1,000~5,000명 사이인 분기 사이트용으로 디자인됩니다.

  - PSTN 게이트웨이 및 *중재 서버*(선택 사항). 이 및 기타 서버 역할에 대 한 자세한 내용은 [Lync server 2013의 서버 역할](lync-server-2013-server-roles.md)을 참조 하십시오.

중앙 사이트에 대한 복구 가능 WAN(광역 네트워크) 링크가 있는 지점에서는 세 번째 옵션인 PSTN 게이트웨이 및 중재 서버(선택 사항)를 사용할 수 있습니다. 더 낮은 기능의 링크가 포함 된 지점 사이트는 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버를 사용 하 여 광역 네트워크 오류가 발생 한 시간에 복구를 제공 해야 합니다. 예를 들어 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버가 배포 된 사이트에서는 분기 사이트를 중앙 사이트에 연결 하는 WAN이 작동 하지 않는 경우 사용자는 여전히 Enterprise Voice 통화를 만들고 받을 수 있습니다. Sba (survivable Branch 기기, Sba (survivable 분기 서버 및 복구에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 Enterprise Voice 복구 계획](lync-server-2013-planning-for-enterprise-voice-resiliency.md) 을 참조 하십시오.

</div>

<div>

## <a name="site-topologies"></a>사이트 토폴로지

배포에는 하나 이상의 중앙 사이트가 포함되어야 하며, 분기 사이트는 포함되지 않을 수도 있고 여러 개 포함될 수도 있습니다. 각 분기 사이트는 중앙 사이트 하나와 연결됩니다. 중앙 사이트에서는 현재 상태 및 회의와 같은 분기 사이트에서 로컬로 호스트 되지 않는 Lync Server 서비스를 분기 사이트에 제공 합니다.

사이트가 여러 개인 경우에는 각 사이트의 프런트 엔드 풀을 페어링하여 재해 복구 기능을 사용하도록 설정해야 합니다. 자세한 내용은 [Lync Server 2013에서 고가용성 및 재해 복구 지원](lync-server-2013-high-availability-and-disaster-recovery-support.md)를 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 서버 역할](lync-server-2013-server-roles.md)  
[Lync Server 2013의 고가용성 및 재해 복구 지원](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[Lync Server 2013의 Enterprise Voice 복구 계획](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

