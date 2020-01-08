---
title: 'Lync Server 2013: 지원 되는 하이브리드 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported hybrid configurations
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945633(v=OCS.15)
ms:contentKeyID: 51541482
ms.date: 05/10/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 142b86720e64fdfd071bc5cacb21e4891e3e7758
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-lync-server-2013-hybrid-configurations"></a>지원 되는 Lync Server 2013 하이브리드 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-05-10_

온-프레미스와 온라인 모두에서 Microsoft Exchange Server 2010 및 Microsoft Exchange Server 2013 및 SharePoint Server와 통합 하도록 Lync Server 2013 배포를 구성할 수 있습니다. 다음 표에 나열 된 기능은 달리 지정 하지 않는 한 모든 클라이언트에서 지원 됩니다. 클라이언트 지원에 대 한 자세한 내용은 비즈니스용 [Skype online 용](http://go.microsoft.com/fwlink/p/?linkid=281902)클라이언트의 Lync Server 2013 및 비즈니스용 skype online 클라이언트 비교 표에 [대 한 클라이언트 비교 표](lync-server-2013-desktop-client-comparison-tables.md) 를 참조 하세요.

<div>

## <a name="integration-with-exchange-server"></a>Exchange Server와 통합

다음 표에는 Microsoft Exchange Server와 통합할 때 하이브리드 배포에서 지원 되는 기능이 나와 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Exchange 온-프레미스</th>
<th>Exchange Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 온-프레미스</strong></p></td>
<td><ul>
<li><p>Outlook에서 메신저 대화/현재 상태</p>
<p>자세한 내용은 <a href="lync-server-2013-im-and-presence.md">Lync Server 2013에서 메신저 대화 및 현재 상태</a> 보기를 참조 하세요.</p></li>
<li><p>Outlook을 통해 온라인 모임 예약 및 참가</p>
<p>자세한 내용은 <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Microsoft Lync Server 2013 및 Microsoft Exchange server 2013 통합</a> 을 참조 하세요.</p></li>
<li><p>Outlook Web App에서 메신저 대화/현재 상태</p>
<p>자세한 내용은 <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">교차 프레미스 환경에서 Microsoft Lync Server 2013 구성을</a> 참조 하세요.</p></li>
<li><p>Outlook Web App을 통해 온라인 모임 예약 및 참가</p></li>
<li><p>모바일 클라이언트에서 메신저 대화/현재 상태</p></li>
<li><p>모바일 클라이언트에서 온라인 모임 참가</p>
<p>자세한 내용은 <a href="lync-server-2013-deploying-mobility.md">Lync Server 2013에서 모바일 배포</a> 를 참조 하세요.</p></li>
<li><p>Outlook 일정 약속 있음/없음 정보를 기준으로 게시 상태</p></li>
<li><p>연락처 목록 (통합 된 대화 상대 저장소를 통해)</p>
<p>자세한 내용은 <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">통합 된 대화 상대 저장소를 사용 하도록 Microsoft Lync Server 2013 구성을</a> 참조 하세요.</p>
<div>

> [!NOTE]  
> Exchange 2013이 필요 합니다.<BR>Lync 2013 데스크톱 클라이언트가 필요 합니다.


</div></li>
<li><p>Lync 2013 클라이언트 및 Lync Web App의 고해상도 연락처 사진</p>
<p>자세한 내용은 <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Microsoft Lync Server 2013에서 고해상도 사진 사용 구성</a> 을 참조 하세요.</p>
<div>

> [!NOTE]  
> Exchange 2013이 필요 합니다.


</div></li>
<li><p>모임 위임</p>
<p>두 사용자가 모두 같은 포리스트에 온라인 상태 이거나 둘 다 온 경우에만 지원 됩니다.</p></li>
<li><p>부재 중 대화 기록 및 통화 로그가 사용자의 exchange 사서함에 기록 됩니다.</p></li>
<li><p>Exchange에서 콘텐츠 (IM 및 모임) 보관</p>
<p>자세한 내용은 <a href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013에서 보관에 대 한 배포 검사 목록을</a> 참조 하세요.</p>
<div>

> [!NOTE]  
> Exchange 2013이 필요 합니다.


</div></li>
<li><p>보관 된 콘텐츠 검색</p>
<div>

> [!NOTE]  
> Exchange 2013이 필요 합니다.


</div></li>
<li><p>음성 메일</p>
<p>자세한 내용은 온 <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">-프레미스 EXCHANGE UM을 배포 하 여 Lync Server 2013 음성 메일 제공</a> 을 참조 하세요.</p></li>
</ul></td>
<td><ul>
<li><p>Outlook에서 메신저 대화/현재 상태</p>
<p>자세한 내용은 <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Exchange Online과 온-프레미스 Lync Server 2013 통합 구성</a> 을 참조 하세요.</p></li>
<li><p>Outlook을 통해 온라인 모임 예약 및 참가</p></li>
<li><p>OWA의 메신저 대화/현재 상태</p>
<p>자세한 내용은 <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Exchange Online과 온-프레미스 Lync Server 2013 통합 구성</a> 을 참조 하세요.</p></li>
<li><p>Outlook Web App에서 온라인 모임 예약 및 참가</p>
<p>자세한 내용은 <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Exchange Online과 온-프레미스 Lync Server 2013 통합 구성</a> 을 참조 하세요.</p></li>
<li><p>모바일 클라이언트에서 메신저 대화/현재 상태</p></li>
<li><p>모바일 클라이언트에서 온라인 모임 참가</p></li>
<li><p>Outlook 일정 약속 있음/없음 정보를 기준으로 게시 상태</p></li>
<li><p>연락처 목록 (통합 된 대화 상대 저장소를 통해) 자세한 내용은 <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">통합 된 대화 상대 저장소를 사용 하도록 Microsoft Lync Server 2013 구성을</a> 참조 하세요.</p>
<div>

> [!NOTE]  
> Lync 서버 2013만 해당 됩니다. Lync 2013 데스크톱 클라이언트가 필요 합니다.


</div></li>
<li><p>Lync 2013 클라이언트 및 Lync Web App의 고해상도 연락처 사진</p>
<p>자세한 내용은 <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Microsoft Lync Server 2013에서 고해상도 사진 사용 구성을</a>참조 하세요.</p></li>
<li><p>모임 위임</p>
<p>두 사용자가 모두 같은 포리스트에 온라인 상태 이거나 둘 다 온 경우에만 지원 됩니다.</p></li>
<li><p>부재 중 대화 기록 및 통화 로그가 사용자의 exchange 사서함에 기록 됩니다.</p></li>
<li><p>Exchange에서 콘텐츠 (IM 및 모임)를 보관 합니다.</p>
<p>자세한 내용은 <a href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013에서 보관에 대 한 배포 검사 목록을</a> 참조 하세요.</p></li>
<li><p>보관 된 콘텐츠를 검색 합니다. 자세한 내용은 <a href="http://go.microsoft.com/fwlink/p/?linkid=285448">SharePoint 용 Exchange EDiscovery 센터 구성</a> 을 참조 하세요.</p></li>
<li><p>음성 메일. 자세한 내용은 <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">호스팅된 EXCHANGE UM에서 Lync Server 2013 사용자에 게 음성 메일 제공</a> 을 참조 하세요.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Outlook의 메신저 대화 및 현재 상태</p></li>
<li><p>Outlook을 통해 온라인 모임 예약 및 참가</p></li>
<li><p>모바일 클라이언트에서 메신저 대화/현재 상태</p></li>
<li><p>부재 중 대화 기록 및 통화 로그가 사용자의 exchange 사서함에 기록 됩니다.</p></li>
<li><p>Lync 2013 클라이언트의 고해상도 연락처 사진</p>
<div>

> [!NOTE]  
> Microsoft Exchange Server 2013이 필요 합니다. 이 기능은 사용자가 비즈니스용 Skype Online으로 이동할 때 Lync Web App에서 지원 되지 않습니다.


</div></li>
<li><p>모바일 클라이언트에서 온라인 모임 참가</p></li>
<li><p>Outlook 일정 약속 있음/없음 정보를 기준으로 게시 상태</p></li>
<li><p>모임 위임</p>
<p>두 사용자가 모두 같은 포리스트에 온라인 상태 이거나 둘 다 온 경우에만 지원 됩니다.</p></li>
</ul></td>
<td><ul>
<li><p>Outlook에서 메신저 대화/현재 상태</p></li>
<li><p>Outlook을 통해 온라인 모임 예약 및 참가</p></li>
<li><p>Outlook Web App에서 메신저 대화/현재 상태</p></li>
<li><p>Outlook Web App에서 온라인 모임 예약 및 참가</p></li>
<li><p>모바일 클라이언트에서 메신저 대화/현재 상태</p></li>
<li><p>모바일 클라이언트에서 온라인 모임 참가</p></li>
<li><p>Outlook 일정 약속 있음/없음 정보를 기준으로 게시 상태</p></li>
<li><p>부재 중 대화 기록 및 통화 로그가 사용자의 exchange 사서함에 기록 됩니다.</p></li>
<li><p>연락처 목록 (통합 된 대화 상대 저장소를 통해)</p>
<div>

> [!NOTE]  
> Lync Server 2013 클라이언트 필요


</div></li>
<li><p>Lync 2013 클라이언트 및 Lync Web App의 고해상도 연락처 사진</p></li>
<li><p>모임 위임</p>
<p>두 사용자가 모두 같은 포리스트에 온라인 상태 이거나 둘 다 온 경우에만 지원 됩니다.</p></li>
<li><p>Exchange에서 콘텐츠 (IM 및 모임) 보관</p></li>
<li><p>보관 된 콘텐츠 검색</p></li>
<li><p>음성 메일</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a>SharePoint와 통합

다음 표에는 SharePoint와 통합할 때 Lync Server 2013 하이브리드 배포에서 지원 되는 기능이 나와 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>SharePoint 온-프레미스</th>
<th>SharePoint Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 온-프레미스</strong></p></td>
<td><ul>
<li><p>기술 검색</p></li>
<li><p>SharePoint에서 현재 상태</p></li>
</ul></td>
<td><ul>
<li><p>SharePoint에서 현재 상태</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>SharePoint에서 현재 상태</p></li>
</ul></td>
<td><ul>
<li><p>SharePoint에서 현재 상태</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

