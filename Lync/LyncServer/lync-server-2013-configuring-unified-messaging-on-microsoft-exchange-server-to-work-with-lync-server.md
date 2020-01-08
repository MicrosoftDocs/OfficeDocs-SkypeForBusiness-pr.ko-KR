---
title: 'Lync Server 2013: Lync Server와 함께 작동하도록 Microsoft Exchange Server의 통합 메시징 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 461d822862e837879f1feb2d3f980b816aae5280
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a>Lync Server 2013과 함께 작동하도록 Microsoft Exchange Server의 통합 메시징 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-11_

<div>


> [!IMPORTANT]  
> UM (통합 메시징)을 사용 하 여 Enterprise Voice 사용자를 위한 전화 접속, Outlook Voice Access 또는 자동 전화 교환 서비스를 제공 하려는 경우 계획 설명서의 <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Lync Server 2013에서 Exchange 통합 메시징 통합에 대 한 계획</A> 을 읽고이 섹션의 지침을 따릅니다.



</div>

엔터프라이즈 음성으로 작업 하도록 Exchange UM (통합 메시징)를 구성 하려면 다음 작업을 수행 해야 합니다.

  - Exchange UM (통합 메시징) 서비스를 실행 하는 서버에서 인증서 구성
    
    <div>
    

    > [!NOTE]  
    > 모든 클라이언트 액세스 및 사서함 서버를 모든 UM SIP URI 다이얼 플랜에 추가 합니다. 그렇지 않은 경우에는 아웃 바운드 통화 라우팅이 예상 대로 작동 하지 않습니다.

    
    </div>

  - 필요에 따라 하나 이상의 UM SIP URI 다이얼 플랜을 구독자 액세스 전화 번호와 함께 만든 다음 해당 Lync Server 다이얼 플랜을 만듭니다.

  - Exchucutil 스크립트를 사용 하 여 다음을 수행 **합니다** .
    
      - UM IP 게이트웨이를 만듭니다.
    
      - UM 헌트 그룹을 만듭니다.
    
      - Lync Server 2013에서 UM Active Directory 도메인 서비스 개체를 읽을 수 있는 권한을 부여 합니다.

  - UM 자동 전화 교환 개체를 만듭니다.

  - 구독자 액세스 개체를 만듭니다.

  - 각 사용자에 대해 SIP URI를 만들고 사용자를 UM SIP URI 다이얼 플랜에 연결 합니다.

<div>

## <a name="requirements-and-recommendations"></a>요구 사항 및 제안

시작 하기 전에이 섹션의 문서에서는 다음과 같은 Exchange 2013 역할을 배포한 것으로 가정 합니다. 클라이언트 액세스 및 사서함. Microsoft Exchange Server 2013에서는 Exchange UM을 이러한 서버에서 서비스로 실행 합니다.

Exchange 2013 배포에 대 한 자세한 내용은 Exchange 2013 TechNet 라이브러리를 참조 하세요.[http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)

또한 다음을 참고 하세요.

  - Exchange UM을 여러 포리스트에 설치 하는 경우 각 UM 포리스트에 대해 Exchange Server 통합 단계를 수행 해야 합니다. 또한 각 UM 포리스트는 Lync Server 2013을 배포 하는 포리스트를 신뢰 하도록 구성 해야 하며, 각 UM 포리스트를 신뢰 하도록 Lync Server 2013를 배포 하는 포리스트를 구성 해야 합니다.

  - 통합 메시징 서비스가 실행 되는 Exchange 서버 역할 및 Lync Server 2013를 실행 하는 서버에 대해 통합 단계를 수행 합니다. Lync Server 2013 통합 단계를 수행 하기 전에 Exchange Server 통합 메시징 통합 단계를 수행 해야 합니다.
    
    <div>
    

    > [!NOTE]  
    > 어떤 서버와 어떤 관리자 역할에 대해 어떤 통합 단계를 수행 해야 하는지 확인 하려면 온 <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">-프레미스 통합 메시징 및 Lync Server 2013 통합에 대 한 배포 프로세스</A>를 참조 하세요.

    
    </div>

Exchange UM을 (를) 실행 하는 각 서버에서 다음 도구를 사용할 수 있어야 합니다.

  - Exchange 관리 셸

  - 다음 작업을 수행 하는 **exchucutil 스크립트.**
    
      - 각 Lync Server 2013에 대해 UM IP 게이트웨이를 만듭니다.
    
      - 각 게이트웨이에 대 한 헌트 그룹을 만듭니다. 각 헌트 그룹의 파일럿 식별자는 게이트웨이와 연결 된 프런트 엔드 풀 또는 Standard Edition 서버에서 사용 하는 UM SIP URI 다이얼 플랜을 지정 합니다.
    
      - Active Directory 도메인 서비스에서 Exchange UM 개체를 읽을 수 있도록 Lync Server 2013 사용 권한을 부여 합니다.

</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Microsoft Exchange Server 통합 메시징을 실행 하는 서버에서 인증서 구성](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [Lync Server 2013 용 Microsoft Exchange에서 통합 메시징 구성](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

