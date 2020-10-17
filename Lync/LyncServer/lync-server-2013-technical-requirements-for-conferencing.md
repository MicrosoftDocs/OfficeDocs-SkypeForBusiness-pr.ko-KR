---
title: Lync Server 2013 회의에 대 한 기술 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d28afb699b63ee3523c7b5d4ae31bf9153459abf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533945"
---
# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a>Lync Server 2013의 회의에 대 한 기술 요구 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-06-25_

Lync Server 2013, 전화 접속 회의, A/V 회의, IM (인스턴트 메시징) 회의 및 웹 회의 기능은 항상 프런트 엔드 서버에서 실행 됩니다.

이 섹션에서는 이러한 서버의 하드웨어 및 소프트웨어 요구 사항과 지원되는 배치에 대해 자세히 설명합니다.

전화 접속 회의는 다양한 구성 요소를 포함하는 기능입니다. 일부 구성 요소는 전화 접속 회의와 관련되며 또 다른 일부 구성 요소는 Enterprise Voice 구성 요소입니다. 이 섹션에서는 전화 접속 회의와 관련된 구성 요소의 요구 사항에 대해 설명합니다. 중재 서버 및 PSTN (공중 전화망) 게이트웨이 요구 사항에 대 한 자세한 내용은 계획 설명서에서 lync server 2013의 중재 서버 [구성 2013 요소](lync-server-2013-mediation-server-component.md) 및 온라인에서 [중재 서버에 대 한 구성 요소 및 토폴로지](lync-server-2013-components-and-topologies-for-mediation-server.md) 를 참조 하십시오.

<div>

## <a name="hardware-requirements"></a>하드웨어 요구 사항

웹 회의와 A/V 회의는 프런트 엔드 서버를 사용 하 여 배치 된 서버 하드웨어 요구 사항은 프런트 엔드 서버와 동일 합니다. 하드웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [server 하드웨어 플랫폼 For Lync server 2013](lync-server-2013-server-hardware-platforms.md) 을 참조 하십시오. 또한 전화 접속 회의에 필요한 다음과 같은 구성 요소도 프런트 엔드 서버와 동일한 하드웨어 요구 사항이 있습니다.

  - 응용 프로그램 서비스

  - 회의 길잡이 응용 프로그램

  - 회의 알림 응용 프로그램

프런트 엔드 서버에 대 한 하드웨어 요구 사항은 Lync Server 2013의 여러 다른 서버 역할에서와 동일 합니다.

</div>

<div>

## <a name="software-requirements"></a>소프트웨어 요구 사항

웹 회의 및 A/V 회의는 프런트 엔드 서버와 배치 된, 서버 소프트웨어 요구 사항은 프런트 엔드 서버와 동일 합니다. 소프트웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 서버 및 도구 운영 체제 지원을](lync-server-2013-server-and-tools-operating-system-support.md) 참조 하십시오.

웹 회의의 경우 Lync Server 2013에서는 PowerPoint 프레젠테이션을 처리 하기 위해 Office Web Apps 및 Office Web Apps 서버 (이전의 WAC Server)도 필요 합니다. 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.

전화 접속 회의의 경우 응용 프로그램 서비스, 회의 수행자 응용 프로그램 및 회의 알림 응용 프로그램은 프런트 엔드 서버와 동일한 운영 체제 요구 사항을 갖습니다. 소프트웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 서버 및 도구 운영 체제 지원을](lync-server-2013-server-and-tools-operating-system-support.md) 참조 하십시오.

회의 전화 교환 응용 프로그램 및 회의 알림 응용 프로그램을 실행 하려면 Windows Media 형식 런타임이 프런트 엔드 서버에 설치 되어 있어야 합니다. Windows Media 형식 런타임은 대기 음악, 녹음된 이름 및 음성 안내에 사용되는 WMA(Windows Media 오디오) 파일을 재생하는 데 필요합니다. Windows Server 2012 및 Windows Server 2012 r 2를 제외 하 고, 설치 프로그램을 실행할 때 windows Media 형식 런타임이 Windows 데스크톱 환경의 일부로 자동 설치 되지만 컴퓨터를 다시 시작 해야 할 수 있습니다. 따라서 설치 프로그램을 실행하기 전에 Windows Media 형식 런타임이 포함된 Windows Desktop Experience의 일부로 설치하는 것이 좋습니다. Windows Server 2012 및 Windows Server 2012 r 2에는 Microsoft Media Foundation이 필요 합니다.

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a>전화 접속 회의에 대한 포트 요구 사항

