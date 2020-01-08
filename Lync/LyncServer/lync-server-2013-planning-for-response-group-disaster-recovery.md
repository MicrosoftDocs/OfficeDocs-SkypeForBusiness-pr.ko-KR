---
title: 'Lync Server 2013: 응답 그룹 재해 복구 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70622364349eb83ecbc171cb3d5bf894ba03d3f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013의 응답 그룹 재해 복구 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

이 섹션에서는 재해 복구를 위해 응답 그룹을 준비 하는 몇 가지 방법과 재해 복구 프로세스에 대 한 개요를 제공 합니다.

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a>응답 그룹 재해 복구 준비

재해 복구 절차를 준비 하 고 수행할 때 다음 사항에 유의 하세요.

<div>


> [!NOTE]  
> 공존 환경에서는이 문서에서 설명 하는 재해 복구 절차에 대해 Lync Server 2013 응답 그룹만 지원 됩니다.



</div>

  - 용량 계획을 수립할 때 재해 복구 계획을 수립 합니다. 재해 복구 용량을 위해 쌍으로 연결 된 풀의 각 풀은 두 풀의 모든 응답 그룹에 대 한 작업 부하를 처리할 수 있어야 합니다. 응답 그룹 용량 계획에 대 한 자세한 내용은 [Lync Server 2013의 응답 그룹에 대 한 용량 계획](lync-server-2013-capacity-planning-for-response-group.md)을 참조 하세요.

  - 이 문서에서 설명 하는 내보내기 절차를 사용 하 여 응답 그룹 응용 프로그램을 배포한 모든 프런트 엔드 풀에 있는 모든 응답 그룹 구성의 정기 백업 복사본을 찍습니다. 자세한 내용은 [Lync Server 2013의 응답 그룹 장애 복구 절차](lync-server-2013-response-group-disaster-recovery-procedures.md)를 참조 하세요. 백업 복사본은 안전한 위치에 보관 하세요.

  - 기록 및 음악 포함 파일을 포함 하 여 응답 그룹 응용 프로그램에 사용 된 모든 원본 오디오 파일의 백업 복사본을 별도로 보관 합니다. 백업 파일은 안전한 곳에 보관 하세요.

  - Lync Server 2013 재해 복구의 경우 모든 응답 그룹 설정에는 배포 전체에서 고유한 이름이 있어야 합니다. 이 요구 사항은 워크플로, 큐, 에이전트 그룹, 휴일 집합 및 비즈니스 시간에 적용 됩니다. 기본 및 백업 풀이 계속 활성 상태 이거나 장애 조치 (failover) 절차를 시작 해야 하는 경우이 요구 사항이 충족 되는지 확인 해야 합니다. 응답 그룹 데이터를 백업 풀로 가져오는 동안 이름 충돌이 발생 하는 경우 가져오기에 실패 합니다. 가져오기 및 장애 조치 절차를 완료 하려면 백업 풀에서 응답 그룹 개체의 이름을 바꾸거나 – ResolveNameConflicts 매개 변수와 함께 **CsRgsConfiguration** cmdlet을 사용 하 여 응답 그룹 개체에 고유 하 게 식별 되는 번호를 추가 하 여 충돌을 자동으로 해결 하는 이름 충돌을 해결 해야 합니다.

  - 일반적으로 매일 백업을 수행 하는 것이 좋지만 많은 양의 변경 내용이 있는 경우에는 백업을 더 자주 예약할 수 있습니다. 재해가 발생 했을 때 손실 될 수 있는 정보의 양은 백업 빈도 및 변경 빈도 및 볼륨에 따라 달라 집니다.

  - 재해 또는 장애 조치 작업이 발생 하기 전에 응답 그룹을 백업 풀로 가져올 수 있습니다. 응답 그룹을 미리 가져오면 호출이 백업 풀로 라우팅되는 즉시 Lync Server 응답 그룹 서비스를 백업 풀에 복원할 수 있기 때문에 가동 중지 시간이 줄어듭니다.
    
    <div>
    

    > [!NOTE]  
    > 응답 그룹 응용 프로그램은 장애 조치가 완료 될 때까지 비활성 풀에 속한 에이전트에 연결할 수 없습니다. 이 기간 동안 응답 그룹 응용 프로그램은 해당 에이전트를 사용할 수 없는 것 처럼 통화를 처리 합니다.

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a>응답 그룹 재해 복구 프로세스

