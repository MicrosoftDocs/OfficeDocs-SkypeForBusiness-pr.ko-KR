---
title: 'Lync Server 2013: 지원 되는 하이브리드 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported hybrid configurations
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945633(v=OCS.15)
ms:contentKeyID: 51541482
ms.date: 05/10/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db6f415b373e8271f771510d925adef1ae672ced
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524055"
---
# <a name="supported-lync-server-2013-hybrid-configurations"></a>지원 되는 Lync Server 2013 하이브리드 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-05-10_

온-프레미스와 온라인 모두에서 Microsoft Exchange Server 2010 및 Microsoft Exchange Server 2013 및 SharePoint Server와의 통합을 위해 Lync Server 2013 배포를 구성할 수 있습니다. 별도로 지정 되지 않은 경우 모든 클라이언트에서 다음 표에 나열 된 기능을 사용할 수 있습니다. 클라이언트 지원에 대 한 자세한 내용은 [비즈니스용 Skype online에](https://go.microsoft.com/fwlink/p/?linkid=281902)대 한 클라이언트의 Lync Server 2013 및 비즈니스용 skype online 클라이언트 비교 테이블 [에 대 한 클라이언트 비교 표](lync-server-2013-desktop-client-comparison-tables.md) 를 참조 하세요.

<div>

## <a name="integration-with-exchange-server"></a>Exchange Server와의 통합

다음 표에서는 Microsoft Exchange Server와 통합 될 때 하이브리드 배포에서 지원 되는 기능을 보여 줍니다.


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
<li><p>Outlook에서 IM/현재 상태</p>
<p>자세한 내용은 <a href="lync-server-2013-im-and-presence.md">Lync Server 2013에서 IM 및 현재 상태</a> 를 참조 하세요.</p></li>
<li><p>Outlook을 통해 온라인 모임 예약 및 참가</p>
<p>자세한 내용은 <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Microsoft Lync Server 2013 및 Microsoft Exchange Server 2013 통합</a> 을 참조 하세요.</p></li>
<li><p>Outlook Web App에서 IM/현재 상태</p>
<p>자세한 내용은 <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">크로스-프레미스 환경에서 Microsoft Lync Server 2013 구성</a> 를 참조 하세요.</p></li>
<li><p>Outlook Web App을 통해 온라인 모임 예약 및 참가</p></li>
<li><p>모바일 클라이언트의 IM/현재 상태</p></li>
<li><p>모바일 클라이언트에서 온라인 모임 참가</p>
<p>자세한 내용은 <a href="lync-server-2013-deploying-mobility.md">Lync Server 2013에서 모바일 기능 배포</a> 를 참조 하세요.</p></li>
<li><p>Outlook 일정 약속 있음/없음 정보를 기반으로 상태 게시</p></li>
<li><p>연락처 목록 (통합 연락처 저장소를 통해)</p>
<p>자세한 내용은 <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">통합 연락처 저장소를 사용 하도록 Microsoft Lync Server 2013 구성을</a> 참조 하십시오.</p>
<div>

> [!NOTE]  
> Exchange 2013이 필요 합니다.<BR>Lync 2013 데스크톱 클라이언트는 필수입니다.


</div></li>
<li><p>Lync 2013 클라이언트 및 Lync Web App의 고해상도 연락처 사진</p>
<p>자세한 내용은 <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Microsoft Lync Server 2013에서 고해상도 사진 사용 구성</a> 를 참조 하세요.</p>
<div>

> [!NOTE]  
> Exchange 2013이 필요 합니다.


</div></li>
<li><p>모임 위임</p>
<p>두 사용자가 같은 포리스트의 온라인에 있거나 둘 다 온-프레미스에 있는 경우에만 지원 됩니다.</p></li>
<li><p>부재 중 대화 기록 및 통화 로그가 사용자의 exchange 사서함에 기록 됨</p></li>
<li><p>Exchange의 콘텐츠 (IM 및 모임) 보관</p>
<p>자세한 내용은 <a href="lync-server-2013-deployment-checklist-for-archiving.md">배포 검사 목록을 Lync Server 2013에서 보관</a> 을 참조 하세요.</p>
<div>

> [!NOTE]  
> Exchange 2013이 필요 합니다.


</div></li>
<li><p>보관 된 콘텐츠 검색</p>
<div>

> [!NOTE]  
> Exchange 2013이 필요 합니다.


</div></li>
<li><p>음성 사서함</p>
<p>자세한 내용은 <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">Lync Server 2013 음성 메일을 제공 하도록 온-프레미스 EXCHANGE UM 배포</a> 를 참조 하세요.</p></li>
</ul></td>
<td><ul>
<li><p>Outlook에서 IM/현재 상태</p>
<p>자세한 내용은 <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Exchange Online과 온-프레미스 Lync Server 2013 통합 구성</a> 를 참조 하세요.</p></li>
<li><p>Outlook을 통해 온라인 모임 예약 및 참가</p></li>
<li><p>OWA의 IM/현재 상태</p>
<p>자세한 내용은 <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Exchange Online과 온-프레미스 Lync Server 2013 통합 구성</a> 를 참조 하세요.</p></li>
<li><p>Outlook Web App에서 온라인 모임 예약 및 참가</p>
<p>자세한 내용은 <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Exchange Online과 온-프레미스 Lync Server 2013 통합 구성</a> 를 참조 하세요.</p></li>
<li><p>모바일 클라이언트의 IM/현재 상태</p></li>
<li><p>모바일 클라이언트에서 온라인 모임 참가</p></li>
<li><p>Outlook 일정 약속 있음/없음 정보를 기반으로 상태 게시</p></li>
<li><p>연락처 목록 (통합 연락처 저장소를 통해) 자세한 내용은 <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">통합 연락처 저장소를 사용 하도록 Microsoft Lync Server 2013 구성을</a> 참조 하십시오.</p>
<div>

> [!NOTE]  
> Lync Server 2013 전용 Lync 2013 데스크톱 클라이언트는 필수입니다.


</div></li>
<li><p>Lync 2013 클라이언트 및 Lync Web App의 고해상도 연락처 사진</p>
<p>자세한 내용은 <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Microsoft Lync Server 2013에서 고해상도 사진 사용 구성</a>를 참조 하세요.</p></li>
<li><p>모임 위임</p>
<p>두 사용자가 같은 포리스트의 온라인에 있거나 둘 다 온-프레미스에 있는 경우에만 지원 됩니다.</p></li>
<li><p>부재 중 대화 기록 및 통화 로그가 사용자의 exchange 사서함에 기록 됨</p></li>
<li><p>Exchange의 콘텐츠 (IM 및 모임)를 보관 합니다.</p>
<p>자세한 내용은 <a href="lync-server-2013-deployment-checklist-for-archiving.md">배포 검사 목록을 Lync Server 2013에서 보관</a> 을 참조 하세요.</p></li>
<li><p>보관 된 콘텐츠를 검색 합니다. 자세한 내용은 <a href="https://go.microsoft.com/fwlink/p/?linkid=285448">Configure Exchange For SharePoint EDiscovery Center</a> 를 참조 하세요.</p></li>
<li><p>음성 사서함 자세한 내용은 <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">Lync Server 2013 users 사용자에 게 호스팅된 EXCHANGE UM에 대 한 음성 메일 제공</a> 을 참조 하십시오.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Outlook의 IM 및 현재 상태</p></li>
<li><p>Outlook을 통해 온라인 모임 예약 및 참가</p></li>
<li><p>모바일 클라이언트의 IM/현재 상태</p></li>
<li><p>부재 중 대화 기록 및 통화 로그가 사용자의 exchange 사서함에 기록 됨</p></li>
<li><p>Lync 2013 클라이언트의 고해상도 대화 상대 사진입니다.</p>
<div>

> [!NOTE]  
> Microsoft Exchange Server 2013이 필요 합니다. 사용자가 비즈니스용 Skype Online에 있는 경우이 기능은 Lync Web App에서 지원 되지 않습니다.


</div></li>
<li><p>모바일 클라이언트에서 온라인 모임 참가</p></li>
<li><p>Outlook 일정 약속 있음/없음 정보를 기반으로 상태 게시</p></li>
<li><p>모임 위임</p>
<p>두 사용자가 같은 포리스트의 온라인에 있거나 둘 다 온-프레미스에 있는 경우에만 지원 됩니다.</p></li>
</ul></td>
<td><ul>
<li><p>Outlook에서 IM/현재 상태</p></li>
<li><p>Outlook을 통해 온라인 모임 예약 및 참가</p></li>
<li><p>Outlook Web App에서 IM/현재 상태</p></li>
<li><p>Outlook Web App에서 온라인 모임 예약 및 참가</p></li>
<li><p>모바일 클라이언트의 IM/현재 상태</p></li>
<li><p>모바일 클라이언트에서 온라인 모임 참가</p></li>
<li><p>Outlook 일정 약속 있음/없음 정보를 기반으로 상태 게시</p></li>
<li><p>부재 중 대화 기록 및 통화 로그가 사용자의 exchange 사서함에 기록 됨</p></li>
<li><p>연락처 목록 (통합 연락처 저장소를 통해)</p>
<div>

> [!NOTE]  
> Lync Server 2013 클라이언트 필요


</div></li>
<li><p>Lync 2013 클라이언트 및 Lync 웹 응용 프로그램의 고해상도 연락처 사진</p></li>
<li><p>모임 위임</p>
<p>두 사용자가 같은 포리스트의 온라인에 있거나 둘 다 온-프레미스에 있는 경우에만 지원 됩니다.</p></li>
<li><p>Exchange의 콘텐츠 (IM 및 모임) 보관</p></li>
<li><p>보관 된 콘텐츠 검색</p></li>
<li><p>음성 메일</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a>SharePoint와의 통합

다음 표에서는 SharePoint와 통합할 때 Lync Server 2013 하이브리드 배포에서 지원 되는 기능을 보여 줍니다.


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
<li><p>SharePoint의 현재 상태</p></li>
</ul></td>
<td><ul>
<li><p>SharePoint의 현재 상태</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>SharePoint의 현재 상태</p></li>
</ul></td>
<td><ul>
<li><p>SharePoint의 현재 상태</p></li>
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

