---
title: 'Lync Server 2013: 알림 응용 프로그램에 대 한 기술 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1da328ef485d4dcc8bdac316aa31cef8880525c5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42022449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013의 알림 응용 프로그램에 대 한 기술 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-11-07_

이 섹션에서는 알림 응용 프로그램에 대 한 다음과 같은 기술 요구 사항을 설명 합니다.

  - 하드웨어 요구 사항

  - 소프트웨어 요구 사항

  - 포트 요구 사항

  - 오디오 파일 요구 사항

<div>

## <a name="hardware-requirements"></a>하드웨어 요구 사항

알림 응용 프로그램의 하드웨어 요구 사항은 프런트 엔드 서버와 동일 합니다. 하드웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [server 하드웨어 플랫폼 For Lync server 2013](lync-server-2013-server-hardware-platforms.md) 을 참조 하십시오.

</div>

<div>

## <a name="software-requirements"></a>소프트웨어 요구 사항

알림 응용 프로그램은 프런트 엔드 서버와 동일한 운영 체제 요구 사항 및 소프트웨어 필수 구성 요소를 포함 합니다. 소프트웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 서버 및 도구 운영 체제 지원을](lync-server-2013-server-and-tools-operating-system-support.md) 참조 하십시오.

알림 응용 프로그램을 실행 하는 모든 프런트 엔드 서버 또는 Standard Edition 서버에는 windows Server 2008 R2 또는 Windows Server 2012을 실행 하는 서버에 대해 Microsoft Media Foundation을 실행 하는 서버에 대해 Windows Media 형식 런타임이 설치 되어 있어야 합니다. Windows Server 2012 R2 Windows Server 2008 r 2의 경우 windows Media 형식 런타임이 Windows 데스크톱 환경의 일부로 설치 됩니다. Windows Media 형식 런타임 또는 Microsoft Media Foundation은 알림 응용 프로그램이 공지 사항 및 음악에 대해 재생 하는 Windows Media 오디오 (.wma) 파일에 필요 합니다.

</div>

<div>

## <a name="port-requirements"></a>포트 요구 사항

알림 응용 프로그램은 다음 포트를 사용 합니다.

  - ****   SIP 수신 대기 요청에 사용 되는 포트 5071

<div>


> [!NOTE]  
> 이 포트는 기본 설정이며 <STRONG>Set-CsApplicationServer</STRONG> cmdlet을 사용하여 변경할 수 있습니다. 이 cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하십시오.



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

