---
title: 비즈니스용 Skype 2015의 중앙 로깅 서비스
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
description: '요약: 비즈니스용 Skype Server 2015의 중앙 로깅 서비스에 대 한 서비스 구성 요소 및 구성 설정에 대해 알아봅니다.'
ms.openlocfilehash: a02d2a283716dd01572e0cbd8cccf075b29fd9b8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186834"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>비즈니스용 Skype 2015의 중앙 로깅 서비스
 
**요약:** 비즈니스용 Skype Server 2015의 중앙 로깅 서비스에 대 한 서비스 구성 요소 및 구성 설정에 대해 알아봅니다.
  
중앙 집중화 된 로깅 서비스는 다음을 수행할 수 있습니다. 
  
- 중앙 위치의 단일 명령으로 하나 이상의 컴퓨터와 풀에 대 한 로깅을 시작 하거나 중지 합니다.
    
- 하나 이상의 컴퓨터 및 풀에서 로그를 검색 합니다. 모든 컴퓨터에서 모든 로그를 반환 하거나 더 간결한 결과를 반환 하도록 검색을 조정할 수 있습니다.
    
- 로깅 세션을 다음과 같이 구성 합니다.
    
  - **시나리오**를 정의 하거나 기본 시나리오를 사용 합니다. 중앙 로깅 서비스의 시나리오는 범위 (전역 또는 사이트)로 구성 되며 시나리오의 용도를 식별 하는 시나리오 이름 및 하나 이상의 공급자입니다. 컴퓨터에서 지정 된 시간에 기본 시나리오와 정의 된 시나리오 하나를 실행할 수 있습니다.
    
  - 기존 공급자를 사용 하거나 새 공급자를 만듭니다. Aprovider는 로깅 세션에서 수집 하는 항목, 세부 정보 수준, 추적할 구성 요소 및 적용 되는 플래그를 정의 합니다.
    
    > [!TIP]
    >  OCSLogger 사용 하는 데 익숙한 경우 termproviders는 **구성 요소** 컬렉션 (예: S4, SIPStack), **로깅 형식** (예: WPP, EventLog 또는 IIS 로그 파일), **추적 수준** (예: 전체, 자세한 정보, 디버그)을 참조 합니다. , **flags** (예: TF_COMPONENT, TF_DIAG) 이러한 항목은 공급자 (Windows PowerShell 변수)에 정의 되 고 중앙 로깅 서비스 명령으로 전달 됩니다.
  
  - 특정 컴퓨터 및 풀에 대 한 로그를 구성 합니다.
    
  - 옵션 **사이트** 의 로깅 세션에 대 한 범위를 정의 합니다 (해당 사이트의 컴퓨터에 로깅 캡처를 실행 하는 경우) 또는 **Global** (배포의 모든 컴퓨터에서 로깅 캡처를 실행 하는 경우)
    
중앙 로깅 서비스는 근본 원인 분석에서 성능 문제에 이르기까지 매우 크거나 작은 문제에 대 한 강력한 문제 해결 도구입니다. 모든 예제는 비즈니스용 Skype 서버 관리 셸을 사용 하 여 표시 됩니다. 도움말은 도구 자체를 통해 명령줄 도구에 대해 제공 되지만 명령줄에서 실행할 수 있는 제한 된 함수 집합이 있습니다. 비즈니스용 Skype Server Management Shell을 사용 하 여 훨씬 더 광범위 하 고 구성 가능한 기능 집합에 액세스할 수 있으므로 항상 처음으로 선택 해야 합니다. 
  
## <a name="logging-service-components"></a>로깅 서비스 구성 요소

 중앙 로깅 서비스는 배포의 모든 서버에서 실행 되며 다음 에이전트 및 서비스로 구성 됩니다.
  
- 중앙 집중식 로깅 서비스 에이전트 ClsAgent는 비즈니스용 Skype 서버를 배포 하는 모든 컴퓨터에서 실행 됩니다. WCF를 통해 ClsController의 명령에 대 한 ( **TCP 50001-50003**포트에서)를 수신 대기 하 고 응답을 컨트롤러에 다시 보냅니다. 로그 세션 (시작/중지/업데이트)을 관리 하 고 로그를 검색 합니다. 또한 로그 보관 및 제거와 같은 정리 작업을 수행 합니다. 
    
