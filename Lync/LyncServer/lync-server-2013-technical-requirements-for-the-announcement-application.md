---
title: 'Lync Server 2013: 알림 응용 프로그램에 대한 기술 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec0da862ce2032f5a659c9e9b7bd3b437349a3cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013의 알림 응용 프로그램에 대한 기술 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-11-07_

이 섹션에서는 알림 신청에 대 한 다음과 같은 기술 요구 사항에 대해 설명 합니다.

  - 하드웨어 요구 사항

  - 소프트웨어 요구 사항

  - 포트 요구 사항

  - 오디오 파일 요구 사항

<div>

## <a name="hardware-requirements"></a>하드웨어 요구 사항

알림 응용 프로그램의 하드웨어 요구 사항은 프런트 엔드 서버와 동일 합니다. 하드웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에 대 한 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md) 을 참조 하세요.

</div>

<div>

## <a name="software-requirements"></a>소프트웨어 요구 사항

알림 신청에는 프런트 엔드 서버와 동일한 운영 체제 요구 사항 및 소프트웨어 필수 구성 요소가 있습니다. 소프트웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 서버 및 도구 운영 체제 지원을](lync-server-2013-server-and-tools-operating-system-support.md) 참조 하세요.

알림 응용 프로그램을 실행 하는 모든 프런트 엔드 서버 또는 Standard Edition 서버에는 windows Server 2008 R2 또는 Windows Server 2012를 실행 하는 서버에 대해 Microsoft Media Foundation을 실행 하는 서버용 Windows Media 형식 런타임이 설치 되어 있어야 합니다. Windows Server 2012 R2. Windows Server 2008 R2의 경우 windows Media 형식 런타임이 Windows 데스크톱 환경의 일부로 설치 됩니다. 알림 응용 프로그램이 공지 사항 및 음악에 대해 재생 하는 Windows media 오디오 (.wma) 파일에는 windows Media 형식 런타임 또는 Microsoft Media Foundation이 필요 합니다.

</div>

<div>

## <a name="port-requirements"></a>포트 요구 사항

알림 응용 프로그램에서는 다음 포트를 사용 합니다.

  - ****   SIP 수신 요청에 사용 되는 포트 5071

<div>


> [!NOTE]  
> 이 포트는 기본 설정 이며, <STRONG>Set-CsApplicationServer</STRONG> cmdlet을 사용 하 여 변경할 수 있습니다. 이 cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>오디오 파일 요구 사항

알림 응용 프로그램은 음악 및 알림에 대 한 웨이브 (.wav) 파일 형식과 Windows Media 오디오 (.wma) 파일 형식을 지원 합니다. 알림 응용 프로그램에 대 한 오디오 파일 요구 사항은 응답 그룹 응용 프로그램의 경우와 동일 합니다. 자세한 내용은 [Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-response-group.md)참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

