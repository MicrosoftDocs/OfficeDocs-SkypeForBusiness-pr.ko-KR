---
title: 호스팅된 Exchange UM 통합에 대 한 Lync Server 2013 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 714b10cfc10e101439670eda6ff3810be06b8599
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>Lync Server 2013의 호스팅된 Exchange UM 통합 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

Lync Server 2013 ExUM 라우팅 응용 프로그램은 온-프레미스 환경에서 Lync Server 2013 및 Exchange UM을 모두 회사 내에서 로컬로 설치 하거나, a에 의해 호스트 되는 Exchange UM을 사용 하 여 Exchange um (통합 메시징)과의 통합을 지원 합니다. 다음 다이어그램과 같이 서비스 공급자를 제공 합니다.

![온-프레미스 Lync Server Exchange UM 배포](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "온-프레미스 Lync Server Exchange UM 배포")

다음과 같은 모드가 지원됩니다.

  - **온-프레미스 모드**   Lync Server 2013 및 Exchange UM은 둘 다 엔터프라이즈 내의 로컬 서버에 배포 됩니다.

  - **크로스-프레미스 모드**   Lync Server 2013는 엔터프라이즈 내의 로컬 서버에 배포 되 고 Exchange UM은 Microsoft exchange online 데이터 센터와 같은 온라인 서비스 공급자의 기능을 통해 호스트 됩니다.

  - **혼합 모드**   Lync Server 2013 배포에는 일부 사용자 사서함이 회사 내에서 Microsoft Exchange Server를 실행 하는 로컬 서버와 호스팅된 Exchange 서비스 데이터 센터에 있는 일부 사서함이 포함 되어 있습니다.
    
    <div>
    

    > [!NOTE]  
    > 혼합 모드는 사용자를 호스트 된 Exchange UM으로 마이그레이션 하는 동안 전환 및 진행 하는 동시에 확인 솔루션으로 사용 하거나, 다른 사용자를 마이그레이션 한 후에 일부의 Exchange UM 서비스를 온-프레미스로 유지 하는 경우 영구 솔루션으로 사용할 수 있습니다.

    
    </div>

Lync Server 2013을 호스팅된 Exchange UM과 통합 하려면 *공유 SIP 주소 공간* ( *분할 도메인*이 라고도 함)을 구성 해야 합니다. 이 구성에서 Lync Server 2013 및 타사에서 호스트 되는 Exchange UM 서비스 공급자는 모두 동일한 SIP 도메인 주소 공간에 액세스할 수 있습니다. 자세한 내용은 계획 설명서의 [Lync Server 2013에서 호스팅된 EXCHANGE UM 통합 아키텍처](lync-server-2013-hosted-exchange-um-integration-architecture.md) 를 참조 하십시오.

</div>

<span> </span>

</div>

</div>

</div>

