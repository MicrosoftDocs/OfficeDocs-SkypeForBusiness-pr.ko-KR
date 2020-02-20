---
title: Lync Server 2013 응답 그룹 재해 복구 절차
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ecd074254243629bbb3a6dc732b11a93cfebbe7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a>Lync Server 2013의 응답 그룹 재해 복구 절차

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

재해 복구의 장애 조치(failover) 단계 중에 응답 그룹은 여러 풀, 즉 사용할 수 없는 기본 풀과 백업 풀에 있습니다. 두 풀의 응답 그룹 이름과 소유자(기본 풀)는 같지만 상위 항목은 다릅니다. 이 기간 동안 응답 그룹 cmdlet은 약간 다르게 작동 합니다. 다음 절차에 지정 된 대로 매개 변수를 사용 해야 합니다. 장애 조치 (failover) 단계에서 cmdlet이 작동 하는 방식에 대 한 자세한 내용은 다음 홉 블로그 문서 "Lync Server 2013: 재해 복구 [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957)중 응답 그룹 복구"를 참조 하세요. 이 블로그 문서는 Lync Server 2013의 릴리스된 버전에도 적용 됩니다.

Lync Server 응답 그룹 서비스에 대 한 재해 복구를 준비 하 고 수행 하려면 다음 절차의 단계를 따르십시오.

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a>장애 조치 및 응답 그룹 장애 조치 (failover)를 수행 하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  정기적으로 백업을 수행 합니다. 명령줄에 다음을 입력합니다.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    예를 들면 다음과 같습니다.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  중단 중에 백업 풀로 장애 조치 (failover) 하는 동안 응답 그룹을 백업 풀로 가져옵니다. 명령줄에 다음을 입력합니다.
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    백업 풀의 응용 프로그램 수준 설정을 기본 풀의 설정으로 바꾸려면 – ReplaceExistingSettings 매개 변수를 포함 합니다. 예:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > 백업 풀의 설정을 바꾸지 않고 주 풀을 복구할 수 없는 경우 기본 풀 설정이 손실 됩니다. 자세한 내용은 <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Lync Server 2013에서 응답 그룹 재해 복구 계획</A>을 참조 하십시오.

    
    </div>

4.  가져온 응답 그룹을 표시 하 여 가져오기가 성공적으로 수행 되었는지 확인 합니다. 가져온 응답 그룹은 여전히 기본 풀에서 소유 하 고 있습니다. 다음을 수행합니다.
    
      - 기본 풀이 소유 하는 백업 풀의 모든 워크플로를 표시 하 고 모든 기본 풀 워크플로가 포함 되어 있는지 확인 합니다. 명령줄에 다음을 입력합니다.
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        예를 들면 다음과 같습니다.
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - 기본 풀이 소유 하는 백업 풀의 모든 큐를 표시 하 고 모든 기본 풀 큐가 포함 되어 있는지 확인 합니다. 명령줄에 다음을 입력합니다.
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        예를 들면 다음과 같습니다.
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - 기본 풀이 소유 하는 백업 풀의 모든 에이전트 그룹을 표시 하 고 모든 기본 풀 에이전트 그룹을 포함 하는지 확인 합니다. 명령줄에 다음을 입력합니다.
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        예를 들면 다음과 같습니다.
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - 기본 풀이 소유 하는 모든 비즈니스 시간을 백업 풀에 표시 하 고 모든 기본 풀의 비즈니스 시간을 포함 하는지 확인 합니다. 명령줄에 다음을 입력합니다.
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        예를 들면 다음과 같습니다.
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - 기본 풀이 소유 하는 모든 휴일 집합을 백업 풀에 표시 하 고 모든 기본 풀 휴일 집합이 포함 되어 있는지 확인 합니다. 명령줄에 다음을 입력합니다.
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        예를 들면 다음과 같습니다.
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    또는 기본 풀이 소유한 모든 응답 그룹 및-Owner 매개 변수 대신 – ShowAll 매개 변수를 사용 하 여 백업 풀이 소유한 위치를 포함 하 여 백업 풀의 모든 응답이 표시 되도록 할 수 있습니다. 예:
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > – ShowAll 매개 변수 또는-Owner 매개 변수를 사용 해야 합니다. 이러한 매개 변수 중 하나를 사용 하지 않으면 백업 풀로 가져온 응답 그룹이 cmdlet에서 반환 된 결과에 나열 되지 않습니다.

    
    </div>

