---
title: 컴퓨터, 사이트 및 전역 중앙 로깅 서비스 구성 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f714c82fdc4ade0fc70b0a977e32ef46b26914d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a>Lync Server 2013에서 컴퓨터, 사이트 및 전역 중앙 로깅 서비스 구성 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-04_

중앙 로깅 서비스는 단일 컴퓨터, 컴퓨터 풀, 사이트 범위 (예: 배포의 컴퓨터 및 풀의 컬렉션이 포함 된 사이트) 또는 전역 범위 (즉, 지정 된 사이트)에서 실행할 수 있습니다. , 배포의 모든 컴퓨터 및 풀.

Lync Server Management Shell을 사용 하 여 중앙 로깅 서비스 범위를 구성 하려면 CsAdministrator 또는 CsServerAdministrator 역할 기반 액세스 제어 (RBAC) 보안 그룹 또는 다음을 포함 하는 사용자 지정 RBAC 역할의 구성원 이어야 합니다. 두 그룹 중 하나. 이 cmdlet이 할당 된 모든 RBAC 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Lync Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

예를 들면 다음과 같습니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> Windows PowerShell에서는 CLSController를 사용 하 여 사용할 수 없는 더 많은 옵션과 추가 구성 옵션을 제공 합니다. CLSController는 명령을 실행 하는 간략 하 고 간결한 메서드를 제공 하지만 CLSController에서 사용할 수 있는 명령 집합으로 제한 됩니다. Windows PowerShell은 CLSController의 명령 프로세서에서 사용할 수 있는 명령 으로만 제한 되지 않으며 광범위 한 명령 집합 및 다양 한 옵션 집합을 제공 합니다. 예를 들어 CLSController는 – 컴퓨터 및 – 풀에 대 한 범위 옵션을 제공 합니다. Windows PowerShell을 사용 하면 대부분의 명령에 컴퓨터 또는 풀을 표시할 수 있으며, 새 시나리오를 정의할 때 (CLSController에 사용자가 수정할 수 없는 제한 된 수의 시나리오가 있는 경우) 사이트 또는 전역 범위를 정의할 수 있습니다. 이 Windows PowerShell의 강력한 기능을 통해 사이트 또는 전역 범위에 시나리오를 정의할 수 있지만 실제 로깅은 컴퓨터 또는 풀로 제한 됩니다.<BR>Windows PowerShell 또는 CLSController에서 실행할 수 있는 명령줄 명령 간에는 기본적인 차이점이 있습니다. Windows PowerShell은 시나리오를 구성 및 정의 하 고 문제 해결 시나리오에 의미 있는 방식으로 해당 시나리오를 다시 사용 하는 다양 한 방법을 제공 합니다. CLSController는 명령을 실행 하 고 결과를 얻을 수 있는 빠르고 효율적인 방법을 제공 하지만 CLSController에 대 한 명령 집합은 명령줄에서 사용할 수 있는 유한 명령으로 제한 됩니다. Windows PowerShell cmdlet과 달리 CLSController는 새 시나리오를 정의 하거나, 사이트 또는 전역 수준의 범위를 관리 하 고, 동적으로 구성할 수 없는 유한 명령 집합의 여러 다른 제한 사항에 대 한 다양 한 제한을 정의할 수 없습니다. CLSController는 빠른 실행을 위한 수단을 제공 하는 반면, Windows PowerShell은 CLSController에서 가능한 기능 외에 중앙 집중식 로깅 서비스 기능을 확장 하는 방법을 제공 합니다.



</div>

[Search-](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15))csclslogging, [표시-csclslogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15)), [시작-csclslogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15)), [동기화-](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15)) csclslogging, Sync-csclslogging, [–](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15))Computers 매개 변수를 사용 하 여 [csclslogging Update](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15)) 명령을 실행 하는 동안 단일 컴퓨터 범위를 정의할 수 있습니다. – Computers 매개 변수는 대상 컴퓨터에 대 한 Fqdn (정규화 된 도메인 이름) 목록을 쉼표로 구분 하 여 받아들입니다.

<div>


> [!TIP]
> 로깅 명령을 실행 하려는 풀 및 쉼표로 구분 된 풀 목록을 정의할 수도 있습니다.



</div>

사이트 및 전역 범위는 **새로운** **중앙의 로깅**서비스 cmdlet에 정의 되어 있습니다 **** . 다음 예제에서는 사이트 및 전역 범위를 설정 하는 방법을 보여 줍니다.

<div>


> [!IMPORTANT]
> 표시 되는 명령에는 다른 섹션에서 설명 하는 매개 변수 및 개념이 포함 되어 있을 수 있습니다. 예제 명령은 <STRONG>– Identity</STRONG> 매개 변수를 사용 하 여 범위를 정의 하 고 나머지 매개 변수를 완전성에 포함 하 고 범위를 지정 하기 위한 것입니다. <STRONG>Set-csclsconfiguration</STRONG> cmdlet에 대 한 자세한 내용은 작업 설명서의 <A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">Set-csclsconfiguration</A> 을 참조 하세요.



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>현재 중앙 집중화 된 로깅 서비스 구성을 검색 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  명령줄 프롬프트에 다음을 입력 합니다.
    
        Get-CsClsConfiguration

새 구성을 만들거나 기존 구성을 업데이트 하기 위해 **새로운 csclsconfiguration** 및 **Set csclsconfiguration** cmdlet을 사용 합니다.

