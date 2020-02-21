---
title: 'Lync Server 2013: 클라이언트 부트스트랩 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0a917364c31da4a944f41da586b53bc6a59b6ef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a>Lync Server 2013에서 클라이언트 부트스트랩 정책 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

GPMC (그룹 정책 관리 콘솔) 및 그룹 정책 개체 편집기는 그룹 정책을 관리 하는 데 사용 하는 도구입니다. Office 그룹 정책 관리 템플릿에는 도메인의 그룹 정책 개체에 대해 구성 하는 레지스트리 기반 정책 설정을 포함 하는 adml (ADML) 관리 템플릿, Lync 2013. ADML 파일은 ADMX 파일에 대 한 언어 관련 보완 기능입니다. 각 ADMX 및 ADML 파일에는 단일 Office 응용 프로그램에 대 한 정책 설정이 포함 되어 있습니다. 자세한 내용은 Office 2013 설명서에서 "Office 2013 관리 템플릿 파일 (ADMX, ADML)"를 참조 하세요 <https://go.microsoft.com/fwlink/p/?linkid=267516>.

Lync 2013에는 사용자가 처음으로 서버에 로그인 하기 전에 구성 해야 하는 몇 가지 클라이언트 부트스트랩 정책이 있습니다. 예를 들어 클라이언트에서 로그인이 완료 될 때까지 사용 해야 하는 기본 서버 및 보안 모드를 예로 들 수 있습니다. 그룹 정책을 사용 하 여 사용자의 컴퓨터 레지스트리를 설정 하 고 서버에서 대역내 프로 비전 설정을 받기 시작 하기 전에 이러한 설정을 설정할 수 있습니다. 다음 표에는 Lync 2013에 사용할 수 있는 그룹 정책 설정이 나와 있습니다.

