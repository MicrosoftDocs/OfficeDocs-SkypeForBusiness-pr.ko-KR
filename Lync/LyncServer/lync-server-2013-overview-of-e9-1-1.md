---
title: 'Lync Server 2013: E9-1-1 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce1c97914abf8e5db393cd932c0a453885e86a5c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530625"
---
# <a name="overview-of-e9-1-1-in-lync-server-2013"></a>Lync Server 2013의 E9-1-1 개요

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-29_

Microsoft Lync Server 2013는 Lync 클라이언트 및 Lync Phone Edition 장치에서의 E9-1-1 (고급 9-1-1) 통화를 지원 합니다. E9-1-1에 대해 Lync Server를 구성 하는 경우 Lync 2013 또는 Lync Phone Edition의 비상 통화에는 위치 정보 서비스 데이터베이스의 ERL (응급 응답 위치) 정보가 포함 됩니다. ERL은 주소와 사무실 건물 또는 복합 시설 내의 위치를 더 정확히 식별하는 데 도움이 되는 기타 정보로 구성됩니다. 사용자가 비상 전화를 걸려면 Lync Server는 통화 오디오를 중재 서버를 통해 E9-1-1 서비스 공급자를 통해 위치 및 콜백 정보와 함께 라우팅합니다. E9-1-1 서비스 공급자는 발신자의 주소를 사용하여 발신자의 위치에 서비스를 제공하는 PASP(Public Safety Answering Point)로 통화를 라우팅하고 PSAP가 발신자 ERL을 조회하는 데 사용하는 ESQK(Emergency Service Query Key)를 함께 전송합니다.

Lync Server에서는 응급 통화를 E9-1-1 서비스 공급자에 게 라우팅하는 두 가지 방법을 지원 합니다.

  - 적격 E9-1-1 서비스 공급자에 대한 SIP(Session Initiation Protocol) 트렁크 연결

  - PSTN(공중 전화망) 기반 E9-1-1 서비스 공급자에 대한 ELIN(Emergency Location Identification Number) 게이트웨이

SIP 트렁크 E9-1-1 서비스 공급자를 사용 하는 경우 위치 정보 서비스 데이터베이스에 ERLs를 추가한 다음 E9-1-1 서비스 공급자가 유지 관리 하는 MSAG (마스터 주소 가이드)에 대해 위치 유효성을 검사 합니다. E9-1-1 서비스 공급자가 지역 정보가 없거나 MSAG에 대해 유효성을 검사 하지 않은 통화를 수신 하는 경우 E9-1-1 서비스 공급자는 전화를 국내/지역별 긴급 통화 응답 센터 (ECRC)로 라우트 하며, 가능한 경우 발신자의 위치를 획득 하 고 해당 전화를 적절 한 PSAP로 수동으로 라우트 하는 특별 한 숙련 된 직원과 팀을 연결 합니다. (일부 SIP 트렁크 E9-1-1 서비스 공급자는 SIP 트렁크가 실패 하는 경우, 9-1-1 통화를 대체 하는 다른 방법을 제공 하는 PSTN direct 전화 걸기 (성공) 번호를 ECRC에 게 제공 하기도 합니다.)

고정 위치가 있는 시간 구분 멀티플렉싱 (TDM) 및 IP 기반 PBX (private branch exchange) 전화와 달리 Lync 끝점은 매우 모바일이 될 수 있습니다. E9 기능을 배포 하는 경우 Lync Server는 발신자가 있는 위치에 관계 없이 긴급 전화를 발신자의 위치를 제공 하는 PSAP로 라우팅할 수 있도록 지원 합니다. 예를 들어 사용자의 주 사무실이 워싱턴의 레드몬드에 있지만 사용자가 캔자스 위치타의 지점에서 긴급 통화를 거는 경우 SIP 트렁크 또는 PSTN 기반 E9-1-1 서비스 공급자는 레드몬드가 아닌 위치타의 PSAP로 통화를 라우팅합니다.

ELIN 게이트웨이를 사용 하는 경우에도 위치 정보 서비스 데이터베이스에 ERLs가 추가 되지만 각 위치에 ELIN 번호도 함께 포함 됩니다. 긴급 통화 중에는 ELIN 번호가 긴급 발신 번호가 됩니다. 그러면 PSTN 통신 회사에서 ELIN을 ALI(Automatic Location Identification) 데이터베이스에 업로드했는지 확인해야 합니다.

