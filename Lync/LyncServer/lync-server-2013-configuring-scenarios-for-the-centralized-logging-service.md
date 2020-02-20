---
title: 'Lync Server 2013: 중앙 로깅 서비스에 대 한 시나리오 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa94715cd3360e032f2d791c0e02cc791c437185
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a>Lync Server 2013에서 중앙 로깅 서비스에 대 한 시나리오 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-05_

시나리오는 범위 (전역, 사이트, 풀 또는 컴퓨터)와 중앙 로깅 서비스에서 사용할 공급자를 정의 합니다. 시나리오를 사용 하 여 공급자 (예: S4, 동안의 sipstack, IM 및 현재 상태)에 추적을 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 시나리오를 구성 하 여 특정 문제 조건을 해결 하는 지정 된 논리 컬렉션에 대 한 모든 공급자를 그룹화 할 수 있습니다. 문제 해결 및 로깅 요구 사항에 맞게 시나리오를 수정 해야 하는 경우 Lync Server 2013 디버그 도구는 *a* 라는 함수를 포함 하는 Windows PowerShell 모듈 (예: *Edit-csclsscenario)* 을 제공 합니다. 이 모듈은 명명 된 시나리오의 속성을 편집 하는 데 목적이 있습니다. 이 항목에서는이 모듈이 작동 하는 방식에 대 한 예를 제공 합니다. Lync Server 2013 디버그 도구는 다음 링크에서 다운로드 됩니다.[https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)

<div>


> [!IMPORTANT]  
> 지정 된 범위 (사이트, 전역, 풀 또는 컴퓨터)에 대해 언제 든 지 최대 두 개의 시나리오를 실행할 수 있습니다. 현재 실행 중인 시나리오를 확인 하려면 Windows PowerShell 및 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get CsClsScenario</A>를 사용 합니다. Windows PowerShell 및 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">설정-CsClsScenario</A>를 사용 하 여 실행 중인 시나리오를 동적으로 변경할 수 있습니다. 로깅 세션 중에 실행 되는 시나리오를 수정 하 여 수집 중인 데이터와 공급자를 조정 하거나 구체화할 수 있습니다.



</div>

Lync Server 관리 셸을 사용 하 여 중앙 로깅 서비스 기능을 실행 하려면 CsAdministrator 또는 CsServerAdministrator의 RBAC (역할 기반 액세스 제어) 보안 그룹 또는 다음 중 하나를 포함 하는 사용자 지정 RBAC 역할의 구성원 이어야 합니다. 두 그룹 중에서 직접 만든 사용자 지정 RBAC 역할을 포함 하 여이 cmdlet이 할당 된 모든 RBAC 역할의 목록을 반환 하려면 Lync Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

예:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

이 항목의 나머지 부분에서는 시나리오를 정의 하 고, 시나리오를 수정 하 고, 실행 중인 시나리오를 검색 하 고, 시나리오를 제거 하 고, 문제 해결을 최적화 하기 위해 시나리오에 포함 된 내용을 지정 하는 방법에 초점을 두고 중앙 로깅 서비스 명령을 실행 하는 방법에는 두 가지가 있습니다. 기본적으로\\C: Program Files\\Common Files\\Microsoft Lync Server 2013\\clscontroller에 있는 clscontroller를 사용할 수 있습니다. 또는 Lync Server 관리 셸을 사용 하 여 Windows PowerShell 명령을 실행할 수 있습니다. 중요 한 차이점은 CLSController .exe를 명령줄에서 사용 하는 경우 사용 가능한 시나리오를 제한적으로 선택할 수 있다는 것입니다. Windows PowerShell을 사용 하는 경우 로깅 세션에서 사용할 새 시나리오를 정의할 수 있습니다.

