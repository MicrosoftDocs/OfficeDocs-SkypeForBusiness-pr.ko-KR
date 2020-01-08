---
title: 'Lync Server 2013: 중앙 집중화 된 로깅 서비스에 대 한 공급자 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e11af1a56e3975f96e19dc43dff27aef1d512ec9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013에서 중앙 집중화 된 로깅 서비스에 대 한 공급자 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-03-19_

중앙 로깅 서비스의 *공급자* 에 대 한 개념 및 구성은 가장 중요 하 게 이해 하는 방법 중 하나입니다. *공급자* 는 lync server 추적 모델의 lync server 서버 역할 구성 요소에 직접 매핑됩니다. 공급자는 추적 되는 Lync Server 2013의 구성 요소, 수집할 메시지 유형 (예: 치명적, 오류 또는 경고) 및 플래그 (예: TF\_CONNECTION 또는 tf\_Diag)를 정의 합니다. 공급자는 각 Lync Server 서버 역할의 추적 가능한 구성 요소입니다. 공급자를 사용 하 여 구성 요소 (예: S4, SIPStack, IM 및 현재 상태)에 추적의 수준과 유형을 정의 합니다. 정의 된 공급자는 특정 문제 조건을 처리 하는 지정 된 논리적 수집에 대 한 모든 공급자를 그룹화 하는 시나리오에서 사용 됩니다.

Lync Server Management Shell을 사용 하 여 중앙 집중화 된 로깅 서비스 기능을 실행 하려면 CsAdministrator 또는 CsServerAdministrator 역할 기반 액세스 제어 (RBAC) 보안 그룹 또는 다음 중 하나를 포함 하는 사용자 지정 RBAC 역할의 구성원 이어야 합니다. 두 그룹 이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) (모든 사용자 지정 RBAC 역할 포함)의 목록을 반환 하려면 Lync Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

예를 들면 다음과 같습니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

이 항목의 나머지 부분에서는 공급자를 정의 하 고, 공급자를 수정 하 고, 문제 해결을 최적화 하는 데 포함 된 공급자 정의에 대해 중점적으로 설명 합니다. 중앙 로깅 서비스 명령을 실행 하는 방법에는 두 가지가 있습니다. 기본적으로\\C: 프로그램 파일\\의 디렉터리에 있는 clscontroller를 사용할 수 있습니다.\\Microsoft Lync Server 2013\\clscontroller. 또는 Lync Server Management Shell을 사용 하 여 Windows PowerShell 명령을 실행할 수 있습니다. 중요 한 차이점은, 명령줄에서 CLSController. exe를 사용 하는 경우에는 공급자가 이미 정의 되 고 변경할 수 없지만 로그 수준을 정의할 수 있다는 것입니다. Windows PowerShell을 사용 하 여 로깅 세션에서 사용할 새 공급자를 정의 하 고, 생성, 수집 하는 내용, 데이터를 수집 하는 수준에 대 한 완전 한 제어 권한을 가질 수 있습니다.

<div class="">


> [!IMPORTANT]  
> 앞에서 언급 했 듯이 공급자는 매우 강력한 기능을 제공 합니다. 그러나 시나리오에는 공급자가 표시 하는 구성 요소에서 추적을 설정 하 고 실행 하는 데 필요한 모든 정보의 embodiment 포함 되어 있기 때문에 더 강력 합니다. 시나리오를 공급자 컬렉션으로 사용 하는 경우 많은 정보를 수집 하 고 명령줄에서 한 번에 하나씩 수백 개의 명령을 실행 하는 등 수백 개의 명령이 포함 된 배치 파일을 실행 하는 것에 비해 느슨하게 전환할 수 있습니다.<BR>공급자의 세부 정보를 자세히 설명 하는 대신 중앙 로깅 서비스는 이미 정의 된 다양 한 시나리오를 제공 합니다. 제공 되는 시나리오는 발생할 수 있는 대부분의 가능한 문제를 다룹니다. 드문 경우 지만, 공급자를 만들고 정의 하 고 시나리오에 할당 해야 할 수 있습니다. 새 공급자 및 시나리오를 만들어야 한다는 것을 조사 하기 전에 제공 되는 각 시나리오에 대해 잘 알고 있어야 합니다. 공급자를 만드는 방법에 대 한 정보를 참조 하는 것은 시나리오를 통해 추적 정보를 수집 하는 방법에 대 한 자세한 내용은 현재 제공 되지 않습니다.



</div>