### <a name="group-policy-settings-for-lync-2013"></a>Lync 2013용 그룹 정책 설정

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>그룹 정책 설정</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>서버 지정<br />
ConfigurationMode</p></td>
<td><p>Lync 2013에서 로그인 중에 사용할 전송 및 서버를 식별 하는 방법을 지정 합니다. 이 설정 내에서 다음을 지정 합니다.</p>
<ul>
<li><p>ServerAddressExternal: 외부 방화벽 외부에서 연결할 때 클라이언트 및 페더레이션 대화 상대에 사용 되는 서버 이름 또는 IP 주소를 지정 합니다.</p></li>
<li><p>ServerAddressInternal: 조직의 방화벽 내부에서 클라이언트에 연결할 때 사용 되는 서버 이름이 나 IP 주소를 지정 합니다.</p></li>
<li><p>Transport: TCP (전송 제어 프로토콜) 또는 TLS (전송 계층 보안)를 지정 합니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>추가 서버 버전 지원<br />
(ConfiguredServerCheckValues)</p></td>
<td><p>Lync Server 2013에서 로그온 하는 서버 버전 이름 목록을 세미콜론으로 구분 하 여 지정 하며, 기본적으로 지원 되는 서버 버전과 함께 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>로그인 오류 로그의 자동 업로드 사용 안 함 (Disable자동 Sendtracing)</p></td>
<td><p>분석을 위해 Lync Server에 로그인 오류 로그를 자동으로 업로드 합니다. 로그인이 성공한 경우 로그가 자동으로 업로드 되지 않습니다. 이 정책을 구성 하지 않으면 다음과 같은 결과가 발생 합니다.</p>
<dl>
<dt><span></span></dt>
<dd><p>Lync Online 사용자의 경우: 로그인 오류 로그가 자동으로 업로드 됩니다.</p>
</dd>
<dt><span></span></dt>
<dd><p>Lync 온-프레미스 사용자: 업로드 하기 전에 사용자에 게 확인 대화 상자가 표시 됩니다.</p>
</dd>
</dl>
<p>이 설정을 사용 하지 않으면 Lync 온-프레미스 및 Lync Online 사용자에 대해 로그인 로그가 Lync Server에 자동으로 업로드 됩니다. 이 설정을 사용 하도록 설정 하면 로그인 로그가 자동으로 업로드 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p>SIP 연결에 대해 HTTP 대체 사용 안 함<br />
(DisableHttpConnect)</p></td>
<td><p>TLS 또는 TCP를 사용할 수 없는 경우 Lync Server에서 HTTP를 사용 하 여 서버에 연결할 수 없습니다. 기본적으로 Lync에서는 먼저 TLS 또는 TCP를 사용 하 여 서버에 연결을 시도 하며, 이러한 전송 방법이 모두 실패 하면 Lync는 HTTP를 사용 하 여 연결을 시도 합니다. 이 정책을 사용하여 대체 HTTP 연결 시도를 사용하지 않도록 설정할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>로그온 자격 증명 필요<br />
(DisableNTCredentials)</p></td>
<td><p>사용자가 SIP 서버에 로그인 하는 동안 Windows 자격 증명을 자동으로 사용 하지 않고 Lync에 대 한 로그온 자격 증명을 제공 해야 합니다.</p></td>
</tr>
<tr class="even">
<td><p>서버 버전 검사 사용 안 함<br />
(DisableServerCheck)</p></td>
<td><p>이 정책을 1로 설정 하면 Lync에서 로그인 하기 전에 서버 이름과 버전을 확인할 수 없습니다. 기본적으로 Lync는 로그인 하기 전에 이러한 검사를 수행 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>BITS를 사용 하 여 주소록 서비스 파일 다운로드<br />
(EnableBitsForGalDownload)</p></td>
<td><p>Lync에서 BITS (Background Intelligent Transfer Service)를 사용 하 여 주소록 서비스 파일을 다운로드할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>SIP 보안 모드 구성<br />
(EnableSIPHighSecurityMode)</p></td>
<td><p>Lync에서 인스턴트 메시지를 보다 안전 하 게 보내고 받을 수 있습니다. 이 정책은 Windows .NET 또는 Microsoft Exchange Server 서비스에는 적용되지 않습니다.</p>
<p>이 정책 설정을 구성 하지 않으면 Lync에서 모든 전송을 사용할 수 있습니다. 그러나 TLS를 사용 하지 않고 서버에서 사용자를 인증 하는 경우 Lync에서 NTLM 또는 Kerberos 인증을 사용 해야 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>전체 주소록 다운로드 초기 지연<br />
(GalDownloadInitialDelay)</p></td>
<td><p>GAL (전체 주소 목록)이 다운로드 될 때 까지의 기간을 지정 합니다. 기본값은 60 분 이며,이는 서버가 GAL 파일의 다운로드를 대기 하는 시간을 0 ~ 60 분 사이의 임의 기간 동안 지연 시키는 것을 의미 합니다.</p></td>
</tr>
<tr class="even">
<td><p>사용자가 Microsoft Lync를 실행 하지 못하도록 차단<br />
(PreventRun)</p></td>
<td><p>사용자가 Lync를 실행할 수 없습니다. 컴퓨터 구성 및 사용자 구성 모두에서 이 정책 설정을 구성할 수 있지만 컴퓨터 구성의 정책 설정이 우선합니다.</p></td>
</tr>
<tr class="odd">
<td><p>사용자 암호 저장 허용<br />
SavePassword</p></td>
<td><p>Lync에서 암호를 저장할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>SIP 압축 모드 구성<br />
(SipCompression)</p></td>
<td><p>SIP 압축을 설정할 시점을 지정합니다. 기본적으로 SIP 압축은 어댑터 속도에 따라 설정됩니다. 이 정책을 설정하면 로그인 시간이 길어질 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>신뢰할 수 있는 도메인 목록<br />
(TrustModelData)</p></td>
<td><p>고객 SIP 도메인의 접두사와 일치 하지 않는 신뢰할 수 있는 도메인을 나열 합니다.</p></td>
</tr>
</tbody>
</table>


서버에 구성된 정책은 사용자가 구성한 그룹 정책 설정 또는 클라이언트 옵션보다 우선적으로 적용됩니다. 다음 표에는 설정이 충돌하는 경우의 적용되는 순서가 요약되어 있습니다.

### <a name="group-policy-precedence"></a>그룹 정책 우선 순위

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>우선권</th>
<th>설정 위치 또는 방법</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>개</p></td>
<td><p>Lync Server 2013 대역내 프로 비전</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="odd">
<td><p>3(sp3)</p></td>
<td><p>HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</p></td>
</tr>
<tr class="even">
<td><p>1-4</p></td>
<td><p>Lync 2013의 Lync-옵션 대화 상자</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a>Lync 2013 관리 템플릿 파일을 사용 하 여 그룹 정책 설정을 정의 하려면

1.  모든 언어 중립적 ADMX 파일을 포함할 루트 수준 폴더를 만듭니다. 예를 들어 다음과 같이 이 위치에 도메인 컨트롤러의 중앙 저장소에 대한 루트 폴더를 만듭니다.
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > 이 절차에서는 도메인의 여러 컴퓨터를 관리 하려는 것으로 가정 합니다. 이 경우에는 주 도메인 컨트롤러의 Sysvol 폴더에 있는 중앙 저장소에 템플릿을 저장 합니다. 이를 통해 도메인 관리 템플릿에 대한 복제된 중앙 저장 위치가 마련됩니다.

    
    </div>

2.  사용할 각 언어에 대 한 하위 폴더를 만듭니다. 이러한 하위 폴더는 언어별 ADML 리소스 파일을 포함 합니다. 예를 들어 다음 위치에는 미국 영어 (EN-US) 용 하위 폴더를 만듭니다.
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

