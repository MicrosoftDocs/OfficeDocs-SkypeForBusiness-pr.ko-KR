---
title: 'Lync Server 2013: 단순 URL에 대한 DNS 요구 사항'
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
ms.openlocfilehash: 2a05b5e5afc645c9219d02c8a551e4c0af9d93b0
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a>Lync Server 2013의 단순 URL에 대한 DNS 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-22_

Lync Server 2013는 사용자에 게 모임 참가를 더욱 쉽게 할 수 있도록 하는 간단한 Url을 지원 하 고, 관리자에 게 Lync Server 관리 도구를 더 쉽게 만들 수 있습니다. 간단한 Url에 대 한 자세한 내용은 [Lync Server 2013의 간단한 Url 계획](lync-server-2013-planning-for-simple-urls.md)을 참조 하세요.

Lync Server는 회의, 전화 접속, 관리자의 세 가지 간단한 Url을 지원 합니다. 시작 및 전화 접속에 대 한 간단한 Url을 설정 해야 하며, 관리자 단순 URL은 선택 사항입니다. 간단한 url을 지원 하기 위해 필요한 DNS (Domain Name System) 레코드는 간단한 url을 정의한 방법과 간단한 Url에 대 한 재해 복구를 지원 하는지 여부에 따라 달라 집니다.

<div>

## <a name="simple-url-option-1"></a>간단한 URL 옵션 1

옵션 1에서는 각 단순 URL에 대 한 새 기본 URL을 만듭니다.

<div class="">


> [!NOTE]  
> 사용자가 간단한 URL 모임 링크를 클릭 하면 DNS A 레코드가 확인 되는 서버가 시작 하도록 올바른 클라이언트 소프트웨어를 결정 합니다. 클라이언트 소프트웨어가 시작 되 면 회의가 호스팅되는 풀과 자동으로 통신 합니다. 이 방법으로 사용자는 레코드가 확인 되는 단순 URL DNS 서버 또는 풀에 관계 없이 모임 콘텐츠를 위해 적절 한 서버로 연결 됩니다.



</div>

### <a name="simple-url-option-1"></a>간단한 URL 옵션 1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>간단한 URL</strong></p></td>
<td><p><strong>예</strong></p></td>
</tr>
<tr class="even">
<td><p>시켜</p></td>
<td><p>https://meet.contoso.comhttps://meet.fabrikam.com(조직의 각 SIP 도메인에 대해 하나씩)</p></td>
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


옵션 1을 사용 하는 경우 다음을 정의 해야 합니다.

  - 각각의 단순 URL에 대해 배포 된 경우 디렉터 IP 주소에 대 한 URL을 확인 하는 DNS A 레코드가 필요 합니다. 그렇지 않으면 프런트 엔드 풀의 부하 분산 장치에 대 한 IP 주소로 확인 해야 합니다. 풀을 배포 하지 않고 Standard Edition server 배포를 사용 하는 경우 DNS A 레코드가 조직에 있는 하나의 Standard Edition server의 IP 주소로 확인 되어야 합니다.
    
    조직에 둘 이상의 SIP 도메인이 있고이 옵션을 사용 하는 경우 각 SIP 도메인에 대해 간단한 Url을 생성 해야 하며 각 사용자에 게 맞는 단순 URL에 대 한 DNS A 레코드가 필요 합니다. 예를 들어 contoso.com와 fabrikam.com가 모두 있는 경우 및 https://meet.contoso.com https://meet.fabrikam.com의 두 가지 모두에 대해 DNS A 레코드를 만들게 됩니다.
    
    또는 여러 SIP 도메인이 있고 이러한 간단한 Url에 대 한 DNS 레코드 및 인증서 요구 사항을 최소화 하려면이 항목의 뒷부분에 설명 된 대로 옵션 3을 사용 합니다.

  - 전화 접속 간단한 URL의 경우 배포 된 URL을 사용 하는 경우 디렉터 IP 주소를 확인 하는 DNS A 레코드가 필요 합니다. 그렇지 않으면 프런트 엔드 풀의 부하 분산 장치에 대 한 IP 주소로 확인 해야 합니다. 풀을 배포 하지 않고 Standard Edition server 배포를 사용 하는 경우 DNS A 레코드가 조직에 있는 하나의 Standard Edition server의 IP 주소로 확인 되어야 합니다.

  - 관리 단순 URL은 내부 전용입니다. 배포 된 사용자가 있는 경우 해당 URL을 디렉터 IP 주소로 확인 하는 DNS A 레코드가 필요 합니다. 그렇지 않으면 프런트 엔드 풀의 부하 분산 장치에 대 한 IP 주소로 확인 해야 합니다. 풀을 배포 하지 않고 Standard Edition server 배포를 사용 하는 경우 DNS A 레코드가 조직에 있는 하나의 Standard Edition server의 IP 주소로 확인 되어야 합니다.

</div>

<div>

## <a name="simple-url-option-2"></a>간단한 URL 옵션 2

옵션 2를 사용 하는 경우, 모임 시작, 전화 접속 로그인, 관리자 단순 Url에는 모두 lync.contoso.com와 같은 일반적인 기본 URL이 있습니다. 따라서 이러한 간단한 Url에 대해 하나의 DNS A 레코드만 필요 하며, 디렉터 풀 또는 프런트 엔드 풀의 IP 주소로 lync.contoso.com 확인 됩니다. 풀을 배포 하지 않고 Standard Edition server 배포를 사용 하는 경우 DNS A 레코드가 조직에 있는 하나의 Standard Edition server의 IP 주소로 확인 되어야 합니다.

