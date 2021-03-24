---
title: 비즈니스용 Skype 서버에서 CLS 로그 캡처 시작 또는 중지
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: '요약: 비즈니스용 Skype 서버 2015에서 중앙 로깅 서비스 로그 캡처 세션을 시작하거나 중지하는 방법을 설명하는 방법을 제공합니다.'
ms.openlocfilehash: 773b93f62690b01d33f84bc5eb68b135280842ea
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098824"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버에서 CLS 로그 캡처 시작 또는 중지
 
**요약:** 비즈니스용 Skype 서버 2015에서 중앙 로깅 서비스 로그 캡처 세션을 시작하거나 중지하는 방법을 학습합니다.
  
중앙 로깅 서비스를 사용하여 추적 로그를 캡처하려면 하나 이상의 컴퓨터 및 풀에서 로깅을 시작하는 명령을 실행합니다. 또한 어떤 컴퓨터 또는 풀, 실행할 시나리오(예: AlwaysOn, 미리 정의한 시나리오 또는 만든 시나리오), 추적할 비즈니스용 Skype 서버 구성 요소(예: S4, SipStack)를 정의하는 매개 변수를 발급합니다.
  
적절한 정보를 캡처하려면 올바른 시나리오를 사용하여 문제와 관련된 정보를 수집해야 합니다. 중앙 로깅 서비스에서 시나리오는 서버 구성 요소, 로깅 수준 및 플래그 컬렉션을 기반으로 로깅을 설정하는 개념으로, 서버 기준에 따라 이러한 요소를 정의할 필요 없이 훨씬 효율적이며 유용합니다. 시나리오를 정의 및 지정하면 인프라 범위 내의 모든 서버 및 풀에서 시나리오가 일관성 있게 실행됩니다.
  
기본 시나리오는 **AlwaysOn** 입니다. AlwaysOn은 이름에서 짐작할 수 있듯이 시나리오를 지속적으로 실행하기 위한 용도로 사용됩니다. AlwaysOn 시나리오는 가장 일반적인 대부분의 서버 구성 요소에 대해 정보 수준의 정보를 수집합니다(정보 로깅 수준에는 정보 메시지 외에 심각, 오류 및 경고도 포함됨). AlwaysOn은 문제 발생 전/중/후에 정보를 수집합니다. 이는 OCSLogger와 같은 이전 로깅 도구의 일반적인 동작과는 크게 다릅니다. OCSLogger는 문제가 이미 발생한 후에 실행하는 방식이었으며, 수집되는 데이터가 사전 예방 방식이 아닌 사후 대응 방식이므로 문제를 해결하기가 보다 어려웠습니다. 문제 구성 요소를 파악하고 해당 문제를 해결하기 위한 일련의 동작을 나타내기 위해 확인해야 하는 정보가 AlwaysOn에 포함되어 있지 않은 경우(AlwaysOn에는 매우 다양하고 폭넓은 공급자가 포함되므로 그럴 가능성은 거의 없음), AlwaysOn은 새 시나리오 만들기, 다른 정보 수집, 다른 검색을 실행하여 보다 세부적인 정보 수집 등 수행해야 하는 다른 작업을 결정하기 위한 적절한 정보 수준을 지시합니다.
  
중앙 로깅 서비스는 명령을 발급하는 두 가지 방법을 제공합니다. 많은 항목은 비즈니스용 Skype 서버 관리 셸을 통해 Windows PowerShell 정사각형으로 초점을 맞추고 있습니다. 다양한 복잡한 구성 및 명령을 사용하는 기능을 통해 중앙 로깅 Windows PowerShell 사용할 수 있습니다. 비즈니스 Windows PowerShell 셸을 통해 사용할 수 있는 기능은 비즈니스용 Skype 서버의 모든 기능에 거의 사용되지 Windows PowerShell 설명되어 있습니다. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>기본 Start-CsClsLogging 사용하여 Windows PowerShell 실행

1. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
2. 다음을 입력하여 중앙 로깅 서비스로 로깅 시나리오를 시작하십시오.
    
   ```PowerShell
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    예를 들어 **AlwaysOn** 시나리오를 시작하려면 다음을 입력합니다.
    
   ```PowerShell
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > AlwaysOn 시나리오에는 기본 기간이 없습니다. 즉, 이 시나리오는 **Stop-CsClsLogging** cmdlet을 사용하여 명시적으로 중지할 때까지 실행됩니다. 자세한 내용은 [Stop-CsClsLogging](/powershell/module/skype/stop-csclslogging?view=skype-ps)을 참조하십시오. 다른 모든 시나리오의 경우 기본 기간은 4시간입니다. 
  