[Lync Server 2013의 중앙 집중화 된 로깅 서비스에 대 한 개요](lync-server-2013-overview-of-the-centralized-logging-service.md)에 도입 된 시나리오에서 사용할 공급자를 정의 하는 주요 요소는 다음과 같습니다.

  - **공급자**   ocslogger 사용 하는 데 익숙한 경우 공급자는 ocslogger 로그를 수집 해야 하는 항목을 지정 하기 위해 선택 하는 구성 요소입니다. 공급자는 동일한 구성 요소 이며, 대부분의 경우에는 OCSLogger 구성 요소와 동일한 이름을 사용 합니다. OCSLogger 익숙하지 않은 경우 공급자는 중앙 로깅 서비스에서 로그를 수집할 수 있는 서버 역할 특정 구성 요소입니다. 중앙 로깅 서비스의 경우 CLSAgent는 공급자 구성에 정의 된 구성 요소의 추적을 수행 하는 중앙 로깅 서비스의 아키텍처 부분입니다.

  - **로깅 수준**   ocslogger는 수집 된 데이터의 세부 수준 수를 선택 하는 옵션을 제공 합니다. 이 기능은 중앙 로깅 서비스 및 시나리오의 핵심 부분이 며 **Type** 매개 변수에 의해 정의 됩니다. 다음 중에서 선택할 수 있습니다.
    
      - **All**   은 정의 된 공급자의 로그에 대 한 치명적인, 오류, 경고 및 정보 유형의 추적 메시지를 수집 합니다.
    
      - **치명적**   은 정의 된 공급자에 대 한 오류를 나타내는 추적 메시지만 수집 합니다.
    
      - **오류**   는 정의 된 공급자에 대 한 오류를 나타내는 추적 메시지와 심각한 메시지를 수집 합니다.
    
      - **경고**   는 정의 된 공급자에 대 한 경고를 나타내는 추적 메시지와 치명적이 고 오류 메시지를 수집 합니다.
    
      - **정보**   는 정의 된 공급자에 대 한 정보 메시지를 나타내는 추적 메시지와 치명적, 오류, 경고 메시지를 수집 합니다.
    
      - **Verbose**   는 정의 된 공급자에 대 한 치명적, 오류, 경고 및 정보 유형의 모든 추적 메시지를 수집 합니다.

  - **Flags**   ocslogger는 추적 파일에서 검색할 수 있는 정보 유형을 정의한 각 공급자에 대 한 플래그를 선택 하는 옵션을 제공 합니다. 공급자에 따라 다음 플래그를 선택할 수 있습니다.
    
      - **TF\_connection**   연결 관련 로그 항목을 제공 합니다. 이러한 로그에는 특정 구성 요소에 설정 된 연결에 대 한 정보가 포함 됩니다. 여기에는 중요 한 네트워크 수준 정보 (즉, 연결 개념 없이 구성 요소)도 포함 될 수 있습니다.
    
      - **TF\_security**   는 보안과 관련 된 모든 이벤트/로그 항목을 제공 합니다. 예를 들어 SipStack의 경우 도메인 유효성 검사 오류, 클라이언트 인증/권한 부여 실패 등의 보안 이벤트입니다.
    
      - **TF\_Diag**   는 구성 요소를 진단 하거나 문제를 해결 하는 데 사용할 수 있는 진단 이벤트를 제공 합니다. 예를 들어 SipStack의 경우 인증서 오류 또는 DNS 경고/오류입니다.
    
      - **TF\_프로토콜**   은 SIP 및 결합 된 커뮤니티 코덱 팩 메시지 등의 프로토콜 메시지를 제공 합니다.
    
      - **TF\_Component**   는 공급자의 일부로 지정 된 구성 요소에 로깅할 수 있도록 합니다.
    
      - **모두**   공급자에 대해 사용할 수 있는 모든 플래그를 설정 합니다.

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>기존 중앙 집중화 된 로깅 서비스 시나리오 공급자에 대 한 정보를 검토 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  기존 공급자의 구성을 검토 하려면 다음을 입력 합니다.
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    예를 들어 전역 회의 수행자에 대 한 정보를 검토 하려면 다음을 입력 합니다.
    
        Get-CsClsScenario -Identity "global/CAA"
    
    이 명령은 연결 된 플래그, 설정 및 구성 요소와 함께 공급자 목록을 표시 합니다. 표시 되는 정보가 부족 하거나 목록이 기본 Windows PowerShell 목록 형식에 비해 너무 긴 경우 다른 출력 방법을 정의 하 여 추가 정보를 표시할 수 있습니다. 이렇게 하려면 다음을 입력 합니다.
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    이 명령의 출력은 공급자 이름, 로깅 형식, 로깅 수준, 플래그, GUID, 역할 등 5 개의 줄 형식으로 표시 되는 각 공급자를 각각 별도의 줄에 표시 합니다.

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>중앙 집중화 된 새 로깅 서비스 시나리오 공급자를 정의 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  시나리오 공급자는 추적 하는 구성 요소, 사용할 플래그, 수집할 세부 정보 수준으로 구성 됩니다. 다음을 입력 하 여이 작업을 수행 합니다.
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    예를 들어 수집 대상을 정의 하 고 Lyss 공급자의 세부 정보 수준에 대 한 추적 공급자 정의는 다음과 같습니다.
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