다음 표에서는 전화 접속 회의에 사용되는 포트에 대해 설명합니다. 부하 분산 장치를 사용하는 경우 풀에서 실행할 응용 프로그램이 사용하는 포트에 대해 부하 분산 장치가 구성되었는지 확인합니다.

이러한 포트는 **Set-CsApplicationServer** cmdlet을 사용하여 변경할 수 있는 기본 설정입니다. 이 cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하십시오.

<div>


> [!NOTE]  
> 풀에서 동일한 응용 프로그램의 모든 인스턴스는 동일한 SIP 수신 대기 포트를 사용합니다.



</div>

### <a name="ports-used-by-dial-in-conferencing"></a>전화 접속 회의에서 사용되는 포트

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>포트 번호</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5072</p></td>
<td><p>SIP 수신 대기 요청에 대해 회의 수행자 응용 프로그램에서 사용 됨</p></td>
</tr>
<tr class="even">
<td><p>5073</p></td>
<td><p>SIP 수신 대기 요청에 대해 회의 알림 응용 프로그램에서 사용 됨</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a>전화 접속 회의에 지원되는 클라이언트

다음 클라이언트를 사용하여 전화 접속 액세스를 지원하는 온-프레미스 회의를 예약할 수 있습니다.

  - Lync 2013 또는 참석자를 설치할 때 자동으로 설치 되는 오프 라인 2013 용 온라인 모임 추가 기능

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a>전화 접속 회의 설정 페이지 요구 사항

전화 접속 회의 설정 페이지에서는 다음 표에 설명 된 운영 체제 및 웹 브라우저의 조합을 지원 합니다.

<div>


> [!NOTE]  
> 32비트 및 64비트 버전의 운영 체제가 지원됩니다.



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>지원되는 운영 체제 및 웹 브라우저

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>운영 체제</th>
<th>웹 브라우저</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows 7</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Firefox</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Internet Explorer 7</p></td>
</tr>
<tr class="odd">
<td><p>Mac OS</p></td>
<td><p>Firefox</p>
<p>Safari</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a>전화 접속 회의에 대한 오디오 파일 요구 사항

Lync Server 2013에서는 전화 접속 회의를 위한 음성 안내 및 음악의 사용자 지정 기능을 지원 하지 않습니다. 그러나 기본 오디오 파일을 변경 해야 하는 강력한 비즈니스 요구 사항이 있는 경우에는 microsoft 기술 자료 문서 961177, [Microsoft Office Communications Server 2007 r 2에서 전화 접속 오디오 회의에 대 한 음성 안내 또는 음악 파일을 사용자 지정 하는 방법을](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177)참조 하세요.

또한 [Microsoft Lync Server 회의 전화 교환 사용자 지정 음성 안내](https://go.microsoft.com/fwlink/p/?linkid=396880) 관리 유틸리티를 사용 하면 전화 발신자가 사용자 지정 프롬프트와 함께 Lync 모임에 참가 하는 경우 다른 모임 항목 환경을 제공 하기 위해 사용 되는 기본 음성 안내를 바꿀 수 있습니다. 사용자 지정 음성 안내는 Lync Server 2010 또는 Lync Server 2013 (Enterprise 또는 Standard Edition)를 실행 하는 서버에 설치할 수 있습니다.

회의 전화 교환 응용 프로그램 및 회의 알림 응용 프로그램은 보류 중인 음악, 기록 된 이름 및 오디오 음성 안내 파일에 대해 다음과 같은 요구 사항을 충족 해야 합니다.

  - WMA(Windows Media 오디오) 파일 형식

  - 16비트 모노

  - 48kbps 2-pass CBR(상수 비트 전송률)

  - -24DB의 음량 수준

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a>전화 접속 회의에 대한 사용자 요구 사항

전화 접속 회의 사용자의 계정에 고유한 전화 번호나 내선 번호가 지정되어야 합니다. 이 요구 사항은 전화 접속 회의를 진행하는 동안 인증을 지원합니다. 엔터프라이즈 사용자 (즉, 조직 내에 Active Directory 도메인 서비스 자격 증명과 Lync Server 계정이 있는 사용자)의 전화 번호 또는 내선 번호를 입력 하 여 인증 된 사용자로 전화를 걸어 회의에 로그인 할 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

