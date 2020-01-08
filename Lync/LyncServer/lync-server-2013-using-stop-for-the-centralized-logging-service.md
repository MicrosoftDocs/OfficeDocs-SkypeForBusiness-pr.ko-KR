---
title: 'Lync Server 2013: 중앙 로깅 서비스에 대해 중지 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 521328b688f90ca591abddb3e59e7d49ae771b15
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013에서 중앙 로깅 서비스에 대 한 중지 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

중지-CsClsLogging cmdlet을 사용 하 여 현재 실행 중인 로깅 세션을 중지할 수 있습니다. 일반적으로 로깅 세션을 중지 해야 하는 경우가 많습니다. 예를 들어 로깅을 중지 하지 않고 로그를 검색 하 고 구성을 변경할 수 있습니다. AlwaysOn 및 UserReplicator와 같은 두 가지 시나리오를 실행 하는 경우 인증과 관련 된 정보를 수집 해야 하는 경우에는 실행을 시작 하기 전에 전역, 사이트, 풀 또는 컴퓨터 범위에서 다른 시나리오 중 하나를 중지 해야 합니다. 인증 시나리오. 자세한 내용은 [중지-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)을 참조 하세요.

<div>


> [!NOTE]  
> 지정 된 배포, 풀 또는 컴퓨터에서 실행할 수 있는 시나리오를 결정할 때는 <STRONG>컴퓨터당</STRONG>두 가지 시나리오를 실행 하는 것이 제한 된다는 점에 유의 해야 합니다. 풀에서 활동을 로깅하는 경우 풀을 단일 엔터티로 처리 해야 합니다. 대부분의 경우 풀의 각 컴퓨터에서 서로 다른 시나리오를 실행 하는 것은 적절 하지 않습니다. 전체 배포에서 지정 된 컴퓨터에 가장 적합 한 시나리오를 고려 하 여 데이터를 수집 하는 문제를 확인 하는 것이 좋습니다. 예를 들어 UserReplicator 시나리오를 고려 하는 경우 Edge 서버 또는 Edge 풀에서 UserReplicator를 실행 하는 데는 매우 적은 값이 있습니다.<BR>문제와 영향의 범위를 파악 한 후에는 컴퓨터와 풀에 대해 실행할 시나리오를 신중 하 게 선택 해야 합니다. AlwaysOn 시나리오는 광범위 한 공급자에 대 한 정보를 수집 하 고, 특정 시나리오는 특정 컴퓨터 또는 풀에 대 한 응용 프로그램 값만 가지 므로 폭넓은 범위 응용 프로그램에 의미가 있습니다. 또한 특정 시나리오의 값을 먼저 이해 하지 않고 로깅 세션을 임의로 시작 하는 경우 주의 해야 합니다. 잘못 된 시나리오를 사용 하거나 작업에 적합 한 시나리오를 사용 하 고 잘못 된 범위 (전역, 사이트, 풀 또는 컴퓨터 일 수 있음)에 시나리오를 적용 하는 경우 시나리오를 전혀 실행 하지 않은 것 처럼 중요 하지 않은 데이터를 얻을 수 있습니다.



</div>

Lync Server Management Shell을 사용 하 여 중앙 집중화 된 로깅 서비스 기능을 제어 하려면 CsAdministrator 또는 CsServerAdministrator 역할 기반 액세스 제어 (RBAC) 보안 그룹 또는이를 포함 하는 사용자 지정 RBAC 역할의 구성원 이어야 합니다. 두 그룹 중 하나. 이 cmdlet이 할당 된 모든 RBAC 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Lync Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

예를 들면 다음과 같습니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>현재 실행 중인 중앙 집중화 된 로깅 서비스 세션을 중지 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  중앙 로깅 서비스를 쿼리하여 다음을 입력 하 여 현재 실행 중인 시나리오를 확인 합니다.
    
        Show-CsClsLogging
    
    Show-(images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "cscl Windows powershell 콘솔") 을 호출한 후 ![Windows powershell 콘솔]
    
    Show-CsClsLogging 결과는 실행 중인 시나리오 및 실행 중인 범위에 대 한 요약입니다. 자세한 내용은 [-CsClsLogging 표시](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)를 참조 하세요.

3.  특정 시나리오에서 현재 실행 중인 로깅 세션을 중지 하려면 다음을 입력 합니다.
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    예를 들면 다음과 같습니다.
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    이 명령은 pool01.contoso.net에서 UserReplicatior 시나리오에 대 한 로깅을 중지 합니다.
    
    <div>
    

    > [!NOTE]  
    > UserReplicator 시나리오를 사용 하 여이 로깅 세션 중에 만든 로그는 삭제 되지 않습니다. 검색-CsClsLogging 명령을 사용 하 여 검색을 실행 하는 데에도 로깅을 계속 사용할 수 있습니다. 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">검색-CsClsLogging</A>을 참조 하세요.

    
    </div>

자매-CsClsLogging을 시작 하는 데 도우미 명령으로 작동 하는 경우 CsClsLogging cmdlet은 시나리오에 정의 된 로깅 세션을 종료 하 고 로깅 세션에서 만든 로그를 유지 합니다. 언제 든 지 지정 된 컴퓨터에서 두 가지 시나리오를 실행할 수 있습니다. 다른 시나리오를 사용 하 여 정보를 수집 하기 위해 한 시나리오를 중지 하는 방법은 대부분의 작업 부하 문제 해결 중에 수행할 수 있는 일반적인 작업입니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[중앙 로깅 서비스의 시작을 사용 하 여 Lync Server 2013에서 로그 캡처](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[Lync Server 2013의 중앙 집중화 된 로깅 서비스 개요](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[표시-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[시작-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[중지-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