[Lync Server 2013의 중앙화 된 로깅 서비스 개요에 설명](lync-server-2013-overview-of-the-centralized-logging-service.md)된 대로 시나리오의 요소는 다음과 같습니다.

  - **공급자**   ocslogger 사용 하는 데 익숙한 경우 공급자는 ocslogger 추적 엔진이 로그를 수집 해야 하는 대상을 알리기 위해 선택한 구성 요소입니다. 공급자는 동일한 구성 요소 이며, 대부분의 경우에는 OCSLogger 있는 구성 요소와 이름이 같습니다. OCSLogger 사용 하는 방법을 잘 모르는 경우 공급자는 중앙 로깅 서비스가 로그를 수집할 수 있는 서버 역할 관련 구성 요소입니다. 공급자 구성에 대 한 자세한 내용은 [Lync Server 2013에서 중앙 로깅 서비스에 대 한 공급자 구성을](lync-server-2013-configuring-providers-for-centralized-logging-service.md)참조 하십시오.

  - **Identity**   매개 변수-identity는 시나리오의 범위와 이름을 설정 합니다. 예를 들어 범위를 "global"로 설정 하 고 시나리오를 "LyssServiceScenario"로 식별할 수 있습니다. 둘을 결합할 때 Id를 정의 합니다 (예: "global/LyssServiceScenario").
    
    원하는 경우 – Name 및 – Parent 매개 변수를 사용할 수 있습니다. 시나리오를 고유 하 게 식별 하는 Name 매개 변수를 정의 합니다. Name을 사용 하는 경우에는 Parent를 사용 하 여 전역 또는 사이트에 시나리오를 추가 해야 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > Name 및 Parent 매개 변수를 사용 하는 경우에는 <STRONG>-Identity</STRONG> 매개 변수를 사용할 수 없습니다.

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>새로운-CsClsScenario cmdlet을 사용 하 여 새 시나리오를 만들려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  로깅 세션에 대 한 새 시나리오를 만들려면 [새-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) 를 사용 하 고 시나리오 이름 (즉, 고유 하 게 식별 되는 방법)을 정의 합니다. WPP (Windows 소프트웨어 추적 전처리기 및 기본값), EventLog (즉, Windows 이벤트 로그 형식) 또는 IISLog (즉, IIS 로그 파일 형식을 기반으로 하는 ASCII 형식 파일)에서 로깅 형식 유형을 선택 합니다. 그런 다음 수준 (이 항목의 로깅 수준에 정의 됨) 및 플래그 (이 항목의 플래그에 정의 됨)를 정의 합니다.
    
    이 예제 시나리오에서는 예제 공급자 변수로 LyssProvider를 사용 합니다.
    
    정의 된 옵션을 사용 하 여 시나리오를 만들려면 다음을 입력 합니다.
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    예:
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    -Name 및 – Parent를 사용 하는 대체 형식은 다음과 같습니다.
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>새로운-CsClsScenario cmdlet을 사용 하 여 여러 공급자가 포함 된 새 시나리오를 만들려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  범위 당 두 개의 시나리오로 제한 됩니다. 그러나 설정 된 공급자 수로 제한 되지는 않습니다. 이 예제에서는 공급자를 세 개 만들고이 세 가지를 모두 정의 하는 시나리오에 할당 하려고 한다고 가정 합니다. 공급자 변수 이름은 LyssProvider, ABServerProvider 및 SIPStackProvider입니다. 여러 공급자를 정의 하 고 시나리오에 할당 하려면 Lync Server 관리 셸 또는 Windows PowerShell 명령 프롬프트에 다음을 입력 합니다.
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > Windows PowerShell에서 알 수 있듯이 값을 사용 하 <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> 는 해시 테이블을 만드는 규칙을 <EM>splatting</EM>이라고 합니다. Windows PowerShell의 splatting에 대 한 자세한 내용은 <A href="https://go.microsoft.com/fwlink/p/?linkid=267760">https://go.microsoft.com/fwlink/p/?LinkId=267760</A>를 참조 하세요.

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>설정-CsClsScenario cmdlet을 사용 하 여 기존 시나리오를 수정 하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  범위 당 두 개의 시나리오로 제한 됩니다. 로깅 캡처 세션이 진행 중인 경우에도 언제 든 지 실행 되는 시나리오를 변경할 수 있습니다. 실행 중인 시나리오를 다시 정의 하는 경우 현재 로깅 세션은 제거 된 시나리오 사용을 중지 한 다음 새 시나리오를 사용 하기 시작 합니다. 그러나 제거 된 시나리오를 사용 하 여 캡처한 로깅 정보는 캡처한 로그에 남아 있습니다. 새 시나리오를 정의 하려면 다음을 수행 합니다 (즉, "S4Provider" 라는 이미 정의 된 공급자를 추가 한다고 가정).
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    예:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    공급자를 바꾸려면 single provider 또는 쉼표로 구분 된 공급자 목록을 정의 하 여 현재 집합을 바꿉니다. 대부분의 공급자 중 하나를 바꾸려는 경우 새 공급자와 현재 공급자를 추가 하 여 새 공급자와 기존 공급자를 모두 포함 하는 새 공급자 집합을 만듭니다. 모든 공급자를 새 집합으로 바꾸려면 다음을 입력 합니다.
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    예를 들어 현재 $LyssProvider, $ABServerProvider 및 $SIPStackProvider를 $LyssServiceProvider으로 바꾸려면 다음과 같이 합니다.
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    현재 $LyssProvider 집합에서 $LyssProvider 공급자로, $ABServerProvider 및 $LyssServiceProvider을 사용 하 여 $SIPStackProvider를 교체 하려면 다음을 입력 합니다.
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>제거-CsClsScenario cmdlet을 사용 하 여 기존 시나리오를 제거 하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  이전에 정의 된 시나리오를 제거 하려면 다음을 입력 합니다.
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    예를 들어 정의 된 시나리오 사이트를 제거 하려면 다음을 수행 합니다. Redmond/LyssServiceScenario:
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

