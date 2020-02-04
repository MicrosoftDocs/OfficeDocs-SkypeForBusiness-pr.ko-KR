---
title: 'Lync Server 2013: 통화 파킹에 대 한 배포 프로세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a00c354aa29a3c9a431b18a686105ab16d94c54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a>Lync Server 2013의 통화 공원 배포 프로세스

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-25_

이 섹션에서는 통화 공원 응용 프로그램 배포 단계에 대해 간략하게 설명 합니다. 통화 공원를 구성 하기 전에 엔터프라이즈 음성을 사용 하 여 Enterprise Edition 또는 Standard Edition을 배포 해야 합니다. 통화 공원에 필요한 구성 요소는 엔터프라이즈 음성을 구축할 때 설치 되 고 사용 가능 합니다.

### <a name="call-park-deployment-process"></a>통화 파킹 배포 프로세스

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
<th>필수 그룹 및 역할</th>
<th>배포 설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>궤도 테이블에서 통화 공원 궤도 범위 구성</p></td>
<td><p>Lync Server 제어판 또는 <strong>CSCallParkOrbit</strong> cmdlet을 사용 하 여 통화 공원에 궤도 범위를 만들고 통화 공원 응용 프로그램을 호스팅하는 응용 프로그램 서비스와 연결 합니다.</p>
<div>

> [!NOTE]  
> 기존 다이얼 플랜을 완벽 하 게 통합 하기 위해 일반적으로 궤도 범위는 가상 확장 블록으로 구성 됩니다. 직접 연결 된 전화 접속 (연결) 번호를 통화 공원 궤도 테이블의 궤도 번호로 지정 하는 것은 지원 되지 않습니다.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Lync Server 2013에서 통화 공원 궤도 범위 만들기 또는 수정</a></p></td>
</tr>
<tr class="even">
<td><p>통화 파킹 설정 구성</p></td>
<td><p><strong>CsCpsConfiguration</strong> cmdlet을 사용 하 여 통화 공원 설정을 구성 합니다. 적어도 파킹 된 통화 시간 초과 시 사용할 대체 대상을 구성 하려면 <strong>Ontimeouturi</strong> 옵션을 구성 하는 것이 좋습니다. 다음 설정을 구성할 수도 있습니다.</p>
<ul>
<li><p>) <strong>Enablemusiconhold</strong> 대기 음악을 사용 하거나 사용 하지 않도록 설정 합니다.</p></li>
<li><p>) <strong>MaxCallPickupAttempts</strong> 호출을 URI (Fallback Uniform resource Identifier)로 전달 하기 전에 파킹 된 통화가 응답 전화로 다시 연결 하는 횟수를 확인 합니다.</p></li>
<li><p>) 통화에 응답 한 전화기로 전화를 <strong>CallPickupTimeoutThreshold</strong> 전에 대기 하는 시간을 결정 합니다.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">Lync Server 2013에서 통화 공원 설정 구성</a></p></td>
</tr>
<tr class="odd">
<td><p>선택적으로 음악을 보류할 때 사용자 지정</p></td>
<td><p>기본 음악을 누르고 싶지 않은 경우 <strong>CsCallParkServiceMusicOnHoldFile</strong> cmdlet을 사용 하 여 오디오 파일을 사용자 지정 하 고 업로드 합니다.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">Lync Server 2013에서 통화 공원 음악을 보류할 때 사용자 지정</a></p></td>
</tr>
<tr class="even">
<td><p>사용자에 게 전화를 걸 수 있도록 음성 정책 구성</p></td>
<td><p>Lync Server 제어판 또는 <strong>EnableCallPark</strong> 옵션과 함께 <strong>CSVoicePolicy</strong> cmdlet을 사용 하 여 음성 정책 사용자에 대 한 통화 대기를 사용 하도록 설정 합니다.</p>
<div>

> [!NOTE]  
> 기본적으로 모든 사용자에 대해 통화 대기를 사용할 수 없습니다.


</div>
<div>

> [!NOTE]  
> 여러 음성 정책을 사용 하는 경우 기본 정책만이 아니라 각 음성 정책에 대해 EnableCallPark 속성이 설정 되어 있는지 확인 합니다.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">Lync Server 2013에서 사용자 용 통화 공원 사용</a></p></td>
</tr>
<tr class="odd">
<td><p>통화 대기에 대한 정규화 규칙 확인</p></td>
<td><p>통화 공원 orbits는 정규화 해서는 안 됩니다. 정규화 규칙에 궤도 범위 중 어느 것도 포함 되어 있지 않은지 확인 합니다. 필요한 경우 orbits의 정규화를 방지 하는 추가 정규화 규칙을 만듭니다.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Lync Server 2013에서 통화 공원에 대 한 정규화 규칙 확인</a></p></td>
</tr>
<tr class="even">
<td><p>통화 공원 배포 확인</p></td>
<td><p>주차장 및 통화 검색을 테스트 하 여 구성이 예상 대로 작동 하는지 확인 합니다.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-call-park-deployment.md">) Lync Server 2013에서 통화 공원 배포 확인</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