재해가 발생할 경우 다음 복구 방법 중 하나를 사용 하 여 응답 그룹을 복구할 수 있습니다.

  - 백업 풀로 장애 조치 하 고 원래 풀로 장애 복구 합니다.

  - 백업 풀로 장애 조치 하 고 다른 FQDN (정규화 된 도메인 이름)을 사용 하 여 새 풀을 만든 다음 응답 그룹을 새 풀로 가져옵니다.

재해 복구의 장애 조치 단계에서 응답 그룹은 기본 풀 (사용할 수 없음) 및 백업 풀에 여러 풀에 위치 합니다. 두 풀의 응답 그룹에는 동일한 이름과 소유자 (기본 풀)가 있지만 부모 항목이 다릅니다.

다른 FQDN을 사용 하 여 새 풀을 만들어 복구 하는 경우 새 풀을 가져올 때 응답 그룹의 소유자로 할당 해야 합니다. **CsRgsConfiguration** cmdlet에서 – OverwriteOwner 매개 변수를 사용 하 여 소유권을 명시적으로 다시 할당할 때 까지는 또는 응답 그룹의 소유권이 원본 풀에 남아 있습니다.

<div>


> [!NOTE]  
> 또한 복구 중에 풀을 다시 작성 한 경우 (즉, 응답 그룹 데이터베이스가 비어 있는 경우), 동일한 FQDN을 사용 하는지 여부에 상관 없이 – OverwriteOwner 매개 변수를 사용 해야 합니다. 풀을 다시 빌드하지 않은 경우 – OverwriteOwner 매개 변수를 사용할 필요가 없지만 응답 그룹을 다시 기본 풀로 가져올 때마다이 매개 변수를 사용할 수 있습니다.



</div>

풀 당 하나의 응용 프로그램 수준 응답 그룹 구성 설정 집합을 하나만 정의할 수 있습니다. 이러한 설정에는 기본 음악 보관 구성, 기본 음악 오디오 파일, 에이전트 ringback 유예 기간, 호출 컨텍스트 구성 등이 포함 됩니다. 이러한 구성 설정을 보려면 **Get-CsRgsConfiguration** cmdlet을 실행 합니다. **CsRgsConfiguration** cmdlet에 대 한 자세한 내용은 [get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)를 참조 하세요.

**CsRgsConfiguration** cmdlet에서 – ReplaceExistingSettings 매개 변수를 사용 하 여 해당 응용 프로그램 수준의 설정을 다른 풀로 전송할 수 있지만, 이렇게 하면 대상 풀의 설정이 재정의 됩니다.

<div>


> [!IMPORTANT]  
> 다른 풀로 설정 전송에 대 한이 제약 조건은 응용 프로그램 수준 설정 및 기본 음악/보류 오디오 파일에만 적용 됩니다. 에이전트 그룹, 큐, 워크플로, 비즈니스 시간 및 휴일 집합에는 적용 되지 않습니다.



</div>

재해가 발생 했을 때 백업 풀의 응용 프로그램 수준 설정을 바꾸지 않고 주 풀을 복구할 수 없는 경우 기본 풀의 응용 프로그램 수준 설정이 손실 됩니다. 복구 하는 동안 기본 풀을 바꿔야 하는 FQDN 또는 fqdn이 다른 새 풀을 만들어야 하는 경우 원래 응용 프로그램 수준 설정을 복구할 수 없습니다. 이 경우 이러한 설정을 사용 하 여 새 풀을 구성 하 고 음악 대기 오디오 파일을 포함 해야 합니다.

재해가 발생 한 동안 **CsRgsConfiguration** cmdlet을 사용 하 여 기본 풀의 응용 프로그램 수준 설정을 백업 풀로 전송 하기로 결정 한 경우 복구 중에 백업 풀의 설정을 기본 풀에서 백업 풀로 전송 하는 것과 동일한 방법으로 해당 풀로 전송할 수 있습니다.

다음 표에서는 응답 그룹 복구와 관련 된 단계를 간략하게 설명 합니다.

이러한 단계를 수행 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 응답 그룹 장애 복구 절차](lync-server-2013-response-group-disaster-recovery-procedures.md)를 참조 하세요.

