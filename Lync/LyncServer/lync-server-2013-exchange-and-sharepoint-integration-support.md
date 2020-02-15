---
title: 'Lync Server 2013: Exchange 및 SharePoint 통합 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 566af847bb177173f91634b9b46cceae1d9c88ea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a>Lync Server 2013의 Exchange 및 SharePoint 통합 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2017-01-18_

Lync Server 2013 및 Lync 2013는 이러한 제품을 통합 하는 경우 Office 2013, Exchange Server 2013, Exchange Server 2016 및 SharePoint를 포함 하 여 다른 응용 프로그램 및 서버 제품과 안전 하 고 원활 하 게 통신할 수 있습니다. Lync Server 2013와 Office를 통합 하면 Lync의 IM (인스턴트 메시징), 향상 된 현재 상태, 전화 통신 및 회의 기능에 대 한 컨텍스트 내 액세스 권한이 사용자에 게 제공 됩니다. Office 사용자는 Outlook 2013 메시징 및 공동 작업 클라이언트 및 기타 Office 프로그램 또는 SharePoint 페이지에서 Lync 기능에 액세스할 수 있습니다. 또한 사용자는 Outlook 대화 내용 폴더에서 Lync 대화 기록을 볼 수 있습니다. Exchange 2013, Exchange 2016 또는 Exchange Online과 통합 된 경우 Lync Server 2013은 다음과 같은 항목도 지원 합니다.

  - 통합 연락처 저장소-사용자가 모든 연락처 정보를 Exchange 또는 Exchange Online에 저장 하 여 Lync 2013, Exchange, Outlook 및 Outlook Web App에서 정보를 전역적으로 사용할 수 있도록 합니다.

  - Exchange 사용자 폴더에 저장 되는 대화 내용 및 웹 회의 기록

  - Lync의 보관 된 콘텐츠 (예: IM 및 모임 콘텐츠)는 Exchange 저장소에 저장할 수 있습니다.

<div>


> [!NOTE]  
> Lync Server 2013에서는 이전 버전의 Microsoft Exchange Server 및 SharePoint Server와의 통합을 지원 하지만, Microsoft Exchange와의 보관 저장소 통합과 같은 이전 버전에서는 일부 기능이 지원 되지 않습니다.<BR>사용자를 Exchange 2013 또는 Exchange 2016로 마이그레이션하는 경우 마이그레이션을 완료 하는 동안 Exchange 저장소와 Lync Server 저장소를 중간에 모두 사용할 수 있습니다. Exchange 및 Lync Server 저장소를 모두 영구 사용 하는 것은 지원 되지 않습니다.



</div>

Lync Server 2013와 Exchange Server 및 SharePoint Server를 통합 하려면 Lync Server 2013, Exchange Server 및 SharePoint Server를 실행 하는 서버 간에 서버 간 인증을 사용 해야 합니다. Lync Server 2013에서는 서버 간 인증 및 권한 부여를 위한 OAuth (오픈 인증) 프로토콜을 지원 합니다. 두 개의 Microsoft 서버 사이에 온-프레미스 서버 간 인증을 위해서는 타사 토큰 서버를 사용할 필요가 없습니다. Lync Server 2013, Exchange Server 및 SharePoint Server에는 서로 인증 목적으로 사용할 수 있는 기본 제공 토큰 서버가 있습니다. 예를 들어 Lync Server 2013는 단독으로 보안 토큰을 발급 하 고 서명을 하며, Exchange와 통신할 때 해당 토큰을 사용할 수 있습니다. 이 경우에는 타사 토큰 서버를 사용할 필요가 없습니다.

Lync Server 2013에서는 두 가지 서버 간 인증 시나리오를 지원 합니다. 여기에는 다음 항목 사이의 서버 간 인증 구성이 포함됩니다.

  - 온-프레미스 Lync Server 2013 및 온-프레미스 Exchange Server 2013, Exchange Server 2016 및/또는 SharePoint Server에 대 한 실시간 설치

  - Office 구성 요소 쌍 (예: Microsoft Exchange 365과 Microsoft Lync Server 365 사이, 또는 Microsoft Lync Server 365 및 Microsoft SharePoint 365 사이)

<div>


> [!NOTE]  
> 온-프레미스 서버와 Office 365 구성 요소 간의 서버 간 인증은이 Lync Server 2013 릴리스에서 지원 되지 않습니다. 즉, Lync Server 2013과 Microsoft Exchange 365의 온-프레미스 설치 사이에 서버 간 인증을 설정할 수 없습니다.



</div>

서버 간 인증에 대 한 자세한 내용은 배포 설명서 또는 작업 설명서의 [Lync server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 를 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

