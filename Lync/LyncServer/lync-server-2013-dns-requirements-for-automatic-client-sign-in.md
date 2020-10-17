---
title: 'Lync Server 2013: 자동 클라이언트 로그인에 대 한 DNS 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b421656d5fefbefa308178962f5c25b9ae72013f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532185"
---
# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>Lync Server 2013의 자동 클라이언트 로그인에 대 한 DNS 요구 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-06-19_

이 섹션에서는 자동 클라이언트 로그인에 필요한 DNS(Domain Name System) 레코드에 대해 설명합니다. Standard Edition 서버 또는 프런트 엔드 풀을 배포할 때는 클라이언트가 자동 검색을 사용하여 적절한 Standard Edition 서버 또는 프런트 엔드 풀에 로그인하도록 구성할 수 있습니다. 클라이언트를 Lync Server 2013에 수동으로 연결 해야 하는 경우에는이 항목을 건너뛰어도 됩니다.

자동 클라이언트 로그인을 지원하려면 다음을 수행해야 합니다.

  - 클라이언트 로그인 요청을 분산시키고 인증하는 단일 서버 또는 풀을 지정합니다. 사용자를 호스팅하는 조직 내의 기존 서버나 풀일 수도 있고, 이 목적을 위해 어떤 사용자도 호스팅하고 있지 않은 전용 서버나 풀을 지정할 수도 있습니다. 고가용성을 위해서는 이 기능에 프런트 엔드 풀을 지정하는 것이 좋습니다.

  - 이 서버 또는 풀에 대한 자동 클라이언트 로그인을 지원하는 내부 DNS SRV 레코드를 만듭니다.
    
    <div>
    

    > [!NOTE]  
    > 다음의 레코드 요구 사항에서 SIP 도메인은 사용자에게 할당된 SIP URI의 호스트 부분을 나타냅니다. 예를 들어 SIP URI의 형식이 *@contoso.com인 경우에는 contoso.com이 SIP 도메인입니다. SIP 도메인은 대개 내부 Active Directory 도메인과 다릅니다. 조직에서 여러 SIP 도메인을 지원할 수도 있습니다.

    
    </div>

클라이언트에 대해 자동 구성을 사용 하도록 설정 하려면 다음 레코드 중 하나를 Lync 클라이언트의 로그인 요청을 배포 하는 프런트 엔드 풀 또는 Standard Edition 서버의 FQDN (정규화 된 도메인 이름)에 매핑하는 내부 DNS SRV 레코드를 만들어야 합니다.

  - \_\_sipinternaltls rdp-tcp.\<domain\> -내부 TLS 연결의 경우

로그인 요청을 분산할 프런트 엔드 풀 또는 Standard Edition 서버에 대해 하나의 SRV 레코드만 만들면 됩니다.

다음 표에서는 contoso.com 및 retail.contoso.com이라는 SIP 도메인을 지원하는 Contoso라는 가상 회사에 필요한 일부 예제 레코드를 보여 줍니다.

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>SIP 도메인이 여러 개인 자동 클라이언트 로그인에 필요한 DNS 레코드의 예

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>로그인 요청을 분산하는 데 사용되는 프런트 엔드 풀의 FQDN</th>
<th>SIP 도메인</th>
<th>DNS SRV 레코드</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>pool01.contoso.com에 매핑되는 _sipinternaltls._tcp.contoso.com 도메인(포트 5061)에 대한 SRV 레코드</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>pool01.contoso.com에 매핑되는 _sipinternaltls._tcp.retail.contoso.com 도메인(포트 5061)에 대한 SRV 레코드</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 기본적으로 DNS 레코드에 대한 쿼리는 SRV 레코드 및 사용자 이름에 있는 도메인 간의 엄격한 도메인 이름 일치를 따릅니다. 접미사 일치를 대신 사용하도록 클라이언트 DNS 쿼리를 설정하려면 DisableStrictDNSNaming 그룹 정책을 구성하면 됩니다. 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013에서 클라이언트 및 장치에 대 한 계획</A> 을 참조 하십시오.



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>자동 클라이언트 로그인에 필요한 인증서 및 DNS 레코드의 예

이 예에서는 앞의 표에 있는 것과 같은 예제 이름을 사용합니다. Contoso 조직은 contoso.com 및 retail.contoso.com이라는 SIP 도메인을 지원하고 이 조직의 모든 사용자는 다음 중 한 형태의 SIP URI를 갖게 됩니다.

  - \<user\>@retail contoso.com

  - \<user\>@contoso .com

</div>

</div>

<span> </span>

</div>

</div>

</div>

