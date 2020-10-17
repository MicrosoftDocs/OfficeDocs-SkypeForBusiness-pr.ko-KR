---
title: 'Lync Server 2013: 중앙 로깅 서비스에 대 한 공급자 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec5d280d05089c4f1efc4fd8c54ab4841d24621d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535005"
---
# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013에서 중앙 로깅 서비스에 대 한 공급자 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-03-19_

중앙 로깅 서비스에서 *공급자* 의 개념 및 구성은 이해 하기 가장 중요 한 사항 중 하나입니다. *공급자* 는 lync server 추적 모델의 lync server 서버 역할 구성 요소에 직접 매핑됩니다. 공급자는 추적할 Lync Server 2013의 구성 요소, 수집할 메시지 유형 (예: 치명적, 오류 또는 경고) 및 플래그 (TF \_ Connection 또는 tf Diag)를 정의 합니다 \_ . 공급자는 각 Lync Server 서버 역할의 추적 가능한 구성 요소입니다. 공급자를 사용 하 여 구성 요소에 대 한 추적 수준 및 유형 (예: S4, 동안의 sipstack, IM 및 현재 상태)을 정의 합니다. 정의 된 공급자는 특정 문제 조건을 해결 하는 지정 된 논리 컬렉션에 대 한 모든 공급자를 그룹화 하는 시나리오에서 사용 됩니다.

Lync Server 관리 셸을 사용 하 여 중앙화 된 로깅 서비스 기능을 실행 하려면 CsAdministrator 또는 CsServerAdministrator의 RBAC (역할 기반 액세스 제어) 보안 그룹 또는 이러한 두 그룹 중 하나를 포함 하는 사용자 지정 RBAC 역할의 구성원 이어야 합니다. 이 cmdlet이 할당 된 모든 RBAC (역할 기반 액세스 제어) 역할 목록을 반환 하려면 (직접 만든 사용자 지정 RBAC 역할 포함) Lync Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

예제:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

이 항목의 나머지 부분에서는 공급자 정의 방법, 공급자를 수정 하는 방법 및 공급자 정의에 포함 된 문제 해결을 최적화 하는 방법에 대해 중점적으로 설명 합니다. 중앙 로깅 서비스 명령을 실행 하는 방법에는 두 가지가 있습니다. 기본적으로 C: \\ Program Files \\ Common Files \\ Microsoft Lync Server 2013 \\ clsagent에 있는 CLSController.exe를 사용할 수 있습니다. 또는 Lync Server 관리 셸을 사용 하 여 Windows PowerShell 명령을 실행할 수 있습니다. 중요 한 차이점은 명령줄에서 CLSController.exe을 사용할 때 공급자가 이미 정의 되어 있으며 변경할 수 없지만 로그 수준을 정의 하는 것이 좋습니다. Windows PowerShell을 사용 하 여 로깅 세션에서 사용할 새 공급자를 정의 하 고, 작성, 수집 및 데이터 수집 수준을 완전히 제어할 수 있습니다.

<div class="">


> [!IMPORTANT]  
> 앞에서 설명한 것 처럼 공급자는 매우 강력 합니다. 그러나 시나리오에는 공급자가 나타내는 구성 요소에 대 한 추적을 설정 하 고 실행 하는 데 필요한 모든 정보의 embodiment 포함 되어 있으므로 더 강력 합니다. 시나리오가 공급자의 모음인 경우에는 명령줄에서 수백 개의 명령을 사용 하 여 많은 정보를 수집 하 고 한 번에 하나씩 수백 개의 명령을 실행 하는 것과 비교할 때 보다 느슨하게 사용할 수 있습니다.<BR>중앙 로깅 서비스는 공급자의 세부 정보를 자세히 파악 하도록 요구 하는 대신 이미 정의 된 여러 시나리오를 제공 합니다. 제공 되는 시나리오에서는 발생할 수 있는 대부분의 가능한 문제를 다룹니다. 드문 경우에는 공급자를 만들고 정의 하 여 시나리오에 할당 해야 할 수 있습니다. 새 공급자 및 시나리오를 만들기 위한 필요성을 조사 하기 전에 제공 되는 각 시나리오에 익숙해지는 것이 좋습니다. 공급자를 만드는 방법에 대 한 정보는 시나리오에서 provider 요소를 사용 하 여 추적 정보를 수집 하는 방법을 익히는 데 도움이 되도록 여기에 제공 되며, 공급자 자체에 대 한 세부 정보는 현재 기본적



</div>

