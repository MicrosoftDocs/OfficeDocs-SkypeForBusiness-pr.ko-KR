---
title: 'Lync Server 2013: Enterprise Voice 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d6bf9f79725f1f4812ac1e1c1c3c0e3217b939b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013에서 엔터프라이즈 음성 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-12_

엔터프라이즈 음성을 배포 하려면 다음을 구성 해야 합니다.

  - 트렁크 만들기

  - 음성 정책 정의

  - 음성 경로 정의

  - 엔터프라이즈 음성에 대 한 사용자 활성화

<div>

## <a name="create-a-trunk"></a>트렁크 만들기

엔터프라이즈 음성 배포에 trunks를 정의 해야 합니다. 위치 기반 라우팅의 경우 트렁크 당 트렁크 구성을 만들어야 합니다. Lync Server 토폴로지 작성기를 사용 하 여 trunks을 정의 하 고 Lync Server Windows PowerShell command, New-Set-cstrunkconfiguration 또는 Lync Server 제어판을 사용 하 여 해당 트렁크 구성을 정의 합니다. 트렁크 구성에서 위치 기반 라우팅을 사용 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 위치 기반 라우팅 사용](lync-server-2013-enabling-location-based-routing.md)Trunks에 위치 기반 라우팅 사용 섹션을 참조 하세요. 이 예제에서는 다음 표에이 시나리오에 사용 되는 trunks 나와 있습니다.

자세한 내용은 [Lync Server 2013의 토폴로지 작성기에서 추가 Trunks 정의](lync-server-2013-define-additional-trunks-in-topology-builder.md)를 참조 하세요.


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>트렁크 이름</th>
<th>시스템 유형</th>
<th>이름</th>
<th>위치</th>
<th>중재 서버</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>트렁크 1 DEL-GW</p></td>
<td><p>PSTN 게이트웨이</p></td>
<td><p>DEL-GW</p></td>
<td><p>뉴델리</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>트렁크 2 HYD-GW</p></td>
<td><p>PSTN 게이트웨이</p></td>
<td><p>HYD-GW</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="odd">
<td><p>트렁크 3 DEL-PBX</p></td>
<td><p>PBX</p></td>
<td><p>DEL-PBX</p></td>
<td><p>뉴델리</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>트렁크 4 HYD-PBX</p></td>
<td><p>PBX</p></td>
<td><p>HYD</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a>음성 정책 정의

엔터프라이즈 음성 배포에 대 한 음성 정책을 정의 해야 합니다. 위치 기반 라우팅을 사용 하는 데 하위 집합만 있으면 사용자의 하위 집합에 위치 기반 라우팅 제한을 적용 하도록 음성 정책을 정의 합니다. 이 예제에서 다음 표에는이 시나리오에 사용 되는 음성 정책이 나와 있습니다. 이 표에는 위치 기반 라우팅과 관련 하 여 설명 하는 설정만 나와 있습니다.

자세한 내용은 [음성 정책 및 PSTN 사용 레코드 구성을 참조 하 여 Lync Server 2013의 기능 및 사용 권한 호출에 권한을 부여](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)합니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>음성 정책 1</th>
<th>음성 정책 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>음성 정책 ID</p></td>
<td><p>뉴델리 voice 정책</p></td>
<td><p>Hyderabad 음성 정책</p></td>
</tr>
<tr class="even">
<td><p>PSTN 용도</p></td>
<td><p>뉴델리 사용, PBX Del 사용, PBX Hyd 사용</p></td>
<td><p>Hyderabad 사용, PBX Hyd 사용, PBX Del 사용</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>해제</p></td>
<td><p>해제</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a>음성 경로 정의

엔터프라이즈 음성 배포에 대 한 음성 경로를 정의 해야 합니다. 이 예제에서 다음 표에는이 시나리오에 사용 되는 음성 경로가 나와 있습니다. 이 표에는 위치 기반 라우팅과 관련 하 여 설명 하는 설정만 나와 있습니다.

자세한 내용은 [Lync Server 2013에서 발신 통화에 대 한 음성 경로 구성을](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)참조 하세요.


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>음성 경로 1</th>
<th>음성 경로 2</th>
<th>음성 경로 3</th>
<th>음성 경로 4</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>이름</p></td>
<td><p>뉴델리 경로</p></td>
<td><p>Hyderabad 경로</p></td>
<td><p>PBX Del 경로</p></td>
<td><p>PBX Hyd 경로</p></td>
</tr>
<tr class="even">
<td><p>PSTN 용도</p></td>
<td><p>뉴델리 사용</p></td>
<td><p>Hyderabad 사용</p></td>
<td><p>PBX Del 사용 현황</p></td>
<td><p>PBX Hyd 사용</p></td>
</tr>
<tr class="odd">
<td><p>트렁크</p></td>
<td><p>트렁크 1 DEL-GW</p></td>
<td><p>트렁크 2 HYD-GW</p></td>
<td><p>트렁크 3 DEL-PBX</p></td>
<td><p>트렁크 4 HYD-PBX</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a>엔터프라이즈 음성에 대 한 사용자 활성화

엔터프라이즈 음성을 사용할 수 있도록 설정 하 고 이전에 정의한 음성 정책으로 해당 사용자에 게 할당 합니다. 이 예제에서는 다음 표에이 시나리오에 사용 되는 배정이 나와 있습니다. 이 표에는 위치 기반 라우팅과 관련 하 여 설명 하는 설정만 나와 있습니다.

자세한 내용은 [Lync Server 2013에서 엔터프라이즈 음성 사용자 사용](lync-server-2013-enable-users-for-enterprise-voice.md)을 참조 하세요.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>E-@에 위치한 사용자</th>
<th>Hyderabad에 있는 사용자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>연결 된 음성 정책</p></td>
<td><p>뉴델리 voice 정책</p></td>
<td><p>Hyderabad 음성 정책</p></td>
</tr>
<tr class="even">
<td><p>샘플 사용자</p></td>
<td><p>DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 위치 기반 라우팅 구성](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

