---
title: A/V 회의에 대 한 Lync Server 2013 배포 검사 목록
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d787cbc1e2bbefcc2cb125e64ab7143ddbd6cf2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a>Lync Server 2013의 A/V 회의에 대 한 배포 검사 목록

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-30_

다른 Lync Server 2013 구성 요소를 배포 하는 경우에는 A/V 회의를 배포 하는 경우에도 토폴로지 작성기를 사용 하 여 회의가 통합 되는 토폴로지를 만들고 게시 해야 합니다.

<div>

## <a name="deployment-sequence"></a>배포 순서

초기 토폴로지를 배포 하는 동시에 또는 하나 이상의 프런트 엔드 풀 또는 Standard Edition 서버를 배포한 후에 회의를 배포할 수 있습니다.

</div>

<div>

## <a name="conferencing-deployment-process"></a>회의 배포 프로세스

다음 표에서는 기존 토폴로지에 회의를 배포 하는 데 필요한 단계에 대해 간략하게 설명 합니다.


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
<th>역할 및 그룹 구성원</th>
<th>설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>필수 하드웨어 및 소프트웨어 설치</strong></p></td>
<td><p>프론트 엔드 풀과 Standard Edition 서버의 프런트 엔드 서버에서 회의가 실행 됩니다. 해당 서버를 설치 하는 데 필요한 사항 외에 추가 하드웨어 또는 소프트웨어 요구 사항이 없습니다.</p>
<div>

> [!NOTE]  
> Lync Server 2013는 Office Web Apps 및 Office Web Apps 서버를 사용 하 여 PowerPoint 프레젠테이션 공유 및 렌더링을 처리 합니다. Office Web Apps 서버를 설치 하 고 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Office Web Apps 서버 및 Lync server 2013의 통합 구성을</A>참조 하세요.


</div></td>
<td><p>로컬 관리자 그룹의 구성원 인 도메인 사용자</p></td>
<td><p>지원 가능성 설명서의 <a href="lync-server-2013-supported-hardware.md">Lync Server 2013에 대해 지원 되는 하드웨어</a></p>
<p>지원 가능성 문서에서 <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013의 서버 소프트웨어 및 인프라 지원</a></p>
<p>계획 설명서의 <a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013에 대 한 시스템 요구 사항을 확인</a> 합니다.</p>
<p>계획 설명서의 <a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013에서 보관을 위한 기술 요구 사항</a></p></td>
</tr>
<tr class="even">
<td><p><strong>회의를 지원 하기 위해 적절 한 내부 토폴로지 만들기</strong></p></td>
<td><p>토폴로지 작성기를 실행 하 여 토폴로지에 회의를 추가한 다음 토폴로지를 게시 합니다.</p></td>
<td><p>토폴로지를 정의 하려면 로컬 사용자 그룹의 구성원 인 계정</p>
<p>도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원이 며, Lync Server 2013 파일 저장소에 사용할 파일 공유에 대 한 모든 권한 (읽기/쓰기/수정)이 있는 토폴로지를 게시 하려면 토폴로지 작성기가 필수 Dacl을 구성할 수 있도록 하는 것이 좋습니다.</p></td>
<td><p>배포 설명서의 <a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Lync Server 2013에 대 한 토폴로지 작성기에서 토폴로지를 정의 하 고 구성</a> 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>회의 정책 및 지원 구성</strong></p></td>
<td><p>Lync Server 2013 제어판 또는 Lync Server 관리 셸을 사용 하 여 회의 설정을 구성 합니다.</p></td>
<td><p>RTCUniversalServerAdmins 그룹 (Windows PowerShell에만 해당) 또는 사용자를 [] 또는 CSAdministrator 역할에 할당</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Lync Server 2013의 회의 정책은</a> 운영 설명서에 있습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 회의 개요](lync-server-2013-overview-of-conferencing.md)  
[Lync Server 2013에서 회의 요구 사항 정의](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

