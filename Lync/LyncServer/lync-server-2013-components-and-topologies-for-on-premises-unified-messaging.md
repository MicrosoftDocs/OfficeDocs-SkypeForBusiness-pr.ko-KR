---
title: 'Lync Server 2013: 온-프레미스 통합 메시징의 구성 요소 및 토폴로지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94a22348ca5b0f17415edf0a4f259d5c58d473a9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a>Lync Server 2013의 온-프레미스 통합 메시징에 대 한 구성 요소 및 토폴로지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-25_

이 항목에서는 Lync Server 2013 배포에 Exchange UM (통합 메시징) 기능을 제공 하는 데 필요한 Microsoft Exchange Server 2013 구성 요소에 대해 설명 합니다. 또한 온-프레미스 Exchange UM 통합을 위해 지원 되는 토폴로지에 대해 설명 합니다.

<div>

## <a name="exchange-server-components"></a>Exchange Server 구성 요소

[통합 메시징 및 Lync Server 2013의 기능](lync-server-2013-features-of-integrated-unified-messaging.md) 에 설명 된 Exchange UM 기능 및 서비스를 조직의 음성 사용자에 게 제공 하려면 사용자 사서함을 호스트 하 고 전자 메일 및 음성 메일에 대해 단일 저장소 위치를 제공 하는 Microsoft Exchange 사서함 서버 및 클라이언트 액세스 서버를 배포 해야 합니다. Exchange UM은 Exchange 사서함 및 클라이언트 액세스 서버에서 서비스로 실행 됩니다.

Microsoft Exchange Server 2007 및 Microsoft Exchange Server 2010의 Exchange UM 구성 요소에 대 한 자세한 내용은 배포 설명서에서 [온-프레미스 EXCHANGE um을 배포 하 여 Lync Server 2013 음성 메일 제공을](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) 참조 하십시오.

</div>

<div>

## <a name="supported-topologies"></a>지원되는 토폴로지

Lync Server 2013 및 Exchange UM (통합 메시징)을 같은 포리스트나 여러 포리스트에 배포할 수 있습니다. 배포가 여러 포리스트에 걸쳐 있는 경우 각 Exchange UM 포리스트에 대해 Exchange 통합 단계를 수행 해야 합니다. 또한 각 Exchange UM 포리스트를 신뢰 하기 위해 Lync Server 2013 포리스트와 Lync Server 2013 포리스트를 신뢰 하도록 각 Microsoft Exchange 포리스트를 구성 해야 합니다. 이 포리스트 트러스트 외에도, 모든 사용자에 대 한 Exchange UM 설정은 Lync Server 2013 포리스트의 사용자 개체에서 설정 해야 합니다.

Lync Server 2013는 Exchange UM 통합을 위해 다음과 같은 토폴로지를 지원 합니다.

  - 단일 포리스트

  - 단일 도메인 (단일 도메인이 포함 된 단일 포리스트) Lync Server 2013, Microsoft Exchange 및 사용자는 모두 동일한 도메인에 있습니다.

  - 여러 도메인 (하나 이상의 자식 도메인이 있는 루트 도메인) Lync Server 2013 및 Microsoft Exchange 서버는 사용자를 만드는 도메인과 다른 도메인에 배포 됩니다. Exchange UM 서버는 지원 되는 Lync Server 2013 풀과는 다른 도메인에 배포할 수 있습니다.

  - 다중 포리스트 (즉, 리소스 포리스트) Lync Server 2013은 단일 포리스트에 배포 된 다음 사용자가 여러 포리스트에 분산 되어 있습니다. 사용자의 Exchange UM 특성을 Lync Server 2013 포리스트로 복제 해야 합니다.
    
    <div>
    

    > [!NOTE]  
    > 여러 포리스트에 Exchange를 배포할 수 있습니다. 각 Exchange 조직은 사용자에 게 Exchange UM을 제공할 수도 있고, Exchange UM을 Lync Server 2013와 동일한 포리스트에 배포할 수도 있습니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

