---
title: 'Lync Server 2013: 응답 그룹 재해 복구 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7df32074881ffac854294e0835287802126f1fd5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013에서 응답 그룹 재해 복구 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

이 섹션에서는 재해 복구용으로 응답 그룹을 준비하는 몇 가지 방법에 대해 설명하며 재해 복구 프로세스에 대해 간략하게 살펴봅니다.

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a>응답 그룹 재해 복구 준비

재해 복구 절차를 준비 및 수행할 때는 다음 사항을 기억하십시오.

<div>


> [!NOTE]  
> 동시 사용 환경에서는이 문서에서 설명 하는 재해 복구 절차에 대해 Lync Server 2013 response 그룹만 지원 됩니다.



</div>

  - 용량을 계획할 때 재해 복구도 계획합니다. 재해 복구 용량의 경우 쌍으로 지정된 풀의 각 풀이 두 풀의 모든 응답 그룹 작업을 처리할 수 있어야 합니다. 응답 그룹 용량 계획에 대 한 자세한 내용은 [Lync Server 2013에서 응답 그룹에 대 한 용량 계획](lync-server-2013-capacity-planning-for-response-group.md)을 참조 하십시오.

  - 이 문서에서 설명 하는 내보내기 절차를 사용 하 여 응답 그룹 응용 프로그램을 배포한 모든 프런트 엔드 풀에 있는 모든 응답 그룹 구성의 백업 복사본을 정기적으로 사용 합니다. 자세한 내용은 [Lync Server 2013의 응답 그룹 재해 복구 절차](lync-server-2013-response-group-disaster-recovery-procedures.md)를 참조 하십시오. 백업 복사본은 안전한 위치에 보관합니다.

  - 응답 그룹 응용 프로그램에 사용한 모든 원본 오디오 파일의 백업 복사본을 보관 합니다 (예를 들어, 모든 레코딩 및 음악 대기 파일 포함). 백업 파일은 안전한 위치에 보관합니다.

  - Lync Server 2013 재해 복구의 경우 모든 응답 그룹 설정에는 배포 전체에서 고유한 이름이 있어야 합니다. 이 요구 사항은 워크플로, 큐, 에이전트 그룹, 휴일 집합 및 업무 시간에 적용됩니다. 기본 풀과 백업 풀이 아직 활성 상태일 때와 장애 조치(failover) 절차를 시작하기 전에 이 요구 사항이 충족되었는지 확인해야 합니다. 응답 그룹 데이터를 백업 풀로 가져오는 동안 이름 충돌이 발생하는 경우 가져오기가 실패합니다. 가져오기 및 장애 조치(failover) 절차를 완료하려면 백업 풀에서 응답 그룹 개체 이름을 바꾸거나, -ResolveNameConflicts 매개 변수를 포함하여 **Import-CsRgsConfiguration** cmdlet을 사용해 응답 그룹 개체에 고유한 식별 번호를 추가함으로써 충돌을 자동으로 해결하는 방법으로 이름 충돌을 해결해야 합니다.

  - 일반적으로는 일별 백업을 수행하는 것이 좋지만 변경 내용이 많은 경우에는 백업을 더 자주 수행하도록 예약할 수 있습니다. 재해 시 손실될 수 있는 정보의 양은 백업의 빈도와 변경 내용의 양 및 변경 빈도에 따라 달라집니다.

  - 재해 또는 장애 조치(failover) 작업을 수행하기 전에 응답 그룹을 백업 풀로 가져올 수 있습니다. 응답 그룹을 미리 가져오면 호출이 백업 풀로 라우팅되는 즉시 Lync Server 응답 그룹 서비스를 백업 풀에 복원할 수 있으므로 가동 중지 시간이 단축 됩니다.
    
    <div>
    

    > [!NOTE]  
    > 응답 그룹 응용 프로그램은 장애 조치 (failover)가 완료 될 때까지 비활성 풀에 속한 에이전트에 연결할 수 없습니다. 이 시간 동안에는 응답 그룹 응용 프로그램이 해당 에이전트를 사용할 수 없는 것으로 통화를 처리 합니다.

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a>응답 그룹 재해 복구 프로세스

재해 시 다음 복구 방식 중 하나를 사용하여 응답 그룹을 복구할 수 있습니다.

  - 백업 풀로 장애 조치(failover) 한 다음 원본 풀로 장애 복구(failback)합니다.

  - 백업 풀로 장애 조치(failover)하고 다른 FQDN(정규화된 도메인 이름)을 사용하여 새 풀을 만든 후에 응답 그룹을 새 풀로 가져옵니다.

