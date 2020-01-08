---
title: 'Lync Server 2013: IIS 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de2205ad049beb05f30dd58795257b62eca68d46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a>Lync Server 2013의 IIS 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-17_

이 절차를 성공적으로 완료 하려면 로컬 관리자 및 도메인 사용자로 서버에 최소한으로 로그온 해야 합니다.

Lync Server 2013, Standard Edition 또는 풀의 첫 번째 프런트 엔드 서버에 대 한 프런트 엔드 서버를 구성 하 고 설치 하기 전에 IIS (인터넷 정보 서비스)에 대 한 서버 역할 및 웹 서비스를 설치 하 고 구성 합니다.

<div class=" ">


> [!IMPORTANT]  
> 조직에서 시스템 드라이브가 아닌 다른 드라이브의 모든 웹 서비스를 IIS와 찾아야 하는 경우, Lync Server 2013을 처음 설치 하는 경우 설정 대화 상자에서 Lync Server 2013 파일의 설치 위치 경로를 변경할 수 있습니다. 관리 도구. IIS를 설치 하기 전에 관리 도구를 설치 합니다. OCSCore를 포함 하 여이 경로에 설치 파일을 설치 하는 경우에는 Lync Server 2013 파일의 나머지 부분도이 드라이브에 배포 됩니다. Dtails의 경우 <A href="lync-server-2013-install-lync-server-administrative-tools.md">Lync Server 2013 관리 도구 설치</A>를 참조 하세요. IIS를 설치할 때 Windows Server 관리자가 배포한 INETPUB을 재배치 하는 방법에 대 한 <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>자세한 내용은을 참조 하세요.



</div>

다음 표에서는 필요한 IIS 7.5 역할 서비스를 나타냅니다.

### <a name="iis-75-role-services"></a>IIS 7.5 역할 서비스

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>역할 제목</th>
<th>역할 서비스</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>일반적인 HTTP 기능 설치 됨</p></td>
<td><p>정적 콘텐츠</p></td>
</tr>
<tr class="even">
<td><p>일반적인 HTTP 기능 설치 됨</p></td>
<td><p>기본 문서</p></td>
</tr>
<tr class="odd">
<td><p>일반적인 HTTP 기능 설치 됨</p></td>
<td><p>HTTP 오류</p></td>
</tr>
<tr class="even">
<td><p>응용 프로그램 개발</p></td>
<td><p>ASP.NET</p>
<p>Windows Server 2012에도 ASP. NET 4.5가 필요 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>응용 프로그램 개발</p></td>
<td><p>.NET 확장성</p></td>
</tr>
<tr class="even">
<td><p>응용 프로그램 개발</p></td>
<td><p>ISAPI (인터넷 서버 API) 확장</p></td>
</tr>
<tr class="odd">
<td><p>응용 프로그램 개발</p></td>
<td><p>ISAPI 필터</p></td>
</tr>
<tr class="even">
<td><p>상태 및 진단</p></td>
<td><p>HTTP 로깅</p></td>
</tr>
<tr class="odd">
<td><p>상태 및 진단</p></td>
<td><p>로깅 도구</p></td>
</tr>
<tr class="even">
<td><p>상태 및 진단</p></td>
<td><p>추적할</p></td>
</tr>
<tr class="odd">
<td><p>보안</p></td>
<td><p>익명 인증 (설치 됨 및 기본적으로 사용 가능)</p></td>
</tr>
<tr class="even">
<td><p>보안</p></td>
<td><p>Windows 인증</p></td>
</tr>
<tr class="odd">
<td><p>보안</p></td>
<td><p>클라이언트 인증서 매핑 인증</p></td>
</tr>
<tr class="even">
<td><p>보안</p></td>
<td><p>요청 필터링</p></td>
</tr>
<tr class="odd">
<td><p>성능을</p></td>
<td><p>정적 콘텐츠 압축</p>
<p>동적 콘텐츠 압축</p></td>
</tr>
<tr class="even">
<td><p>관리 도구</p></td>
<td><p>IIS 관리 콘솔</p></td>
</tr>
<tr class="odd">
<td><p>관리 도구</p></td>
<td><p>IIS 관리 스크립트 및 도구</p></td>
</tr>
</tbody>
</table>


