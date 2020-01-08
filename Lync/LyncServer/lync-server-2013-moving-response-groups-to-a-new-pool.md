---
title: 'Lync Server 2013: 응답 그룹을 새 풀로 이동'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e682ce99826cd5b9f2812c358e1028bfb491ddef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a>Lync Server 2013에서 응답 그룹을 새 풀로 이동

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

Lync Server 2013에는 FQDN (정규화 된 도메인 이름)이 다른 경우에도 한 풀의 응답 그룹을 다른 풀로 이동 하기 위한 새로운 cmdlet 지원이 도입 되었습니다.

한 프런트 엔드 풀의 응답 그룹을 다른 FQDN을 사용 하는 다른 프런트 엔드 풀로 이동 하려면 다음 절차의 단계를 사용 합니다.

<div>


> [!NOTE]  
> 공존 환경에서 Lync Server 2013&nbsp;프런트 엔드 풀 간에만 응답 그룹을 이동할 수 있습니다.



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a>다른 FQDN을 사용 하 여 응답 그룹을 풀로 이동 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  원본 풀에서 응답 그룹을 내보냅니다. 명령줄에 다음을 입력 합니다.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    예를 들면 다음과 같습니다.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    내보내는 동안 원본 풀에서 응답 그룹을 제거 하려면 – RemoveExportedConfiguration 매개 변수를 포함 합니다. 예를 들면 다음과 같습니다.
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  응답 그룹을 대상 풀로 가져오고 대상 풀을 새 담당자로 지정 합니다. 명령줄에 다음을 입력 합니다.
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    또한 응답 그룹 응용 프로그램 수준 설정을 원본 풀에서 대상 풀로 복사 하려는 경우 – ReplaceExistingRgsSettings 매개 변수를 포함 합니다. 풀 당 하나의 응용 프로그램 수준 설정 집합을 정의할 수 있습니다. 원본 풀의 응용 프로그램 수준 설정을 대상 풀로 복사 하는 경우 원본 풀의 설정이 대상 풀에 대 한 설정을 바꿉니다. 원본 풀의 응용 프로그램 수준 설정을 복사 하지 않으면 대상 풀의 기존 설정이 가져온 응답 그룹에 적용 됩니다.
    
    예를 들면 다음과 같습니다.
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > 응용 프로그램 수준 설정에는 기본 음악 보존 구성, 기본 음악 대기 오디오 파일, 에이전트 ringback 유예 기간 및 통화 컨텍스트 구성이 포함 됩니다. 이러한 구성 설정을 보려면 <STRONG>Get-CsRgsConfiguration</STRONG> cmdlet을 실행 합니다. 이 cmdlet에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-help CsRgsConfiguration</A>을 참조 하세요.

    
    </div>

4.  다음을 수행 하 여 가져온 응답 그룹 구성을 표시 하 여 가져오기가 성공적으로 수행 되었는지 확인 합니다.
    
      - 모든 워크플로를 가져왔는지 확인 합니다. 명령줄에 다음을 입력 합니다.
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - 모든 큐를 가져왔는지 확인 합니다. 명령줄에 다음을 입력 합니다.
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - 모든 에이전트 그룹을 가져왔는지 확인 합니다. 명령줄에 다음을 입력 합니다.
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - 모든 비즈니스 시간을 가져왔는지 확인 합니다. 명령줄에 다음을 입력 합니다.
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - 모든 공휴일 집합을 가져왔는지 확인 합니다. 명령줄에 다음을 입력 합니다.
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  응답 그룹 중 하나에 호출을 배치 하 고 통화가 올바르게 처리 되었는지 확인 하 여 가져오기가 성공적으로 수행 되었는지 확인 합니다.

6.  대상 풀의 에이전트 그룹에 로그인 할 수 있는 공식 에이전트 그룹의 구성원 인 에이전트를 요청 합니다.

7.  이전에 원본 풀에서 응답 그룹을 제거 하지 않은 경우 원본 풀에서 응답 그룹을 제거 합니다. 명령줄에 다음을 입력 합니다.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    예를 들면 다음과 같습니다.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

