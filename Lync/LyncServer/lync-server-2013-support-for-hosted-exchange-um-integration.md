---
title: Lync Server 2013 호스팅된 Exchange UM 통합 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56ba107c9a782acb15ccd8d57f82cf567f2b75e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>Lync Server 2013의 호스팅된 Exchange UM 통합 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

Lync Server 2013 ExUM 라우팅 응용 프로그램은 온-프레미스 환경의 UM (통합 메시징)과 Lync Server 2013 및 Exchange UM을 모두 엔터프라이즈 내에서 로컬로 설치 하거나,에 의해 호스팅되는 Exchange UM과 통합할 수 있도록 지원 합니다. 서비스 공급자 (다음 다이어그램에 표시 됨)

온-프레미스 lync ![Server exchange Um 배포](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "온-프레미스 LYNC Server exchange um 배포")

지원 되는 모드는 다음과 같습니다.

  - **온-프레미스 모드**   Lync Server 2013 및 Exchange UM은 모두 엔터프라이즈 내의 로컬 서버에 배포 됩니다.

  - **크로스-프레미스 모드**   Lync Server 2013는 엔터프라이즈 내의 로컬 서버에 배포 되며 Exchange UM은 Microsoft exchange online 데이터 센터와 같은 온라인 서비스 공급자의 기능에서 호스팅됩니다.

  - **혼합 모드**   Lync Server 2013 배포에는 엔터프라이즈 내에서 Microsoft Exchange Server를 실행 하는 로컬 서버와 호스팅된 Exchange 서비스 데이터 센터에 있는 일부 사서함이 있는 사용자 사서함이 몇 개 있습니다.
    
    <div>
    

    > [!NOTE]  
    > 혼합 모드는 사용자를 호스트 된 Exchange UM로 마이그레이션하는 동안 전환 솔루션으로 사용할 수 있으며, 다른 사용자의 Exchange UM 서비스를 마이그레이션 후에는 일부 사용자에 게 유지 하도록 선택 하는 경우 영구 솔루션으로 사용 됩니다.

    
    </div>

Lync Server 2013을 호스트 된 Exchange UM과 통합 하려면 *공유 SIP 주소 공간* ( *분할 도메인*이 라고도 함)을 구성 해야 합니다. 이 구성에서는 Lync Server 2013와 타사의 호스트 된 Exchange UM 서비스 공급자가 모두 동일한 SIP 도메인 주소 공간에 액세스할 수 있습니다. 자세한 내용은 계획 설명서의 [Lync Server 2013에서 호스팅된 EXCHANGE UM 통합 아키텍처](lync-server-2013-hosted-exchange-um-integration-architecture.md) 를 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