5.  가져온 응답 그룹에 전화를 걸고 통화가 올바르게 처리 되는지 확인 하 여 가져오기가 성공적으로 수행 되었는지 확인 합니다.

6.  공식 에이전트 그룹의 구성원 인 에이전트에 게 백업 풀의 해당 에이전트 그룹에 로그인 하도록 요청 합니다.

7.  가져온 응답 그룹을 평소와 같이 관리 하 고 수정 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 응답 그룹이 백업 풀에 있는 동안에는 Lync Server 관리 셸을 사용 하 여 관리 해야 합니다. Lync Server 제어판을 사용 하 여 백업 풀로 가져온 응답 그룹을 관리할 수는 없습니다.

    
    </div>

8.  기본 풀이 복원 되 고 장애 복구 (failback)가 완료 되 면 백업 풀로 가져온 기본 풀 응답 그룹을 내보냅니다. 명령줄에 다음을 입력합니다.
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  응답 그룹을 다시 기본 풀로 가져옵니다. 명령줄에 다음을 입력합니다.
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    예를 들면 다음과 같습니다.
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > 복구 중에 동일한 FQDN (정규화 된 도메인 이름)을 사용 하는지 여부에 관계 없이 풀을 다시 작성 하는 경우 – OverwriteOwner 매개 변수가 필요 합니다. 기본적으로 응답 그룹을 기본 풀로 다시 가져올 때는 항상 – OverwriteOwner 매개 변수를 사용할 수 있습니다.

    
    </div>
    
    기본 풀을 대체할 새 풀 (같거나 다른 FQDN)을 배포 했으며 새 풀에 대해 백업 풀의 응용 프로그램 수준 설정을 사용 하려는 경우에는-ReplaceExistingSettings 매개 변수를 포함 합니다. 명령줄에 다음을 입력합니다.
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    예를 들면 다음과 같습니다.
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > 새 풀에 대 한 응용 프로그램 수준 설정 및 기본 음악 대기 오디오 파일을 백업 풀의 설정으로 바꾸지 않으려면 새 풀에 기본 응용 프로그램 수준 설정이 사용 됩니다.

    
    </div>

10. 가져온 응답 그룹 구성을 표시 하 여 기본 풀로 다시 가져오기가 성공적으로 완료 되었는지 확인 합니다. 다음을 수행합니다.
    
      - 기본 풀의 모든 워크플로를 표시 하 고 가져온 모든 워크플로가 포함 되어 있는지 확인 합니다. 명령줄에 다음을 입력합니다.
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        예를 들면 다음과 같습니다.
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - 기본 풀의 모든 큐를 표시 하 고 가져온 모든 큐가 포함 되어 있는지 확인 합니다. 명령줄에 다음을 입력합니다.
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        예를 들면 다음과 같습니다.
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - 기본 풀의 모든 에이전트 그룹을 표시 하 고 가져온 모든 에이전트 그룹을 포함 하는지 확인 합니다. 명령줄에 다음을 입력합니다.
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        예를 들면 다음과 같습니다.
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - 기본 풀의 모든 업무 시간을 표시 하 고 가져온 모든 비즈니스 시간을 포함 하는지 확인 합니다. 명령줄에 다음을 입력합니다.
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        예를 들면 다음과 같습니다.
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - 기본 풀의 모든 휴일 집합을 표시 하 고 가져온 휴일 집합이 모두 포함 되었는지 확인 합니다. 명령줄에 다음을 입력합니다.
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        예를 들면 다음과 같습니다.
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. 가져온 응답 그룹에 전화를 걸고 통화가 올바르게 처리 되는지 확인 하 여 가져오기가 성공적으로 수행 되었는지 확인 합니다.

12. 필요한 경우 백업 풀에서 기본 풀이 소유한 응답 그룹을 제거 합니다. 명령줄에 다음을 입력합니다.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    예를 들면 다음과 같습니다.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > 이 단계에서는 내보낸 구성을 사용 하 여 새 파일을 만든 후 백업 풀에서 제거 합니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

