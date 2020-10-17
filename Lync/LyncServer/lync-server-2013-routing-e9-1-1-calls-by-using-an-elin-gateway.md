---
title: 'Lync Server 2013: ELIN 게이트웨이를 사용 하 여 E9-1-1 통화 라우팅'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a3fb7a36680ff3ef35de44d53fc10a676d46242
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511245"
---
# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a>Lync Server 2013에서 ELIN 게이트웨이를 사용 하 여 E9-1-1 통화 라우팅

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-05_

Unified Communications Open Interoperability Program의 일부 파트너는 자격이 있는 E9-1-1 서비스 공급자에 대한 SIP 트렁크 연결의 대안으로 사용할 수 있는 자격이 있는 ELIN(Emergency Location Identification Number) 지원 게이트웨이를 제공합니다. ELIN 게이트웨이는 PSTN(공중 전화망) 기반의 E9-1-1 서비스에 대한 ISDN 또는 CAMA(Centralized Automatic Message Accounting) 연결을 지원합니다. ELIN 게이트웨이를 제공 하는 파트너와 해당 설명서에 대 한 링크는을 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425) .

E9-1-1 서비스 공급자에 대 한 SIP 트렁크 연결과 마찬가지로, 게이트웨이에서는 발신자의 가장 적합 한 공용 안전 응답 지점 (PSAP)에 긴급 통화를 라우팅하는 방법도 제공 하지만, 이러한 게이트웨이는 위치 식별자로 ELIN을 사용 합니다. 조직의 각 ERL (응급 응답 위치)에 대해 ELINs를 정의 합니다. 자세한 내용은 [Lync Server 2013에서 ELINS에 대 한 위치 관리](lync-server-2013-managing-locations-for-elin-gateways.md)를 참조 하십시오.

비상 전화에 ELIN 게이트웨이를 사용 하는 경우 SIP 트렁크 연결에 사용 하는 것과 동일한 Lync Server E9-1-1 인프라를 사용 합니다. 즉, 위치 정보 서비스 데이터베이스는 Lync Server 클라이언트에 대 한 위치를 제공 하 고 위치 정책은 해당 기능을 사용 하도록 설정 하 고 경로를 정의 합니다. 그러나 ELIN 게이트웨이를 사용 하는 경우에는 Elin를 위치 정보 서비스 데이터베이스에 추가 하 고 PSTN 캐리어가이를 ALI (자동 위치 식별) 데이터베이스에 업로드 하도록 해야 합니다.

Lync 클라이언트가 위치 정보 서비스에서 위치를 가져올 때 위치에는 ELIN이 포함 됩니다. 긴급 통화 중 ELIN에는 ELIN 게이트웨이에 전송된 위치가 포함됩니다. ELIN 게이트웨이는 통화를 긴급 통화로 식별하고 통화 당사자의 번호를 ELIN으로 전환합니다. 그런 후 ELIN 게이트웨이는 호출 번호로 ELIN을 사용해서 통화를 PSTN으로 라우팅합니다. PSTN E9-1-1 공급자는 MSAG(Master Street Address Guide) 데이터베이스의 부속 데이터베이스인 ALI 데이터베이스에서 ELIN을 조회합니다. 그런 후 PSTN은 ALI 조회를 기반으로 가장 적합한 PSAP로 통화를 전송하고, PSAP는 ALI 조회를 기반으로 첫 번째 응답자를 발신자의 위치로 보냅니다. 호출 중인 번호는 콜백을 위해 미리 정의된 일정 기간 동안 ELIN 게이트웨이에 캐시로 저장됩니다. 콜백 중에는 PSAP가 ELIN 게이트웨이에 연결하여 발신자의 DID(direct inward dialing) 번호를 얻기 위해 ELIN으로 전환합니다.

ELIN 게이트웨이는 조직 내 네트워크 내부에서만 긴급 통화를 지원합니다. 네트워크 외부로부터의 긴급 통화는 지원하지 않습니다.

<div>


> [!NOTE]  
> 비상 전화에 SIP 트렁크 연결을 사용 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 통화를 사용 하 여 Lync Server 2013에서 sip 트렁크를</A>참조 하십시오.



</div>

다음 다이어그램에서는 ELIN 게이트웨이를 사용할 때 Lync Server에서 PSAP로의 긴급 통화가 라우팅되는 방식을 보여 줍니다.

**ELIN 게이트웨이로 E9-1-1 통화 라우팅**

![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")

1.  위치, 발신자의 콜백 번호 및 (선택 사항) 알림 URL 및 회의 콜백 번호를 포함 하는 SIP 초대가 Lync Server로 라우팅됩니다.

2.  Lync Server는 긴급 전화 번호와 일치 하 고 해당 통화를 적절 한 위치 정책에 정의 된 **PSTN 사용** 값에 따라 중재 서버에 라우트 하 고 여기에서 elin 게이트웨이로 라우팅합니다.

3.  ELIN 게이트웨이는 ISDN 또는 CAMA 트렁크를 통해 통화를 PSTN으로 라우팅합니다.

4.  PSTN은 통화를 긴급 통화로 식별하고 이를 네트워크에서 E9-1-1 선택적 라우터로 라우팅합니다. E9-1-1 선택적 라우터는 지리적 위치 정보를 가져오기 위해 ALI 데이터베이스에서 발신자의 번호를 조회합니다. E9-1-1 선택적 라우터는 ALI 데이터베이스에서 검색된 위치 정보를 기반으로 가장 적합한 PSAP에 통화를 전송합니다.

5.  알림에 대 한 위치 정책을 구성한 경우 조직의 보안 관리자 중 한 명 이상이 특수 Lync 긴급 알림 인스턴트 메시지를 보냅니다. 이 메시지는 항상 보안 담당자의 화면에 표시되며, 발신자 이름, 전화 번호, 시간 및 위치가 포함되어 해당 보안 담당자가 인스턴트 메시지 또는 음성을 사용해서 긴급 발신자에게 신속하게 응답할 수 있게 해줍니다.

6.  통화가 중간에 끊어지면 PSAP는 ELIN을 사용해서 발신자에게 직접 연락합니다. ELIN 게이트웨이는 발신자의 DID를 위해 ELIN을 전환합니다.

</div>

<span> </span>

</div>

</div>

</div>