– Level은 치명적, 오류, 경고 및 정보 메시지를 수집 합니다. 사용 된 플래그는 Lyss 공급자에 대해 정의 된 모든 것 이며 TF\_CONNECTION, tf\_Diag 및 tf\_Protocol을 포함 합니다.

변수 $LyssProvider 정의 된 후에는 **새 CsClsScenario** cmdlet을 사용 하 여 lyss 공급자에서 추적을 수집할 수 있습니다. 새 시나리오에 대 한 공급자 만들기 및 할당을 완료 하려면 다음을 입력 합니다.

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

여기서 $LyssProvider은 **새 CsClsProvider**를 사용 하 여 만든 정의 된 시나리오를 포함 하는 변수입니다.

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>기존 중앙 집중화 된 로깅 서비스 시나리오 공급자를 변경 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  기존 공급자의 구성을 업데이트 하거나 변경 하려면 다음을 입력 합니다.
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    그런 다음 시나리오를 업데이트 하 여 다음을 입력 하 여 공급자를 할당 합니다.
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

이 명령의 최종 결과는 시나리오 사이트: 레드먼드/RedmondLyssInfo에 할당 된 공급자에 대 한 플래그와 수준을 업데이트 하는 것입니다. Get-CsClsScenario를 사용 하 여 새 시나리오를 볼 수 있습니다. 자세한 내용은 [Get CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)를 참조 하세요.

<div class="">


> [!WARNING]  
> <STRONG>새-ClsCsProvider</STRONG> 는 플래그가 유효한 지 여부를 확인 하지 않습니다. 플래그의 맞춤법 (예: TF_DIAG 또는 TF_CONNECTION)이 정확한 지 확인 합니다. 플래그에 맞춤법이 잘못 된 경우 공급자는 필요한 로그 정보를 반환할 수 없습니다.



</div>

이 시나리오에 추가 공급자를 추가 하려면 다음을 입력 합니다.

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

Add 지시문을 사용 하 여 정의 된 각 공급자는 이미 **새 CsClsProvider** 프로세스를 사용 하 여 정의 되었습니다.

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a>시나리오 공급자를 제거 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  제공 된 cmdlet을 사용 하 여 기존 공급자를 업데이트 하 고 새 공급자를 만들 수 있습니다. 공급자를 제거 하려면 Provider 매개 변수에 대 한 Replace 지시문을 **Set-CsClsScenario**에 사용 해야 합니다. 공급자를 완전히 제거 하는 유일한 방법은 동일한 이름의 재정의 된 공급자로 바꾼 다음 Update 지시문을 사용 하는 것입니다. 예를 들어, 공급자 LyssProvider는 WPP를 사용 하 여 로그 유형, 디버그로 설정 된 수준 집합, 그리고 flags 집합\_은 tf CONNECTION\_및 tf DIAG로 정의 됩니다. 플래그를 "모두"로 변경 해야 합니다. 공급자를 변경 하려면 다음을 입력 합니다.
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  시나리오 및이에 연결 된 공급자를 완전히 제거 하려면 다음을 입력 합니다.
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    예를 들면 다음과 같습니다.
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > Cmdlet <STRONG>제거-CsClsScenario</STRONG> 에서는 확인 메시지가 표시 되지 않습니다. 시나리오는 자신에 게 할당 된 공급자와 함께 삭제 됩니다. 처음으로 생성 하는 데 사용 된 명령을 다시 실행 하 여 시나리오를 다시 만들 수 있습니다. 제거 된 시나리오 또는 공급자를 복구 하는 방법은 없습니다.

    
    </div>

**제거-CsClsScenario** cmdlet을 사용 하 여 시나리오를 제거 하면 범위에서 해당 시나리오가 완전히 제거 됩니다. 자신이 만든 시나리오와 시나리오의 일부인 공급자를 사용 하려면 새 공급자를 만들고 새 시나리오에 할당 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[신규-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[-CsClsScenario 제거](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[새-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