[Lync Server 2013의 중앙 로깅 서비스에 대 한 개요](lync-server-2013-overview-of-the-centralized-logging-service.md)에서 소개 된 시나리오에서 사용할 공급자 정의의 주요 요소는 다음과 같습니다.

  - **공급자**     OCSLogger 사용 하는 데 익숙한 경우 공급자는 OCSLogger 추적 엔진이 로그를 수집 해야 하는 대상을 알리기 위해 선택한 구성 요소입니다. 공급자는 동일한 구성 요소 이며, 대부분의 경우에는 OCSLogger 있는 구성 요소와 이름이 같습니다. OCSLogger 아닌 경우 공급자는 중앙 로깅 서비스에서 로그를 수집할 수 있는 서버 역할 관련 구성 요소입니다. 중앙 로깅 서비스의 경우 CLSAgent는 공급자 구성에서 정의 하는 구성 요소를 추적 하는 중앙 로깅 서비스의 아키텍처 부분입니다.

  - **로깅 수준**     OCSLogger 수집 된 데이터에 대 한 세부 수준 수를 선택 하는 옵션을 제공 합니다. 이 기능은 중앙 로깅 서비스 및 시나리오의 필수 부분이 며 **Type** 매개 변수에 의해 정의 됩니다. 다음 중에서 선택할 수 있습니다.
    
      - **모든**     정의 된 공급자에 대 한 로그에 치명적, 오류, 경고 및 정보 유형의 추적 메시지를 수집 합니다.
    
      - **치명적**     정의 된 공급자에 대 한 오류를 나타내는 추적 메시지만 수집 합니다.
    
      - **오류**     정의 된 공급자에 대 한 오류를 나타내는 추적 메시지와 심각한 메시지를 수집 합니다.
    
      - **경고**     정의 된 공급자에 대 한 경고를 나타내는 추적 메시지와 치명적이 고 오류 메시지를 수집 합니다.
    
      - **정보**     정의 된 공급자에 대 한 정보 메시지를 나타내는 추적 메시지와 심각, 오류 및 경고 메시지를 수집 합니다.
    
      - **자세한 정보**     표시 정의 된 공급자에 대 한 치명적, 오류, 경고 및 정보 유형의 모든 추적 메시지를 수집 합니다.

  - **플래그**     OCSLogger 추적 파일에서 검색할 수 있는 정보 유형을 정의한 각 공급자에 대해 플래그를 선택 하는 옵션을 제공 합니다. 공급자에 따라 다음 플래그를 선택할 수 있습니다.
    
      - **TF \_ 연결**     연결 관련 로그 항목을 제공 합니다. 이러한 로그에는 특정 구성 요소에서 설정 된 연결에 대 한 정보가 포함 됩니다. 여기에는 중요 한 네트워크 수준 정보 (즉, 연결 개념을 제외 하 고 구성 요소)가 포함 될 수도 있습니다.
    
      - **TF \_ Security**     에서는 보안과 관련 된 모든 이벤트/로그 항목을 제공 합니다. 예를 들어 동안의 sipstack의 경우 도메인 유효성 검사 오류 및 클라이언트 인증/권한 부여 오류와 같은 보안 이벤트가 발생 합니다.
    
      - **TF \_ Diag**는     구성 요소를 진단 하거나 문제를 해결 하는 데 사용할 수 있는 진단 이벤트를 제공 합니다. 예를 들어 동안의 sipstack의 경우 인증서 오류 또는 DNS 경고/오류입니다.
    
      - **TF \_ 프로토콜**     SIP 및 결합 된 커뮤니티 코덱 팩 메시지와 같은 프로토콜 메시지를 제공 합니다.
    
      - **TF \_ Component**     공급자의 일부로 지정 된 구성 요소에 대해 로깅을 사용 하도록 설정 합니다.
    
      - **모든**     공급자에 대해 사용 가능한 모든 플래그를 설정 합니다.

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>기존의 중앙화 된 로깅 서비스 시나리오 공급자에 대 한 정보를 검토 하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  기존 공급자의 구성을 검토 하려면 다음을 입력 합니다.
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    예를 들어 전역 회의 전화 교환에 대 한 정보를 검토 하려면 다음을 입력 합니다.
    
        Get-CsClsScenario -Identity "global/CAA"
    
    이 명령은 연결 된 플래그, 설정 및 구성 요소와 함께 공급자 목록을 표시 합니다. 표시 되는 정보가 충분 하지 않거나 목록이 너무 길어 기본 Windows PowerShell 목록 형식에 맞지 않는 경우 다른 출력 방법을 정의 하 여 추가 정보를 표시할 수 있습니다. 이렇게 하려면 다음을 입력합니다.
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    이 명령의 출력은 각 공급자를 5 줄 형식으로 표시 하며,이 형식은 공급자 이름, 로깅 유형, 로깅 수준, 플래그, GUID 및 역할이 각각 하나씩 별도의 줄에 나타납니다.

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>새 중앙화 된 로깅 서비스 시나리오 공급자를 정의 하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  시나리오 공급자는 추적, 사용할 플래그, 수집할 세부 정보 수준으로 구성 됩니다. 다음을 입력 하 여이 작업을 수행 합니다.
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    예를 들어 Lyss 공급자에서 수집할 항목 및 세부 정보 수준을 정의 하는 추적 공급자 정의는 다음과 같습니다.
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

