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
ms.openlocfilehash: f55e8f573b4000d56a002adb9bd40d03b2021cba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a>호스팅된 Exchange UM과 Lync Server 2013의 통합을 위한 배포 프로세스

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-25_

Lync Server 2013을 호스팅된 Exchange UM (통합 메시징)과 통합 하기 위한 효과적인 계획을 사용 하려면 다음 사항을 고려해 야 합니다.

  - Lync Server 2013과 호스팅된 Exchange UM의 통합을 위한 필수 구성 요소

  - 통합 프로세스 중 필요한 단계

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a>호스팅된 Exchange UM과의 통합을 위한 배포 필수 구성 요소

통합 프로세스를 시작 하려면 먼저 Lync Server 2013 (최소, 프런트 엔드 풀 또는 Standard Edition 서버),에 지 서버 및 Lync 2013 또는 Lync 2010 클라이언트를 배포 해야 합니다.

</div>

<div>

## <a name="integration-process"></a>통합 프로세스

다음 표에서는 호스팅된 Exchange UM 통합 프로세스에 대 한 개요를 제공 합니다. 배포 단계에 대 한 자세한 내용은 배포 설명서의 [호스팅된 EXCHANGE UM에서 Lync Server 2013 users 음성 메일 제공](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) 을 참조 하십시오.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>단계</th>
<th>단계</th>
<th>권한 및 사용 권한</th>
<th>배포 설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>에 지 서버를 구성 합니다.</p></td>
<td><ol>
<li><p>페더레이션을 위해에 지 서버를 구성 합니다.</p></li>
<li><p>에 지 서버에 데이터를 수동으로 복제 합니다.</p></li>
<li><p>에 지 서버에서 호스팅 공급자를 구성 합니다.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">호스팅된 Exchange UM과의 통합을 위해에 지 서버 구성</a></p></td>
</tr>
<tr class="even">
<td><p>호스팅된 음성 메일 정책을 구성 합니다.</p></td>
<td><ol>
<li><p>전역 호스트 된 음성 메일 정책을 수정 하거나 사이트 또는 사용자별 범위를 사용 하 여 호스팅된 새 음성 메일 정책을 만듭니다.</p></li>
<li><p>사용자별 범위가 포함 된 정책의 경우 사용자 또는 그룹에 정책을 할당 합니다.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Lync Server 2013에서 호스팅된 음성 메일 정책 관리</a></p></td>
</tr>
<tr class="odd">
<td><p>사용자가 호스팅된 음성 메일을 사용 하도록 설정 합니다.</p></td>
<td><ul>
<li><p>사서함이 호스팅된 Exchange 서비스에 있는 사용자에 대 한 사용자 계정을 구성 합니다.</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Lync Server 2013에서 호스팅된 음성 메일에 대해 사용자를 사용 하도록 설정</a></p></td>
</tr>
<tr class="even">
<td><p>호스팅된 대화 상대 개체를 구성 합니다.</p></td>
<td><ol>
<li><p>호스팅된 Exchange UM에 대 한 자동 전화 교환 대화 상대 개체를 만듭니다.</p></li>
<li><p>호스팅된 Exchange UM에 대 한 구독자 액세스 대화 상대 개체를 만듭니다.</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]  
> 연락처 개체를 만들거나, 수정 하거나, 제거 하려면 새 연락처 개체가 저장 된 Active Directory 조직 구성 단위에 대 한 올바른 사용 권한을 가져야 합니다 (예를 들어, e c e c e n t e c e i n t e c e c r i e c r i e c r i e c e)을 실행 하는 사용자 이 사용 권한은 부여-CsOUPermission cmdlet을 실행 하 여 부여할 수 있습니다. 자세한 내용은 Lync Server 관리 셸 설명서를 참조하십시오.


</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Lync Server 2013에서 호스팅된 Exchange UM에 대 한 대화 상대 개체 만들기</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

