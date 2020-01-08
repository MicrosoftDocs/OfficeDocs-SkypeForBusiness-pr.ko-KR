---
title: 'Lync Server 2013: 역방향 프록시에 대한 인증서 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be12aabd8c4d7aa026e6c7e1ab6f1d5189a596c8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013에서 역방향 프록시에 대한 인증서 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-08_

각 역방향 프록시 서버에는 수신 서비스에서 사용할 웹 서버 인증서가 필요 합니다. 웹 서버 인증서는 공용 CA (인증 기관)에서 발급 해야 합니다.

이 및 기타 인증서 요구 사항에 대 한 자세한 내용은 [Lync Server 2013에서 외부 사용자 액세스에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-external-user-access.md)참조 하세요.

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a>역방향 프록시에 대 한 웹 서비스 인증서를 설정 하려면

  - 웹 서비스 인증서 설정을 포함 하 여 역방향 프록시를 이미 설정 해야 합니다. Edge 서버의 배포를 시작 하기 전에이 작업을 수행 하지 않은 경우 [Lync Server 2013의 리버스 프록시 서버 설정](lync-server-2013-setting-up-reverse-proxy-servers.md) 절차를 사용 하 여 요청을 만들고 웹 서비스 인증서를 설치한 다음 각 웹 게시 규칙을 만들고 인증서를 사용 하도록 구성 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

