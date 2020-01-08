---
title: 'Lync Server 2013: Exchange 및 SharePoint 통합 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c4d378337643adf79557bd4bbb649a01948de27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a>Lync Server 2013의 Exchange 및 SharePoint 통합 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2017-01-18_

이러한 제품을 통합 하는 경우 lync Server 2013 및 Lync 2013은 Office 2013, Exchange Server 2013, Exchange Server 2016, SharePoint를 비롯 한 다른 응용 프로그램 및 서버 제품과 안전 하 고 원활 하 게 통신할 수 있습니다. Lync Server 2013 및 Office를 통합 하면 사용자가 Lync의 인스턴트 메시지 (IM), 향상 된 현재 상태, 전화 통신, 회의 기능에 대 한 컨텍스트에 대 한 액세스를 제공할 수 있습니다. Office 사용자는 Outlook 2013 메시징 및 공동 작업 클라이언트와 다른 Office 프로그램 또는 SharePoint 페이지에서 Lync 기능에 액세스할 수 있습니다. 또한 사용자는 Outlook 대화 내용 폴더에서 Lync 대화 기록을 볼 수 있습니다. Exchange 2013, Exchange 2016 또는 Exchange Online과 통합 되는 경우 Lync Server 2013은 다음 사항도 지원 합니다.

  - Lync 2013, Exchange, Outlook 및 Outlook Web App에서 정보를 전역적으로 사용할 수 있도록 사용자가 Exchange 또는 Exchange Online에 모든 연락처 정보를 저장할 수 있는 통일 된 연락처 저장소.

  - Exchange 사용자 폴더에 저장 되는 대화 기록 및 웹 회의 기록

  - IM 및 모임 콘텐츠와 같은 Lync의 보관 된 콘텐츠는 Exchange 저장소에 저장할 수 있습니다.

<div>


> [!NOTE]  
> Lync Server 2013는 이전 버전의 Microsoft Exchange Server 및 SharePoint Server와의 통합을 지원 하지만, Microsoft Exchange와 함께 보관 저장소 통합과 같은 이전 버전에서는 일부 기능이 지원 되지 않습니다.<BR>사용자를 Exchange 2013 또는 Exchange 2016로 마이그레이션하는 경우 마이그레이션을 완료 하는 동안 Exchange 저장소와 Lync Server 저장소를 중간에 모두 사용할 수 있습니다. Exchange 및 Lync Server 저장소 모두의 영구 사용은 지원 되지 않습니다.



</div>

Lync server 2013와 Exchange Server 및 SharePoint Server를 통합 하려면 Lync Server 2013, Exchange Server 및 SharePoint Server를 실행 하는 서버 간에 서버 간 인증이 필요 합니다. Lync Server 2013는 서버 간 인증 및 권한 부여에 대 한 OAuth (열기 권한 부여) 프로토콜을 지원 합니다. 두 Microsoft 서버 간에 온-프레미스 서버 간 인증의 경우 타사 토큰 서버를 사용할 필요가 없습니다. Lync Server 2013, Exchange Server 및 SharePoint Server에는 서로 인증 목적으로 사용할 수 있는 기본 제공 토큰 서버가 있습니다. 예를 들어 Lync Server 2013는 보안 토큰 자체에 발급 및 서명을 할 수 있으며 Exchange와 통신할 때 해당 토큰을 사용 합니다. 이 경우 타사 토큰 서버를 사용할 필요가 없습니다.

Lync Server 2013는 두 가지 서버 간 인증 시나리오를 지원 합니다. 여기에는 다음과 같은 서버 간 인증 구성이 포함 됩니다.

  - Lync Server 2013의 온-프레미스 설치 및 Exchange Server 2013, Exchange Server 2016 및/또는 SharePoint Server의 온-프레미스 설치

  - 한 쌍의 Office 구성 요소 (예: Microsoft Exchange 365와 Microsoft Lync Server 365 또는 Microsoft Lync Server 365와 Microsoft SharePoint 365)

<div>


> [!NOTE]  
> 온-프레미스 서버와 Office 365 구성 요소 간의 서버 간 인증은이 Lync Server 2013 릴리스에서 지원 되지 않습니다. 즉,이는 Lync Server 2013 및 Microsoft Exchange 365의 온-프레미스 설치 간에 서버 간 인증을 설정할 수 없음을 의미 합니다.



</div>

서버 간 인증에 대 한 자세한 내용은 배포 설명서 또는 작업 설명서의 [Lync server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 를 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

