---
title: 'Lync Server 2013: 통화 대기에 대 한 배포 프로세스'
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
ms.openlocfilehash: 997097da30db000df82cba020b043748a1a5f62d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522635"
---
# <a name="deployment-process-for-call-park-in-lync-server-2013"></a>Lync Server 2013의 통화 대기 배포 프로세스

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-25_

이 섹션에서는 통화 대기 응용 프로그램을 배포 하는 과정에 대 한 개요를 제공 합니다. 통화 대기를 구성 하기 전에 enterprise Edition 또는 Standard Edition을 Enterprise Voice로 배포 해야 합니다. 통화 대기에 필요한 구성 요소는 Enterprise Voice를 배포할 때 설치 및 활성화 됩니다.

### <a name="call-park-deployment-process"></a>통화 대기 배포 프로세스

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
<th>필수 그룹 및 역할</th>
<th>배포 설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>파킹된 통화 번호 표에서 통화 대기 파킹된 통화 번호 범위 구성</p></td>
<td><p>Lync Server 제어판 또는 <strong>get-cscallparkorbit</strong> cmdlet을 사용 하 여 통화 대기 궤도 테이블에 궤도 범위를 만들고 통화 대기 응용 프로그램을 호스트 하는 응용 프로그램 서비스에 연결 합니다.</p>
<div>

> [!NOTE]  
> 기존 다이얼 플랜과 원활하게 통합할 수 있도록, 파킹된 통화 번호 범위는 일반적으로 가상 내선 번호 블록으로 구성됩니다. DID(Direct Inward Dialing) 번호를 통화 대기 파킹된 통화 번호 표에서 파킹된 통화 번호로 할당할 수는 없습니다.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Lync Server 2013에서 통화 대기 번호 범위 만들기 또는 수정</a></p></td>
</tr>
<tr class="even">
<td><p>통화 파킹 설정 구성</p></td>
<td><p><strong>New-cscpsconfiguration</strong> cmdlet을 사용 하 여 통화 대기 설정을 구성 합니다. 최소 대기 통화 시간이 초과 될 때 사용할 대체 대상을 구성 하려면 <strong>Ontimeouturi</strong> 옵션을 구성 하는 것이 좋습니다. 또한 다음 설정을 구성할 수 있습니다.</p>
<ul>
<li><p>(선택 사항) <strong>EnableMusicOnHold</strong> - 대기 음악을 사용하거나 사용하지 않도록 설정합니다.</p></li>
<li><p>(선택 사항) <strong>MaxCallPickupAttempts</strong> - 대기된 통화를 대체 URI(Uniform Resource Identifier)로 착신 전환할 때까지 해당 통화가 전화기에서 다시 울리는 횟수를 결정합니다.</p></li>
<li><p>(선택 사항) <strong>CallPickupTimeoutThreshold</strong> - 통화가 대기된 후부터 전화를 받은 전화기가 다시 울릴 때까지의 경과 시간을 결정합니다.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">Lync Server 2013의 통화 대기 설정 구성</a></p></td>
</tr>
<tr class="odd">
<td><p>원하는 경우 대기 음악을 사용자 지정합니다.</p></td>
<td><p><strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet을 사용하여 오디오 파일을 사용자 지정하고 업로드합니다(기본 대기 음악을 사용하지 않으려는 경우)</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">Lync Server 2013에서 통화 대기 음악 사용자 지정</a></p></td>
</tr>
<tr class="even">
<td><p>사용자에 대해 통화 대기를 사용 하도록 음성 정책 구성</p></td>
<td><p>음성 정책의 사용자에 대해 통화 대기를 사용 하도록 설정 하려면 Lync Server 제어판 또는 <strong>EnableCallPark</strong> 옵션을 가진 <strong>set-csvoicepolicy</strong> cmdlet을 사용 합니다.</p>
<div>

> [!NOTE]  
> 기본적으로 모든 사용자에 대해 통화 대기를 사용 하지 않도록 설정 되어 있습니다.


</div>
<div>

> [!NOTE]  
> 음성 정책이 여러 개인 경우에는 기본 정책뿐 아니라 각 음성 정책에 대해 EnableCallPark 속성이 설정되어 있는지 확인합니다.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">Lync Server 2013의 사용자에 대해 통화 대기를 사용 하도록 설정</a></p></td>
</tr>
<tr class="odd">
<td><p>통화 파킹에 대한 정규화 규칙 확인</p></td>
<td><p>통화 대기 파킹된 통화 번호는 정규화해서는 안 됩니다. 정규화 규칙에 파킹된 통화 번호 범위가 포함되어 있지 않은지 확인하고, 필요한 경우에는 파킹된 통화 번호가 정규화되지 않도록 추가 정규화 규칙을 만드십시오.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Lync Server 2013의 통화 대기에 대 한 정규화 규칙 확인</a></p></td>
</tr>
<tr class="even">
<td><p>통화 대기 배포 확인</p></td>
<td><p>파킹 및 통화 검색을 테스트 하 여 구성이 예상 대로 작동 하는지 확인 합니다.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-call-park-deployment.md">반드시 Lync Server 2013의 통화 대기 배포 확인</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

