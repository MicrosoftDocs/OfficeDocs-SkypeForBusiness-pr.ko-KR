---
title: 'Lync Server 2013: 오디오 회의 공급자에 대 한 페더레이션 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation for an audio conferencing provider
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn510996(v=OCS.15)
ms:contentKeyID: 60595883
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5c1ca77b2f68a2285fb15d65c19631323a03bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-for-an-audio-conferencing-provider-in-lync-server-2013"></a>Lync Server 2013에서 오디오 회의 공급자에 대 한 페더레이션 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-07-24_

하이브리드 배포에서 ACP (오디오 회의 공급자)를 사용 하려는 경우 (lync Online 포함-온-프레미스), 온-프레미스 Lync 배포와 ACP 파트너 간의 페더레이션을 허용 된 파트너 서버로 구성 해야 합니다. 이 경우에는 온-프레미스 배포의 페더레이션 도메인 목록에 ACP 파트너 도메인 및 Edge 서버 (액세스 프록시 라고도 함)를 추가 하 여 페더레이션을 구성할 수 있습니다. 그런 다음 ACP 파트너는 온-프레미스에 지 서버 풀의 FQDN을 허용 되는 페더레이션 도메인 목록에 추가 해야 합니다. 추가 detailsYour ACP 파트너를 위해 ACP 공급자에 게 문의 하 여 온-프레미스에 지 서버 풀의 FQDN을 허용 된 페더레이션 도메인 목록에 추가 해야 합니다.

  - **ACP 도메인 및 Edge 서버를 허용 되는 페더레이션 도메인으로 추가**
    
    ACP 도메인을 허용 된 파트너 서버 (허용 페더레이션 도메인)로 추가 하려면 [Lync Server 2013에서 허용 되는 외부 도메인에 대 한 지원 구성](lync-server-2013-configure-support-for-allowed-external-domains.md)의 단계를 따르세요. Edge 서버의 경우 ACP 파트너의 Edge 서버의 FQDN을 추가 합니다. 해당 Edge 서버에 대 한 FQDN을 얻으려면 ACP 파트너에 게 문의 하 여 액세스 프록시로도 해당 사용자가 참조할 수 있도록 해야 할 수 있습니다.

  - **ACP 파트너에 대 한 Edge 서버 풀의 FQDN을 제공 합니다.**
    
    ACP 파트너는 허용 되는 페더레이션 도메인으로 사용자의 Edge 서버 풀의 FQDN을 추가 하 여 온-프레미스 도메인을 허용 된 파트너 서버로 추가 하도록 페더레이션을 구성 해야 합니다.

</div>

<span> </span>

</div>

</div>

</div>