### <a name="response-group-disaster-recovery-steps"></a>응답 그룹 재해 복구 단계

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>단계의</th>
<th>방법은</th>
<th>필수 그룹 및 역할</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>중단 전</p></td>
<td><p>루틴을 기준으로 <strong>CsRgsConfiguration</strong> cmdlet을 실행 하 여 응답 그룹 응용 프로그램이 배포 된 모든 프런트 엔드 풀의 모든 응답 그룹 구성에 대 한 백업을 만듭니다.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>비활성 동안</p></td>
<td><p><strong>가져오기-CsRgsConfiguration</strong> cmdlet을 실행 하 여 백업 된 Lync Server 응답 그룹 서비스 구성을 기본 풀에서 백업 풀로 가져옵니다.</p>
<div>

> [!NOTE]  
> 백업 풀의 응용 프로그램 수준 응답 그룹 설정을 기본 풀의 설정으로 대체 하려면 – ReplaceExistingSettings 매개 변수를 사용 합니다. 기본 풀의 응용 프로그램 수준 설정을 백업 풀로 전송 하지 않고 주 풀을 복구할 수 없는 경우 기본 풀의 설정이 손실 됩니다.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="odd">
<td><p>가져온 후</p></td>
<td><p>모든 응답 그룹 구성을 백업 풀로 가져왔는지 확인 하려면 – ShowAll 매개 변수 (모든 응답 그룹 표시) 또는 – Owner 매개 변수 (가져온 응답 그룹만 표시)를 사용 하 여 응답 그룹 cmdlet을 실행 합니다.</p>
<div>

> [!IMPORTANT]  
> – ShowAll 매개 변수 또는 – Owner 매개 변수를 사용 하지 않는 경우 백업 풀로 가져온 응답 그룹이 cmdlet에서 반환 된 결과에 나열 되지 않습니다.


</div>
<p>다음 cmdlet을 실행 합니다.</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>장애 조치 이후</p></td>
<td><ul>
<li><p>백업 풀로 가져온 응답 그룹에 테스트 호출을 배치 하 고 통화가 올바르게 처리 되었는지 확인 합니다.</p></li>
<li><p>모든 공식 에이전트는 백업 풀의 정식 그룹에 다시 로그인 해야 합니다.</p></li>
<li><p>구성 변경 내용 관리:</p>
<p>백업 풀로 가져올지 또는 백업 풀에서 소유 하 든 지에 관계 없이 백업 풀의 응답 그룹은 중단 중 평소와 같이 수정 될 수 있습니다.</p>
<div>

> [!IMPORTANT]  
> Lync Server Management Shell을 사용 하 여 백업 풀로 가져온 응답 그룹을 관리 해야 합니다. 이 응답 그룹은 백업 풀에 있는 동안 Lync Server 제어판을 사용 하 여 관리할 수 없습니다.


</div></li>
</ul></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="odd">
<td><p>복구 후, 장애 복구 전</p></td>
<td><p>-Source 매개 변수를 백업 풀로 지정 하 고-Owner 매개 변수를 기본 풀로 <strong>CsRgsConfiguration</strong> cmdlet을 실행 하 여 기본 풀이 소유한 응답 그룹을 백업 풀에서 내보냅니다.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>장애 복구 후</p></td>
<td><ul>
<li><p><strong>CsRgsConfiguration</strong> cmdlet을 실행 하 여 응답 그룹을 다시 기본 풀로 가져옵니다.</p>
<div>

> [!NOTE]  
> 주 풀을 복구할 수 없고 새 풀을 배포 하 여 해당 파일을 바꾸려면 – ReplaceExistingSettings 매개 변수를 사용 하 여 백업 풀의 응용 프로그램 수준 설정을 새 풀로 이전 합니다. 백업 풀에서 설정을 전송 하지 않으면 새 풀에 기본 설정이 사용 됩니다.


</div></li>
<li><p>모든 응답 그룹 구성을 성공적으로 다시 기본 풀로 가져왔는지 확인 하려면 – ShowAll 매개 변수 (모든 응답 그룹을 표시 하기 위해) 또는 – Owner 매개 변수를 사용 하 여 다음 cmdlet을 실행 합니다 (가져온 응답 그룹만 표시).</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></li>
<li><p>기본 풀로 다시 가져온 응답 그룹에 테스트 호출을 배치 하 고 통화가 올바르게 처리 되었는지 확인 합니다.</p></li>
<li><p>또는-RemoveExportedConfiguration 매개 변수를 사용 하 여 백업 풀에서 <strong>CsRgsConfiguration</strong> cmdlet을 실행 하 여 백업 풀의 기본 풀에서 소유 하는 응답 그룹을 제거할 수도 있습니다.</p></li>
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

