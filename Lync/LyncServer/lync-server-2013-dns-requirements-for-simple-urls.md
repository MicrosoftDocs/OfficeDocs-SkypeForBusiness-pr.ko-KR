---
title: 'Lync Server 2013: 단순 Url에 대 한 DNS 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98db338c48bbb764aefe3d5cab4bcba58b2b23c4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501375"
---
# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a>Lync Server 2013의 단순 Url에 대 한 DNS 요구 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-22_

Lync Server 2013은 사용자에 게 모임을 보다 쉽게 참가할 수 있도록 하는 단순 Url을 지원 하며, 관리자에 게 Lync Server 관리 도구를 보다 쉽게 활용 합니다. 단순 Url에 대 한 자세한 내용은 [Lync Server 2013의 단순 Url 계획](lync-server-2013-planning-for-simple-urls.md)을 참조 하십시오.

Lync Server에서는 모임, 전화 접속, 관리자의 세 가지 간단한 Url을 지원 합니다. 모임 및 전화 접속에 대 한 단순 Url을 설정 해야 하며, 관리자 단순 URL은 선택 사항입니다. 단순 URL을 지원하는 데 필요한 DNS(Domain Name System) 레코드는 이러한 단순 URL을 정의한 방법 및 단순 URL에 대해 재해 복구를 지원할지 여부에 따라 다릅니다.

<div>

## <a name="simple-url-option-1"></a>단순 URL 옵션 1

옵션 1에서는 각 단순 URL에 대한 새로운 기본 URL을 만듭니다.

<div class="">


> [!NOTE]  
> 사용자가 단순 URL 모임 링크를 클릭하면 DNS A 레코드에서 확인하는 서버에서 시작할 올바른 클라이언트 소프트웨어를 결정합니다. 클라이언트 소프트웨어는 시작되는 즉시 전화 회의가 호스팅되는 풀과 자동으로 통신합니다. 따라서 사용자가 단순 URL DNS A 레코드에서 확인한 서버 또는 풀에 관계없이 모임 콘텐츠에 적절한 서버로 이동합니다.



</div>

### <a name="simple-url-option-1"></a>단순 URL 옵션 1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>단순 URL</strong></p></td>
<td><p><strong>예</strong></p></td>
</tr>
<tr class="even">
<td><p>조건</p></td>
<td><p>https://meet.contoso.com, https://meet.fabrikam.com 등은 (조직의 각 SIP 도메인에 대해 하나씩)</p></td>
</tr>
<tr class="odd">
<td><p>전화 접속</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>관리자</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


옵션 1을 사용하는 경우 다음을 정의해야 합니다.

  - 디렉터를 배포한 경우 각 모임 단순 URL에 대해 URL을 디렉터의 IP 주소로 확인하는 DNS A 레코드가 있어야 합니다. 그렇지 않으면 DNS A 레코드에서 프런트 엔드 풀 부하 분산 장치의 IP 주소를 확인해야 합니다. 풀을 배포하지 않고 Standard Edition 서버 배포를 사용하는 경우 DNS A 레코드는 조직에 있는 Standard Edition 서버 하나의 IP 주소를 확인해야 합니다.
    
    조직에 둘 이상의 SIP 도메인이 있는 경우 이 옵션을 사용하려면 각 SIP 도메인에 대해 모임 단순 URL을 만들어야 하며 각 모임 단순 URL에 대한 DNS A 레코드가 있어야 합니다. 예를 들어 contoso.com 및 fabrikam.com가 둘 다 있는 경우 및에 대 한 DNS A 레코드를 https://meet.contoso.com 만듭니다 https://meet.fabrikam.com .
    
    또는 여러 SIP 도메인이 있는 경우 이러한 단순 URL에 필요한 DNS 레코드 및 인증서를 최소화하려면 옵션 3(이 항목의 뒷부분에 나오는 설명 참조)을 사용합니다.

  - 디렉터를 배포한 경우 각 전화 접속 단순 URL에 대해 URL을 디렉터의 IP 주소로 확인하는 DNS A 레코드가 있어야 합니다. 그렇지 않으면 DNS A 레코드에서 프런트 엔드 풀 부하 분산 장치의 IP 주소를 확인해야 합니다. 풀을 배포하지 않고 Standard Edition 서버 배포를 사용하는 경우 DNS A 레코드는 조직에 있는 Standard Edition 서버 하나의 IP 주소를 확인해야 합니다.

  - 관리 단순 URL은 내부 전용입니다. 이 URL에는 디렉터를 배포한 경우 URL을 디렉터의 IP 주소로 확인하는 DNS A 레코드가 있어야 합니다. 그렇지 않으면 DNS A 레코드에서 프런트 엔드 풀 부하 분산 장치의 IP 주소를 확인해야 합니다. 풀을 배포하지 않고 Standard Edition 서버 배포를 사용하는 경우 DNS A 레코드는 조직에 있는 Standard Edition 서버 하나의 IP 주소를 확인해야 합니다.

</div>

<div>

## <a name="simple-url-option-2"></a>단순 URL 옵션 2

옵션 2를 사용하는 경우에는 모임, 전화 접속 및 관리 단순 URL 모두 공통 기본 URL(예: lync.contoso.com)을 사용합니다. 따라서 이러한 단순 URL에 대해 lync.contoso.com을 디렉터 풀 또는 프런트 엔드 풀의 IP 주소로 확인하는 DNS A 레코드가 하나만 있으면 됩니다. 풀을 배포하지 않고 Standard Edition 서버 배포를 사용하는 경우 DNS A 레코드는 조직에 있는 Standard Edition 서버 하나의 IP 주소를 확인해야 합니다.

