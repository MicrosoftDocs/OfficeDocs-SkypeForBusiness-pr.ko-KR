---
title: 'Lync Server 2013: DNS 요약 - 역방향 프록시'
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
ms.openlocfilehash: ae4834ce608f6726403e8742a4d506b173309b35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>Lync Server 2013의 DNS 요약 - 역방향 프록시

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-22_

리버스 프록시에서 다음과 같이 두 개의 네트워크 어댑터를 구성 합니다.

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>역방향 프록시 네트워크 어댑터 요구 사항

  - **네트워크 어댑터 1 (내부 인터페이스)** 예제
    
    172.25.33.40이 할당 된 내부 인터페이스입니다.
    
    기본 게이트웨이가 정의 되어 있지 않습니다.
    
    역방향 프록시 내부 인터페이스를 포함 하는 네트워크에서 Lync Server 프런트 엔드 풀 서버를 포함 하는 네트워크 (예: 172.25.33.0에서 192.168.10.0)가 있는지 확인 합니다.

  - **네트워크 어댑터 2 (외부 인터페이스)** 예제
    
    최소 하나의 공용 IP 주소가이 네트워크 어댑터에 할당 됩니다.
    
    게이트웨이는 외부 경계에서 라우터 또는 통합 방화벽을 가리키도록 정의 됩니다. (시나리오 예제에서 10.45.16.1)

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
<th>위치/형식/포트</th>
<th>Q</th>
<th>IP 주소</th>
<th>/메모에 매핑</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>외부 DNS/A</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>외부 게시 리소스에 할당 된 수신기</p></td>
<td><p>내부 배포의 외부 웹 서비스. 이 리버스 프록시를 사용 하 고 외부 웹 서비스를 정의한 모든 SIP 도메인에 대해 모든 풀 및 단일 서버에 대해 추가 레코드를 정의 하 고 만들 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>외부 DNS/A</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>외부 게시 리소스에 할당 된 수신기</p></td>
<td><p>배포의 감독 또는 디렉터 풀에 대 한 외부 웹 서비스. 다른 SIP 도메인에 연결 될 수 있는 별도의 디렉터 중에서 디렉터를 한 개까지 정의할 수 있습니다.</p>
<div>

> [!IMPORTANT]  
> 디렉터에 대 한 DNS 레코드를 정의 하 고 게시 하는 것은 프런트 엔드 풀 또는 디렉터 결정이 아닙니다. 디렉터를 사용 하는 경우에는 감독 및 프런트 엔드 풀 외부 웹 서비스를 모두 정의 하 고 게시 해야 합니다. 토폴로지에 정의 되어 있는 경우 인증 및 기타 사용에 대 한 특정 트래픽 종류가 먼저 디렉터로 전송 됩니다.


</div></td>
</tr>
<tr class="odd">
<td><p>외부 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>외부 게시 리소스에 할당 된 수신기</p></td>
<td><p>전화 접속 회의 외부에 게시 됨</p></td>
</tr>
<tr class="even">
<td><p>외부 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>외부 게시 리소스에 할당 된 수신기</p></td>
<td><p>회의가 외부적으로 발표 됨</p></td>
</tr>
<tr class="odd">
<td><p>외부 DNS/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Office Web Apps Server에 할당 된 수신기</p></td>
<td><p>내부 또는 주변에 배포 되 고 외부 클라이언트 액세스용으로 게시 된 Office Web Apps 서버</p></td>
</tr>
<tr class="even">
<td><p>외부 DNS/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>외부 게시 리소스에 할당 된 수신기</p></td>
<td><p>Lync에서 외부 게시 된 자동 검색을 비롯 하 여 모바일, Microsoft Lync Web App, 스케줄러 웹 앱을 검색 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

