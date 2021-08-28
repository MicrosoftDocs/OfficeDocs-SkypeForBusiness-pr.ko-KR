---
title: 2015년 8월의 중앙 로깅 서비스에서 만든 캡처 비즈니스용 Skype 서버 로그
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: '요약: 2015년 8월에 중앙 로깅 서비스 캡처 로그를 검색하고 비즈니스용 Skype 서버 방법을 설명하는 문서를 제공합니다.'
ms.openlocfilehash: ff33e2d680c83b9d997e2c17d8852d8bd816edbf
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58636042"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>2015년 8월의 중앙 로깅 서비스에서 만든 캡처 비즈니스용 Skype 서버 로그
 
**요약:** 2015년 8월에 중앙 로깅 서비스 캡처 로그를 검색하고 비즈니스용 Skype 서버 방법을 학습합니다.
  
중앙 로깅 서비스의 검색 기능은 다음과 같은 이유로 유용하고 강력합니다. 
  
- 검색과 결과가 정의하는 조건을 기준으로 단일 컴퓨터, 풀, 사이트 또는 전역 범위에서 실행됩니다.
    
- 처음에는 검색 범위를 넓게 지정했다가 나중에 시간, 구성 요소, 컴퓨터 등 보다 구체적인 대상이 지정된 조건으로 좁힐 수 있습니다. 동일한 로그를 검색할 때 검색 조건이 변경될 때 로깅 세션을 다시 실행할 필요가 없습니다.
    
- 범위에 속하는 모든 컴퓨터 및 풀에서 검색 결과를 모은 다음 검색 조건의 모든 결과를 나타내는 단일 출력 파일에 수집 및 집계합니다(검색 시 실행 중이었던 시나리오 및 해당 시나리오에 의해 캡처된 데이터로 제한됨). **Snooper**, **메모장** 등의 익숙한 도구를 사용하여 배포 전체의 출력 파일 및 추적 메시지를 읽습니다.
    
개별 컴퓨터의 CLSAgent가 하나 이상의 시나리오(지정된 시간에 컴퓨터당 두 개의 시나리오를 실행할 수 있음)를 기준으로 로그를 만듭니다. 로그 및 로그에 연결된 인덱스와 캐시 파일은 CLSAgent를 통해 관리됩니다. 검색을 정의하고 실행하면 검색 명령은 검색할 정보를 CLSAgent에 지시합니다. 그러면 CLSAgent는 로그 파일, 캐시 파일 및 인덱스 파일에 대해 쿼리를 실행하고 검색 결과를 CLSController로 반환합니다. CLSController는 검색 범위 내의 모든 컴퓨터와 풀에서 검색 결과를 받습니다. 그런 다음 CLSController는 로그를 집계(결합)하여 시간 간격순으로 배치합니다(가장 오래된 항목부터 시간상 가장 최근 항목순).
  
각 검색 후 **Sync-CsClsLogging** cmdlet이 실행되며, 이 cmdlet은 검색에 사용된 캐시를 플러시합니다(CLSAgent가 유지 관리하는 캐시 파일이 아님). 캐시를 플러시하면 CLSController에 다음 검색 작업을 위한 새 로그 및 추적 파일 캡처 버퍼가 생성됩니다.
  
중앙 로깅 서비스를 이용하려면 검색할 문제와 관련된 컴퓨터 및 풀 로그에서 추적 메시지만 반환하도록 검색을 구성하는 방법을 잘 이해해야 합니다. issues
  
비즈니스용 Skype 서버 관리 셸을 사용하여 중앙 로깅 서비스 검색 기능을 실행하려면 CsAdministrator 또는 CsServerAdministrator RBAC(역할 기반 액세스 제어) 보안 그룹 또는 이러한 두 그룹 중 하나를 포함하는 사용자 지정 RBAC 역할의 구성원이 되어야 합니다. 직접 만든 사용자 지정 RBAC 역할을 포함하여 이 cmdlet이 할당된 모든 RBAC 역할의 목록을 반환하기 위해 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행합니다.
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