조직에 둘 이상의 SIP 도메인이 있는 경우 각 SIP 도메인에 대해 간단한 Url을 사용 해야 하며 각 사용자에 게 맞는 단순 URL에 대 한 DNS A 레코드가 필요 합니다. 이 예제에서는 세 개의 간단한 Url이 모두 lync.contoso.com에 기반을 둔 반면 fabrikam.com에 대 한 추가 소개 간단한 URL이 다른 기본 URL로 설정 됩니다. 이 예제에서는 https://lync.contoso.com 및 https://lync.fabrikam.com에 대 한 DNS A 레코드를 만들어야 합니다. 간단한 URL 옵션 3에는 여러 SIP 도메인이 있는 경우 이름 지정 및 DNS A 레코드를 처리 하는 다른 방법이 나와 있습니다.

### <a name="simple-url-option-2"></a>간단한 URL 옵션 2

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>간단한 URL</strong></p></td>
<td><p><strong>예</strong></p></td>
</tr>
<tr class="even">
<td><p>시켜</p></td>
<td><p>https://lync.contoso.com/Meethttps://lync.fabrikam.com/Meet(조직의 각 SIP 도메인에 대해 하나씩)</p></td>
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

## <a name="simple-url-option-3"></a>간단한 URL 옵션 3

옵션 3은 많은 SIP 도메인이 있고, 별도의 간단한 Url을 사용 하 려 하지만 간단한 url에 대 한 DNS 레코드 및 인증서 요구 사항을 최소화 하려는 경우에 가장 유용 합니다. 이 예제에서는 lync.contoso.com를 디렉터 풀 또는 프런트 엔드 풀의 IP 주소로 확인 하는 하나의 DNS A 레코드만 필요 합니다.

### <a name="simple-url-option-3"></a>간단한 URL 옵션 3

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>간단한 URL</strong></p></td>
<td><p><strong>예</strong></p></td>
</tr>
<tr class="even">
<td><p>시켜</p></td>
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

## <a name="disaster-recovery-option-for-simple-urls"></a>간단한 Url에 대 한 재해 복구 옵션

프런트 엔드 풀을 포함 하는 사이트가 여러 개 있고 DNS 공급자가 GeoDNS를 지 원하는 경우, 장애 복구를 지원 하도록 간단한 Url에 대 한 DNS 레코드를 설정 하 여 전체 프론트 엔드 풀 하나가 다운 되어도 간단한 URL 기능이 계속 됩니다. 이 재해 복구 기능은 모임 및 전화 접속 간단한 Url을 지원 합니다.

이를 구성 하려면 두 개의 GeoDNS 주소를 만듭니다. 각 주소에는 재해 복구용으로 서로 연결 된 두 개의 풀로 확인 되는 두 개의 DNS A 또는 CNAME 레코드가 있습니다. 하나의 GeoDNS 주소는 내부 액세스에 사용 되며, 두 풀의 내부 웹 FQDN 또는 부하 분산 장치 IP 주소로 확인 됩니다. 다른 GeoDNS 주소는 외부 액세스에 사용 되며, 두 풀의 외부 웹 FQDN 또는 부하 분산 장치 IP 주소를 확인 합니다. 다음은 풀에 대 한 Fqdn을 사용 하 여 단순 URL을 충족 하는 예제입니다.

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

그런 다음 두 GeoDNS 주소에 대 한 meet.contoso.com (예:)와 일치 하는 단순 URL을 확인 하는 CNAME 레코드를 만듭니다.

<div class="">


> [!NOTE]  
> 네트워크에서 <EM>hairpinning</EM> 를 사용 하는 경우 (조직 내에서 제공 하는 트래픽을 포함 하 여 외부 링크를 통해 모든 간단한 URL 트래픽을 라우팅하는 경우), 외부 geodns 주소를 구성 하 고 해당 하는 단순 url을 해당 외부 주소로만 해결할 수 있습니다.



</div>

이 메서드를 사용 하는 경우 라운드 로빈 메서드를 사용 하 여 두 개의 풀에 요청을 분산 하거나, 기본 풀 (예: 지리적으로 가까운 풀)에 연결 하 고, 다음의 경우에만 다른 풀을 사용 하도록 각 GeoDNS 주소를 구성할 수 있습니다. 연결 실패.

전화 접속 단순 URL에 대해 동일한 구성을 설정할 수 있습니다. 이렇게 하려면 이전 예제와 같은 추가 레코드를 만들고 DNS 레코드 `dialin` `meet` 에서 대체 합니다. 관리 간단한 URL의 경우이 섹션의 앞에 나열 된 세 가지 옵션 중 하나를 사용 합니다.

이 구성을 설정한 후에는 모니터링 응용 프로그램을 사용 하 여 오류를 감시 하도록 HTTP 모니터링을 설정 해야 합니다. 외부 액세스의 경우 모니터에서 외부 웹 FQDN 또는 부하 분산 장치에 대 한 자동 검색 요청이 두 풀에 대해 성공적으로 제공 되는지 확인 합니다. 예를 들어 다음 요청에는 **ACCEPT** 헤더가 없어야 하 고 **200 OK**를 반환 해야 합니다.

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

내부 액세스의 경우 두 풀에 대 한 내부 웹 FQDN 또는 부하 분산 장치 IP 주소에서 포트 5061을 모니터링 해야 합니다. 연결 실패가 감지 되는 경우 이러한 풀의 VIP는 포트 80, 443 및 444을 닫아야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

