---
title: 'Lync Server 2013: 통화 허용 제어 서비스에 대한 배포 검사 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dd425d53a282cc24fed8ad2f8be9acc5bf42209
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a>Lync Server 2013의 통화 허용 제어 서비스에 대한 배포 검사 목록

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-08_

호출 허용 제어 (CAC)를 효과적으로 계획 하려면 다음 사항을 고려해 야 합니다.

  - CAC 배포를 위한 필수 구성 요소

  - 사전 설정 및 구성 결정에 필요한 정보 (배포를 미리 하기 위해 필요 함)

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a>통화 허용 제어에 대 한 배포 선행 조건

통화 허용 제어를 배포 하기 전에 먼저 프런트 엔드 풀 또는 Standard Edition 서버를 포함 하 여 Lync Server 2013 내부 서버를 배포 해야 합니다.

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a>통화 허용 제어에 대 한 정보 요구 사항

다음 표에는 통화 허용 제어를 배포 하는 데 필요한 정보가 요약 되어 있습니다.

### <a name="information-requirements-for-call-admission-control-deployment"></a>통화 허용 제어 배포에 대 한 정보 요구 사항

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>방법</th>
<th>필요한 정보 요약</th>
<th>설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>조직에서 필요로 하는 Lync Server 기능</p></td>
<td><ul>
<li><p>조직에서 지원 되는 기능</p></li>
<li><p>개별 사용자에 대해 사용할 수 있는 기능</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013에서 통화 허용 제어 서비스에 대한 요구 사항 정의</a></p></td>
</tr>
<tr class="even">
<td><p>배포할 토폴로지 및 구성 요소</p></td>
<td><ul>
<li><p>CAC 관련 구성 요소는 Lync Server 2013의 일부로 자동으로 설치 됩니다.</p></li>
</ul></td>
<td><p><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013에서 통화 허용 제어 서비스에 대한 요구 사항 정의</a></p></td>
</tr>
<tr class="odd">
<td><p>시스템 요구 사항</p></td>
<td><ul>
<li><p>하드웨어 요구 사항</p></li>
<li><p>소프트웨어 요구 사항</p></li>
<li><p>Collocation 요구 사항</p></li>
</ul></td>
<td><p><a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013의 시스템 요구 사항 확인</a></p></td>
</tr>
<tr class="even">
<td><p>인프라 요구 사항</p></td>
<td><ul>
<li><p>CAC에는 특정 인프라 요구 사항이 필요 하지 않습니다.</p></li>
</ul></td>
<td><p><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Lync Server 2013의 통화 허용 제어 서비스에 대한 인프라 요구 사항</a></p></td>
</tr>
<tr class="odd">
<td><p>네트워크 인터페이스 요구 사항</p></td>
<td><ul>
<li><p>내부 및 외부 인터페이스 정보</p></li>
<li><p>라우팅 정보 (NextHop 블로그의 정보 포함 <a href="http://go.microsoft.com/fwlink/p/?linkid=203149">http://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server 팀의 고객 응답 채널)</p></li>
</ul></td>
<td><p><a href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013에서 외부 사용자 액세스 배포</a></p></td>
</tr>
<tr class="even">
<td><p>배포 전략</p></td>
<td><ul>
<li><p>배포 순서</p></li>
<li><p>작업 그룹 또는 도메인</p></li>
<li><p>보안</p></li>
<li><p>모니터링 및 감사</p></li>
<li><p>하드웨어 고려 사항</p></li>
</ul></td>
<td><p><a href="lync-server-2013-best-practices-for-call-admission-control.md">Lync Server 2013의 통화 허용 제어 서비스 모범 사례</a></p></td>
</tr>
<tr class="odd">
<td><p>배포 프로세스</p></td>
<td><ul>
<li><p>필요 조건</p></li>
<li><p>정보 요구 사항</p></li>
<li><p>프로세스 및 절차</p></li>
</ul></td>
<td><p><a href="lync-server-2013-configure-call-admission-control.md">Lync Server 2013에서 통화 허용 제어 구성</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

