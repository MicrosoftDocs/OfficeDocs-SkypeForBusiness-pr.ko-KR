---
title: 비즈니스용 Skype 2015의 중앙 로깅 서비스에서 만든 캡처 로그 검색
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: '요약: 비즈니스용 Skype 서버 2015에서 중앙 집중화 된 로깅 서비스 캡처 로그를 검색 하 고 읽는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 81bf539c6a06c52354db23bbeea97fb9525cbbd5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186804"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>비즈니스용 Skype 2015의 중앙 로깅 서비스에서 만든 캡처 로그 검색
 
**요약:** 비즈니스용 Skype 서버 2015에서 중앙 로깅 서비스 캡처 로그를 검색 하 고 읽는 방법에 대해 알아봅니다.
  
중앙 로깅 서비스의 검색 기능은 다음과 같은 이유로 유용 하 고 강력 합니다. 
  
- 검색 및 결과는 정의한 기준에 따라 단일 컴퓨터, 풀, 사이트 또는 전역 범위에서 실행 됩니다.
    
- 검색은 초기에 광범위 하 게 사용할 수 있으며 시간, 구성 요소 또는 컴퓨터와 같은 더 많은 대상 기준으로 축소 됩니다. 동일한 로그를 검색 하는 경우 검색 조건이 변경 되 면 로깅 세션을 다시 실행할 필요가 없습니다.
    
- 검색 결과는 범위 내 모든 컴퓨터와 풀에서 수집 되며 검색 조건의 모든 결과를 나타내는 단일 출력 파일로 수집 되 고 집계 됩니다 (실행 중인 시나리오와 시스템에서 캡처한 데이터에 따라 제한 됨). 시나리오). **Snooper** 또는 **메모장** 등의 익숙한 도구를 사용 하 여 배포에서 출력 파일 및 추적 메시지를 읽을 수 있습니다.
    
각 개별 컴퓨터의 CLSAgent는 시나리오 또는 시나리오를 기반으로 로그를 만듭니다 (컴퓨터당 두 가지 시나리오는 주어진 시간에 실행 될 수 있음). 로그 및 관련 인덱스 및 캐시 파일은 CLSAgent에서 관리 합니다. 검색을 정의 하 고 실행할 때 검색 명령은 검색할 정보에 대해 CLSAgent에 지시 합니다. CLSAgent는 로그 파일, 캐시 파일, 인덱스 파일에 대해 쿼리를 실행 하 고 검색 결과를 CLSContoller에 반환 합니다. CLSController는 검색 범위에 있는 모든 컴퓨터 및 풀에서 검색 결과를 받습니다. 그런 다음 CLSController는 로그를 집계 (결합) 하 고, 오래 된 항목에 먼저 입력 하 고, 최근 항목에 마지막으로 시간을 붙여 넣습니다.
  
각 검색 후에 **동기화-CsClsLogging** cmdlet이 실행 되 고, 검색에 사용 되는 캐시를 플러시합니다 (clsagent에서 유지 관리 하는 캐시 파일과 혼동 하지 않음). 캐시를 플러시하 면 다음 검색 작업을 위해 CLSController에 정리 된 로그 및 추적 파일 캡처 버퍼가 있는지 확인 하는 데 도움이 됩니다.
  
중앙 로깅 서비스의 이점을 최대한 활용 하려면 검색을 구성 하 여 리서치 하려는 문제와 관련 된 컴퓨터 및 풀 로그의 추적 메시지만 반환 하는 방법에 대해 잘 알고 있어야 합니다. 사항
  
비즈니스용 Skype Server Management Shell을 사용 하 여 중앙 집중식 로깅 서비스 검색 기능을 실행 하려면 CsAdministrator 또는 CsServerAdministrator 역할 기반 액세스 제어 (RBAC) 보안 그룹 또는 사용자 지정 RBAC 역할 중 하나의 구성원 이어야 합니다. 이러한 두 그룹 중 하나가 포함 되어 있습니다. 이 cmdlet이 할당 된 모든 RBAC 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 비즈니스용 Skype Server 관리 셸 또는 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