<div>


> [!NOTE]  
> Lync 연결 아날로그 장치는 위치 정보 서비스에서 위치 정보를 수신 하거나 E9-1-1 서비스 공급자로 전송 위치를 수신할 수 없습니다. SIP 트렁크 E9-1-1 서비스 공급자 옵션을 사용하며 아날로그 전화에서 E9-1-1을 지원해야 하는 경우에는 두 가지 옵션이 있습니다. 
> <UL>
> <LI>
> <P><STRONG>기존 p-ALI 옵션</STRONG> &nbsp; &nbsp; &nbsp; 아날로그 전화가 배포 되는 각 사이트에 로컬 PSTN 게이트웨이가 있고 각 아날로그 전화에가 있는 경우에는 개인 스위치/자동 위치 식별 (ALI) 서비스 공급자를 사용 하 여 직접 아날로그 장치의 위치를 프로 비전 할 수 있습니다. 이 경우 이러한 전화로부터 걸려온 E9-1-1 통화를 E9-1-1 서비스 공급자 SIP 트렁크로 라우팅하는 대신 통화가 로컬 게이트웨이를 통해 사이트에 서비스를 제공하는 PSTN 공급자로 직접 라우팅되도록 특수하게 만들어진 Lync 음성 정책을 구성하여 아날로그 장치 연락처 개체에 할당할 수 있습니다. 긴급 통화가 걸려오면 PSTN 트렁크와 연결된 PS-ALI 공급자의 데이터베이스가 각 아날로그 전화의 DID를 실제 위치에 매핑하고 이 위치를 PSAP에 제공합니다. 전화가 다른 ERL로 이동될 때마다 PS-ALI 서비스 공급자에서 이러한 레코드가 업데이트되어야 합니다.</P>
> <LI>
> <P><STRONG>E9-1-1 서비스 공급자 옵션</STRONG> &nbsp; &nbsp; &nbsp; E9-1-1 서비스 공급자가 지 원하는 경우 아날로그 전화 DIDs 및 해당 ERLs를 E9-1-1 서비스 공급자에 등록할 수 있습니다. 공급자가 PIDF-로 데이터를 포함 하지 않는 Lync Server의 호출을 수신 하는 경우 공급자는 통화 당사자의 번호에 일치 하는 데이터베이스가 있는지 여부를 확인할 수 있습니다. 공급자는 데이터베이스에서 검색 된 ERL를 사용 하 여 올바른 PSAP로 긴급 통화를 자동으로 라우트할 수 있으며, PSAP는 발송자가 발신자의 위치를 조회할 수 있도록 하는 아날로그 장치 및 ESQK 레코드를 수신 합니다.</P></LI></UL>ELIN 게이트웨이 옵션을 사용하며 아날로그 장치에서 E9-1-1을 지원해야 하는 경우에는 위의 첫 번째 옵션에 설명되어 있는 것처럼 PS-ALI 서비스 공급자를 통해 직접 아날로그 장치의 위치를 프로비전할 수 있습니다.</div>

Lync Server 측면에서 E9-1-1 프로세스를 두 단계로 분리할 수 있습니다.

  - 1단계: 위치 얻기

  - 2단계: 긴급 통화를 E9-1-1 서비스 공급자로 라우팅

이 섹션에서는 이 두 단계의 작동 방식에 대해 설명합니다.

클라이언트 위치를 자동으로 감지하도록 인프라를 구성하려는 경우 먼저 발신자를 위치에 매핑하는 데 사용할 네트워크 요소를 결정해야 합니다. 사용할 수 있는 옵션에 대 한 자세한 내용은 [Lync Server 2013에서 위치를 확인 하는 데 사용 되는 네트워크 요소 정의](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)를 참조 하십시오.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 위치 가져오기](lync-server-2013-acquiring-a-location.md)

  - [Lync Server 2013에서 SIP 트렁크를 사용 하 여 E9-1-1 통화 라우팅](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [Lync Server 2013에서 ELIN 게이트웨이를 사용 하 여 E9-1-1 통화 라우팅](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