조직에 둘 이상의 SIP 도메인이 있는 경우 여전히 각 SIP 도메인에 대해 모임 단순 URL을 만들어야 하며 각 모임 단순 URL에 대한 DNS A 레코드가 있어야 합니다. 이 예에서는 세 가지 단순 URL이 모두 lync.contoso.com을 기반으로 하지만 fabrikam.com에 대한 추가 모임 단순 URL이 다른 기본 URL로 설정됩니다. 이 예에서는 및에 대 한 DNS A 레코드를 만들어야 https://lync.contoso.com 합니다 https://lync.fabrikam.com . 단순 URL 옵션 3에서는 여러 SIP 도메인이 있는 이름 지정 및 DNS A 레코드를 처리하는 다른 방법을 보여 줍니다.

### <a name="simple-url-option-2"></a>단순 URL 옵션 2

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>단순 URL</strong></p></td>
<td><p><strong>예</strong></p></td>
</tr>
<tr class="even">
<td><p>조건</p></td>
<td><p>https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet 등은 (조직의 각 SIP 도메인에 대해 하나씩)</p></td>
</tr>
<tr class="odd">
<td><p>전화 접속</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>관리자</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a>단순 URL 옵션 3

옵션 3은 많은 SIP 도메인이 있고 각각에 별도의 단순 URL을 사용하지만 이러한 단순 URL에 필요한 DNS 레코드 및 인증서를 최소화하려는 경우에 가장 유용합니다. 이 예에서는 lync.contoso.com을 디렉터 풀 또는 프런트 엔드 풀의 IP 주소로 확인하는 DNS A 레코드가 하나만 있으면 됩니다.

### <a name="simple-url-option-3"></a>단순 URL 옵션 3

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>단순 URL</strong></p></td>
<td><p><strong>예</strong></p></td>
</tr>
<tr class="even">
<td><p>조건</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>전화 접속</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p>관리자</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a>단순 URL용 재해 복구 옵션

프런트 엔드 풀이 포함 된 사이트가 여러 개 있고 DNS 공급자가 GeoDNS를 지 원하는 경우에는 간단한 url에 대 한 DNS 레코드를 설정 하 여 재해 복구를 지원할 수 있으므로 하나의 전체 프런트 엔드 풀이 다운 되더라도 간단한 URL 기능이 계속 작동 합니다. 이 재해 복구 기능은 모임 및 전화 접속 단순 URL을 지원합니다.

이와 같이 구성하려면 GeoDNS 주소 두 개를 만듭니다. 각 주소에는 재해 복구용으로 쌍으로 지정된 두 개의 풀로 확인되는 DNS A 또는 CNAME 레코드 두 개가 포함됩니다. GeoDNS 주소 중 하나는 내부 액세스용으로 사용되며, 두 풀에 대한 내부 웹 FQDN 또는 부하 분산 장치 IP 주소로 확인됩니다. 나머지 GeoDNS 주소는 외부 액세스용으로 사용되며, 두 풀의 외부 웹 FQDN 또는 부하 분산 장치 IP 주소로 확인됩니다. 아래에는 풀의 FQDN을 사용하는 모임 단순 URL의 예가 나와 있습니다.

   ```console
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```console
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

그런 후에 meet.contoso.com과 같은 모임 단순 URL을 두 개의 GeoDNS 주소로 확인하는 CNAME 레코드를 만듭니다.

<div class="">


> [!NOTE]  
> 네트워크에서 <EM>헤어핀</EM>(조직 내부에서 생성되는 트래픽을 비롯하여 모든 단순 URL 트래픽을 외부 링크를 통해 라우팅)을 사용하는 경우에는 외부 GeoDNS 주소만 구성하고 모임 단순 URL을 해당 외부 주소로만 확인할 수 있습니다.



</div>

이 방법을 사용하는 경우 각 GeoDNS 주소가 라운드 로빈 방법을 사용하여 요청을 두 풀로 분산시키거나, 기본적으로 한 풀(예: 지리적으로 더 가까이 있는 풀)에 연결하고 다른 풀은 연결 오류 시에만 사용하도록 구성할 수 있습니다.

전화 접속 단순 URL에 대해 같은 구성을 설정할 수 있습니다. 이렇게 하려면 앞의 예에서와 같은 추가 레코드를 DNS 레코드로 대체 하 여 `dialin` 만듭니다 `meet` . 관리 단순 URL의 경우 이 섹션 앞부분에 나와 있는 세 가지 옵션 중 하나를 사용합니다.

이 구성을 설정한 후에는 모니터링 응용 프로그램을 사용하여 오류를 감시할 HTTP 모니터링을 설정해야 합니다. 외부 액세스의 경우 모니터를 사용 하 여 HTTPS에서 외부 웹 FQDN에 대 한 자동 검색 요청 또는 두 풀의 부하 분산 장치에 대 한 IP 주소를 모두 올바르게 설정 했는지 확인 합니다. 예를 들어 다음 요청은 **ACCEPT** 헤더를 포함하면 안 되며 **200 OK**를 반환해야 합니다.

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

내부 액세스의 경우에는 두 풀에 대해 내부 웹 FQDN 또는 부하 분산 장치 IP 주소에서 포트 5061을 모니터링해야 합니다. 연결 오류가 감지되면 이러한 풀의 VIP가 포트 80, 443 및 444를 닫아야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