재해 복구의 장애 조치(failover) 단계 중에 응답 그룹은 여러 풀, 즉 사용할 수 없는 기본 풀과 백업 풀에 있습니다. 두 풀의 응답 그룹 이름과 소유자(기본 풀)는 같지만 상위 항목은 다릅니다.

다른 FQDN을 사용해 새 풀을 만들어서 복구하는 경우에는 응답 그룹을 가져올 때 응답 그룹 소유자로 새 풀을 할당해야 합니다. 응답 그룹 소유권은 -OverwriteOwner 매개 변수를 포함하여 **Import-CsRgsConfiguration** cmdlet을 사용해 소유권을 명시적으로 다시 할당하지 않으면 이처럼 다시 할당할 때까지 원본 풀에 유지됩니다.

<div>


> [!NOTE]  
> 또한 동일한 FQDN을 사용 하는지 여부에 관계 없이 복구 중에 풀을 다시 구성한 경우에는-OverwriteOwner 매개 변수를 사용 해야 합니다. 풀을 다시 작성하지 않은 경우에는 -OverwriteOwner 매개 변수를 사용하지 않아도 되지만, 응답 그룹을 기본 풀로 다시 가져올 때마다 이 매개 변수를 다시 사용할 수 있습니다.



</div>

풀 당 응용 프로그램 수준 응답 그룹 구성 설정 집합을 하나만 정의할 수 있습니다. 이러한 설정에는 기본 통화 대기음 구성, 기본 통화 대기음 오디오 파일, 에이전트 되걸기 유예 기간, 통화 컨텍스트 구성 등이 있습니다. 이러한 구성 설정을 보려면 **Get-CsRgsConfiguration** cmdlet을 실행합니다. **Export-csrgsconfiguration** cmdlet에 대 한 자세한 내용은 [get-export-csrgsconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)를 참조 하십시오.

-ReplaceExistingSettings 매개 변수를 포함해 **Import-CsRgsConfiguration** cmdlet을 사용하여 풀 간에 이러한 응용 프로그램 수준 설정을 전송할 수는 있지만 이렇게 하면 대상 풀의 설정이 재정의됩니다.

<div>


> [!IMPORTANT]  
> 다른 풀로 설정을 전송하는 작업과 관련된 이 제약 조건은 응용 프로그램 수준 설정 및 기본 통화 대기음 오디오 파일에만 해당됩니다. 에이전트 그룹, 큐, 워크플로, 업무 시간 및 휴일 집합에는 해당 제약 조건이 적용되지 않습니다.



</div>

재해 중에 백업 풀의 응용 프로그램 수준 설정을 바꾸지 않으려는 경우 기본 풀을 복구할 수 없으면 기본 풀의 응용 프로그램 수준 설정이 손실됩니다. 복구 중에 새 풀을 만들어 기본 풀을 대체해야 하는 경우(같은 FQDN 또는 다른 FQDN 사용)에는 원본 응용 프로그램 수준 설정을 복구할 수 없습니다. 이 경우 이러한 설정을 사용하여 새 풀을 구성하고 통화 대기음 오디오 파일을 포함해야 합니다.

**Import-CsRgsConfiguration** cmdlet을 사용하여 재해 중에 응용 프로그램 수준 설정을 기본 풀에서 백업 풀로 전송하기로 결정하는 경우, 기본 풀에서 백업 풀로 설정을 전송한 것과 같은 방법으로 복구 중에 설정을 백업 풀에서 새 풀로 전송할 수 있습니다.

아래 표에는 응답 그룹 복구 시 수행하는 단계가 간략하게 나와 있습니다.

이러한 단계를 수행 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 응답 그룹 재해 복구 절차](lync-server-2013-response-group-disaster-recovery-procedures.md)를 참조 하십시오.

### <a name="response-group-disaster-recovery-steps"></a>응답 그룹 재해 복구 단계

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>단계</th>
<th>단계</th>
<th>필수 그룹 및 역할</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>중단 전</p></td>
<td><p>루틴을 사용 하 여 <strong>export-csrgsconfiguration</strong> cmdlet을 실행 하 여 응답 그룹 응용 프로그램이 배포 되는 모든 프런트 엔드 풀에 있는 모든 응답 그룹 구성의 백업을 만듭니다.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>중단 상태</p></td>
<td><p><strong>Export-csrgsconfiguration</strong> cmdlet을 실행 하 여 백업 된 Lync Server 응답 그룹 서비스 구성을 기본 풀에서 백업 풀로 가져옵니다.</p>
<div>

