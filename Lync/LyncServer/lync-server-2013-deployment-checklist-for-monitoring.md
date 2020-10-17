---
title: 'Lync Server 2013: 모니터링을 위한 배포 검사 목록'
description: 'Lync Server 2013: 모니터링에 대 한 배포 검사 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3d3293accf6e25c20ae8391f9107ae75fef338
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568331"
---
# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a>Lync Server 2013의 모니터링을 위한 배포 검사 목록

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-05_

모니터링은 각 프런트 엔드 서버에 이미 설치 되어 활성화 되어 있지만 실제로 Microsoft Lync Server 2013에 대 한 모니터링 데이터를 수집 하기 전에 먼저 수행 해야 하는 몇 가지 단계가 있습니다. 이러한 단계는 다음 검사 목록에 설명되어 있습니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>단계</p></td>
<td><p>단계</p></td>
<td><p>역할 및 그룹 구성원 자격</p></td>
<td><p>설명서</p></td>
</tr>
<tr class="even">
<td><p><strong>하드웨어 및 소프트웨어 필수 구성 요소 설치</strong></p></td>
<td><p>모니터링을 위한 백 엔드 데이터 저장소로 작동할 컴퓨터에 지원되는 버전의 Microsoft SQL Server를 설치합니다.</p></td>
<td><p>로컬 관리자 그룹의 구성원인 도메인 사용자여야 합니다.</p></td>
<td><p>지원 가능성 설명서의 <a href="lync-server-2013-supported-hardware.md">Lync Server 2013에 대해 지 원하는 하드웨어</a></p>
<p>지원 가능성 가이드의 <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013에 제공 되는 서버 소프트웨어 및 인프라 지원</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>모니터링을 지원하는 적절한 내부 토폴로지 만들기</strong></p></td>
<td><p>Lync Server 2013 토폴로지 작성기를 사용 하 여 모니터링 데이터베이스를 토폴로지에 추가한 다음 업데이트 된 토폴로지를 게시 합니다.</p></td>
<td><p>토폴로지를 정의하려면 로컬 사용자 그룹의 구성원인 사용자여야 합니다.</p>
<p>토폴로지를 게시하려면 도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원이어야 합니다.</p></td>
<td><p>배포 가이드의 <a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Lync Server 2013에서 모니터링 저장소를 프런트 엔드 풀과 연결</a></p></td>
</tr>
<tr class="even">
<td><p><strong>적합한 모니터링 설정 사용</strong></p></td>
<td><p>전역 및/또는 사이트 범위에서 CDR(통화 정보 기록) 및/또는 QoE(체감 품질) 모니터링을 사용합니다.</p></td>
<td><p>RTCUniversalServerAdmins 그룹의 구성원인 사용자 또는 CsCdrConfiguration 및 CsQoEConfiguration cmdlet에 대한 액세스 권한을 제공하는 RBAC 역할이 지정된 사용자여야 합니다.</p></td>
<td><p>운영 가이드의 <a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Lync Server 2013에서 통화 정보 기록 및 경험 수준 설정 구성</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

