---
title: 'Lync Server 2013: 응답 그룹 배포 프로세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc249ec8df233e6c22c9d5c1b54b81e23c5a173
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a>Lync Server 2013의 응답 그룹 배포 프로세스

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-27_

이 섹션에서는 응답 그룹 응용 프로그램 배포와 관련 된 단계 및 단계에 대 한 개요를 제공 합니다.

### <a name="response-group-deployment-process"></a>응답 그룹 배포 프로세스

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
<th>권한</th>
<th>배포 설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>응답 그룹 응용 프로그램 설치</p></td>
<td><p>Enterprise Voice를 배포할 때 응답 그룹 응용 프로그램이 기본적으로 설치 및 활성화 됩니다.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">Lync Server 2013에서 Enterprise Voice 배포</a></p></td>
</tr>
<tr class="even">
<td><p>응답 그룹 구성 요소 설치</p></td>
<td><p>Lync Server cmdlet, Lync Server 제어판, 응답 그룹 구성 도구, 에이전트의 로그인 및 로그 아웃 콘솔 및 응답 그룹 클라이언트 웹 서비스는 웹 서비스의 일부로 설치 됩니다. 웹 서비스는 Enterprise Edition 풀이나 Standard Edition Server 배포 시 설치됩니다.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 배포</a></p></td>
</tr>
<tr class="odd">
<td><p>사용자가 Lync 2013 및 Enterprise Voice를 사용할 수 있도록 설정</p></td>
<td><p>Lync Server 및 Enterprise Voice를 위한 에이전트로 사용할 사용자를 사용 하도록 설정 합니다. 에이전트 그룹에 사용자를 추가하려면 해당 사용자가 사용되도록 설정해야 합니다. 일반적으로 사용자는 Enterprise Edition 또는 Standard Edition 서버 배포 중에 Lync Server를 사용할 수 있습니다. Enterprise Voice 배포 중에 사용자가 Enterprise Voice를 사용할 수 있도록 설정 됩니다.</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Lync Server 2013에 대해 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Lync Server 2013에서 Enterprise Voice를 사용할 수 있도록 사용자 설정</a></p></td>
</tr>
<tr class="even">
<td><p>에이전트 그룹, 큐 및 워크플로로 구성 된 응답 그룹 만들기 및 구성</p></td>
<td><ol>
<li><p>Lync Server 제어판 또는 Lync Server 관리 셸을 사용 하 여 다음을 수행 합니다.</p>
<ol>
<li><p>에이전트 그룹을 만들고 구성 합니다.</p></li>
<li><p>큐를 만들고 구성 합니다.</p></li>
</ol></li>
<li><p>필요한 경우 Lync Server 관리 셸을 사용 하 여 미리 정의 된 응답 그룹 업무 시간 및 휴일을 만듭니다.</p></li>
<li><p>응답 그룹 구성 도구 또는 Lync Server 관리 셸을 사용 하 여 사용자 지정 응답 그룹 업무 시간 및 휴일을 포함 하 여 워크플로 (헌트 그룹 또는 IVR (대화형 음성 응답) 호출 흐름)를 만들 수 있습니다.</p>
<div>

> [!NOTE]  
> Lync Server 제어판을 통해 응답 그룹 구성 도구에 액세스할 수 있습니다.


</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsResponseGroupManager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">응답 그룹 에이전트 그룹 만들기 Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">Lync Server 2013에서 응답 그룹 큐 만들기</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">반드시 Lync Server 2013에서 응답 그룹 업무 시간 정의</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">반드시 Lync Server 2013에서 응답 그룹 휴일 집합 정의</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">Lync Server 2013에서 워크플로 만들기 또는 수정</a></p></td>
</tr>
<tr class="odd">
<td><p>반드시 응용 프로그램 수준 설정 사용자 지정</p></td>
<td><p>Lync Server 관리 셸을 사용 하 여 기본 음악 대기 구성, 기본 음악 대기 오디오 파일, 에이전트의 되 걸기 유예 기간 및 통화 컨텍스트 구성을 사용자 지정 합니다.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">Lync Server 2013에서 응용 프로그램 수준 응답 그룹 설정 관리</a></p></td>
</tr>
<tr class="even">
<td><p>반드시 응답 그룹 관리 위임</p></td>
<td><p>사용자에 게 CsResponseGroupManager 역할을 할당 하 여 응답 그룹의 구성을 위임 합니다. 그러면 응답 그룹 관리자가 자신에 게 할당 된 응답 그룹을 구성할 수 있습니다.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013에서 역할 기반 액세스 제어 계획</a></p></td>
</tr>
<tr class="odd">
<td><p>응답 그룹 배포 확인</p></td>
<td><p>헌트 그룹 및 대화형 음성 응답 워크플로에 대한 통화 응답을 테스트하여 구성이 예상대로 작동하는지 확인합니다.</p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