- 중앙 로깅 서비스 컨트롤러 Cmdlet 비즈니스용 Skype Server 관리 셸에서는 ClsAgent에 시작, 중지, 플러시 및 검색 명령을 보냅니다. 검색 명령을 보내면 결과 로그가 ClsControllerLib로 반환 되 고 집계 됩니다. 컨트롤러는 에이전트에 명령을 보내고, 이러한 명령의 상태를 받고, 검색 범위에 있는 컴퓨터의 모든 에이전트에서 반환 되는 검색 로그 파일 데이터를 관리 하 고, 의미 있고 순서가 지정 된 출력 집합에 로그 데이터를 집계 합니다. 다음 항목의 정보는 비즈니스용 Skype 서버 관리 셸을 사용 하는 데 초점을 맞추었습니다.
    
**Clscontroller에 대 한 ClsController 통신**

![CLSController와 CLSAgent 간의 관계.](../../media/Ops_CLS_Architecture.jpg)
  
Windows Server 명령줄 인터페이스 또는 비즈니스용 Skype 서버 관리 셸을 사용 하 여 명령을 실행 합니다. 명령은 사용자가 로그인 하 여 로컬로 ClsAgent에 또는 배포의 다른 컴퓨터와 풀로 전송 된 컴퓨터에서 실행 됩니다.
  
ClsAgent는 all에 대 한 인덱스 파일을 유지 합니다. 로컬 컴퓨터에 있는 파일을 캐시 합니다. ClsAgent는 옵션 CacheFileLocalFolders가 정의한 모든 볼륨에서 균등 하 게 분산 되도록 각 볼륨의 80%를 초과 하지 않도록 (즉, 로컬 캐시 위치와 백분율을 사용 하 여 **구성할 수 있습니다.) Set-CsClsConfiguration** cmdlet). 또한 ClsAgent는 로컬 컴퓨터에서 이전에 캐싱된 이벤트 추적 로그 (.etl) 파일을 에이징 하는 역할을 합니다. 2 주 후 (즉, **설정-CsClsConfiguration** cmdlet을 사용 하 여 시간을 구성할 수 있음) 이러한 파일은 로컬 컴퓨터에서 파일 공유에 복사 되 고 삭제 됩니다. 자세한 내용은 [Set CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)을 참조 하세요. 검색 요청이 수신 되 면 검색 조건을 사용 하 여 에이전트에서 유지 관리 되는 인덱스의 값을 기준으로 검색을 수행 하도록 캐시 된 .etl 파일 집합을 선택 합니다.
  
> [!NOTE]
> 로컬 컴퓨터에서 파일 공유로 이동 된 파일은 ClsAgent를 통해 검색할 수 있습니다. ClsAgent가 파일 공유로 파일을 이동 하면 ClsAgent가 파일의 에이징 및 제거를 유지 하지 않습니다. 파일 공유에서 파일 크기를 모니터링 하 고 삭제 하거나 보관 하는 관리 작업을 정의 해야 합니다. 
  
