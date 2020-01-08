---
title: 'Lync Server 2013: E9-1-1 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 144f189c119653ddb02316193e78b9156fad2278
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a>Lync Server 2013의 E9-1-1 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-29_

Microsoft Lync Server 2013는 Lync 클라이언트 및 Lync Phone Edition 장치에서 향상 된 9-1-1 (E9-1) 통화를 지원 합니다. E9-1-1 용 Lync Server를 구성 하면 Lync 2013 또는 Lync Phone Edition에서 제공 하는 비상 전화에는 위치 정보 서비스 데이터베이스의 ERL (비상 응답 위치) 정보가 포함 됩니다. ERLs는 사무실 건물과 다른 다중 테 넌 트 시설에서 더 정확한 위치를 식별 하는 데 도움이 되는 도심 (즉, 거리) 주소와 기타 정보로 구성 됩니다. 사용자가 비상 전화를 걸 때 Lync Server는 E9-1 서비스 공급자에 대 한 중재 서버를 통해 위치 및 콜백 정보와 함께 통화 오디오를 라우팅합니다. E9-1-1 서비스 공급자는 호출자의 도심 주소를 사용 하 여 호출자의 위치를 제공 하는 PSAP (공개 안전 응답 위치)로 통화를 라우팅하고, PSAP에서 호출자의 ERL를 조회 하는 데 사용 하는 ESQK (응급 서비스 쿼리 키)를 따라 보냅니다.

Lync Server는 E9-1-1 서비스 공급자에 대 한 비상 통화 라우팅 두 가지 방법을 지원 합니다.

  - 적격 E9-1-1 서비스 공급자에 대 한 SIP (세션 초기화 프로토콜) 트렁크 연결

  - PSTN (공개 교환 전화) 기반 E9-1-1 서비스 공급자에 대 한 비상 위치 Id 번호 (ELIN) 게이트웨이

