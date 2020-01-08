---
title: 'Lync Server 2013: IIS 요청 추적 로그 파일 모니터링'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1257e350dd7695bf132959d6b4cde4843192e41
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a>Lync Server 2013에서 IIS 요청 추적 로그 파일 모니터링

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-14_

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

Mcx (Lync Server Mobility Service)에 대 한 IIS (인터넷 정보 서비스) 요청 추적을 사용 하도록 설정 하는 경우 생성 되는 로그 파일은 하루에 최대 3gb의 디스크 공간을 소모할 수 있습니다. IIS 추적 로깅은 기본적으로 사용 하도록 설정 되어 있습니다. 프런트 엔드 서버를 모니터링 하 여 디스크 공간이 부족 한지 확인 해야 합니다.

기본적으로 IIS 는% inetpub\\\\\\%의 로그 파일을 저장 합니다.

전체 서버에 대해 IIS 요청 추적을 해제 하려면 명령줄에 다음을 입력 합니다.

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

**HttpLogging** 명령에 대 한 자세한 내용은을 [http://go.microsoft.com/fwlink/p/?linkId=234927](http://go.microsoft.com/fwlink/p/?linkid=234927)참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

