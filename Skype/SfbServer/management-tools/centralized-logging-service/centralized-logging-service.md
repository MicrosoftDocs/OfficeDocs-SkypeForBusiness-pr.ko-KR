---
title: 비즈니스용 Skype 2015의 중앙 로깅 서비스
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
description: '요약: 2015년 8월의 중앙 로깅 서비스에 대한 서비스 구성 요소 및 구성 비즈니스용 Skype 서버 대해 자세히 알아보는 방법을 설명하는 문서입니다.'
---

# <a name="centralized-logging-service-in-skype-for-business-2015"></a>비즈니스용 Skype 2015의 중앙 로깅 서비스
 
**요약:** 2015년 8월의 중앙 로깅 서비스에 대한 서비스 구성 요소 및 구성 비즈니스용 Skype 서버 대해 자세히 알아보습니다.
  
중앙 로깅 서비스는 다음을 할 수 있습니다. 
  
- 중앙 위치에서 단일 명령을 사용하여 하나 이상의 컴퓨터 및 풀에 대한 로깅을 시작하거나 중지합니다.
    
- 하나 이상의 컴퓨터 및 풀에서 로그를 검색합니다. 검색을 조정하여 모든 컴퓨터의 모든 로그를 반환하거나 더 많은 결과를 반환할 수 있습니다.
    
- 다음과 같이 로깅 세션을 구성합니다.
    
  - **시나리오** 를 정의하거나 기본 시나리오를 사용합니다. 중앙 로깅 서비스의 시나리오는 범위(전역 또는 사이트), 시나리오의 목적을 식별하는 시나리오 이름 및 하나 이상의 공급자로 설정됩니다. 컴퓨터에서 특정 시기에 하나의 정의된 시나리오와 기본 시나리오를 실행할 수 있습니다.
    
  - 기존 공급자를 사용하거나 새 공급자를 만듭니다. Aprovider는 로깅 세션에서 수집하는 내용, 세부 정보 수준, 추적할 구성 요소 및 적용되는 플래그를 정의합니다.
    
    > [!TIP]
    >  OCSLogger에 익숙한 경우 용어providers는 구성 요소 컬렉션(예: S4  , SIPStack), 로깅 유형(예: WPP  , EventLog 또는 IIS 로그 파일), 추적 수준(예: All, verbose, debug) 및 플래그(예: TF_COMPONENT, TF_DIAG)를 참조합니다.  이러한 항목은 공급자(Windows PowerShell 변수)에 정의되고 중앙 로깅 서비스 명령으로 전달됩니다.
  
  - 특정 컴퓨터 및 풀에 대한 로그를 구성합니다.
    
  - 사이트 옵션(해당 사이트의 컴퓨터에서만 로깅 캡처를  실행) 또는 **Global**(배포의 모든 컴퓨터에서 로깅 캡처 실행) 옵션에서 로깅 세션의 범위를 정의합니다.
    
중앙 로깅 서비스는 근본 원인 분석에서 성능 문제까지 크고 작은 문제에 대한 강력한 문제 해결 도구입니다. 모든 예제는 관리 셸을 사용하여 비즈니스용 Skype 서버 있습니다. 도구 자체를 통해 명령줄 도구에 대한 도움말이 제공되지만 명령줄에서 실행할 수 있는 기능은 제한적입니다. 비즈니스용 Skype 서버 관리 셸을 사용하면 훨씬 더 크고 훨씬 더 많은 구성 가능한 기능 집합에 액세스할 수 있으므로 항상 첫 번째 선택이 될 수 있습니다. 
  
## <a name="logging-service-components"></a>로깅 서비스 구성 요소

 중앙 로깅 서비스는 배포의 모든 서버에서 실행되는 다음 에이전트 및 서비스로 구성됩니다.
  
- 중앙 로깅 서비스 에이전트 ClsAgent는 배포된 모든 비즈니스용 Skype 서버 실행됩니다. WCF를 통해 ClsController의 명령을 수신(포트 **TCP 50001-50003**)에서 수신하고 응답을 컨트롤러로 다시 전송합니다. 로그 세션(시작/중지/업데이트)을 관리하고 로그를 검색합니다. 또한 로그 보관 및 제거와 같은 보관 작업을 수행하기도 합니다. 
    
