---
title: 'Lync Server 2013: Microsoft Exchange Server 2013과 통합'
description: 'Lync Server 2013: Microsoft Exchange Server 2013과 통합'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54ab4a81e5455bc0a44677b1509876f39ff4d985
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543984"
---
# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Microsoft Lync Server 2013과 Microsoft Exchange Server 2013 통합

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-07-09_

Exchange 및 Lync Server에는 통합 및 호환성에 대 한 긴 기록이 있습니다. 이 통합은 각 클라이언트 응용 프로그램 내에서 가장 잘 나타납니다. 예를 들어 Lync 현재 상태 정보는 Microsoft Outlook에 보고 될 수 있습니다. 마찬가지로 Lync에서는 Outlook 일정을 사용 하 여 현재 상태 정보를 자동으로 업데이트할 수 있습니다. 예를 들어 Lync는 일정에 모임이 예정 되어 있음을 표시 하는 모든 경우에 사용자 상태를 사용 중으로 변경할 수 있습니다. Lync Server를 실행 하기 위해 Exchange를 실행 하지 않아도 되는 경우에도 두 제품을 함께 사용 하는 경우에는 "epitomizes" 라는 용어의 정의를 함께 활용 하는 것이 거의 확실 하지 않습니다.

이는 특히 Microsoft Lync Server 2013 및 Microsoft Exchange Server 2013 버전에서 발생 합니다. Microsoft Exchange Server 2010 및 Microsoft Lync Server 2010에 나와 있는 통합 메시징 및 IM 및 현재 상태와 같은 기능 외에도, 서버 제품의 2013 릴리스에는 여러 가지 새로운 기능이 포함 되어 있습니다. 이러한 기능은 다음과 같습니다.

  - **Lync 보관 통합**. Lync Server 2013 관리자는 여전히 인스턴트 메시징 및 웹 회의 내용을 SQL Server에 보관 하는 옵션을 사용할 수 있습니다 (이러한 기록이 Lync Server 2010에 보관 되었던 방식). 그렇지만 관리자는 대화 내용을 Exchange 2013에 보관 하 고 Exchange 보관 통신을 사용 하는 것과 같은 방식으로 개별 사용자 사서함에 해당 성적을 저장 하도록 선택할 수 있습니다. 즉, Exchange 및 Lync Server 모두에서 모든 전자 통신을 위한 단일 리포지토리를 사용 하 여 필요한 경우 보관 된 통신을 보다 쉽게 검색 하 고 검색할 수 있습니다.

  - **통합 연락처 저장소** Lync Server 2010에서는 사용자가 Outlook 및 Lync에서 별도의 연락처 목록을 유지 관리 해야 했습니다. 실제로 두 제품에서 같은 연락처를 사용할 수 있도록 하려면 Outlook 및 Lync 용으로 중복 된 연락처 목록을 유지 관리 해야 했습니다. 그러나 Lync Server 2013를 사용 하 여 사용자 연락처를 Exchange 2013 및 통합 연락처 저장소에 저장할 수 있습니다. 단일 연락처 저장소를 사용 하면 Lync 2013, Outlook 2013 및 Outlook Web Access 2013에서 동일한 연락처 집합을 사용할 수 있도록 하나의 연락처 집합만 유지 관리할 수 있습니다.

  - **OWA의 Lync 모임 예약** Lync Server 2013 및 Exchange 2013 통합을 사용 하는 경우 사용자는 Outlook Web Access 2013에서 Lync 모임을 예약할 수 있습니다.

  - 고해상도 **사진** Lync 2010에서는 연락처의 작은 사진만 표시할 수 있습니다. 이러한 사진은 Active Directory에 저장 되 고 Active Directory에서는 저장 된 사진에 대해 48 픽셀 크기 제한에 48 픽셀을 적용 하기 때문입니다. 그러나 Lync Server 2013를 사용 하 여 사진을 Microsoft Exchange에 저장할 수 있습니다. 이렇게 하면 해상도가 고해상도 인 사진을 648 픽셀 단위로 648 픽셀까지 크게 허용 합니다. 예상할 수 있듯이 Lync 2013는 이러한 고해상도 사진을 표시할 수 있도록 업그레이드 되었습니다.

이러한 새로운 기능을 사용 하려면 Lync Server 2013 및 Exchange 2013이 모두 필요 합니다. 이외에도 이러한 새로운 기능을 활용 하려는 사용자에 게는 Lync Server 2013 및 Exchange 2013에 대 한 계정이 있어야 하며 최신 버전의 클라이언트 소프트웨어 (예: Lync 2013)를 사용 해야 합니다. 예를 들어 Lync Server 2010에 있는 사용자는 통합 연락처 저장소를 사용할 수 없습니다. 마찬가지로, 고해상도 사진을 Lync 2010에 표시할 수 없습니다.

이 문서에서는 Lync Server 2013 및 Exchange 2013을 통합 하는 방법에 대 한 정보를 제공 합니다. 보관 통합 및 통합 연락처 저장소와 같은 새로운 기능을 사용 하는 방법에 대 한 단계별 정보를 포함 합니다. 이 문서에서는 이러한 두 제품의 초기 설정 및 구성에 대해 설명 합니다. Lync Server 2013 배포에 대 한 자세한 내용은의 Lync Server 2013 Tech Center를 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127) . Exchange 2013 배포에 대 한 자세한 내용은의 Exchange 2013 기술 센터를 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528) .

<div>

## <a name="in-this-section"></a>이 섹션의 내용

[Microsoft Lync Server 2013 및 Microsoft Exchange Server 2013 통합을 위한 필수 구성 요소](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Microsoft Lync Server 2013 및 Microsoft Exchange Server 2013에서 파트너 응용 프로그램 구성](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[Microsoft Exchange Server 2013 보관을 사용 하도록 Microsoft Lync Server 2013 구성](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[보관 된 Microsoft Lync Server 2013 데이터를 검색 하도록 Microsoft SharePoint Server 2013 구성](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[통합 연락처 저장소를 사용 하도록 Microsoft Lync Server 2013 구성](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[Microsoft Lync Server 2013에서 고해상도 사진 사용 구성](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[Microsoft Lync Server 2013 음성 메일에 대해 Microsoft Exchange Server 2013 통합 메시징 구성](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[Microsoft Lync Server 2013 및 Microsoft Outlook Web App 2013 통합](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