**Get-CsClsConfiguration**을 실행 하면 배포에 현재 기본 전역 구성이 있지만 사이트 구성이 정의 되지 않은 다음 스크린샷은 다음과 같은 정보가 표시 됩니다.

![Get-CsClsConfiguration의 샘플 출력.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get-CsClsConfiguration의 샘플 출력.")

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>컴퓨터 로컬 저장소에서 현재 중앙 집중화 된 로깅 서비스 구성을 검색 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  명령줄 프롬프트에 다음을 입력 합니다.
    
        Get-CsClsConfiguration -LocalStore

**Get-CsClsConfiguration** 이 매개 변수를 지정 하지 않는 첫 번째 예제를 사용 하는 경우 명령은 데이터에 대 한 중앙 관리 저장소를 참조 합니다. -LocalStore 매개 변수를 지정 하는 경우이 명령은 중앙 관리 저장소 대신 컴퓨터 LocalStore를 참조 합니다.

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>현재 정의 된 시나리오 목록을 검색 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  명령줄 프롬프트에 다음을 입력 합니다.
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    예를 들어 전역 범위에서 정의 된 시나리오를 검색 하려면 다음을 실행 합니다.
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

Cmdlet **Get CsClsConfiguration** 은 항상 지정 된 범위의 구성에 속하는 시나리오를 표시 합니다. 대부분의 경우, 모든 시나리오가 표시 되지 않고 잘릴 수 있습니다. 여기에 사용 되는 명령에는 모든 시나리오와 사용 되는 공급자, 설정 및 플래그에 대 한 일부 정보가 나열 됩니다.

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 중앙 로깅 서비스에 대 한 전역 범위를 업데이트 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  명령줄 프롬프트에 다음을 입력 합니다.
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    예를 들면 다음과 같습니다.
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

이 명령은 배포의 각 컴퓨터와 풀에 CLSAgent를 알려 추적 파일의 롤오버 값 크기를 40 메가바이트 단위로 설정 합니다. 모든 사이트의 컴퓨터 및 풀은 명령의 영향을 받으며, 구성 된 추적 로그 롤오버 값을 40 메가바이트 ()로 설정 합니다.

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 중앙 로깅 서비스의 사이트 범위를 업데이트 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  명령줄 프롬프트에 다음을 입력 합니다.
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    예를 들면 다음과 같습니다.
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > 이 예제에 나와 있는 것 처럼 로그 파일의 기본 위치 는%TEMP%\Tracing.입니다. 그러나 파일을 기록 하 고 CSLAgent가 네트워크 서비스로 실행 되는 실제 CLSAgent 이기 때문 에% TEMP% 변수 는%WINDIR%\ServiceProfiles\NetworkService\AppData\Local.로 확장 됩니다.

    
    </div>

이 명령은 사이트 Redmond의 각 컴퓨터와 풀의 CLSAgent에 게 추적 파일의 롤오버 값 크기를 40 mb로 설정 하도록 지시 합니다. 다른 사이트의 컴퓨터와 풀은 명령에 영향을 받지 않으며, 기본적으로 (20mb) 또는 로깅 세션 시작 중에 정의 된 현재 구성 되어 있는 추적 로그 롤오버 값이 계속 사용 됩니다.

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a>중앙 집중화 된 새 로깅 서비스 구성을 만들려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  명령줄 프롬프트에 다음을 입력 합니다.
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > 새로운-CsClsConfiguration을 사용 하면 많은 선택적 구성 설정에 액세스할 수 있습니다. 구성 옵션에 대 한 자세한 내용은 온 <A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)">-CsClsConfiguration</A> 및 <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Lync Server 2013의 중앙 로깅 서비스 구성 설정 이해</A>를 참조 하세요.

    
    </div>
    
    예를 들어 캐시 파일에 대 한 네트워크 폴더, 로그 파일에 대 한 롤오버 기간 및 로그 파일에 대 한 롤오버 크기를 정의 하는 새 구성을 만들려면 다음을 입력 합니다.
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

새 구성 만들기와 중앙 로깅 서비스의 새 속성을 정의 하는 방법을 주의 깊게 계획 해야 합니다. 변경 하는 데는 주의를 기울여야 하며 문제 시나리오를 올바르게 기록 하는 기능에 대 한 영향을 이해 하 고 있는지 확인 해야 합니다. 로그를 크기와 관리 하는 기능을 개선 하 고 발생 하는 문제 해결을 가능 하 게 하는 구성 변경 작업을 수행 하는 것이 좋습니다.

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>기존 중앙 로깅 서비스 구성을 제거 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  명령줄 프롬프트에 다음을 입력 합니다.
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    예를 들어 로그 파일 롤오버 시간을 늘리기 위해 만든 중앙 로깅 서비스 구성을 제거 하려면 롤오버 로그 파일 크기를 늘리고 다음과 같이 로그 파일 캐시 위치를 네트워크 공유로 설정 합니다.
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > "새 중앙 로깅 서비스 구성을 만들려면" 절차에서 만든 새 구성입니다.

    
    </div>

사이트 수준 구성을 제거 하도록 선택 하면 사이트에 전역 설정이 사용 됩니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 중앙 집중화 된 로깅 서비스 개요](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Lync Server 2013에서 중앙 집중화 된 로깅 서비스 구성 설정 관리](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))  
[-CsClsConfiguration 제거](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

