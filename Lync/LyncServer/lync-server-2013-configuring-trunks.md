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
ms.openlocfilehash: 09151bf1e5fab592f8051878bcd8218690583309
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a>Lync Server 2013에서 트렁크 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

Enterprise Voice 배포의 일부로 중재 서버와 다음 중 하나 이상의 피어 간에 트렁크를 구성 하 여 조직의 Enterprise Voice 클라이언트 및 장치에 대해 공중 전화망 (PSTN) 연결을 제공할 수 있습니다.

  - ITSP(인터넷 전화 통신 서비스 공급자)에 대한 SIP 트렁크 연결

  - PSTN 게이트웨이

  - PBX(Private Branch Exchange)

자세한 내용은 계획 설명서에서 [Lync Server 2013의 PSTN 연결 계획](lync-server-2013-planning-for-pstn-connectivity.md) 을 참조 하십시오.

<div>


> [!IMPORTANT]  
> 트렁크 구성을 시작하기 전에 토폴로지가 작성되었으며 중재 서버 및 해당 피어가 구성되어 서로 연결되었는지 확인합니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013의 토폴로지 작성기에서 게이트웨이 정의</A> 를 참조 하십시오.



</div>

<div>


> [!NOTE]  
> 트렁크 구성의 일부로 인해 미디어에서 중재 서버를 바이패스 하도록 하는 Lync Server 2013 미디어 바이패스 기능을 사용 하도록 설정할 수 있습니다. 트렁크는 미디어 바이패스를 사용하거나 사용하지 않도록 설정한 상태로 구성할 수 있지만, 사용하도록 설정하는 것이 좋습니다. 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-media-bypass.md">Lync Server 2013에서 미디어 바이패스를 계획</A> 합니다 .를 참조 하십시오.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 여러 트렁크 지원](lync-server-2013-multiple-trunk-support.md)

  - [Lync Server 2013의 트렁크 간 라우팅](lync-server-2013-inter-trunk-routing.md)

  - [Lync Server 2013에서 트렁크 구성 정보 보기](lync-server-2013-view-trunk-configuration-information.md)

  - [Lync Server 2013의 미디어 바이패스로 트렁크 구성](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [Lync Server 2013에서 미디어 바이패스 없이 트렁크 구성](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [Lync Server 2013에서 새 트렁크 구성 설정 컬렉션 만들기](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [Lync Server 2013에서 SIP 트렁크 구성 설정의 기존 컬렉션 삭제](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [Lync Server 2013에서 SIP 트렁크 구성 설정 수정](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [Lync Server 2013에서 SIP 트렁크 구성 설정 테스트](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [Lync Server 2013의 개별 SIP 트렁크에 대 한 정보 보기](lync-server-2013-view-information-about-individual-sip-trunks.md)

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

