---
title: 'Lync Server 2013: 자동 클라이언트 로그인을 위한 DNS 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afd8ac315222a5582bde9802c22ab7b4911ddfe3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>Lync Server 2013의 자동 클라이언트 로그인에 대 한 DNS 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-19_

이 섹션에서는 자동 클라이언트 로그인에 필요한 DNS (Domain Name System) 레코드에 대해 설명 합니다. 스탠더드 버전의 서버 또는 프런트 엔드 풀을 배포 하는 경우 자동 검색을 사용 하도록 클라이언트를 구성 하 여 적절 한 Standard Edition server 또는 프런트 엔드 풀에 로그인 할 수 있습니다. 클라이언트가 Lync Server 2013에 수동으로 연결 해야 하는 경우이 항목을 건너뛸 수 있습니다.

자동 클라이언트 로그인을 지원 하려면 다음을 수행 해야 합니다.

  - 단일 서버 또는 풀을 지정 하 여 클라이언트 로그인 요청을 배포 하 고 인증 합니다. 이는 사용자를 호스트 하는 조직의 기존 서버 또는 풀 일 수도 있고 사용자를 호스트 하지 않는이 용도의 전용 서버 또는 풀을 지정할 수도 있습니다. 고가용성을 위해이 함수의 프런트 엔드 풀을 지정 하는 것이 좋습니다.

  - 이 서버 또는 풀에 대 한 자동 클라이언트 로그인을 지원 하기 위해 내부 DNS SRV 레코드를 만듭니다.
    
    <div>
    

    > [!NOTE]  
    > 다음 레코드 요구 사항에서 SIP 도메인은 사용자에 게 할당 된 SIP Uri의 호스트 부분을 가리킵니다. 예를 들어 SIP Uri가 * @contoso .com 인 경우 contoso.com는 SIP 도메인입니다. SIP 도메인은 내부 Active Directory 도메인과 다른 경우가 많습니다. 조직에서 여러 SIP 도메인을 지원할 수도 있습니다.

    
    </div>

클라이언트에 자동 구성을 사용 하도록 설정 하려면 다음 레코드 중 하나를 Lync에서 로그인 요청을 배포 하는 프런트 엔드 풀 또는 스탠더드 버전 서버의 FQDN (정규화 된 도메인 이름)에 매핑하는 내부 DNS SRV 레코드를 만들어야 합니다. 클라이언트

  - \_sipinternaltls. \_tcp. \<domain\> -내부 TLS 연결용

프런트 엔드 풀 또는 Standard Edition 서버에 대해 단일 SRV 레코드만 만들거나 로그인 요청을 배포 하는 경우에만 필요 합니다.

다음 표에서는 contoso.com 및 retail.contoso.com의 SIP 도메인을 지 원하는 가상 회사 Contoso에 필요한 몇 가지 예제 레코드를 보여 줍니다.

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>여러 SIP 도메인에 대 한 자동 클라이언트 로그인에 필요한 DNS 레코드의 예

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>로그인 요청을 배포 하는 데 사용 되는 프런트 엔드 풀의 FQDN</th>
<th>SIP 도메인</th>
<th>DNS SRV 레코드</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>_Sipinternaltls에 대 한 SRV 레코드 (pool01.contoso.com에 매핑되는 5061 포트를 통한 _tcp .com 도메인</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>Pool01.contoso.com에 매핑되는 5061 포트를 통해 _tcp _sipinternaltls에 대 한 SRV 레코드</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 기본적으로 DNS 레코드에 대 한 쿼리는 사용자 이름 및 SRV 레코드의 도메인 간에 엄격한 도메인 이름 일치를 따릅니다. 클라이언트 DNS 쿼리에서 접미사 일치를 대신 사용 하려는 경우 DisableStrictDNSNaming 그룹 정책을 구성할 수 있습니다. 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013에서 클라이언트 및 장치 계획</A> 을 참조 하세요.



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>자동 클라이언트 로그인에 필요한 인증서 및 DNS 레코드의 예

이 예제에서는 앞의 표에 같은 예제 이름을 사용 합니다. Contoso 조직에서는 contoso.com 및 retail.contoso.com의 SIP 도메인을 지원 하며, 모든 사용자는 다음 형식 중 하나로 SIP URI를 갖습니다.

  - \<contoso.com\>사용자 @retail

  - \<사용자\>@contoso

</div>

</div>

<span> </span>

</div>

</div>

</div>

