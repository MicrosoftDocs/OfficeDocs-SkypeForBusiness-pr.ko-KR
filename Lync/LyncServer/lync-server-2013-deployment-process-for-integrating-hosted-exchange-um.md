---
title: 'Lync Server 2013: 호스팅된 Exchange UM 통합을 위한 배포 프로세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b314ea3bd7a88264a72c804c7c67ed3baa819972
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a>호스팅된 Exchange UM과 Lync Server 2013의 통합을 위한 배포 프로세스

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-25_

Lync 서버 2013와 호스팅된 Exchange 통합 메시징 (UM)을 통합 하기 위한 효과적인 계획을 위해서는 다음을 고려해 야 합니다.

  - Lync Server 2013을 호스트 된 Exchange UM과 통합 하기 위한 필수 조건

  - 통합 프로세스 중 필요한 단계

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a>호스팅된 Exchange UM과 통합 하기 위한 배포 필수 조건

통합 프로세스를 시작 하려면 먼저 Lync Server 2013 (최소, 프런트 엔드 풀 또는 Standard Edition 서버), Edge 서버, Lync 2013 또는 Lync 2010 클라이언트를 배포 해야 합니다.

</div>

<div>

## <a name="integration-process"></a>통합 프로세스

다음 표에서는 호스팅된 Exchange UM 통합 프로세스에 대해 간략하게 설명 합니다. 배포 단계에 대 한 자세한 내용은 배포 설명서의 [호스팅된 EXCHANGE UM에서 Lync Server 2013 사용자에 게 음성 메일 제공](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) 을 참조 하세요.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>단계의</th>
<th>방법은</th>
<th>권한 및 사용 권한</th>
<th>배포 설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Edge 서버를 구성 합니다.</p></td>
<td><ol>
<li><p>에지 서버에서 페더레이션을 사용할 수 있도록 구성합니다.</p></li>
<li><p>Edge 서버에 데이터를 수동으로 복제 합니다.</p></li>
<li><p>Edge 서버에서 호스팅 공급자를 구성 합니다.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">호스팅된 Exchange UM과의 통합을 위한 에지 서버 구성</a></p></td>
</tr>
<tr class="even">
<td><p>호스팅된 음성 메일 정책 구성</p></td>
<td><ol>
<li><p>글로벌 호스팅 음성 메일 정책을 수정 하거나 사이트 또는 사용자별 범위를 사용 하 여 새로 호스팅되는 음성 메일 정책을 만듭니다.</p></li>
<li><p>사용자별 범위 정책에 대해 정책을 사용자 또는 그룹에 할당 합니다.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Lync Server 2013에서 호스팅된 음성 메일 정책 관리</a></p></td>
</tr>
<tr class="odd">
<td><p>사용자가 호스팅된 음성 메일을 사용할 수 있도록 설정 합니다.</p></td>
<td><ul>
<li><p>사서함이 호스팅된 Exchange 서비스에 속한 사용자의 사용자 계정을 구성 합니다.</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Lync Server 2013에서 사용자가 호스팅된 음성 사서함을 사용할 수 있도록 설정</a></p></td>
</tr>
<tr class="even">
<td><p>호스팅된 연락처 개체를 구성 합니다.</p></td>
<td><ol>
<li><p>호스트 된 Exchange UM에 대 한 자동 전화 교환 연락처 개체를 만듭니다.</p></li>
<li><p>호스트 된 Exchange UM에 대 한 구독자 액세스 연락처 개체를 만듭니다.</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]  
> 연락처 개체를 만들거나 수정 하거나 제거 하려면 새 연락처 개체가 저장 된 Active Directory 조직 구성 단위에 대해 Set-CsExUmContact 또는 Remove-CsExUmContact cmdlet을 실행 하는 사용자에 게 올바른 사용 권한이 있어야 합니다. 이 권한은 부여-CsOUPermission cmdlet을 실행 하 여 부여할 수 있습니다. 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.


</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Lync Server 2013에서 호스팅된 Exchange UM에 대한 대화 상대 개체 만들기</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