예를 들면 다음과 같습니다.
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

이 항목의 나머지 부분에서는 문제 해결을 최적화 하기 위해 검색을 정의 하는 방법에 대해 중점적으로 설명 합니다.
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>중앙 로깅 서비스를 사용 하 여 기본 검색을 실행 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. 전역 범위에서 배포에 AlwaysOn 시나리오가 실행 되 고 있는지 확인 한 다음 명령 프롬프트에서 다음을 입력 합니다.
    
   ```
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> 기본적으로 검색-CsClsLogging은 검색 결과를 콘솔에 보냅니다. 검색 결과를 파일에 저장 하려는 경우-outputfilepath _ \<문자열 정식 파일 경로\>_ 를 사용 합니다. -OutputFilePath 매개 변수를 정의 하려면 따옴표로 묶인 문자열 형식으로 경로와 파일 이름을 매개 변수의 일부로 제공 합니다 (예: C:\LogFiles\SearchOutput.txt). 이 예제에서는 디렉터리 c 로그 파일이 존재 하 고 폴더에 대 한 읽기 및 쓰기 권한 (NTFS 사용 권한 수정)이 있는지 확인 해야 합니다. 출력이 추가 되 고 덮어쓰여지지 않습니다. 별도의 파일이 필요한 경우 각 검색에 대해 고유한 파일 이름을 정의 합니다. 
  
예를 들면 다음과 같습니다.
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>중앙 로깅 서비스를 사용 하 여 풀이나 컴퓨터에서 기본 검색을 실행 하려면

1. 특정 풀이나 컴퓨터로 검색을 제한 하려면-Computers 매개 변수를 컴퓨터의 정규화 된 이름으로 정의한 컴퓨터와 함께 사용 하 고, 다음과 같이 따옴표로 묶이고 쉼표로 구분 합니다.
    
   ```
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

예를 들면 다음과 같습니다.
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. 두 대 이상의 컴퓨터를 검색 하려면 다음과 같이 따옴표로 묶여 여러 컴퓨터 이름을 입력 하 고 쉼표로 구분 합니다.
    
   ```
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. 단일 컴퓨터 대신 전체 풀을 검색 해야 하는 경우-Computers 매개 변수를-풀링합니다으로 변경 하 고 컴퓨터 이름을 제거한 다음 쉼표로 구분 된 풀 또는 풀로 바꿉니다.
    
    예를 들면 다음과 같습니다.
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. 검색 명령을 사용 하는 경우에는 배포의 풀 (예: 프런트 엔드 풀, Edge 풀, 영구 채팅 서버 풀 등)과 배포에서 풀로 정의 된 사용자 중 풀이 될 수 있습니다.
    
    예를 들면 다음과 같습니다.
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a>시간 매개 변수를 사용 하 여 검색을 실행 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. 기본적으로 검색의 시간 관련 매개 변수에 대 한 시작 시간은 검색 시작 후 5 분 전의 25 분입니다. 즉, 4:00:00 PM에서 검색 하는 경우 검색 시작 시간은 3:35:00 PM으로 4:05:00 PM으로 표시 됩니다. 현재 시간 전에 60 분 또는 3 시간 전에 검색 해야 하는 경우-StartTime 매개 변수를 사용 하 고 날짜 및 시간 문자열을 설정 하 여 검색을 시작할 시간을 표시 합니다. 
    
    예를 들어-StartTime 및-EndTime을 사용 하 여 시간 및 날짜 범위를 정의 하면 풀의 11/20/2012에 오전 8 시와 9 시 사이의 검색을 정의할 수 있습니다. 다음과 같이 c:\logfile.txt 이라는 파일에 결과를 기록 하도록 출력 경로를 설정할 수 있습니다.
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> 지정 하는 시간 및 날짜 문자열은 "날짜 시간" 또는 "시간 날짜" 일 수 있습니다. "명령은 문자열을 구문 분석 하 고, cmdlet을 실행 하는 컴퓨터의 로캘 및 culture 설정 및 날짜 및 시간에 적절 한 값을 사용 합니다. 
  
3. 11:00:00 오전 11/20/2012에 시작 되는 로그를 검색 하려면-StartTime을 정의 합니다. 특정 EndTime을 정의 하지 않는 한 검색의 기본 시간 범위는 30 분입니다. 결과 검색은 정의 된 컴퓨터 또는 풀의 로그를 오전 11:00:00에서 11:30:00 AM으로 반환 합니다.
    
예를 들면 다음과 같습니다.
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. 특정 기간 내에 로그 검색을 수행 하려면-StartTime 및-EndTime을 정의 합니다. 컴퓨터 edge01.contoso.net 1 PM부터 2:45 PM 까지의 로그가 필요 합니다. 
    
예를 들면 다음과 같습니다.
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>다른 조건과 일치 옵션을 사용 하 여 고급 검색을 실행 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. 특정 구성 요소에 대 한 추적을 수집 하는 명령을 실행 하려면 다음을 입력 합니다.
    
   ```
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