결과 로그 파일은 **Snooper** 와 **메모장과**같은 텍스트 파일을 읽을 수 있는 도구를 비롯 한 다양 한 도구를 사용 하 여 읽고 분석할 수 있습니다. Snooper는 비즈니스용 Skype 서버 2015 디버그 도구의 일부 이며 [웹 다운로드](https://go.microsoft.com/fwlink/p/?LinkId=285257)로 제공 됩니다.
  
OCSLogger 같은 중앙 로깅 서비스에는 추적할 여러 구성 요소가 있으며 TF_COMPONENT 및 TF_DIAG와 같은 플래그를 선택 하는 옵션을 제공 합니다. 또한 중앙 로깅 서비스는 OCSLogger의 로깅 수준 옵션도 유지 합니다.
  
명령줄 ClsController에서 비즈니스용 Skype Server Management Shell을 사용 하는 경우 가장 중요 한 이점은 문제 공간, 사용자 지정 플래그 및 로깅 수준을 대상으로 하는 선택 된 공급자를 사용 하 여 새 시나리오를 구성 하 고 정의할 수 있다는 것입니다. ClsController에서 사용할 수 있는 시나리오는 실행 파일에 대해 정의 된 것으로 제한 됩니다.
  
이전 버전에서는 관리자와 지원 담당자가 배포의 컴퓨터에서 추적 파일을 수집할 수 있도록 OCSLogger 제공 되었습니다. 모든 강점에 대 한 OCSLogger 단점을가지고 있습니다. 주어진 시간에 한 컴퓨터 에서만 로그를 수집할 수 있습니다. 각각의 OCSLogger 별도의 복사본을 사용 하 여 여러 컴퓨터에 로그온 할 수 있지만, 여러 개의 로그로 끝나지만 결과를 집계할 수 있는 방법은 없습니다.
  
사용자가 로그 검색을 요청 하면 ClsController는 요청을 보낼 컴퓨터 (즉, 선택 된 시나리오에 따라)를 결정 합니다. 또한 저장 된 .etl 파일이 있는 파일 공유에 검색을 보낼지 여부를 결정 합니다. 검색 결과가 ClsController에 반환 되 면 컨트롤러는 해당 결과를 사용자에 게 표시 되는 단일 시간 순서 결과 집합으로 병합 합니다. 사용자는 추가 분석을 위해 검색 결과를 로컬 컴퓨터에 저장할 수 있습니다.
  
로깅 세션을 시작할 때 해결 하려고 하는 문제에 상대적인 시나리오를 지정 합니다. 언제 든 지 두 가지 시나리오를 실행할 수 있습니다. 이러한 두 가지 시나리오 중 하나는 AlwaysOn 시나리오 여야 합니다. 이름에서 알 수 있듯이,이는 항상 배포에서 실행 되 고 모든 컴퓨터, 풀 및 구성 요소에 대 한 정보를 수집 합니다.
  
> [!IMPORTANT]
> 기본적으로 AlwaysOn 시나리오는 배포에서 실행 되지 않습니다. 시나리오를 명시적으로 시작 해야 합니다. 시작 된 후에는 명시적으로 중지 될 때까지 계속 실행 되 고 컴퓨터를 다시 부팅할 때까지 실행 상태가 유지 됩니다. 시나리오 시작 및 중지에 대 한 자세한 내용은 [비즈니스용 Skype 서버 2015에서 CLS 로그 캡처 시작 또는 중지](start-or-stop-log-capture.md)를 참조 하세요. 
  
문제가 발생 하면 보고 된 문제와 관련 된 두 번째 시나리오를 시작 합니다. 문제를 재현 하 고 두 번째 시나리오에 대 한 로깅을 중지 합니다. 보고 된 문제에 상대적인 로그 검색을 시작 합니다. 집계 된 로그 수집은 사이트의 모든 컴퓨터 또는 배포의 전역 범위에서 추적 메시지가 포함 된 로그 파일을 생성 합니다. 검색에서 feasibly 분석할 수 있는 것 보다 더 많은 데이터를 반환 하는 경우 (일반적으로 신호 대 잡음 비율이 라고도 함) 보다 좁은 매개 변수를 사용 하 여 다른 검색을 실행 합니다. 이 시점에서 표시 되는 패턴을 확인 하 고 문제를 보다 명확 하 게 파악 하는 데 도움이 될 수 있습니다. 최종적으로 몇 가지 구체화 된 검색을 수행한 후 문제와 관련 된 데이터를 찾아 근본 원인을 파악할 수 있습니다.
  
> [!TIP]
> 비즈니스용 Skype 서버에서 문제가 발생 하는 경우 "문제에 대해 이미 알고 있는 사항"을 입력 하 여 시작 합니다. 문제 경계를 수량화 하는 경우 비즈니스용 Skype 서버에서 운영 엔티티의 상당 부분을 제거할 수 있습니다. 
  
사용자가 연락처를 찾을 때 현재 결과가 표시 되지 않는 것을 알고 있는 경우를 예로 들어 보겠습니다. 미디어 구성 요소, 엔터프라이즈 음성, 회의 및 기타 다양 한 구성 요소에서 발생 하는 문제를 찾는 것이 아닙니다. 실제로 문제가 발생 한 위치는 클라이언트에서 나 서버 쪽 문제일 수 있습니다. 연락처는 Active Directory에서 사용자 복제기에 의해 수집 되 고 주소록 서버 (ABServer)를 통해 클라이언트에 게 전달 됩니다. 이 ABServer는 RTC 데이터베이스에서 업데이트를 가져와 (사용자 복제기에서 기록 하 고) 기본적으로 1:30 AM으로이를 주소록 파일에 모읍니다. 비즈니스용 Skype 서버 클라이언트는 임의 일정에 따라 새 주소록을 검색 합니다. 프로세스가 작동 하는 방식을 알고 있으므로 사용자 복제기, ABServer가 주소록 파일을 검색 하 고 만들지 않는 경우 Active Directory에서 수집 하는 데이터와 관련 된 문제로 인해 검색을 줄일 수 있습니다. 주소록 파일을 다운로드 하는 중입니다.
  
## <a name="current-configuration"></a>현재 구성

중앙 로깅 서비스는 로깅 서비스를 수집 하는 방법, 수집 하는 방법, 수집 하는 위치, 로그 설정에 대해 정의 하도록 구성 됩니다. 이러한 설정은 전체적으로 (즉, 전체 배포의 경우) 또는 사이트 (즉, 배포의 명명 된 사이트)에 정의 합니다. 정의한 모든 로깅은 로그 시작, 중지, 플러시, 검색 명령에 사용 하는 id에 적합 한 설정을 사용 합니다.
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>현재 중앙 집중화 된 로깅 서비스 구성을 표시 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. 명령줄 프롬프트에 다음을 입력 합니다.
    
   ```
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > "Site: Redmond"와 같이 정의 `-Identity` 및 범위를 통해 반환 되는 구성 설정의 범위를 좁히거나 확장 하 여 사이트 Redmond에 대 한 CsClsConfiguration만 반환할 수 있습니다. 구성의 지정 된 부분에 대 한 세부 정보를 원하는 경우 다른 Windows PowerShell cmdlet에 출력을 파이프 할 수 있습니다. 예를 들어 "Redmond" 사이트의 구성에 정의 된 시나리오에 대 한 세부 정보를 보려면 다음을 입력 합니다.`Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Get-CsClsConfiguration의 샘플 출력.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    Cmdlet의 결과에는 중앙 로깅 서비스의 현재 구성이 표시 됩니다.
    
|**구성 설정**|**설명**|
|:-----|:-----|
|**Identity** <br/> |이 구성의 범위 및 이름을 식별 합니다. 글로벌 구성은 한 개, 사이트별 구성은 하나만 있습니다.  <br/> |
|**등** <br/> |이 구성에 대해 정의 된 모든 시나리오의 목록입니다.  <br/> |
|**SearchTerms** <br/> |구성에 대 한 정의 된 검색 용어입니다. Office 365, 온-프레미스 배포가 아닙니다.  <br/> |
|**SecurityGroups** <br/> |사용자 (즉, 보안 그룹의 구성원)를 제어 하는 정의 된 보안 그룹은 자신이 위치한 사이트를 기반으로 하는 컴퓨터를 볼 수 있습니다. 이 컨텍스트에서 사이트는 토폴로지 작성기에 정의 된 사이트입니다.  <br/> |
|**영역과** <br/> |정의 된 지역은 지역 (예: EMEA)에 SecurityGroups를 수집 하는 데 사용 됩니다.  <br/> |
|**EtlFileRolloverSizeMB** <br/> |매개 변수는 새 이벤트 추적 로그 (.etl) 파일이 만들어지기 전에 로그 파일의 최대 크기를 나타냅니다. EtlFileRolloverMinutes에 설정 된 최대 시간이 아직 도달 하지 않은 경우에도 정의 된 크기에 도달 하면 새 로그 파일이 만들어집니다.  <br/> |
|**EtlFileRolloverMinutes** <br/> |새 .etl 파일을 만들기 전에 로그가 대기할 수 있는 최대 시간 (분)을 정의 합니다. EtlFileRolloverSizeMB에 설정 된 최대 크기에 도달 하지 않은 경우에도 타이머가 만료 될 때 새 로그 파일이 만들어집니다.  <br/> |
|**TmfFileSearchPath** <br/> |추적 메시지 형식 파일을 검색 하는 위치입니다.  <br/> |
|**CacheFileLocalFolders** <br/> |컴퓨터에 캐시 파일이 기록 되는 위치에 대 한 정의 된 경로입니다. CLSAgent는 캐시 파일을 기록 하 고 네트워크 서비스의 컨텍스트에서 실행 됩니다. 이 경우에는% TEMP%를%WINDIR%\ServiceProfiles\NetworkService\AppData\Local.로 확장 합니다. 기본적으로 캐시 파일 및 로그 파일은 동일한 디렉터리에 기록 됩니다.  <br/> |
|**CacheFileNetworkFolder** <br/> |로깅 작업 중 캐시 파일을 받을 UNC (범용 명명 규칙) 경로를 정의할 수 있습니다.  <br/> |
|**Cachefilelocal보존 기간** <br/> |캐시 파일이 유지 되는 최대 시간 (일)으로 정의 됩니다.  <br/> |
|**CacheFileMaxDiskUsage** <br/> |캐시 파일에서 사용할 수 있는 디스크 공간의 백분율로 정의 됩니다.  <br/> |
|**ComponentThrottleLimit** <br/> |자동 스로틀 limiter 트리거되기 전에 구성 요소가 생성할 수 있는 초당 최대 추적 수로 정의 됩니다.  <br/> |
|**ComponentThrottleSample** <br/> |ComponentThrottleLimit를 초과할 수 있는 60 초의 시간 수입니다.  <br/> |
|**이상 Clsagentserviceversion** <br/> |실행할 수 있는 CLSAgent의 최소 버전입니다. 이 요소는 Office 365를 대상으로 합니다.  <br/> |
   