예를 들면 다음과 같습니다.
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

이 항목의 나머지 부분에서는 문제 해결 과정을 최적화하기 위해 검색을 정의하는 방법에 대해 중점적으로 설명합니다.
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>중앙 로깅 서비스를 사용하여 기본 검색을 실행하기 위해

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
2. 배포의 전역 범위에서 AlwaysOn 시나리오가 실행 중인지 확인한 후 명령 프롬프트에 다음을 입력합니다.
    
   ```PowerShell
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> 기본적으로 Search-CsClsLogging은 검색 결과를 콘솔로 보냅니다. 검색 결과를 파일에 저장하려는 경우 -OutputFilePath 를 사용  _\<string fully qualified file path\>_ 합니다. -OutputFilePath 매개 변수를 정의하기 위해 매개 변수의 일부로 경로와 파일 이름을 큰 인용 부호로 묶은 문자열 형식으로 C:\LogFiles\SearchOutput.txt. 이 예제에서는 C:\LogFiles 디렉터리가 있으며 해당 폴더에서 파일 읽기 및 쓰기 권한(수정 NTFS 권한)이 있는지 확인해야 합니다. 출력은 추가되며 기존 로그를 덮어쓰지 않습니다. 별도의 파일이 필요하면 각 검색에 대해 고유한 파일 이름을 정의합니다. 
  
예를 들면 다음과 같습니다.
    
  ```PowerShell
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>중앙 로깅 서비스를 사용하여 풀 또는 컴퓨터에서 기본 검색을 실행하려면

1. 특정 풀 또는 컴퓨터로 검색을 제한하려면 다음과 같이 -Computers 매개 변수를 컴퓨터의 정식 이름에 의해 정의된 컴퓨터와 함께 인용 부호로 묶고 각 묶음으로 구분합니다.
    
   ```PowerShell
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

예를 들면 다음과 같습니다.
    
  ```PowerShell
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. 둘 이상의 컴퓨터를 검색하려면 다음과 같이 여러 컴퓨터 이름을 따옴표로 묶고 쉼표로 구분합니다.
    
   ```PowerShell
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. 단일 컴퓨터 대신 전체 풀을 검색해야 하는 경우 -Computers 매개 변수를 -Pools로 변경하고 컴퓨터 이름을 제거한 다음 각 풀을 따오기 표시를 각 MA로 구분하여 풀 또는 풀로 바꿔야 합니다.
    
    예를 들어 다음과 같은 가치를 제공해야 합니다.
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. 검색 명령을 사용하는 경우 풀은 프런트 엔드 풀, 에지 풀, 영구 채팅 서버 풀 또는 배포에서 풀로 정의된 다른 풀과 같은 배포의 모든 풀이 될 수 있습니다.
    
    예를 들면 다음과 같습니다.
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a>시간 매개 변수를 사용하여 검색을 실행하려면

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
2. 기본적으로 검색의 시간별 매개 변수의 시작 시간은 검색을 시작한 후 5분 전인 25분 전입니다. 즉, 오후 4:00:00에 검색하는 경우 검색 시작 시간은 오후 3시 35분에서 오후 4시 50분까지로 표시됩니다. 현재 시간 60분 또는 3시간 전에 검색해야 하는 경우 -StartTime 매개 변수를 사용하여 날짜 및 시간 문자열을 설정하여 검색을 시작할 시간을 나타냅니다. 
    
    예를 들어 -StartTime 및 -EndTime을 사용하여 시간 및 날짜 범위를 정의하면 풀에서 2012년 11월 20일 오전 8시에서 9시 사이에 검색을 정의할 수 있습니다. 그리고 다음과 같이 결과를 c:\logfile.txt라는 파일에 쓰도록 출력 경로를 설정할 수 있습니다.
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> 지정하는 시간 및 날짜 문자열은 "날짜 시간" 또는 "시간 날짜"일 수 있습니다. " 이 명령은 문자열을 구문 분석하고 날짜 및 시간 및 cmdlet을 실행하는 컴퓨터의 로컬 및 문화권 설정에 적절한 값을 사용합니다. 
  
3. 2012년 11월 20일 오전 11시부터 로그를 검색하려면 -StartTime을 정의합니다. 특정 -EndTime을 정의하지 않는 한 검색의 기본 시간 범위는 30분입니다. 이 경우 수행되는 검색은 정의된 컴퓨터에서 오전 11시에서 11시 30분 사이의 로그를 반환합니다.
    
예를 들면 다음과 같습니다.
    
  ```PowerShell
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. 특정 기간 내에 로그 검색을 수행하려면 -StartTime 및 -EndTime을 정의합니다. edge01.contoso.net 컴퓨터에서 오후 1시~2시 45분의 로그를 검색해야 한다고 가정해 보겠습니다. 
    
