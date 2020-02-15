---
title: 'Lync Server 2013: 응답 그룹에 대 한 기술 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 041f4c6ada99d6991c18b20f77701c78eec8cd95
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42022569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a>Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-11-07_

이 섹션에서는 응답 그룹 응용 프로그램에 대 한 다음 기술 요구 사항에 대해 설명 합니다.

  - 하드웨어 요구 사항

  - 소프트웨어 요구 사항

  - 포트 요구 사항

  - 오디오 파일 요구 사항

  - 응답 그룹 구성 도구 요구 사항

<div>

## <a name="hardware-requirements"></a>하드웨어 요구 사항

응답 그룹 응용 프로그램의 하드웨어 요구 사항은 프런트 엔드 서버와 동일 합니다. 하드웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [server 하드웨어 플랫폼 For Lync server 2013](lync-server-2013-server-hardware-platforms.md) 을 참조 하십시오.

</div>

<div>

## <a name="software-requirements"></a>소프트웨어 요구 사항

응답 그룹 응용 프로그램은 프런트 엔드 서버와 동일한 운영 체제 요구 사항 및 소프트웨어 필수 구성 요소를 포함 합니다. 소프트웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 서버 및 도구 운영 체제 지원을](lync-server-2013-server-and-tools-operating-system-support.md) 참조 하십시오.

응답 그룹 음악 및 알림에 대해 Windows Media 오디오 (.wma) 파일을 사용 하는 경우 응답 그룹 응용 프로그램을 실행 하는 모든 프런트 엔드 서버 또는 Standard Edition 서버에 windows Media 형식 런타임이 설치 되어 있어야 합니다. Windows Server 2012 또는 Windows Server 2012 r 2를 실행 하는 서버에 대 한 서버 2008 R2 또는 Microsoft Media Foundation Windows Server 2008 R2의 경우 windows Media 형식 런타임이 Windows 데스크톱 환경의 일부로 설치 됩니다.

오디오 요구 사항에 대한 자세한 내용은 이 섹션의 뒷 부분에 나오는 "오디오 파일 요구 사항"을 참조하십시오.

</div>

<div>

## <a name="port-requirements"></a>포트 요구 사항

응답 그룹 응용 프로그램은 다음 포트를 사용 합니다.

  - ****   SIP 수신 대기 요청에 사용 되는 포트 5071

  - ****   서버 간 통신에 사용 되는 포트 8404
    
    <div>
    

    > [!NOTE]  
    > 이 포트는 일치 서비스에 사용 되며, 응답 그룹 응용 프로그램을 프런트 엔드 서버가 두 개 이상 있는 풀에 배포 하는 경우에 필요 합니다.

    
    </div>

<div>


> [!NOTE]  
> 이러한 포트는 <STRONG>Set-CsApplicationServer</STRONG> cmdlet을 사용하여 변경할 수 있는 기본 설정입니다. 이 cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하십시오.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>오디오 파일 요구 사항

응답 그룹 응용 프로그램은 응답 그룹 메시지, 대기 음악 또는 IVR (대화형 음성 응답) 질문에 대 한 웨이브 (.wav) 파일 형식과 Windows Media 오디오 (.wma) 파일 형식을 지원 합니다.

Windows Media 오디오 파일 형식을 사용 하려면 windows Media 형식 런타임이 Windows Server 2008 R2 및 Windows Server 2008를 실행 하는 프런트 엔드 서버에 설치 되어 있어야 합니다. 자세한 내용은 이 섹션의 앞 부분에 있는 "소프트웨어 요구 사항"을 참조하십시오.

<div>

## <a name="supported-wave-file-formats"></a>지원되는 웨이브 파일 형식

모든 웨이브 파일은 다음 요구 사항을 충족해야 합니다.

  - 8비트 또는 16비트 파일

  - LPCM(선형 펄스 부호 변조), A-Law 또는 mu-Law 형식

  - 모노 또는 스테레오

  - 4MB 이하

최상의 웨이브 파일 성능을 위해서는 16kHz/모노/16비트의 웨이브 파일을 사용하는 것이 좋습니다.

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a>지원되는 Windows Media 오디오 파일 형식

Windows Media 오디오 파일을 사용할 경우 낮은 비트 전송률을 사용하고 시스템 성능이 정상인지 확인합니다.

Microsoft Expression Encoder 4를 사용하여 파일을 Windows Media 오디오 형식으로 변환할 수 있습니다. 수식 인코더 4를 다운로드 하려면를 [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)참조 하세요.

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a>응답 그룹 구성 도구 요구 사항

응답 그룹 구성 도구는 다음 표에 설명 된 운영 체제 및 웹 브라우저의 조합을 지원 합니다.

<div>


> [!NOTE]  
> 32비트 또는 64비트 버전의 운영 체제가 지원됩니다. 32비트 버전의 Internet Explorer만 지원됩니다.



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
<td><p>Windows Vista SP(서비스 팩) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8(기본 모드)</p>
<p>Internet Explorer 9(기본 모드)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 서비스 팩 1</p></td>
<td><p>Internet Explorer 8(기본 모드)</p>
<p>Internet Explorer 9(기본 모드)</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 서비스 팩 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8(기본 모드)</p>
<p>Internet Explorer 9(기본 모드)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 서비스 팩 1</p></td>
<td><p>Internet Explorer 8(기본 모드)</p>
<p>Internet Explorer 9(기본 모드)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a>응답 그룹 에이전트 콘솔

에이전트 콘솔은 다음 표에 설명된 운영 체제 및 웹 브라우저의 조합을 지원합니다.

<div>


> [!NOTE]  
> 32비트 또는 64비트 버전의 운영 체제가 지원됩니다. 32비트 버전의 Internet Explorer만 지원됩니다.



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
<td><p>Windows Vista SP(서비스 팩) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8(기본 모드)</p>
<p>Internet Explorer 9(기본 모드)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 서비스 팩 1</p></td>
<td><p>Internet Explorer 8(기본 모드)</p>
<p>Internet Explorer 9(기본 모드)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 서비스 팩 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8(기본 모드)</p>
<p>Internet Explorer 9(기본 모드)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 서비스 팩 1</p></td>
<td><p>Internet Explorer 8(기본 모드)</p>
<p>Internet Explorer 9(기본 모드)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

