---
title: 'Lync Server 2013: DNS 요약-역방향 프록시'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a468e74206fdc6bad8f078267688450636b8a725
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532145"
---
# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>Lync Server 2013의 DNS 요약-역방향 프록시

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-22_

다음과 같이 역방향 프록시에 네트워크 어댑터 두 개를 구성합니다.

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>역방향 프록시 네트워크 어댑터 요구 사항

  - **네트워크 어댑터 1(내부 인터페이스)** 예
    
    172.25.33.40이 할당된 내부 인터페이스입니다.
    
    기본 게이트웨이가 정의되어 있지 않습니다.
    
    역방향 프록시 내부 인터페이스를 포함 하는 네트워크에서 Lync Server 프런트 엔드 풀 서버가 포함 된 네트워크 (예: 172.25.33.0에서 192.168.10.0로의 경로)가 있는지 확인 합니다.

  - **네트워크 어댑터 2(외부 인터페이스)** 예
    
    이 네트워크 어댑터에는 최소 하나의 공용 IP 주소가 할당됩니다.
    
    게이트웨이는 외부 경계의 통합 방화벽 또는 라우터를 가리키도록 정의됩니다(시나리오 예에서는 10.45.16.1).

### <a name="dns-records-required-for-reverse-proxy"></a>역방향 프록시에 필요한 DNS 레코드

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
<th>IP 주소</th>
<th>매핑 대상/설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>외부 DNS/A</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>외부에 게시된 리소스에 할당되는 수신기</p></td>
<td><p>내부 배포의 외부 웹 서비스입니다. 이 역방향 프록시를 사용하며 외부 웹 서비스를 정의한 모든 SIP 도메인에 대해 모든 풀과 단일 서버용으로 추가 레코드를 정의하고 만들 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>외부 DNS/A</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>외부에 게시된 리소스에 할당되는 수신기</p></td>
<td><p>배포에 있는 디렉터 또는 디렉터 풀에 대 한 외부 웹 서비스입니다. 다른 SIP 도메인과 연결 될 수 있는 여러 디렉터를 각 디렉터로 정의할 수 있습니다.</p>
<div>

> [!IMPORTANT]  
> 디렉터에 대 한 DNS 레코드를 정의 하 고이를 게시 하는 것은 프런트 엔드 풀 또는 디렉터 결정이 아닙니다. 감독을 사용 하는 경우에는 디렉터 및 프런트 엔드 풀 외부 웹 서비스를 모두 정의 하 고 게시 해야 합니다. 토폴로지에 정의 된 경우 인증 및 기타 사용을 위한 특정 트래픽 유형이 디렉터로 먼저 전송 됩니다.


</div></td>
</tr>
<tr class="odd">
<td><p>외부 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>외부에 게시된 리소스에 할당되는 수신기</p></td>
<td><p>전화 접속 회의를 외부적으로 게시하는 데 사용됨</p></td>
</tr>
<tr class="even">
<td><p>외부 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>외부에 게시된 리소스에 할당되는 수신기</p></td>
<td><p>전화 회의를 외부적으로 게시하는 데 사용됨</p></td>
</tr>
<tr class="odd">
<td><p>외부 DNS/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Office Web Apps 서버에 대해 할당 된 수신기</p></td>
<td><p>내부 또는 경계에 배포 되 고 외부 클라이언트 액세스용으로 게시 된 Office Web Apps 서버</p></td>
</tr>
<tr class="even">
<td><p>외부 DNS/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>외부에 게시된 리소스에 할당되는 수신기</p></td>
<td><p>외부에서 게시 된 자동 검색 및 모바일 기능, Microsoft Lync Web App 및 스케줄러 웹 앱을 포함 하는 Lync 검색 외부 레코드</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

