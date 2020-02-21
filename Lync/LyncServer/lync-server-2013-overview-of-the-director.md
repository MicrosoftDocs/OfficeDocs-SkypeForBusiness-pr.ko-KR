---
title: 'Lync Server 2013: 디렉터 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cf4e40f211cb992e914be20dc9962d55f229bc2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a>Lync Server 2013의 디렉터 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-08_

디렉터는 사용자 요청을 인증 하지만 사용자 계정을 사용 하지 않는 Lync Server 2013을 실행 하는 서버입니다. 선택적으로 디렉터를 배포할 수 있는 두 가지 시나리오는 다음과 같습니다.

  - 에 지 서버를 배포 하 여 외부 사용자가 액세스할 수 있도록 설정 하는 경우에는 디렉터도 배포 해야 합니다. 이 시나리오에서는 디렉터가 외부 사용자를 인증 한 다음 트래픽을 내부 서버에 전달 합니다. 디렉터를 사용 하 여 외부 사용자를 인증 하는 경우 프런트 엔드 풀 서버는 이러한 사용자의 인증을 수행 하는 오버 헤드에서 제거할 수 있습니다. 또한 서비스 거부 공격과 같은 악의적인 트래픽에 대 한 내부 프런트 엔드 풀을 방지 하는 데에도 도움이 됩니다. 이러한 공격에 잘못 된 외부 트래픽이 발생 하는 네트워크의 경우에는 디렉터에서이 트래픽을 종료 합니다.

  - 중앙 사이트에 여러 프런트 엔드 풀을 배포 하는 경우 해당 사이트에 디렉터를 추가 하면 인증 요청을 합리화 하 고 성능을 향상 시킬 수 있습니다. 이 시나리오에서는 모든 요청이 먼저 디렉터로 이동한 다음 올바른 프런트 엔드 풀로 라우팅합니다.

</div>

<span> </span>

</div>

</div>

</div>

