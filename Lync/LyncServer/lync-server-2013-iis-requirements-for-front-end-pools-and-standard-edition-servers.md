---
title: 프런트 엔드 풀 및 Standard Edition server에 대 한 IIS 요구 사항
description: 프런트 엔드 풀 및 Standard Edition server에 대 한 IIS 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f56452c7e47352333ac3ac5a51d649b0828a0ff9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573344"
---
# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a>Lync Server 2013의 프런트 엔드 풀 및 Standard Edition 서버에 대 한 IIS 요구 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-06-19_

Standard Edition 서버 및 프런트 엔드 서버 및 디렉터의 경우 Lync Server 2013 installer는 다음과 같은 목적으로 IIS (인터넷 정보 서비스)에서 가상 디렉터리를 만듭니다.

  - 사용자가 주소록 서비스에서 파일을 다운로드할 수 있도록 설정 하려면

  - 클라이언트에서 업데이트를 가져올 수 있도록 설정 하려면

  - 회의를 사용 하도록 설정 하려면

  - 사용자가 모임 콘텐츠를 다운로드할 수 있도록 설정 하려면

  - 사용자가 메일 그룹을 확장할 수 있도록 설정 하려면

  - 전화 회의를 사용 하도록 설정 하려면

  - 응답 그룹 기능을 사용 하도록 설정 하려면

또한 Lync Server 2010 용 누적 업데이트: 11 월 2011 설치 관리자는 다음 목적을 위해 IIS에서 가상 디렉터리를 만듭니다.

  - 모바일 장치에서 IM (인스턴트 메시징) 및 현재 상태와 같은 모바일 기능을 지원 하기 위한 프런트 엔드 서버 또는 Standard Edition server

  - 모바일 장치에서 이동성 리소스를 자동으로 검색할 수 있도록 프런트 엔드 서버 또는 Standard Edition 서버 및 디렉터에서



> [!NOTE]
> 모바일 기능을 배포 하는 경우에는 IIS 7.5를 사용 하는 것이 좋습니다. Lync Server Mobility Service installer는 성능을 개선 하기 위해 몇 가지 ASP.NET 플래그를 설정 합니다. IIS 7.5는 Windows Server 2008 R2에서 기본적으로 설치되며, Mobility Service 설치 관리자는 ASP.NET 설정을 자동으로 변경합니다. Windows Server 2008에서 IIS 7.0을 사용하는 경우에는 이러한 설정을 수동으로 변경해야 합니다.



Lync Server를 사용 하려면 다음 IIS 모듈을 설치 해야 합니다.


> [!IMPORTANT]
> 조직에서 IIS 및 모든 웹 서비스를 시스템 드라이브가 아닌 다른 드라이브에 배치 해야 하는 경우 설치 대화 상자에서 Lync Server 파일의 설치 위치 경로를 변경할 수 있습니다. OCSCore.msi를 포함 하 여이 경로에 설치 파일을 설치 하면 나머지 Lync Server 파일이이 드라이브에도 배포 됩니다. IIS를 설치할 때 Windows Server 관리자가 배포한 INETPUB의 위치를 변경 하는 방법에 대 한 자세한 내용은를 참조 하십시오 <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> .


  - 정적 콘텐츠

  - 기본 문서

  - HTTP 오류

  - ASP.NET

  - .NET 확장성

  - ISAPI(인터넷 서버 API) 확장

  - ISAPI 필터

  - HTTP 로깅

  - 로깅 도구

  - 추적은

  - Windows 인증

  - 요청 필터링

  - 정적 콘텐츠 압축

  - 동적 콘텐츠 압축

  - IIS 관리 콘솔

  - IIS 관리 스크립트 및 도구

  - 익명 인증 (IIS가 설치 될 때 기본적으로 설치 됨)

  - 클라이언트 인증서 매핑 인증

다음 표에는 내부 액세스를 위한 가상 디렉터리의 Uri와 해당 사용자가 참조 하는 파일 시스템 리소스가 나와 있습니다.

