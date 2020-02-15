---
title: 'Lync Server 2013: Lync Server에서 작동 하도록 Microsoft Exchange Server의 통합 메시징 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cbb859a3cd9f49791eb7b959a59c00c38db6336
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41995973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a>Lync Server 2013에서 작동 하도록 Microsoft Exchange Server의 통합 메시징 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-11_

<div>


> [!IMPORTANT]  
> Exchange UM (통합 메시징)을 사용 하 여 Enterprise Voice users에 대 한 전화 응답, Outlook Voice Access 또는 자동 전화 교환 서비스를 제공 하려는 경우 계획 설명서의 <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Lync Server 2013에서 Exchange 통합 메시징 통합에 대 한 계획</A> 을 읽고이 섹션의 지침을 따르세요.



</div>

Enterprise Voice와 함께 작동 하도록 Exchange UM (통합 메시징)을 구성 하려면 다음 작업을 수행 해야 합니다.

  - Exchange UM (통합 메시징) 서비스를 실행 하는 서버에서 인증서 구성
    
    <div>
    

    > [!NOTE]  
    > 모든 클라이언트 액세스 및 사서함 서버를 모든 UM SIP URI 다이얼 플랜에 추가 합니다. 그렇지 않으면 아웃 바운드 통화 라우팅이 예상 대로 작동 하지 않습니다.

    
    </div>

  - 필요에 따라 하나 이상의 UM SIP URI 다이얼 플랜을 구독자 액세스 전화 번호와 함께 만든 다음 해당 Lync Server 다이얼 플랜을 만듭니다.

  - **Exchucutil.ps1** 스크립트를 사용 하 여 다음을 수행 합니다.
    
      - UM IP 게이트웨이 만들기
    
      - UM 헌트 그룹 만들기
    
      - Lync Server 2013에 UM Active Directory 도메인 서비스 개체를 읽을 수 있는 권한을 부여 합니다.

  - UM 자동 전화 교환 개체를 만듭니다.

  - 구독자 액세스 개체를 만듭니다.

  - 각 사용자에 대해 SIP URI를 만들고 UM SIP URI 다이얼 플랜에 사용자를 연결 합니다.

<div>

## <a name="requirements-and-recommendations"></a>요구 사항 및 권장 사항

시작 하기 전에이 섹션의 설명서에서는 클라이언트 액세스 및 사서함과 같은 Exchange 2013 역할을 배포한 것으로 가정 합니다. Microsoft Exchange Server 2013에서 Exchange UM은 이러한 서버에서 서비스로 실행 됩니다.

Exchange 2013 배포에 대 한 자세한 내용은 다음 위치에서 Exchange 2013 TechNet 라이브러리를 참조 하세요.[http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)

또한 다음에 주의하십시오.

  - Exchange UM이 여러 포리스트에 설치 된 경우 각 UM 포리스트에서 Exchange Server 통합 단계를 수행 해야 합니다. 또한 각 UM 포리스트는 Lync Server 2013이 배포 되는 포리스트를 신뢰 하도록 구성 해야 하며, Lync Server 2013가 배포 되는 포리스트는 각 UM 포리스트를 신뢰 하도록 구성 해야 합니다.

  - 통합 메시징 서비스가 실행 되 고 있는 Exchange 서버 역할과 Lync Server 2013을 실행 하는 서버에서 함께 수행 하는 작업에 대해 설명 합니다. Lync Server 2013 통합 단계를 수행 하기 전에 Exchange Server 통합 메시징 통합 단계를 수행 해야 합니다.
    
    <div>
    

    > [!NOTE]  
    > 어떤 서버에서 어떤 통합 단계를 수행 하 고 어떤 관리자 역할을 사용 하는지 확인 하려면 <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">온-프레미스 통합 메시징 및 Lync Server 2013 통합을 위한 배포 프로세스</A>를 참조 하십시오.

    
    </div>

다음 도구는 Exchange UM을 실행 하는 각 서버에서 사용할 수 있어야 합니다.

  - Exchange 관리 셸

  - 다음 작업을 수행하는 스크립트 **exchucutil.ps1**
    
      - 각 Lync Server 2013에 대해 UM IP 게이트웨이를 만듭니다.
    
      - 각 게이트웨이에 대한 헌트 그룹 만들기. 각 헌트 그룹의 파일럿 식별자는 게이트웨이와 연결 된 프런트 엔드 풀 또는 Standard Edition 서버에서 사용 하는 UM SIP URI 다이얼 플랜을 지정 합니다.
    
      - Lync Server 2013에 Active Directory 도메인 서비스에서 Exchange UM 개체를 읽을 수 있는 권한을 부여 합니다.

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

