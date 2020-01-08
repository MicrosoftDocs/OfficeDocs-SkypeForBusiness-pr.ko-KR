---
title: 'Lync Server 2013: ELIN 게이트웨이를 사용하여 E9-1-1 전화 라우팅'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdb4b5879f92da79e8a6ec96f61e24fbe182c028
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a>Lync Server 2013에서 ELIN 게이트웨이를 사용하여 E9-1-1 전화 라우팅

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-05_

통합 커뮤니케이션 열려 있는 일부 파트너는 정규화 된 E9 서비스 공급자에 대 한 SIP 트렁크 연결을 대신할 수 있는 정식 비상 위치 식별 번호 (ELIN) 가능 게이트웨이를 제공 합니다. ELIN 게이트웨이는 PSTN (공개 교환 통신망) 기반 E9-1-1 서비스에 대 한 ISDN 또는 중앙화 된 자동 메시지 계정 (CAMA) 연결을 지원 합니다. 게이트웨이에서 ELIN 제공 하는 파트너와 해당 문서에 대 한 링크에 대 [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425)한 자세한 내용은을 참조 하세요.

E9에 대 한 SIP 트렁크 연결과 마찬가지로, 게이트웨이의 ELIN 호출자의 가장 적절 한 공용 안전 응답 시점 (PSAP)으로 긴급 통화를 라우팅하는 방법을 제공 하지만, 이러한 게이트웨이에서는 위치 식별자로 ELIN을 사용 합니다. 조직의 각 ERL (응급 응답 위치)에 대 한 ELINs을 정의 합니다 (자세한 내용은 [Lync Server 2013의 게이트웨이에서 elins 대 한 위치 관리](lync-server-2013-managing-locations-for-elin-gateways.md)).

게이트웨이에서 비상 전화를 위해 ELIN gateway를 사용 하는 경우 SIP 트렁크 연결에 사용 하는 것과 동일한 Lync Server E9-1-1 인프라를 사용 합니다. 즉, 위치 정보 서비스 데이터베이스는 Lync Server 클라이언트에 위치를 제공 하 고 위치 정책은 해당 기능을 사용 하도록 설정 하 고 라우팅을 정의 합니다. 그러나 ELIN gateway를 사용 하는 경우에는 위치 정보 서비스 데이터베이스에 Elin 기능을 추가 하 고 PSTN 캐리어가이를 ALI (자동 위치 식별) 데이터베이스에 업로드 해야 합니다.

Lync 클라이언트가 위치 정보 서비스에서 해당 위치를 가져올 때 위치에는 ELIN이 포함 됩니다. 비상 전화 시에는 ELIN gateway로 전송 된 위치에 ELIN이 포함 됩니다. ELIN gateway는 전화를 비상 통화로 식별 하 고 전화 상대의 번호를 ELIN으로 바꿉니다. 그런 다음 게이트웨이에서 ELIN은 통화를 전화 번호로 연결 되는 ELIN 사용 하 여 PSTN으로 라우팅합니다. PSTN E9-1-1 공급자는 ALI 데이터베이스에서 ELIN 조회 하며,이는 보조 데이터베이스인 MSAG (마스터 주소 가이드) 데이터베이스에 있는 자매입니다. 그런 다음 PSTN은 ALI 조회를 기반으로 가장 적합 한 PSAP로 호출을 보내고, PSAP는 ALI lookup에 따라 호출자의 위치에 첫 번째 응답자를 보냅니다. 전화 번호는 미리 정의 된 콜백 시간 동안 게이트웨이에서 ELIN 캐시 됩니다. 콜백을 진행 하는 동안 PSAP는 호출자의 직접 안쪽으로 거는 전화 접속 (예) 번호에 대 한 ELIN 교환 하는 게이트웨이에서 ELIN 도달 합니다.

ELIN 게이트웨이는 조직의 네트워크 내 에서만 긴급 통화를 지원 합니다. 네트워크 외부에서 발생 한 비상 통화는 지원 하지 않습니다.

<div>


> [!NOTE]  
> 비상 전화를 위해 SIP 트렁크 연결을 사용 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Lync Server 2013에서 sip 트렁크를 사용 하 여 E9 라우팅-1-1 통화</A>를 참조 하세요.



</div>

다음 다이어그램은 게이트웨이에서 ELIN을 사용할 때 Lync Server에서 PSAP로 긴급 통화를 라우팅하는 방법을 보여 줍니다.

**라우팅 E9-ELIN 게이트웨이에서 1 ~ 1 개 통화**

![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")

1.  위치, 발신자의 콜백 번호 및 (선택 사항) 알림 URL과 컨퍼런스 콜백 번호를 포함 하는 SIP 초대가 Lync Server로 라우팅됩니다.

2.  Lync Server는 비상 번호와 일치 하 고 해당 위치 정책에 정의 된 **PSTN 사용** 값에 기반 하 여 해당 전화를 중재 서버에 연결 하 고, 게이트웨이에서는 elin으로 연결을 라우팅합니다.

3.  ELIN gateway는 ISDN 또는 CAMA 트렁크에 전화를 걸고 PSTN으로 보냅니다.

4.  PSTN은 통화를 비상 통화로 식별 하 고이를 E9-1-1-네트워크의 선택적 라우터로 라우팅합니다. E9-1 선택적 라우터는 ALI 데이터베이스에서 발신자의 번호를 조회 하 여 지리적 위치를 가져옵니다. E9-1 선택 라우터는 ALI 데이터베이스에서 검색 된 위치 정보에 따라 가장 적합 한 PSAP로 호출을 보냅니다.

5.  알림에 대 한 위치 정책을 구성한 경우 조직의 보안 책임자 중 한 명에 게 특별 Lync 긴급 알림 인스턴트 메시지가 전송 됩니다. 이 메시지는 항상 보안 관리자의 화면에 표시 되며, 발신자의 이름, 전화 번호, 시간 및 위치를 포함 하 여 보안 담당자가 인스턴트 메시지 또는 음성을 사용 하 여 긴급 호출자에 게 신속 하 게 응답할 수 있도록 합니다.

6.  통화가 중간에 끊어지면 PSAP는 ELIN을 사용 하 여 직접 호출자에 게 연락을 합니다. 게이트웨이에서 ELIN은 호출자의 기능을 위해 ELIN을 바꿉니다.

</div>

<span> </span>

</div>

</div>

</div>

