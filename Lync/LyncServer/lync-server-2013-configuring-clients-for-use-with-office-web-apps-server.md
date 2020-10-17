---
title: 'Lync Server 2013: Office Web Apps 서버에서 사용할 클라이언트 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bf46a16d38e37dd8faac39a438053dcc7b8c103
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537065"
---
# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a>Office Web Apps 서버에서 사용할 Lync Server 2013의 클라이언트 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-25_

사용자가 Office Web App 서버의 전체 기능을 경험할 수 있도록 하려면 해당 사용자를 Microsoft Lync 2013로 업그레이드 해야 합니다. Lync 2013의 사용자만이 실제 PowerPoint 프레젠테이션에 관계 없이 PowerPoint 슬라이드를 스크롤할 수 있습니다. 즉, 이러한 사용자는 실제 프레젠테이션을 사용 하지 않고 언제 든 지 프레젠테이션의 모든 슬라이드를 볼 수 있습니다. Lync 2013을 사용 하 고 있지 않은 사용자는 여전히 온라인 회의에 참가 하 고 PowerPoint 프레젠테이션을 볼 수 있습니다. 그러나 슬라이드를 독립적으로 스크롤하거나 슬라이드 전환을 보거나 포함 된 동영상을 볼 수는 없습니다.

이러한 기능은 항상 Lync 2013 사용자에 게 제공 됩니다. 이는 PowerPoint 발표자가 Microsoft Lync 2010을 실행 하는 경우에도 마찬가지입니다. Lync 2010을 실행 하는 사용자가 PowerPoint 프레젠테이션을 호스팅하는 경우 lync Server 2013은 Office Web Apps 서버와 함께 조정 되어 Lync 2013 사용자가 해당 프레젠테이션의 Office Web Apps 서버 버전을 볼 수 있도록 합니다. Office Web Apps 서버는 Lync 2013 이외의 클라이언트를 실행 하는 사용자에 게 PowerPoint 서비스를 제공 하지 않습니다. 대신 이러한 사용자는 회의 서버 서비스에 연결 하 여 Microsoft Lync Server 2010에서와 같은 방식으로 PowerPoint 프레젠테이션을 봅니다. 또한 이러한 사용자는 Lync Server 2010에서 제공 하는 제한 된 기능에만 액세스할 수 있음을 의미 합니다.

Office Web Apps 서버에서 사용자를 Lync 2013로 업그레이드 하는 것 외에 클라이언트 구성은 필요 하지 않지만 전화 회의 참가자를 Internet Explorer 9로 업그레이드 하는 것이 좋습니다. Internet Explorer 8을 사용 하 여 회의에 액세스할 수 있지만 웹 브라우저를 사용할 때는 몇 가지 제한 사항이 있습니다. 예를 들어 Internet Explorer 8 사용자는 PowerPoint 스테이지의 크기를 사용자 지정 크기로 조정할 수 없습니다. 대신 미리 정의 된 3 가지 스테이지 크기 중 하나를 사용 하는 것으로 제한 됩니다. 마찬가지로 Internet Explorer 8 사용자는 미디어 파일을 재생할 수 없습니다.

</div>

<span> </span>

</div>

</div>

</div>