3. Enter 키를 눌러 명령을 실행합니다. 
    
    > [!NOTE]
    > 명령이 실행되어 배포의 컴퓨터로부터 상태를 받을 때가지 시간이 약간 걸릴 수 있습니다(30~60초). 
  
     ![Start-CsClsLogging을 실행합니다.](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. 다른 시나리오를 시작하려면 실행하려는 추가 시나리오 이름(예: **Authentication** 시나리오)을 포함하여 **Start-CsClsLogging** cmdlet을 사용합니다.
    
   ```PowerShell
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > 지정된 컴퓨터에서 항상 총 2개의 시나리오를 실행할 수 있습니다. 명령의 범위가 전역인 경우에는 배포의 모든 컴퓨터에서 시나리오를 실행합니다. 세 번째 시나리오를 시작하려면 새 시나리오를 실행할 컴퓨터, 풀, 사이트 또는 전역 범위에서 로깅을 중지해야 합니다. 전역 범위를 시작한 경우에는 하나 이상의 컴퓨터 및 풀에서 시나리오 하나 또는 둘 다에 대해 로깅을 중지하면 됩니다. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>고급 Start-CsClsLogging 사용하여 Windows PowerShell 실행

1. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
2. 추가 매개 변수를 사용하여 로깅 명령을 관리할 수 있습니다. -Duration을 사용하여 시나리오를 실행할 기간을 조정할 수 있습니다. 또한 -Computers( 컴퓨터 FQDNS(정식 도메인 이름)의 목록(콤보로 구분)를 정의하거나 로깅을 실행할 풀의 FQDNS 목록인 -Pools를 정의할 수도 있습니다.
    
    "pool01.contoso.net" 풀에서 UserReplicator 시나리오에 대한 로깅 세션을 시작해야 합니다. 또한 로깅 세션 기간을 8시간으로 정의합니다. 이렇게 하려면 다음을 입력합니다.
    
   ```PowerShell
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    이 시나리오가 정상적으로 실행되면 다음과 같은 결과가 반환됩니다.
    
     ![Start-CsClsLogging을 실행합니다.](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
이 예제에서는 AlwaysOn 시나리오와 UserReplicator 시나리오가 실행됩니다. 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>중앙 로깅 서비스 로그 캡처 중지
<a name="stop"> </a>

Stop-CsClsLogging cmdlet을 사용하여 현재 실행 중인 로깅 세션을 중지할 수 있습니다. 일반적으로 로깅 세션을 중지해야 하는 상황은 많지 않습니다. 예를 들어 로깅을 먼저 중지하지 않고도 로그를 검색하고 구성을 변경할 수 있습니다. 두 시나리오(AlwaysOn 및 UserReplicator)를 실행 중인데 Authentication 관련 정보를 수집해야 하는 경우에는 전역, 사이트, 풀 또는 컴퓨터 범위에서 다른 시나리오 중 하나를 중지해야 Authentication 시나리오 실행을 시작할 수 있습니다. 자세한 내용은 [Stop-CsClsLogging](/powershell/module/skype/stop-csclslogging?view=skype-ps)을 참조하십시오.
  
> [!NOTE]
> 특정 배포, 풀 또는 컴퓨터에서 실행할 수 있는 시나리오를 결정할 때 AlwaysOn 및 하나의 사용자 지정 시나리오를 컴퓨터당 두 개의 시나리오로만 실행할 수 있습니다. 풀에서 활동을 로깅 중이라면 풀을 엔터티 하나로 간주해야 합니다. 대부분의 경우에는 풀의 각 컴퓨터에서 서로 다른 시나리오를 실행하지 않습니다. 데이터를 수집 중인 문제를 확인하여 전체 배포에서 지정된 컴퓨터에 가장 적합한 시나리오를 고려하는 것이 적절합니다. 예를 들어 UserReplicator 시나리오를 고려할 경우 에지 서버 또는 에지 풀에서 UserReplicator를 실행하는 데는 값이 거의 없습니다. 
  
문제와 영향의 범위를 파악한 후에는 각 컴퓨터와 풀에서 실행할 시나리오를 적절하게 선택해야 합니다. AlwaysOn 시나리오는 다양한 공급자에 대한 정보를 수집하므로 폭넓은 응용 프로그램에 적합하기는 하지만, 특정 시나리오는 특정 컴퓨터나 풀에서만 응용 프로그램과 관련하여 유용합니다. 또한 먼저 지정된 시나리오의 유용성을 파악하지 않고 로깅 세션을 임의로 시작할 때도 주의해야 합니다. 잘못된 시나리오를 사용하거나 작업에 적합한 시나리오를 사용하기는 하지만 잘못된 범위(전역/사이트/풀/컴퓨터)에서 시나리오를 적용하는 경우에는 시나리오를 전혀 실행하지 않은 것과 마찬가지로 부적절한 데이터가 제공될 수 있습니다.
  
비즈니스용 Skype 서버 관리 셸을 사용하여 중앙 로깅 서비스 기능을 제어하려면 CsAdministrator 또는 CsServerAdministrator RBAC(역할 기반 액세스 제어) 보안 그룹 또는 이러한 두 그룹 중 하나를 포함하는 사용자 지정 RBAC 역할의 구성원이 되어야 합니다. 이 cmdlet이 할당된 모든 RBAC 역할(직접 만든 사용자 지정 RBAC 역할 포함)의 목록을 반환하기 위해 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

예:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> 따라서 궁금할 수 있습니다. 이제 로깅을 사용하도록 설정했습니다. 로그는 어디에 보관하나요? CLS 에이전트로 전송된 관리 셸 쿼리를 사용하여 로그에 저장된 정보에 액세스하고 결과를 여러 가능한 파일 형식으로 출력할 수 있습니다. 여기서 각 서버에서 CLS 에이전트가 레코드를 보관하는 것은 실제로 알 중요하지 않습니다.  로그 파일은 지정하고 읽고 분석하는 위치에 저장할 수 있습니다. 로그  파일은Snooper.exe파일과 같은 텍스트 파일을 읽을 수 있는 모든 도구를 사용하여 **Notepad.exe.** Snooper.exe 는 비즈니스용 Skype 서버 2015 디버그 도구의 일부로, 웹 다운로드로 [사용할 수 있습니다.](https://go.microsoft.com/fwlink/p/?LinkId=285257)

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>현재 실행 중인 중앙 로깅 서비스 세션을 중지합니다.

1. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
2. 중앙 로깅 서비스를 쿼리하여 다음을 입력하여 현재 실행 중인 시나리오를 검색합니다.
    
   ```PowerShell
   Show-CsClsLogging
   ```

   ![Windows PowerShell 호출한 후 콘솔에서 Show-CsCl](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   Show-CsClsLogging의 결과는 실행 중인 시나리오 및 시나리오가 실행되는 범위의 요약입니다. 자세한 내용은 [Show-CsClsLogging](/powershell/module/skype/show-csclslogging?view=skype-ps)을 참조하십시오.
    
3. 특정 시나리오를 사용하여 현재 실행 중인 로깅 세션을 중지하려면 다음을 입력합니다.
    
   ```PowerShell
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   예를 들면 다음과 같습니다.
    
   ```PowerShell
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   이 명령은 pool01.contoso.net에서 UserReplicatior 시나리오를 사용한 로깅을 중지합니다.
    
    > [!NOTE]
    > UserReplicator 시나리오를 사용하여 이 로깅 세션 중에 작성되는 로그는 삭제되지 않습니다. Search-CsClsLogging 명령을 사용하면 로깅에 대해 검색을 계속 실행할 수 있습니다. 자세한 내용은 [Search-CsClsLogging](/powershell/module/skype/search-csclslogging?view=skype-ps)을 참조하십시오. 
  
Start-CsClsLogging의 보조 명령으로 작동하는 Stop-CsClsLogging cmdlet은 시나리오에 의해 정의된 로깅 세션을 종료하고 로깅 세션에서 작성된 로그를 보관합니다. 지정된 컴퓨터에서 한 번에 두 개의 시나리오를 실행할 수 있습니다. 한 시나리오를 중지하고 다른 시나리오를 사용하여 정보를 수집하는 방법은 대부분의 작업 문제 해결 중에 수행할 수 있는 일반적인 작업입니다.
## <a name="see-also"></a>참고 항목
<a name="stop"> </a>

[비즈니스용 Skype 2015의 중앙 로깅 서비스](centralized-logging-service.md)