SIP 트렁크 E9-1-1 서비스 공급자를 사용 하는 경우 위치 정보 서비스 데이터베이스에 ERLs를 추가 하 고 E9-1-1 서비스 공급자가 유지 관리 하는 MSAG (마스터 주소 가이드)에 대해 위치 유효성을 검사 합니다. E9-1 서비스 공급자가 위치 정보가 없거나 MSAG에 대해 유효성을 검사 하지 않은 전화를 받은 경우 E9-1 서비스 공급자는 국가/지역 긴급 통화 응답 센터 (ECRC)에 게 전화를 라우팅하고, 가능한 경우 호출자의 위치를 구두로 하 고 적절 한 PSAP에 대 한 통화를 수동으로 라우팅하는 특정 교육을 받고 있는 직원을 대상으로 합니다. (일부 SIP 트렁크 E9-1-1 서비스 공급자는 고객에 게 PSTN 직접 내부 전화 걸기 (9-1-1) 번호를 제공 하 여 SIP 트렁크가 어떠한 이유로 든 실패 하는 경우이를 라우팅 하는 대체 방법을 제공 합니다.

고정 위치가 있는 시간 구분 멀티플렉싱 (TDM) 및 IP 기반 개인 분기 교환 (PBX) 전화와는 달리 Lync 끝점은 매우 모바일 일 수 있습니다. E9 기능을 배포 하는 경우 Lync Server는 호출자의 위치에 관계 없이 긴급 전화를 사용 하 여 호출자의 위치를 제공 하는 PSAP로 라우팅할 수 있도록 합니다. 예를 들어 사용자의 기본 office가 Redmond, 인천에 있지만, Wichita의 지사에 있는 컴퓨터에서 비상 전화를 사용 하는 경우 SIP 트렁크 또는 PSTN 기반 E9-1-1 서비스 공급자가 통화를 Wichita의 PSAP에 라우팅합니다. Kansas , Redmond의 PSAP에는 해당 하지 않습니다.

게이트웨이에서 ELIN을 사용 하는 경우 위치 정보 서비스 데이터베이스에 ERLs도 추가 되지만 각 위치에 ELIN 번호를 포함 합니다. 비상 전화를 걸 때의 ELIN 번호는 비상 전화 번호가 됩니다. 그런 다음 PSTN 반송파가 ELINs을 자동 위치 확인 (ALI) 데이터베이스로 업로드 하는지 확인 해야 합니다.

<div>


> [!NOTE]  
> Lync에 연결 된 아날로그 장치는 위치 정보 서비스에서 위치 정보를 받을 수 없으며, E9-1-1 서비스 공급자에 위치를 전송 합니다. SIP 트렁크 E9-1-1 서비스 공급자 옵션을 사용 하 고 아날로그 전화기에서 E9-1-1을 지원 해야 하는 경우 다음 두 가지 옵션이 있습니다. 
> <UL>
> <LI>
> <P><STRONG>전통적인 PS-ALI 옵션</STRONG>&nbsp;&nbsp;&nbsp;아날로그 전화가 배포 되는 각 사이트에 로컬 PSTN 게이트웨이가 있고 각 아날로그 전화기가 있는 경우 개인 스위치/자동 위치 식별 (PS-ALI) 서비스 공급자를 사용 하 여 아날로그 디바이스의 위치를 직접 제공할 수 있습니다. 이 경우 특수 하 게 조작 된 Lync 음성 정책을 구성 하 고 아날로그 디바이스 연락처 개체에 할당 하 여 해당 전화에서 E9-1-1로 직접 전화를 걸어 사이트를 서비스 하는 PSTN 공급자에 게 로컬 게이트웨이를 라우팅 하는 대신 E9-1-1 서비스 공급자에 대 한 통화 SIP 트렁크). 비상 통화가 시작 되 면 PSTN 트렁크와 연결 된 PS ALI 공급자의 데이터베이스가 각 아날로그 전화기를 실제 위치로 매핑하고이 위치를 PSAP에 제공 합니다. 이러한 레코드는 휴대폰을 다른 ERLs로 이동할 때마다 PS-ALI 서비스 공급자로 업데이트 해야 합니다.</P>
> <LI>
> <P><STRONG>E9-1-1 서비스 공급자 옵션</STRONG>&nbsp;&nbsp;&nbsp;E9-1-1 서비스 공급자에서 지원 되는 경우, E9-1-1 서비스 공급자에 아날로그 휴대폰 dids 및 해당 erls를 등록할 수 있습니다. 공급자가 PIDF-대/소문자 데이터를 포함 하지 않는 Lync Server에서 전화를 받으면 공급자는 전화 파티의 번호와 일치 하는 데이터베이스가 있는지 여부를 확인할 수 있습니다. 공급자는 해당 데이터베이스에서 검색 된 ERL를 사용 하 여 올바른 PSAP로 긴급 통화를 자동으로 라우트할 수 있으며, PSAP는 발송자가 발신자의 위치를 조회할 수 있도록 하는 아날로그 디바이스와 ESQK 레코드를 받습니다.</P></LI></UL>ELIN gateway 옵션을 사용 하 고 아날로그 전화기에서 E9-1-1을 지원 해야 하는 경우 위의 첫 번째 옵션에서 설명한 대로 PS-ALI 서비스 공급자를 사용 하 여 아날로그 디바이스의 위치를 직접 프로 비전 할 수 있습니다.



</div>

Lync Server 관점에서 E9-1 프로세스는 다음 두 단계로 나눌 수 있습니다.

  - 1 단계: 위치 가져오기

  - 2 단계: E9-1-1 서비스 공급자에 대 한 비상 통화 라우팅

이 섹션에서는 이러한 단계의 작동 방식에 대해 설명 합니다.

클라이언트 위치를 자동으로 검색 하도록 인프라를 구성 하려는 경우 먼저 호출자를 위치로 매핑하는 데 사용할 네트워크 요소를 결정 해야 합니다. 사용할 수 있는 옵션에 대 한 자세한 내용은 [Lync Server 2013의 위치를 확인 하는 데 사용 되는 네트워크 요소 정의](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)를 참조 하세요.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 위치 얻기](lync-server-2013-acquiring-a-location.md)

  - [Lync Server 2013에서 SIP 트렁크를 사용하여 E9-1-1 통화 라우팅](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [Lync Server 2013에서 ELIN 게이트웨이를 사용하여 E9-1-1 전화 라우팅](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

