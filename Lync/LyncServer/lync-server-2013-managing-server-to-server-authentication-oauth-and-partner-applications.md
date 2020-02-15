---
title: 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0d554bc935ea24f7098472a5c893f58dc717839
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a>Lync Server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-05-14_

Microsoft Lync Server 2013는 다른 응용 프로그램 및 서버 제품과 안전 하 고 원활 하 게 통신할 수 있어야 합니다. 예를 들어 연락처 데이터 및/또는 보관 데이터가 Microsoft Exchange Server 2013에 저장 되도록 Lync Server 2013를 구성할 수 있습니다. 그러나 Lync Server와 Exchange가 서로 안전 하 게 통신할 수 있는 경우에만이 작업을 수행할 수 있습니다. 마찬가지로 Microsoft SharePoint Server 내에서 Lync Server 회의를 예약할 수 있습니다. 단, 두 서버 (SharePoint 및 Lync Server)가 서로 신뢰 하는 경우에만이 작업을 수행할 수 있습니다. Lync-Exchange 통신에는 하나의 인증 메커니즘을 사용할 수 있지만 Lync 간 통신을 위한 별도의 메커니즘을 사용 하는 것이 가능 하지만, 모든 서버 간 방식으로 표준화 된 방법을 사용 하는 것이 보다 효율적이 고 효율적인 방법입니다. 인증 및 권한 부여

서버 간 인증에 표준화 된 단일 방법을 사용 하는 것은 Lync Server 2013에서 수행 하는 방법입니다. 2013 릴리스의 경우 Lync Server 2013 (Exchange 2013 및 Microsoft SharePoint Server를 비롯 한 기타 Microsoft 서버 제품)은 서버 간 인증 및 권한 부여에 대 한 OAuth (Open Authorization) 프로토콜을 지원 합니다. 대부분의 주요 웹 사이트에서 사용되는 표준 권한 부여 프로토콜인 OAuth를 사용하는 경우 사용자 자격 증명과 암호가 컴퓨터 간에 전달되지 않습니다. 대신 인증 및 권한 부여는 보안 토큰 교환을 기반으로 하며, 이러한 토큰이 일정 기간 동안 특정 리소스 집합에 대한 액세스 권한을 부여합니다.

OAuth 인증은 일반적으로 한 명의 인증 서버와 서로 통신 해야 하는 두 개의 영역에 대 한 세 가지 당사자를 포함 합니다. 인증 서버를 사용 하지 않고 서버 간 인증을 수행할 수도 있으며이 문서 뒷부분에서 설명할 프로세스입니다. 보안 토큰은 통신 해야 하는 두 영역에 대 한 인증 서버 (보안 토큰 서버 라고도 함)에서 발급 합니다. 이러한 토큰은 한 영역에서 시작 되는 통신을 다른 영역에서 신뢰 해야 하는지 확인 합니다. 예를 들어 권한 부여 서버는 특정 Lync Server 2013 영역의 사용자가 지정 된 Exchange 2013 영역에 액세스할 수 있는지 확인 하는 토큰과 토큰을 발급할 수 있습니다.

<div>


> [!NOTE]
> 영역은 단순한 보안 컨테이너입니다. 기본적으로 Lync Server 2013에서는 기본 SIP 도메인을 OAuth 영역으로 사용 합니다. 추가 SIP 네임 스페이스가 OAuth 인증서의 주체 대체 이름 목록에 추가 됩니다.



</div>

Lync Server 2013에서는 세 가지 서버 간 인증 시나리오를 지원 합니다. Lync Server 2013를 사용 하 여 다음을 수행할 수 있습니다.

  - Lync Server 2013의 온-프레미스 설치와 Exchange 2013 및/또는 Microsoft SharePoint Server의 온-프레미스 설치 간에 서버 간 인증을 구성 합니다.

  - Office 365 구성 요소 쌍 간 (예: Microsoft Exchange 및 Microsoft Lync Server 간, 또는 Microsoft Lync Server와 Microsoft SharePoint 간) 간에 서버 간 인증을 구성 합니다.

  - 크로스-프레미스 환경의 서버 간 인증(온-프레미스 서버와 Office 365 구성 요소 간의 서버 간 인증) 구성