예를 들면 다음과 같습니다.
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

결과 검색은 지난 30 분 동안 배포의 모든 컴퓨터와 풀에 대 한 SIPStack, S4 및 UserServices에 대 한 추적 구성 요소가 있는 모든 로그 항목을 반환 합니다.
    
3. Pool01.contoso.net 라는 프런트 엔드 풀에 대해서도 동일한 구성 요소로 검색을 제한 하려면 다음을 입력 합니다.
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. 여러 매개 변수가 있는 명령에 대 한 기본 검색 논리는 정의 된 각 매개 변수와 논리 OR를 사용 하는 것입니다. **-Matchall** 매개 변수를 지정 하 여이 동작을 변경할 수 있습니다. 이렇게 하려면 다음을 입력 합니다.
    
   ```
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. 시나리오가 AlwaysOn과 같이 지속적으로 실행 되도록 설정 되어 있거나 장기 실행 시나리오 로그가 사용자가 로컬 컴퓨터를 파일 공유로 롤백할 수 있습니다. 새 구성을 만들거나 Set-CsClsConfiguration을 사용 하 여 기존 구성을 수정 하기 위해 새로운 CsClsConfiguration을 사용 하 여 CacheFileNetworkFolder 매개 변수를 사용 하 여 파일 공유를 정의 합니다. 검색할 로그 모음에 파일 공유를 포함 하지 않으려면 다음과 같이 SkipNetworkLogs 매개 변수를 사용 합니다.
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>중앙 로깅 서비스에서 캡처 로그 읽기

검색을 실행 한 후 보고 된 문제를 추적 하는 데 사용할 수 있는 파일을가지고 있는 경우 중앙 로깅 서비스의 실질적인 이점을 얻게 됩니다. 파일을 읽을 수 있는 방법에는 여러 가지가 있습니다. 출력 파일은 표준 텍스트 형식으로 되어 있으며, Notepad.exe 또는 텍스트 파일을 열고 읽는 데 사용할 수 있는 다른 프로그램을 사용 하면 됩니다. 대용량 파일과 복잡 한 문제가 발생 하는 경우 중앙 로깅 서비스에서 로깅 출력을 읽고 구문 분석 하도록 디자인 된 Snooper 같은 도구를 사용할 수 있습니다. Snooper는 별도의 다운로드로 제공 되는 디버그 도구에 포함 되어 있습니다. 디버그 도구는 다음과 같이 [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257)다운로드할 수 있습니다. 디버그 도구를 설치 하면 짧은 컷 및 메뉴 항목이 만들어지지 않습니다. 디버그 도구를 설치한 후 Windows 탐색기, 명령줄 창 또는 비즈니스용 Skype Server Management Shell을 열고 Business Server 2015 용 C:\Program Files\Skype 디렉터리 (기본 위치)로 이동 하 여 디버깅 도구를 만듭니다. Snooper를 두 번 클릭 하거나 Snooper를 입력 한 다음 명령줄 또는 비즈니스용 Skype Server Management Shell을 사용 하는 경우 enter 키를 누릅니다.
  
> [!IMPORTANT]
> 이 항목의 목적은 문제 해결 기법을 자세히 설명 하 고 논의 하는 것이 아닙니다. 문제 해결 및 관련 프로세스는 복잡 한 주제입니다. 해결 방법에 대 한 자세한 내용과 특정 작업 부하 문제 해결에 대 한 자세한 내용은의 [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)Microsoft Lync Server 2010 Resource Kit 책을 참조 하세요. 프로세스와 절차는 계속 해 서 비즈니스용 Skype 서버 2015에 적용 됩니다. 
  
### <a name="to-open-a-log-file-in-snooper"></a>Snooper에서 로그 파일을 열려면

1. Snooper를 사용 하 고 로그 파일을 열려면 로그 파일에 대 한 읽기 권한이 필요 합니다. Snooper를 사용 하 고 로그 파일에 액세스 하려면 CsAdministrator의 구성원 이거나,이 두 그룹 중 하나를 포함 하는 CsServerAdministrator 역할 기반 액세스 컨트롤 (RBAC) 보안 그룹 또는 사용자 지정 RBAC 역할 이어야 합니다. 
    
2. 디버깅 도구 (LSnooper Cdebugtools)를 설치한 후 Windows 탐색기 또는 명령줄을 사용 하 여 디렉터리를 위치로 변경 합니다. 기본적으로 디버깅 도구는 Business Server 2015 \ 디버깅 도구에 대 한 C:\Program Files\Skype에 있습니다. Snooper를 두 번 클릭 하거나 실행 합니다.
    
3. Snooper가 열리면 **파일**을 마우스 오른쪽 단추로 클릭 하 고 **OpenFile**을 클릭 하 고 로그 파일을 찾은 다음 **열기** 대화 상자에서 파일을 선택 하 고 **열기**를 클릭 합니다.
    
4. **추적** 탭에 로그 파일의 **추적** 메시지가 표시 됩니다. 수집 된 추적의 메시지 내용을 보려면 **메시지** 탭을 클릭 합니다.
    
### <a name="to-display-a-call-flow-diagram"></a>통화 흐름 다이어그램을 표시 하려면

1. Snooper를 사용 하 고 로그 파일을 열려면 로그 파일에 대 한 읽기 권한이 필요 합니다. Snooper를 사용 하 고 로그 파일에 액세스 하려면 CsAdministrator의 구성원 이거나,이 두 그룹 중 하나를 포함 하는 CsServerAdministrator 역할 기반 액세스 컨트롤 (RBAC) 보안 그룹 또는 사용자 지정 RBAC 역할을 만들어야 합니다.
    
2. 로그 파일을 열고 **메시지** 탭을 클릭 하 고 메시지 보기에서 대화를 선택 하거나 **추적** 탭에서 추적 구성 요소를 선택 합니다.
    
3. **통화 흐름**을 클릭 합니다.
    
> [!NOTE]
> 호출 흐름의 일부가 아닌 메시지 또는 추적을 클릭 하면 다이어그램이 나타나지 않으며 "이 메시지는 callSnooper에 적합 하지 않습니다." 라는 상태 메시지가 표시 됩니다. 다른 메시지 또는 추적을 선택 하면 메시지 또는 추적이 호출 흐름의 일부인 경우 호출 흐름이 표시 됩니다. 
  
4. 메시지 또는 추적 선을 이동 하 고 새 다이어그램을 표시 하기 위해 호출 흐름 다이어그램이 업데이트 또는 변경 되는지 확인 합니다.
    
5. 요소 위에 커서를 올리면 호출 메시지, 끝점 및 기타 구성 요소에 대 한 정보를 얻을 수 있습니다.