– Level은 치명적, 오류, 경고 및 정보 메시지를 수집 합니다. Lyss 공급자에 대해 정의 된 플래그는 모두 사용 되며 TF \_ Connection, tf \_ DIAG 및 tf Protocol을 포함 합니다 \_ .

$LyssProvider 변수를 정의한 후에는이를 **새 CsClsScenario** cmdlet과 함께 사용 하 여 lyss 공급자 로부터 추적을 수집할 수 있습니다. 새 시나리오에 대 한 공급자 만들기 및 할당을 완료 하려면 다음을 입력 합니다.

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

여기서 $LyssProvider은 **새 CsClsProvider**로 만든 정의 된 시나리오를 포함 하는 변수입니다.

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>기존의 중앙화 된 로깅 서비스 시나리오 공급자를 변경 하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  기존 공급자의 구성을 업데이트 하거나 변경 하려면 다음을 입력 합니다.
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    그런 다음 다음을 입력 하 여 시나리오를 업데이트 하 여 공급자를 할당 합니다.
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

이 명령의 최종 결과는 시나리오 사이트: Redmond/RedmondLyssInfo에 게 할당 된 공급자에 대 한 플래그 및 수준이 업데이트 된 것입니다. Get-CsClsScenario를 사용 하 여 새 시나리오를 볼 수 있습니다. 자세한 내용은 [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)를 참조 하십시오.

<div class="">


> [!WARNING]  
> <STRONG>새-ClsCsProvider</STRONG> 에서는 플래그가 유효한 지 여부를 확인 하지 않습니다. 플래그의 철자 (예: TF_DIAG 또는 TF_CONNECTION)가 올바른지 확인 합니다. 플래그의 철자가 올바르지 않으면 공급자가 필요한 로그 정보를 반환할 수 없습니다.



</div>

이 시나리오에 공급자를 더 추가 하려면 다음을 입력 합니다.

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

Add 지시문을 사용 하 여 정의 된 각 공급자는 이미 **새-CsClsProvider** 프로세스를 사용 하 여 정의 됩니다.

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a>시나리오 공급자를 제거 하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  제공 된 cmdlet을 사용 하면 기존 공급자를 업데이트 하 고 새 공급자를 만들 수 있습니다. 공급자를 제거 하려면 Provider 매개 변수의 Replace 지시문을 **설정-CsClsScenario**로 사용 해야 합니다. 공급자를 완전히 제거 하는 유일한 방법은이를 동일한 이름의 다시 정의 된 공급자로 바꾸고 Update 지시문을 사용 하는 것입니다. 예를 들어 provider LyssProvider는 WPP를 사용 하 여 정의 되며,이 형식은 디버그로 설정 되며, 플래그 집합은 TF \_ CONNECTION AND tf \_ DIAG입니다. 플래그를 "All"로 변경 해야 합니다. 공급자를 변경 하려면 다음을 입력 합니다.
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  시나리오와 해당 역할과 연결 된 공급자를 완전히 제거 하려면 다음을 입력 합니다.
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    예제:
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > Cmdlet <STRONG>제거-CsClsScenario</STRONG> 에서는 확인 메시지를 표시 하지 않습니다. 시나리오가 할당 된 공급자와 함께 삭제 됩니다. 처음에 사용 하는 데 사용한 명령을 다시 실행 하 여 시나리오를 다시 만들 수 있습니다. 제거 된 시나리오 또는 공급자를 복구 하는 절차는 없습니다.

    
    </div>

**제거-CsClsScenario** cmdlet을 사용 하 여 시나리오를 제거 하면 범위에서 시나리오가 완전히 제거 됩니다. 만든 시나리오 및 시나리오의 일부인 공급자를 사용 하려면 새 공급자를 만들고 새 시나리오에 할당 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[새 CsClsScenario](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[제거-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[설정-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[새-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