### <a name="virtual-directories-for-internal-access"></a>내부 액세스용 가상 디렉터리

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>기능</th>
<th>가상 디렉터리 URI</th>
<th>참조 대상</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>주소록 서버</p></td>
<td><p>https:// &lt; 내부 FQDN &gt; /ABS/int/Handler</p></td>
<td><p>내부 사용자 용 주소록 서버 다운로드 파일의 위치</p></td>
</tr>
<tr class="even">
<td><p>자동 검색 서비스</p></td>
<td><p>https:// &lt; 내부 FQDN &gt; /자동 검색</p></td>
<td><p>내부 모바일 장치 사용자에 대 한 모바일 리소스를 찾는 Lync Server 자동 검색 서비스의 위치입니다.</p></td>
</tr>
<tr class="odd">
<td><p>클라이언트 업데이트</p></td>
<td><p>http:// &lt; 내부 FQDN &gt; /AutoUpdate/Int</p></td>
<td><p>내부 컴퓨터 기반 클라이언트용 업데이트 파일의 위치</p></td>
</tr>
<tr class="even">
<td><p>회의</p></td>
<td><p>http:// &lt; 내부 FQDN &gt; /vrvi</p></td>
<td><p>내부 사용자에 대 한 회의 리소스의 위치입니다.</p></td>
</tr>
<tr class="odd">
<td><p>장치 업데이트</p></td>
<td><p>http:// &lt; 내부 FQDN &gt; /DeviceUpdateFiles_Int</p></td>
<td><p>내부 UC 장치에 대 한 UC (통합 통신) 장치 업데이트 파일의 위치</p></td>
</tr>
<tr class="even">
<td><p>모임</p></td>
<td><p>http:// &lt; 내부 FQDN &gt; /etc/place/null</p></td>
<td><p>내부 사용자에 대 한 모임 콘텐츠 위치입니다.</p></td>
</tr>
<tr class="odd">
<td><p>모바일 서비스</p></td>
<td><p>https:// &lt; 내부 FQDN &gt; /Mcx</p></td>
<td><p>내부 모바일 장치 사용자에 대 한 모바일 서비스 리소스의 위치</p></td>
</tr>
<tr class="even">
<td><p>그룹 확장 및 주소록 웹 쿼리 서비스</p></td>
<td><p>http:// &lt; 내부 FQDN &gt; /GroupExpansion/int/service.asmx</p></td>
<td><p>내부 사용자에 대 한 그룹 확장을 사용 하도록 설정 하는 웹 서비스의 위치입니다. 또한 내부 Lync Mobile Microsoft Lync 2010 모바일 클라이언트에 전체 주소 목록 정보를 제공 하는 주소록 웹 쿼리 서비스의 위치가 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>전화 회의</p></td>
<td><p>http:// &lt; 내부 FQDN &gt; /PhoneConferencing/Int</p></td>
<td><p>내부 사용자에 대 한 전화 회의 데이터의 위치입니다.</p></td>
</tr>
<tr class="even">
<td><p>장치 업데이트</p></td>
<td><p>http:// &lt; 내부 FQDN &gt; /RequestHandler</p></td>
<td><p>내부 UC 장치가 로그를 업로드 하 고 업데이트를 확인할 수 있도록 하는 장치 업데이트 웹 서비스 요청 처리기의 위치입니다.</p></td>
</tr>
<tr class="odd">
<td><p>응답 그룹 응용 프로그램</p></td>
<td><p>http:// &lt; 내부 FQDN &gt; /RgsConfig</p>
<p>http:// &lt; 내부 FQDN &gt; /RgsClients</p></td>
<td><p>응답 그룹 구성 도구의 위치입니다.</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> 통합 된 구성의 프런트 엔드 풀에 대해 서버를 풀에 추가 하려면 먼저 IIS를 배포 해야 합니다.


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="보안이" alt="security" />보안 메모:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Iis 웹 구성 요소 서버에서 사용 하는 인증서를 할당 하려면 IIS 관리 스냅인을 사용 해야 합니다.</td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

