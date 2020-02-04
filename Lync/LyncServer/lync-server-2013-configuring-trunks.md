---
title: 'Lync Server 2013: 트렁크 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1021295b375e4f28294ffb1ca5738d651f9ced2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a>Lync Server 2013에서 트렁크 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

엔터프라이즈 음성 배포의 일부로, 중재 서버와 다음 피어 중 하나 이상을 구성할 수 있으므로 조직의 엔터프라이즈 음성 클라이언트 및 장치에 대 한 PSTN (공개 통신 네트워크) 연결을 제공 합니다.

  - 인터넷 전화 통신 서비스 공급자 (ITSP)에 대 한 SIP 트렁크 연결

  - PSTN 게이트웨이

  - PBX (사설 분기 교환)

자세한 내용은 계획 설명서의 [Lync Server 2013에서 PSTN 연결 계획](lync-server-2013-planning-for-pstn-connectivity.md) 을 참조 하세요.

<div>


> [!IMPORTANT]  
> 트렁크 구성을 시작 하기 전에 토폴로지가 만들어졌는지, 중재 서버와 해당 피어가 서로 구성 되어 연결 되었는지 확인 합니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013의 토폴로지 작성기에서 게이트웨이 정의</A> 를 참조 하세요.



</div>

<div>


> [!NOTE]  
> 트렁크 구성의 일부로 서, Lync Server 2013 미디어 건너뛰기 기능을 사용 하도록 설정 하 여 미디어에서 중재 서버를 우회할 수 있습니다. 미디어 바이패스를 사용 하도록 설정 하거나 포함 하지 않고 Trunks를 구성할 수 있지만, 사용 하도록 설정 하는 것이 좋습니다. 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-media-bypass.md">Lync Server 2013에서 미디어 바이패스 계획</A> 을 참조 하세요.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 여러 트렁크 지원](lync-server-2013-multiple-trunk-support.md)

  - [Lync Server 2013의 트렁크 간 라우팅](lync-server-2013-inter-trunk-routing.md)

  - [Lync Server 2013에서 트렁크 구성 정보 보기](lync-server-2013-view-trunk-configuration-information.md)

  - [Lync Server 2013에서 미디어 바이패스를 사용 하 여 트렁크 구성](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [Lync Server 2013에서 미디어 바이패스 없이 트렁크 구성](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [Lync Server 2013에서 새 트렁크 구성 설정 모음 만들기](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [Lync Server 2013에서 기존 SIP 트렁크 구성 설정 모음 삭제](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [Lync Server 2013에서 SIP 트렁크 구성 설정 수정](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [Lync Server 2013에서 SIP 트렁크 구성 설정 테스트](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [Lync Server 2013의 개별 SIP trunks에 대 한 정보 보기](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 토폴로지 작성기에서 게이트웨이 정의](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[Lync Server 2013의 PSTN 연결 계획](lync-server-2013-planning-for-pstn-connectivity.md)  
[Lync Server 2013의 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