**제거-CsClsScenario** cmdlet은 지정 된 시나리오를 제거 하지만 캡처한 추적은 계속 해 서 검색을 수행할 수 있습니다.

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a>ClsController. a 모듈을 사용 하 여 편집-CsClsScenario cmdlet을 로드 하 고 언로드하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > ClsController 모듈은 별도의 웹 다운로드로 제공 됩니다. 이 모듈은 Lync Server 2013 디버깅 도구의 일부입니다. 기본적으로 디버깅 도구는 C:\Program Files\Lync Server 2013 \ 디버깅 도구 디렉터리에 설치 됩니다.

    
    </div>

2.  Windows PowerShell에서 다음을 입력 합니다.
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > 모듈 로드에 성공 하면 Windows PowerShell 명령 프롬프트로 돌아갑니다. 모듈이 로드 되 고 편집-CsClsScenario를 사용할 수 있는지 확인 하려면를 입력 <CODE>Get-Help Edit-CsClsScenario</CODE>합니다. EditCsClsScenario에 대 한 구문의 기본 개요 표시 되어야 합니다.

    
    </div>

3.  모듈을 언로드하려면 다음을 입력 합니다.
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > 모듈을 성공적으로 언로드하면 Windows PowerShell 명령 프롬프트로 돌아갑니다. 모듈이 언로드되는 지 확인 하려면를 입력 <CODE>Get-Help Edit-CsClsScenario</CODE>합니다. Windows PowerShell에서 cmdlet에 대 한 도움말을 찾으려고 하 고 실패 했습니다.

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>기존 공급자를 시나리오에서 편집-ClsController 모듈을 사용 하 여 제거 하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  AlwaysOn 시나리오에서 공급자를 제거 하려면 다음을 입력 합니다.
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    예를 들어:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    ScenarioName 및 ProviderName 매개 변수는 위치 (명령줄의 예상 위치에서 정의 되어야 함) 매개 변수입니다. 시나리오 이름이 2 위치에 있고 공급자가 3 위치, 즉 cmdlet의 이름을 위치 1로 지정 하는 경우 매개 변수 이름을 명시적으로 정의할 필요가 없습니다. 이 정보를 사용 하면 위의 명령에 다음과 같은 형식이 지정 됩니다.
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    매개 변수 값을 배치 하는 위치는 – Scenario 및 – Provider에만 적용 됩니다. 다른 모든 매개 변수는 명시적으로 정의 해야 합니다.

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>ClsController 모듈을 사용 하 여 시나리오에 공급자를 추가 하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  AlwaysOn 시나리오에 공급자를 추가 하려면 다음을 입력 합니다.
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    예를 들어:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    \-Loglevel은 치명적, Error, Warning, Info, Verbose, Debug 또는 All 형식일 수 있습니다. -Flags는 TF\_COMPONENT, tf\_DIAG와 같이 공급자에서 지 원하는 모든 플래그를 사용할 수 있습니다. -Flags는 모두 값일 수도 있습니다.
    
    Cmdlet의 위치 기능을 사용 하 여 앞의 예제를 입력할 수도 있습니다. 예를 들어 AlwaysOn 시나리오에 provider \ 서버를 추가 하려면 다음을 입력 합니다.
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