이 시점에서는 Exchange 2013, SharePoint Server 및 Lync Server 2013만 서버 간 인증을 지원 하 고, 이러한 서버 중 하나를 실행 하지 않는 경우에는 OAuth 인증을 완벽 하 게 구현할 수 없게 됩니다.

또한 서버 간 인증을 사용할 필요가 없다는 것을 지적 해야 합니다. Lync Server 2013을 배포 하기 위해 서버 간 인증이 필요 하지는 않습니다. Lync Server 2013이 다른 서버 (예: Exchange 2013)와 통신할 필요가 없는 경우에는 서버 간 인증이 필요 하지 않습니다.

그러나 "통합 연락처 저장소"와 같은 일부 Lync Server의 새로운 기능을 사용 하려는 경우에는 서버 간 인증이 필요 합니다. 통합 연락처 저장소를 사용 하는 경우 Lync server 2013 연락처 정보가 Lync Server 대신 Exchange 2013에 저장 됩니다. 이를 통해 사용자는 Lync, Microsoft Outlook 또는 Microsoft Outlook Web Access 내에서 쉽게 액세스할 수 있는 단일 연락처 집합이 있을 수 있습니다. 통합 연락처 저장소에는 Exchange 2013와 정보를 공유 하기 위해 Lync Server 2013이 필요 하기 때문에 기능을 배포 하려면 서버 간 인증을 사용 해야 합니다. 서버 간 인증은 인스턴트 메시징 세션의 기록이 개별 데이터베이스 레코드가 아닌 Exchange 2013 전자 메일로 저장 되는 Exchange 보관을 사용 하도록 선택한 경우에도 필요 합니다.

Lync server의 Office 365 버전에서 해당 Exchange와 통신 하려면 먼저 Lync Server 2013에서 인증 서버 로부터 보안 토큰을 받아야 합니다. 그러면 Lync Server는이 보안 토큰을 사용 하 여 Exchange에 자신을 식별 합니다. Lync Server 2013와 통신 하려면 Office 365 버전의 Exchange에서 동일한 프로세스를 거쳐야 합니다.

그러나 두 Microsoft 서버 간의 온-프레미스 서버 간 인증에서는 타사 토큰 서버를 사용할 필요가 없습니다. Lync Server 2013 및 Exchange 2013 같은 서버 제품에는 서버 간 인증을 지 원하는 다른 Microsoft 서버 (예: SharePoint Server)의 인증 목적으로 사용할 수 있는 기본 제공 토큰 서버가 있습니다. 예를 들어 Lync Server 2013은 자체적으로 보안 토큰을 발급하고 서명한 다음 해당 토큰을 사용하여 Exchange 2013과 통신할 수 있습니다. 이러한 경우에는 타사 토큰 서버가 필요하지 않습니다.

Lync Server 2013의 온-프레미스 구현에 대해 서버 간 인증을 구성 하려면 다음 두 가지 작업을 수행 해야 합니다.

  - Lync Server의 기본 제공 토큰 발급자에 인증서 할당

  - Lync Server 2013이 통신할 서버를 "파트너 응용 프로그램"으로 구성 합니다. 예를 들어 Lync Server 2013이 Exchange 2013와 통신 해야 하는 경우 Exchange를 파트너 응용 프로그램으로 구성 해야 합니다.

<div>


> [!NOTE]
> "파트너 응용 프로그램"은 Lync Server 2013이 타사 보안 토큰 서버를 거치지 않고도 보안 토큰을 직접 교환할 수 있는 응용 프로그램입니다.



</div>

OAuth는 제품의 핵심 부분 이므로 사용 하지 않도록 설정 하거나 제거할 수 없습니다.

<div>

## <a name="see-also"></a>참고 항목


[Microsoft Lync Server 2013에 서버 간 인증 인증서 할당](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[크로스-프레미스 환경에서 Microsoft Lync Server 2013 구성](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