- 중앙 로깅 서비스 컨트롤러 cmdlet 비즈니스용 Skype 서버 관리 셸은 시작, 중지, 플러시 및 검색 명령을 ClsAgent로 전송합니다. 검색 명령이 전송되는 경우 결과 로그가 검색 ClsControllerLib.dll 집계됩니다. 컨트롤러는 에이전트로 명령을 보내고, 해당 명령의 상태를 수신하고, 검색 범위에 있는 컴퓨터의 모든 에이전트에서 반환되는 검색 로그 파일 데이터를 관리하고, 로그 데이터를 의미 있고 순서가 있는 출력 집합으로 집계합니다. 다음 항목의 정보는 비즈니스용 Skype 서버 관리 셸 사용에 초점을 맞추고 있습니다.
    
**ClsController에서 ClsAgent로의 통신**

![CLSController와 CLSAgent 간의 관계입니다.](../../media/Ops_CLS_Architecture.jpg)
  
Windows Server 명령줄 인터페이스 또는 비즈니스용 Skype 서버 실행합니다. 명령은 로그인된 컴퓨터에서 실행되어 ClsAgent에 로컬로 전송되거나 배포의 다른 컴퓨터 및 풀로 전송됩니다.
  
ClsAgent는 로컬 컴퓨터에 있는 모든 .CACHE 파일의 인덱스 파일을 유지합니다. ClsAgent는 CacheFileLocalFolders 옵션으로 정의된 모든 볼륨에 걸쳐 균등하게 분산되도록 .CACHE 파일을 할당하며 각 볼륨의 80% 이하만 사용합니다(**Set-CsClsConfiguration** cmdlet을 사용하여 로컬 캐시 위치와 비율을 구성 가능). 또한 ClsAgent는 오래된 캐시된 이벤트 추적 로그(.etl) 파일을 로컬 컴퓨터에서 에이징합니다. 2주 후에(**Set-CsClsConfiguration** cmdlet을 사용하여 기간을 구성 가능) 이러한 파일은 파일 공유로 복사되어 로컬 컴퓨터에서 삭제됩니다. 자세한 내용은 [Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps)을 참조하십시오. 검색 요청이 수신되면 검색 조건을 사용하여 캐시된 .etl 파일 집합을 선택하고 에이전트에서 유지되는 인덱스의 값을 사용하여 검색을 수행합니다.
  
> [!NOTE]
> 로컬 컴퓨터에서 파일 공유로 이동된 파일은 ClsAgent에서 검색할 수 있습니다. ClsAgent에서 파일을 파일 공유로 이동한 후에는 해당 파일의 에이징 및 제거를 유지하지 않습니다. 사용자는 파일 공유에서 파일 크기를 모니터링하여 파일을 삭제하거나 보관하는 관리 작업을 정의해야 합니다. 
  
