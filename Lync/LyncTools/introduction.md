---
title: 소개
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d496d0aeaabd8ef7502cae8db89f2668d0574499
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction"></a>소개

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-24_

Lync Server 2013 스트레스 및 성능 도구 (as/Ccptool이 라고도 함)는 다음 형식의 사용자 로드를 시뮬레이션할 수 있습니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>인스턴트 메시지 (IM) 및 현재 상태</p></td>
<td><p>오디오 회의</p></td>
</tr>
<tr class="even">
<td><p>응용 프로그램 공유</p></td>
<td><p>PSTN (공개 통신 네트워크) 시뮬레이션을 포함 한 VoIP (Voice over IP)</p></td>
</tr>
<tr class="odd">
<td><p>웹 액세스 클라이언트 회의</p></td>
<td><p>Microsoft Lync 2013 수행자</p></td>
</tr>
<tr class="even">
<td><p>응답 그룹</p></td>
<td><p>메일 그룹 확장</p></td>
</tr>
<tr class="odd">
<td><p>주소록 다운로드 및 주소록 쿼리</p></td>
<td><p>향상 된 9-1-1 (E9-1) 통화 및 위치 프로필 (다이얼 플랜)</p></td>
</tr>
<tr class="even">
<td><p>MultiView</p></td>
<td><p>회의에서 여러 스트림 보기</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


Lync Server 2013 스트레스 및 성능 도구는 고급 구성을 통해서만 교차 풀 부하 생성 및 페더레이션을 지원 합니다.

또한이 도구는 다음 클라이언트에 대 한 사용자 로드를 시뮬레이션 하지 않습니다.

  - Office Live Meeting 2007

  - Lync 2013 영구 채팅

결과적으로 Lync Server 2013 스트레스 및 성능 도구는 다음 구성 요소 테스트를 지원 하지 않습니다.

  - Lync 2013 영구 채팅

  - Exchange 통합 시나리오

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a>Lync Server 2013 스트레스 및 성능 도구에 포함 된 응용 프로그램 및 파일

Lync Server 2013 스트레스 및 성능 도구에는 다음과 같은 응용 프로그램이 포함 됩니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>도구</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserProvisioningTool</p></td>
<td><p>Lync Server 2013 사용자 프로비저닝 도구 이 도구는 사용자 및 연락처를 만드는 데 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>UserProfileGenerator</p></td>
<td><p>Lync Server 2013 부하 구성 도구입니다. 이 도구는 시뮬레이션할 사용자 부하의 특성을 구성 하는 데 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>L<c13> Cperftool .exe</p></td>
<td><p>Lync 서버 2013 스트레스 및 성능 도구. L<c13> Cperftool은 사용자 부하를 시뮬레이트하는 도구입니다.</p></td>
</tr>
<tr class="even">
<td><p>Default. tmx</p></td>
<td><p>Lync Server 2013 로깅 도구를 사용 하려면 Default .ttmx가 필요 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>예제 프로비저닝 스크립트</p></td>
<td><p>이러한 예제는 특정 시나리오를 기반으로 부하 테스트 실행에 대 한 토폴로지를 구성 하는 데 사용 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

