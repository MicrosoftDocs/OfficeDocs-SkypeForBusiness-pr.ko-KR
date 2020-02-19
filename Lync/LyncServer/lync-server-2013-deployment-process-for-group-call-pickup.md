---
title: 'Lync Server 2013: 그룹 통화 픽업 배포 프로세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 150434b57aa90048c1009851473349093435c116
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013의 그룹 통화 픽업 배포 프로세스

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-25_

이 섹션에서는 그룹 통화 픽업 배포와 관련 된 단계에 대 한 개요를 제공 합니다. 그룹 호출 픽업를 구성 하기 전에 enterprise Edition 또는 Standard Edition을 Enterprise Voice로 배포 해야 합니다. Enterprise Voice를 배포할 때 그룹 통화 픽업에 필요한 구성 요소를 설치 하 고 사용 하도록 설정 합니다.

### <a name="group-call-pickup-deployment-process"></a>그룹 통화 픽업 배포 프로세스

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
<td><p>토폴로지에서 SEFAUtil resource kit 도구 사용</p></td>
<td><ol>
<li><p>새 <strong>new-cstrustedapplicationpool</strong> cmdlet을 사용 하 여 신뢰할 수 있는 새 응용 프로그램 풀을 만듭니다.</p></li>
<li><p><strong>New-cstrustedapplication</strong> cmdlet을 사용 하 여 SEFAUtil 도구를 신뢰할 수 있는 응용 프로그램으로 지정 합니다.</p></li>
<li><p><strong>Enable-cstopology</strong> cmdlet을 실행 하 여 토폴로지를 사용 하도록 설정 합니다.</p></li>
<li><p>1 단계에서 만든 신뢰할 수 있는 응용 프로그램 풀에 있는 프런트 엔드 서버에 resource kit 도구를 설치 합니다.</p></li>
<li><p>배포에 있는 사용자의 착신 전환 설정을 표시 하기 위해 실행 하 여 SEFAUtil가 제대로 실행 되 고 있는지 확인 합니다.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">Lync Server 2013에서 SEFAUtil 도구 배포</a></p></td>
</tr>
<tr class="even">
<td><p>통화 대기 궤도 테이블에서 통화 픽업 번호 범위 구성</p></td>
<td><p><strong>Get-cscallparkorbit</strong> cmdlet을 사용 하 여 통화 대기 궤도 테이블에 통화 픽업 번호 범위를 만들고 call pickup 범위에 grouppickup 형식을 지정 합니다.</p>
<div>

> [!NOTE]  
> Lync Server 관리 셸을 사용 하 여 통화 대기 궤도 테이블에서 그룹 통화 픽업 번호 범위를 만들고, 수정 하 고, 제거 하 고, 확인 해야 합니다. Lync Server 제어판에서는 그룹 통화 픽업 번호 범위를 사용할 수 없습니다.


</div>
<div>

> [!NOTE]  
> 기존 다이얼 플랜과 원활 하 게 통합 하기 위해 숫자 범위는 일반적으로 가상 확장 블록으로 구성 됩니다. 통화 대기 번호 표에서 범위 번호를 직접 안쪽 전화 걸기 (*)로 지정 하는 것은 지원 되지 않습니다.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Lync Server 2013에서 통화 픽업 그룹 번호 구성</a></p></td>
</tr>
<tr class="odd">
<td><p>사용자에 게 통화 픽업 번호 할당 및 사용자에 대 한 그룹 통화 픽업 사용</p></td>
<td><p>SEFAUtil resource kit tool의/enablegrouppickup 매개 변수를 사용 하 여 그룹 통화 픽업을 사용 하도록 설정 하 고 사용자에 대 한 통화 픽업 번호를 할당 합니다.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Lync Server 2013의 사용자에 대 한 그룹 통화 픽업 사용 설정 및 그룹 번호 할당</a></p></td>
</tr>
<tr class="even">
<td><p>사용자에 게 할당 된 통화 픽업 번호 및 기타 관심 수를 알립니다.</p></td>
<td><p>모든 사용자가 그룹 통화 픽업 사용자에 대 한 통화를 검색할 수 있으므로 사용자는 두 개 이상의 그룹을 모니터링할 수 있습니다.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Lync Server 2013의 사용자에 게 그룹 통화 픽업 할당 전달</a></p></td>
</tr>
<tr class="odd">
<td><p>그룹 통화 픽업 배포 확인</p></td>
<td><p>통화 배치 및 검색을 테스트 하 여 구성이 예상 대로 작동 하는지 확인 합니다.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">반드시 Lync Server 2013에서 그룹 통화 픽업 배포 확인</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