예를 들면 다음과 같습니다.
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>다른 조건 및 일치 옵션을 사용하여 고급 검색을 실행하려면

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
2. 명령을 실행하여 특정 구성 요소의 추적을 수집하려면 다음을 입력합니다.
    
   ```PowerShell
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

예를 들면 다음과 같습니다.
    
  ```PowerShell
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

이 경우 실행되는 검색은 배포의 모든 컴퓨터 및 풀에서 지난 30분 동안의 SIPStack, S4 및 UserServices에 대한 추적 구성 요소를 포함하는 모든 로그 항목을 반환합니다.
    
3. 동일한 구성 요소로 검색을 이름 있는 프런트 엔드 풀로만 pool01.contoso.net 입력합니다.
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. 매개 변수가 여러 개인 경우 명령에 사용되는 기본 검색 논리는 정의된 각 매개 변수에 대해 논리 OR을 사용하는 것입니다. **-MatchAll** 매개 변수를 지정하여 이 동작을 변경할 수 있습니다. 이렇게 하려면 다음을 입력합니다.
    
   ```PowerShell
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. AlwaysOn과 같이 시나리오가 지속적으로 실행되도록 설정되어 있거나 장기 실행 시나리오를 정의한 경우에는 로그가 로컬 컴퓨터에서 파일 공유로 이동될 수 있습니다. 이 경우 New-CsClsConfiguration을 사용하여 새 구성을 만들거나 Set-CsClsConfiguration을 사용하여 기존 구성을 수정하는 방법으로 CacheFileNetworkFolder 매개 변수를 사용해 파일 공유를 정의합니다. 검색에서 검색할 로그 모음에 파일 공유를 포함하지 않으려면 다음과 같이 SkipNetworkLogs 매개 변수를 사용합니다.
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>중앙 로깅 서비스에서 캡처 로그 읽기

검색을 실행하고 보고된 문제를 추적하는 데 사용할 수 있는 파일이 있는 경우 중앙 로깅 서비스의 실질적인 이점을 실감할 수 있습니다. 파일을 읽을 수 있는 방법은 여러 가지가 있습니다. 출력 파일이 표준 텍스트 형식이면 Notepad.exe 또는 텍스트 파일을 열고 읽을 수 있는 기타 프로그램을 사용할 수 있습니다. 파일 크기가 크고 더 복잡한 문제의 경우 중앙 로깅 서비스에서 로깅 Snooper.exe 읽고 구문 분석하도록 설계된 도구와 같은 도구를 사용할 수 있습니다. Snooper는 별도의 다운로드로 사용할 수 있는 디버그 도구에 포함되어 있습니다. 여기에서 디버그 도구를 다운로드할 수 [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257) 있습니다. . 디버그 도구를 설치하면 짧은 잘라 내기 및 메뉴 항목이 만들어지지 않습니다. 디버그 도구를 설치한 후 Windows Explorer, 명령줄 창 또는 비즈니스용 Skype 서버 관리 셸을 열고 디렉터리(기본 위치) C:\Program Files\비즈니스용 Skype 서버 2015\Debugging Tools로 이동하십시오. 명령줄을 Snooper.exe 두 번 클릭하거나 Snooper.exe 입력한 다음 명령줄을 사용하는 경우 Enter를 누르거나 관리 비즈니스용 Skype 서버 클릭합니다.
  
> [!IMPORTANT]
> 이 문서에서는 문제 해결 기술에 대해 자세히 설명하거나 논의하지 않습니다. 문제 해결 및 관련 프로세스는 복잡한 주제입니다. 기본 사항 문제 해결 및 특정 작업 문제 해결에 대한 자세한 내용은 Microsoft Lync Server 2010 Resource Kit book()을 [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003) 참조합니다. 프로세스 및 절차는 2015 비즈니스용 Skype 서버 적용됩니다. 
  
### <a name="to-open-a-log-file-in-snooper"></a>Snooper에서 로그 파일을 열려면

1. Snooper를 사용하여 로그 파일을 열려면 로그 파일에 대한 읽기 액세스 권한이 있어야 합니다. Snooper를 사용하여 로그 파일에 액세스하려면 CsAdministrator 또는 CsServerAdministrator RBAC(역할 기반 액세스 제어) 보안 그룹의 구성원이거나 이들 두 그룹 중 하나를 포함하는 사용자 지정 RBAC 역할의 구성원이어야 합니다. 
    
2. 디버깅 도구(LyncDebugTools.msi)를 설치한 후 Snooper.exe 탐색기 또는 명령줄에서 Windows 디렉터리를 변경합니다. 기본적으로 디버깅 도구는 C:\Program Files\비즈니스용 Skype 서버 2015\Debugging Tools에 있습니다. Snooper.exe를 두 번 클릭하거나 실행합니다.
    
3. Snooper가 열리면 **File(파일)** 을 클릭하고 **OpenFile** 을 클릭한 다음 **Open(열기)** 대화 상자에서 로그 파일을 찾아 선택한 후 **Open(열기)** 을 클릭합니다.
    
4. 로그 파일의 추적  메시지가 추적 **탭에** 표시됩니다. 메시지 **탭을 클릭하여** 수집된 추적의 메시지 내용을 볼 수 있습니다.
    
### <a name="to-display-a-call-flow-diagram"></a>통화 흐름 다이어그램을 표시하려면

1. Snooper를 사용하여 로그 파일을 열려면 로그 파일에 대한 읽기 액세스 권한이 있어야 합니다. Snooper를 사용하여 로그 파일에 액세스하려면 CsAdministrator 또는 CsServerAdministrator RBAC(역할 기반 액세스 제어) 보안 그룹의 구성원이거나 이들 두 그룹 중 하나를 포함하는 사용자 지정 RBAC 역할의 구성원이어야 합니다.
    
2. 로그 파일을 열고 **Messages(메시지)** 탭을 클릭한 다음 메시지 보기에서 대화를 선택하거나, **Trace(추적)** 탭에서 추적 구성 요소를 선택합니다.
    
3. **Call Flow(통화 흐름)** 을 클릭합니다.
    
> [!NOTE]
> 통화 흐름에 속하지 않는 메시지나 추적을 클릭하면 다이어그램이 나타나지 않습니다. 그러면 "이 메시지는 통화 흐름에 사용할 수 없습니다."라는 상태 메시지가 Snooper 아래쪽에 표시됩니다. 통화 흐름의 일부인 다른 메시지나 추적을 선택하면 통화 흐름이 나타납니다. 
  
4. 메시지 또는 추적 줄 간을 이동하여 통화 흐름 다이어그램이 새로운 다이어그램을 표시하도록 업데이트 또는 변경되는지 확인합니다.
    
5. 통화 메시지, 끝점, 기타 구성 요소에 대한 정보를 확인하려면 요소 위에 마우스 커서를 놓습니다.