결과 로그 파일은 **Snooper.exe** 를 비롯한 다양한 도구와 텍스트 파일을 읽을 수 있는 모든 도구(예: **Notepad.exe**)를 사용하여 읽고 분석할 수 있습니다. Snooper.exe 2015 비즈니스용 Skype 서버 도구의 일부로, 웹 다운로드로 [사용할 수 있습니다](https://go.microsoft.com/fwlink/p/?LinkId=285257).
  
OCSLogger와 마찬가지로 중앙 로깅 서비스에는 추적할 몇 가지 구성 요소가 있으며, OCS 및 로깅과 같은 플래그를 선택할 TF_COMPONENT TF_DIAG. 중앙 로깅 서비스는 OCSLogger의 로깅 수준 옵션도 보존합니다.
  
명령줄 ClsController보다 비즈니스용 Skype 서버 관리 셸을 사용할 때 가장 중요한 이점은 문제 공간, 사용자 지정 플래그 및 로깅 수준을 대상으로 하는 선택한 공급자를 사용하여 새 시나리오를 구성하고 정의할 수 있는 것입니다. 반면 ClsController에서 사용할 수 있는 시나리오는 실행 파일에 정의된 시나리오로 한정됩니다.
  
이전 버전에서는 관리자와 지원 담당자가 배포의 컴퓨터에서 추적 파일을 수집할 수 있도록 OCSLogger.exe가 제공되었습니다. OCSLogger는 다양한 장점이 있지만 한 가지 단점이 있습니다. 즉, 한 번에 한 컴퓨터에서만 로그를 수집할 수 있습니다. 별도의 OCSLogger를 사용하여 여러 컴퓨터에 로그온할 수도 있지만 이렇게 하면 여러 로그가 생성되며 결과를 집계하기 어렵습니다.
  
사용자가 로그 검색을 요청하면 ClsController는 선택된 시나리오에 따라 요청을 전송할 컴퓨터를 결정합니다. 또한 저장된 .etl 파일이 있는 파일 공유로 검색을 전송해야 할지 여부를 결정합니다. 검색 결과가 ClsController에 반환되면 이 컨트롤러는 결과를 시간순으로 정렬된 단일 결과 집합으로 병합하여 사용자에게 제공합니다. 사용자는 검색 결과를 로컬 컴퓨터에 저장하여 추가로 분석할 수 있습니다.
  
로깅 세션을 시작할 때 해결할 문제와 관련된 시나리오를 지정해야 합니다. 한 번에 두 시나리오를 실행할 수 있으며, 그 중 하나는 AlwaysOn 시나리오여야 합니다. 이름에서 알 수 있듯이 AlwaysOn 시나리오는 모든 컴퓨터, 풀 및 구성 요소에 대한 정보를 수집하며 배포에서 항상 실행되어야 합니다.
  
> [!IMPORTANT]
> 기본적으로 AlwaysOn 시나리오는 배포에서 실행되지 않습니다. 시나리오를 명시적으로 시작해야 합니다. 일단 시작되면 명시적으로 중지될 때까지 계속 실행되고 컴퓨터 재부팅을 통해 실행 상태가 지속됩니다. 시나리오 시작 및 중지에 대한 자세한 내용은 [Start or stop CLS log capture in 비즈니스용 Skype 서버 참조합니다](start-or-stop-log-capture.md). 
  
문제가 발생할 경우 보고된 문제와 관련된 두 번째 시나리오를 시작합니다. 문제를 재현하고 두 번째 시나리오의 로깅을 중지합니다. 그런 다음 보고된 문제와 관련된 로그 검색을 시작합니다. 집계된 로그 컬렉션을 사용하여 사이트 내 모든 컴퓨터 또는 전체 배포 범위의 추적 메시지가 포함된 로그 파일이 생성됩니다. 검색 결과 제대로 분석할 수 없을 정도로 많은 데이터가 반환될 경우("신호 대 노이즈 비율"에서 노이즈가 너무 높음) 보다 좁은 범위의 매개 변수를 사용하여 검색을 다시 실행할 수 있습니다. 이렇게 하면 나타나는 패턴을 인식하여 문제에 더욱 명확하게 중점을 둘 수 있습니다. 몇 번의 구체화된 검색을 통해 문제와 관련된 데이터를 찾아 근본 원인을 파악할 수 있습니다.
  
> [!TIP]
> 2016년 8월의 문제 시나리오가 비즈니스용 Skype 서버 "문제를 이미 알고 있는 것은 무엇일까요?"를 묻는 것으로 시작하세요. 문제 경계를 수량화하는 경우 문제 경계에서 운영 엔터티의 상당 부분을 비즈니스용 Skype 서버. 
  
사용자가 연락처를 검색할 때 최신 결과를 얻지 못하며 여러분이 이 사실을 알고 있는 시나리오를 예로 들어 보겠습니다. 미디어 구성 요소, Enterprise Voice, 회의 및 기타 여러 구성 요소에서 문제를 찾는 데는 아무 점도 없습니다. 이 상황에서 모르는 사항은 문제가 실제로 발생한 위치(클라이언트 쪽 또는 서버 쪽)일 것입니다. 연락처는 User Replicator에 의해 Active Directory에서 수집되고 ABServer(주소장 서버)를 통해 클라이언트로 전달됩니다. ABServer는 RTC 데이터베이스(User Replicator가 해당 업데이트를 기록한 위치)에서 업데이트를 다운로드하여 기본적으로 오전 1시 30분에 주소부 파일에 수집합니다. 비즈니스용 Skype 서버 클라이언트는 임의 일정으로 새 주소부를 검색합니다. 프로세스의 작동 방법을 알고 있기 때문에 Active Directory에서 User Replicator, ABServer가 주소장 파일을 검색 및 만들지 못하거나 클라이언트가 주소장 파일을 다운로드하지 않는 경우 Active Directory에서 수집되는 데이터와 관련된 문제로 인해 발생할 수 있는 원인에 대한 검색을 줄일 수 있습니다.
  
## <a name="current-configuration"></a>현재 구성

중앙 로깅 서비스는 로깅 서비스가 수집할 용도, 로깅 서비스가 수집하는 방법, 수집 위치 및 로그 설정을 정의하도록 구성됩니다. 이러한 설정은 전역적으로(즉, 전체 배포의 경우) 또는 사이트(즉, 배포의 명명된 사이트)에 대해 정의합니다. 사용자가 정의하는 모든 로깅에는 로그를 시작, 중지, 플러시 및 검색하기 위한 명령에 사용하는 identity에 적합한 설정이 사용됩니다.
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>현재 중앙 로깅 서비스 구성을 표시하려면

1. 비즈니스용 Skype 서버 시작 **: 시작,** 모든 **프로그램, 비즈니스용 Skype** **2015** 를 클릭한 다음 관리 **비즈니스용 Skype 서버 클릭합니다**.
    
2. 명령줄 프롬프트에 다음을 입력합니다.
    
   ```PowerShell
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > `-Identity` 정의를 통해 반환되는 구성 설정 범위와 범위(예: "Site:Redmond")를 좁히거나 확장하여 Redmond 사이트에 대한 CsClsConfiguration만 반환할 수 있습니다. 구성의 특정 부분에 대한 세부 정보를 원할 경우 출력을 다른 cmdlet으로 Windows PowerShell 있습니다. 예를 들어 사이트 "Redmond"의 구성에 정의된 시나리오에 대한 세부 정보를 확인하려면 다음을 입력합니다. `Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Get-CsClsConfiguration의 샘플 출력입니다.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    cmdlet의 결과에는 중앙 로깅 서비스의 현재 구성이 표시됩니다.
    
|**구성 설정**|**설명**|
|:-----|:-----|
|**ID** <br/> |이 구성의 범위 및 이름을 식별합니다. 전역 구성 한 개와 사이트당 한 개의 구성만 있습니다.  <br/> |
|**시나리오** <br/> |이 구성에 대해 정의된 모든 시나리오를 나열합니다.  <br/> |
|**SearchTerms** <br/> |구성에 대해 정의된 검색어입니다. Microsoft 365 Office 365 배포를 설치하거나 구성하지 않습니다.  <br/> |
|**SecurityGroups** <br/> |사용자가 위치한 사이트를 기반으로 컴퓨터를 볼 수 있는 사용자(즉, 보안 그룹의 구성원)를 제어하는 정의된 보안 그룹입니다. 이 컨텍스트에서 사이트는 토폴로지 작성기에서 정의된 사이트입니다.  <br/> |
|**지역** <br/> |정의된 지역은 특정 지역(예: EMEA)에서 SecurityGroups를 수집하는 데 사용됩니다.  <br/> |
|**EtlFileRolloverSizeMB** <br/> |이 매개 변수는 새 이벤트 추적 로그(.etl) 파일을 만들기 전 로그 파일의 최대 크기를 나타냅니다. EtlFileRolloverMinutes에 설정된 최대 시간에 아직 도달하지 않았어도 정의된 크기에 도달하면 새 로그 파일이 만들어집니다.  <br/> |
|**EtlFileRolloverMinutes** <br/> |새 .etl 파일을 만들기 전에 로그에서 경과될 수 있도록 정의된 최대 시간(분)입니다. 할 수 있도록 EtlFileRolloverSizeMB에 설정된 최대 크기에 아직 도달하지 않았어도 타이머 시간이 초과되면 새 로그 파일이 만들어집니다.  <br/> |
|**TmfFileSearchPath** <br/> |추적 메시지 형식 파일을 검색할 위치입니다.  <br/> |
|**CacheFileLocalFolders** <br/> |컴퓨터에서 캐시 파일을 기록할 위치에 대해 정의된 경로입니다. CLSAgent는 네트워크 서비스의 컨텍스트에 따라 캐시 파일을 기록하고 실행됩니다. 여기서 %TEMP%는 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local로 확장됩니다. 기본적으로 캐시 파일과 로그 파일은 동일한 디렉터리에 기록됩니다.  <br/> |
|**CacheFileNetworkFolder** <br/> |로깅 작업 중 캐시 파일을 수신하기 위한 UNC(범용 명명 규칙) 경로를 정의할 수 있습니다.  <br/> |
|**CacheFileLocalRetentionPeriod** <br/> |캐시 파일을 보존할 수 있는 최대 시간(일)으로 정의됩니다.  <br/> |
|**CacheFileMaxDiskUsage** <br/> |캐시 파일이 사용할 수 있는 디스크 공간 비율로 정의됩니다.  <br/> |
|**ComponentThrottleLimit** <br/> |자동 스로틀 리미터가 트리거되기 전 구성 요소가 생성할 수 있는 초당 최대 추적 수로 정의됩니다.  <br/> |
|**ComponentThrottleSample** <br/> |ComponentThrottleLimit를 초과할 수 있는 횟수(60초 이내)입니다.  <br/> |
|**MinimumClsAgentServiceVersion** <br/> |실행할 수 있는 CLSAgent의 최소 버전입니다. 이 요소는 Microsoft 365 또는 Office 365.  <br/> |
