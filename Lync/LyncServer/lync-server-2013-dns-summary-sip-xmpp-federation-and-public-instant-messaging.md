---
title: DNS 요약-SIP, XMPP 페더레이션 및 공용 인스턴트 메시징
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c2ccaab6d1d3bcb1cf597bef076601544f47aad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>DNS 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공용 인스턴트 메시징

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2017-03-09_

Office Communications Server 또는 Lync Server 파트너와의 페더레이션을 정의 하는 데 필요한 DNS (Domain Name System) 레코드는 다른 측면 파트너가 사용자의 도메인에 대 한 자동 DNS 검색을 허용 하는지 결정에 따라 결정 됩니다. Sipfederationtls를 게시 하 \_는 경우 \_tcp를 *SIP 도메인 이름\> \<* SRV 레코드의 경우 다른 SIP 페더레이션 도메인은 해당 페더레이션을 "검색" 할 수 있습니다. Lync Server 제어판에서 도메인 및 차단 된 도메인 설정을 사용 하거나, Lync Server 관리 셸 및 **Get**, **Set**, **New**, **csalloweddomain** 및 **-get-csblockeddomain** PowerShell cmdlet을 사용 하 여 허용 또는 차단 된 도메인 구성을 설정 하 여 사용자와 통신할 수 있는 페더레이션 도메인을 제어할 수 있습니다. 이러한 설정을 구성하는 방법 및 PowerShell cmdlet을 사용하는 방법에 대한 자세한 내용은 이 항목 끝부분의 **관련 항목**을 참조하십시오.

DNS 레코드 요약 표에는 공개(검색 가능) 페더레이션에 필요한 항목이 나와 있습니다. 페더레이션 검색을 구현 하지 않으려는 경우에는 \_sipfederationtls를 구성 하지 않기로 결정할 수 있습니다. \_tcp를 *SIP 도메인 이름\> 레코드입니다. \<*

<div>


> [!IMPORTANT]
> _sipfederationtls._tcp. <EM>SIP 도메인 이름&gt; &lt;</EM> SRV 레코드 이지만 검색 가능한 페더레이션을 사용할 필요는 없습니다. 이와 같은 시나리오의 한 가지 예로 사용자를 위해 모바일 기능을 배포한 경우를 들 수 있습니다. PNCH (mobility push notification clearinghouse)는 lync 2010 모바일 클라이언트 또는 lync 2013 모바일 클라이언트를 사용 하 여 Apple iPhone 또는 iPad에서 Microsoft Lync Mobile client에 사용 되는 특별 한 유형의 페더레이션 이며, Lync 2010 모바일 클라이언트나 Windows Phone을 사용 하는 경우 모바일 기능 및 PNCH의 경우에는 _sipfederationtls._tcp. <EM>SIP 도메인 이름&gt; &lt;</EM> SRV 레코드는 이동성 및 푸시 알림의 경우에 사용 됩니다. 이 문제를 완화하고 검색 가능성을 제어하려면 <STRONG>파트너 도메인 검색 사용</STRONG> 설정 선택을 취소하여 검색을 해제합니다.



</div>

배포에 XMPP (extensible messaging and 현재 상태 프로토콜)를 구성 하려면에 지 서버 또는에 지 풀의 액세스에 지 서비스에 대 한 레코드를 확인 하는 두 개의 DNS (domain name system) 레코드를 외부 DNS 서버에 만듭니다.

공용 인스턴트 메시징 연결에 대 한 DNS (domain name system)를 구성 하는 경우 외부 사용자를 지 원하는 구성에서 공용 IM 연결을 지원 한다는 것을 알 수 있습니다. 에 지 서버 또는에 지 풀을 이미 구성한 경우에는 공용 IM 연결을 지 원하는 데 필요한 DNS 레코드가 있어야 합니다.

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a>DNS 요약-공용 인스턴트 메시징 연결을 포함 하는 SIP 페더레이션


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Location/TYPE/Port</th>
<th>FQDN</th>
<th>IP 주소/FQDN 호스트 레코드</th>
<th>매핑 대상/설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>외부 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls _tcp. contoso.</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>액세스에 지 서비스 외부 인터페이스는 다른 잠재적 페더레이션 파트너에 대 한 페더레이션 자동 검색에 필요 하며, "허용 SIP 도메인" (이전 릴리스의 향상 된 페더레이션 이라고 함) 이라고 합니다. Lync를 사용 하는 사용자가 있는 모든 SIP 도메인에 필요에 따라 반복</p>



> [!IMPORTANT]
> 이 SRV 레코드는 모바일 기능 및 푸시 알림 클리어링 하우스에 필요합니다. SIP 도메인이 두 개 이상 있는 경우 Lync 모바일 클라이언트를 사용할 각 도메인에 대해 SRV 레코드를 만들고 게시 합니다. 배포에서 지 원하는 각 SIP 도메인에 대 한 명시적 SRV 레코드가 없는 경우 푸시 알림 서비스와 Apple 푸시 알림 서비스가 예상 대로 작동 하지 않을 수 있습니다.

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a>DNS 요약-XMPP (Extensible Messaging and 현재 상태 프로토콜)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Location/TYPE/Port</th>
<th>FQDN</th>
<th>IP 주소/FQDN 호스트 레코드</th>
<th>매핑 대상/설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>외부 DNS/SRV/5269</p></td>
<td><p>_xmpp-.com. _tcp</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>액세스에 지 서비스 또는에 지 풀의 XMPP 프록시 외부 인터페이스 Lync 사용 가능 사용자가 있는 모든 내부 SIP 도메인에 대해 필요에 따라 반복 글로벌 정책, 사용자가 있는 사이트 정책 또는 도메인에 적용 되는 사용자 정책을 통해 외부 액세스 정책을 구성 하 여 XMPP 대화 상대와의 연결을 허용 합니다. Lync 사용 가능 사용자입니다. XMPP 페더레이션 파트너 정책 에서도 허용 되는 XMPP 도메인을 구성 해야 합니다. 자세한 내용은 관련 <strong>항목을 참조</strong> 하십시오.</p></td>
</tr>
<tr class="even">
<td><p>외부 DNS/A</p></td>
<td><p>xmpp.contoso.com(예제)</p></td>
<td><p>XMPP 프록시를 호스팅하는에 지 서버 또는에 지 풀에 있는 액세스에 지 서비스의 IP 주소</p></td>
<td><p>XMPP 프록시 서비스를 호스팅하는 액세스에 지 서비스 또는에 지 풀을 가리킵니다. 일반적으로 사용자가 만드는 SRV 레코드는 이 호스트(A 또는 AAAA) 레코드를 가리킵니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 XMPP 페더레이션 설정](lync-server-2013-setting-up-xmpp-federation.md)  
[Lync Server 2013에서 푸시 알림 구성](lync-server-2013-configuring-for-push-notifications.md)  
[Lync Server 2013에서 페더레이션 파트너 검색을 사용 하거나 사용 하지 않도록 설정](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[Lync Server 2013의 외부 사용자 액세스에 대 한 시나리오](lync-server-2013-scenarios-for-external-user-access.md)  
[Lync Server 2013에 대 한 DNS 요구 사항 확인](lync-server-2013-determine-dns-requirements.md)  


[Lync Server 2013에서 조직에 대 한 SIP 페더레이션 도메인 관리](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