Windows Server 2008 R2 SP1 x64 운영 체제에서 Windows PowerShell 2.0을 사용할 수 있습니다. 먼저 ServerManager 모듈을 가져온 다음 IIS 7.5 역할 및 역할 서비스를 설치 해야 합니다.

   ```
    Import-Module ServerManager
   ```

   ```
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> 익명 인증은 IIS 서버 역할을 사용 하 여 기본적으로 설치 됩니다. IIS를 설치한 후에 익명 인증을 관리할 수 있습니다. 자세한 내용은에서 <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>"익명 인증 사용 (IIS 7)"을 참조 하세요.



</div>

다음 표에서는 Windows Server 2012 및 Windows Server 2012 R2에 대 한 필수 IIS 8.0 및 IIS 8.5 역할 서비스를 표시 합니다.

<div class=" ">


> [!NOTE]  
> Windows Server 2012 및 Windows Server 2012 R2의 경우 Add-windowsfeature cmdlet이 설치-Add-windowsfeature cmdlet으로 대체 되었습니다. 자세한 내용은 <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">설치-add-windowsfeature</A>를 참조 하세요.



</div>

### <a name="iis-80-and-iis-85-role-services"></a>IIS 8.0 및 IIS 8.5 역할 서비스

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>역할 제목</th>
<th>역할 서비스</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>웹 서버 (IIS)</p></td>
<td><p>웹 서버</p></td>
</tr>
<tr class="even">
<td><p>일반적인 HTTP 기능</p></td>
<td><p>기본 문서</p></td>
</tr>
<tr class="odd">
<td><p>일반적인 HTTP 기능</p></td>
<td><p>디렉터리 검색</p></td>
</tr>
<tr class="even">
<td><p>일반적인 HTTP 기능</p></td>
<td><p>HTTP 오류</p></td>
</tr>
<tr class="odd">
<td><p>일반적인 HTTP 기능</p></td>
<td><p>정적 콘텐츠</p></td>
</tr>
<tr class="even">
<td><p>일반적인 HTTP 기능</p></td>
<td><p>HTTP 리디렉션</p></td>
</tr>
<tr class="odd">
<td><p>상태 및 진단</p></td>
<td><p>HTTP 로깅</p></td>
</tr>
<tr class="even">
<td><p>상태 및 진단</p></td>
<td><p>로깅 도구</p></td>
</tr>
<tr class="odd">
<td><p>상태 및 진단</p></td>
<td><p>요청 모니터</p></td>
</tr>
<tr class="even">
<td><p>상태 및 진단</p></td>
<td><p>추적할</p></td>
</tr>
<tr class="odd">
<td><p>보안</p></td>
<td><p>요청 필터링</p></td>
</tr>
<tr class="even">
<td><p>보안</p></td>
<td><p>기본 인증</p></td>
</tr>
<tr class="odd">
<td><p>보안</p></td>
<td><p>클라이언트 인증서 매핑 인증</p></td>
</tr>
<tr class="even">
<td><p>보안</p></td>
<td><p>Windows 인증</p></td>
</tr>
<tr class="odd">
<td><p>응용 프로그램 개발</p></td>
<td><p>.Net 확장성 3.5</p></td>
</tr>
<tr class="even">
<td><p>응용 프로그램 개발</p></td>
<td><p>.Net 확장성 4.5</p></td>
</tr>
<tr class="odd">
<td><p>응용 프로그램 개발</p></td>
<td><p>ASP.Net 3.5</p></td>
</tr>
<tr class="even">
<td><p>응용 프로그램 개발</p></td>
<td><p>ASP.Net 4.5</p></td>
</tr>
<tr class="odd">
<td><p>응용 프로그램 개발</p></td>
<td><p>ISAPI 확장</p></td>
</tr>
<tr class="even">
<td><p>응용 프로그램 개발</p></td>
<td><p>ISAPI 필터</p></td>
</tr>
<tr class="odd">
<td><p>응용 프로그램 개발</p></td>
<td><p>서버 쪽 포함</p></td>
</tr>
<tr class="even">
<td><p>관리 도구</p></td>
<td><p>IIS 관리 콘솔</p></td>
</tr>
<tr class="odd">
<td><p>관리 도구</p></td>
<td><p>IIS 6 메타 베이스 호환성</p></td>
</tr>
<tr class="even">
<td><p>관리 도구</p></td>
<td><p>IIS 관리 스크립트 및 도구</p></td>
</tr>
<tr class="odd">
<td><p>.Net 3.5 프레임 워크 기능</p></td>
<td><p>.Net 3.5 프레임 워크</p></td>
</tr>
<tr class="even">
<td><p>.Net 4.5 프레임 워크 기능</p></td>
<td><p>.Net Framework 4.5</p></td>
</tr>
<tr class="odd">
<td><p>.Net 4.5 프레임 워크 기능</p></td>
<td><p>ASP.Net 4.5</p></td>
</tr>
<tr class="even">
<td><p>.Net 4.5 프레임 워크 기능</p></td>
<td><p>HTTP 활성화</p></td>
</tr>
<tr class="odd">
<td><p>.Net 4.5 프레임 워크 기능</p></td>
<td><p>TCP 포트 공유</p></td>
</tr>
<tr class="even">
<td><p>백그라운드 인텔리전트 전송 서비스</p></td>
<td><p>IIS Server Extensions</p></td>
</tr>
<tr class="odd">
<td><p>잉크 및 필기 서비스</p></td>
<td><p>잉크 및 필기 서비스</p></td>
</tr>
<tr class="even">
<td><p>미디어 파운데이션</p></td>
<td><p>미디어 파운데이션</p></td>
</tr>
<tr class="odd">
<td><p>사용자 인터페이스 및 인프라</p></td>
<td><p>그래픽 관리 도구 및 인프라</p></td>
</tr>
<tr class="even">
<td><p>사용자 인터페이스 및 인프라</p></td>
<td><p>데스크톱 환경</p></td>
</tr>
<tr class="odd">
<td><p>사용자 인터페이스 및 인프라</p></td>
<td><p>서버 그래픽 셸</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation 3.5</p></td>
<td><p>Windows Identity Foundation 3.5</p></td>
</tr>
<tr class="odd">
<td><p>Windows Process Activation Service</p></td>
<td><p>프로세스 모델</p></td>
</tr>
<tr class="even">
<td><p>Windows Process Activation Service</p></td>
<td><p>구성 Api</p></td>
</tr>
</tbody>
</table>


Windows Server 2012 및 Windows Server 2012 R2에서 Windows PowerShell 3.0을 사용 하 여 IIS 요구 사항을 설치할 수 있습니다. Windows PowerShell 3.0에서 ServerManager 모듈을 사용 하 여 다음을 입력 합니다.

   ```
    Import-Module ServerManager
   ```

   ```
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> Windows Server 2012의 새로운 기능은 Windows Server 2012 원본 미디어를 찾을 수 있는 위치를 정의 하는 – Source 매개 변수입니다. 미디어는 DVD 드라이브 (예: D:\Sources\Sxs) 또는 미디어 파일이 복사 된 네트워크 공유 (예: \\fileserver\windows2012\sources\Sxs)로 정의할 수 있습니다.



</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 프런트 엔드 풀 및 Standard Edition 서버에 대한 IIS 요구 사항](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