> [!NOTE]  
> 백업 풀의 응용 프로그램 수준 응답 그룹 설정을 기본 풀의 설정으로 바꾸려면 – ReplaceExistingSettings 매개 변수를 사용 합니다. 응용 프로그램 수준 설정을 기본 풀에서 백업 풀로 전송하지 않는 경우 기본 풀을 복구할 수 없으면 기본 풀의 설정이 손실됩니다.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="odd">
<td><p>가져오기 후</p></td>
<td><p>-ShowAll 매개 변수 (모든 응답 그룹 표시) 또는-Owner 매개 변수 (가져온 응답 그룹만 표시)를 사용 하 여 응답 그룹 cmdlet을 실행 하 여 모든 응답 그룹 구성을 백업 풀로 가져왔는지 확인 합니다.</p>
<div>

> [!IMPORTANT]  
> -ShowAll 매개 변수 또는 -Owner 매개 변수를 사용하지 않으면 백업 풀로 가져온 응답 그룹이 cmdlet에서 반환하는 결과에 나열되지 않습니다.


</div>
<p>다음 cmdlet을 실행합니다.</p>
<ul>
<li><p><strong>Get-csrgsworkflow</strong></p></li>
<li><p><strong>Get-csrgsqueue</strong></p></li>
<li><p><strong>Get-csrgsagentgroup</strong></p></li>
<li><p><strong>Get-csrgshoursofbusiness</strong></p></li>
<li><p><strong>New-csrgsholidayset</strong></p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>장애 조치(failover) 후</p></td>
<td><ul>
<li><p>백업 풀로 가져온 응답 그룹에 대해 테스트 통화를 수행하여 통화가 올바르게 처리되는지 확인합니다.</p></li>
<li><p>모든 공식 에이전트가 백업 풀에서 공식 그룹에 다시 로그인해야 합니다.</p></li>
<li><p>구성 변경 내용을 관리합니다.</p>
<p>백업 풀의 응답 그룹은 백업 풀로 가져온 것이든 백업 풀이 소유한 것이든 중단 상태에서 일반적인 방법으로 수정할 수 있습니다.</p>
<div>

> [!IMPORTANT]  
> Lync Server 관리 셸을 사용 하 여 백업 풀로 가져온 응답 그룹을 관리 해야 합니다. Lync Server 제어판을 사용 하 여 이러한 응답 그룹은 백업 풀에 있을 때 관리할 수 없습니다.


</div></li>
</ul></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="odd">
<td><p>복구 후/장애 복구(failback) 전</p></td>
<td><p>-Source 매개 변수를 백업 풀로, -Owner 매개 변수를 기본 풀로 지정하여 <strong>Export-CsRgsConfiguration</strong> cmdlet을 실행해 백업 풀에서 기본 풀이 소유한 응답 그룹을 내보냅니다.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>장애 복구(failback) 후</p></td>
<td><ul>
<li><p><strong>Import-CsRgsConfiguration</strong> cmdlet을 실행하여 응답 그룹을 기본 풀로 다시 가져옵니다.</p>
<div>

> [!NOTE]  
> 기본 풀을 복구할 수 없어 새 풀을 배포해 기본 풀을 대체하는 경우에는 -ReplaceExistingSettings 매개 변수를 사용하여 응용 프로그램 수준 설정을 백업 풀에서 새 풀로 전송합니다. 백업 풀에서 설정을 전송하지 않으면 새 풀에서는 기본 설정을 사용합니다.


</div></li>
<li><p>-ShowAll 매개 변수(모든 응답 그룹 표시) 또는 -Owner 매개 변수(가져온 응답 그룹만 표시)를 포함해 다음 cmdlet을 실행하여 모든 응답 그룹 구성을 기본 풀로 올바르게 다시 가져왔는지 확인합니다.</p>
<ul>
<li><p><strong>Get-csrgsworkflow</strong></p></li>
<li><p><strong>Get-csrgsqueue</strong></p></li>
<li><p><strong>Get-csrgsagentgroup</strong></p></li>
<li><p><strong>Get-csrgshoursofbusiness</strong></p></li>
<li><p><strong>New-csrgsholidayset</strong></p></li>
</ul></li>
<li><p>기본 풀로 다시 가져온 응답 그룹에 대해 테스트 통화를 수행하여 통화가 올바르게 처리되는지 확인합니다.</p></li>
<li><p>원하는 경우 백업 풀에서 -RemoveExportedConfiguration 매개 변수를 포함하여 <strong>Export-CsRgsConfiguration</strong> cmdlet을 실행해 기본 풀이 소유한 응답 그룹을 백업 풀에서 제거합니다.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

