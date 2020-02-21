---
title: 중앙화 된 로깅 서비스 구성 설정 이해
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b326f7ee869b060a423696817c21d7cb763bb0a2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Lync Server 2013의 중앙 로깅 서비스 구성 설정 이해

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

중앙 로깅 서비스는 로깅 서비스에서 수집할 대상, 수집 방법, 수집 되는 위치 및 로그 설정에 따라 정의 하도록 구성 됩니다. 이러한 설정은 전역으로 (즉, 전체 배포의 경우) 또는 사이트 (즉, 배포의 명명 된 사이트)에 정의 됩니다. 사용자가 정의하는 모든 로깅에는 로그를 시작, 중지, 플러시 및 검색하기 위한 명령에 사용하는 identity에 적합한 설정이 사용됩니다.

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a>현재 중앙화 된 로깅 서비스 구성을 표시 하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  명령줄 프롬프트에 다음을 입력합니다.
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > "Site: Redmond"와 같이 정의 <CODE>-Identity</CODE> 및 범위로 반환 되는 구성 설정의 범위를 좁히거나 확장 하 여 사이트 Redmond에 대 한 CsClsConfiguration만 반환할 수 있습니다. 구성의 지정 된 부분에 대 한 세부 정보를 원하는 경우 다른 Windows PowerShell cmdlet에 출력을 파이프 할 수 있습니다. 예를 들어 "Redmond" 사이트의 구성에 정의 된 시나리오에 대 한 세부 정보를 보려면 다음을 입력 합니다.<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE>

    
    </div>
    
    ![Get CsClsConfiguration의 예제 출력입니다.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get CsClsConfiguration의 예제 출력입니다.")
    
    이 cmdlet의 결과에는 중앙화 된 로깅 서비스의 현재 구성이 표시 됩니다.
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>구성 설정</th>
    <th>설명</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>ID</strong></p></td>
    <td><p>이 구성의 범위 및 이름을 식별합니다. 전역 구성 한 개와 사이트당 한 개의 구성만 있습니다.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>시나리오</strong></p></td>
    <td><p>이 구성에 대해 정의된 모든 시나리오를 나열합니다.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>SearchTerms</strong></p></td>
    <td><p>구성에 대해 정의된 검색어입니다. Office 365, 온-프레미스 배포를 지원 하지 않습니다.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>SecurityGroups</strong></p></td>
    <td><p>사용자가 위치한 사이트를 기반으로 컴퓨터를 볼 수 있는 사용자(즉, 보안 그룹의 구성원)를 제어하는 정의된 보안 그룹입니다. 이 컨텍스트에서 사이트는 토폴로지 작성기에 정의 된 사이트입니다.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>일치</strong></p></td>
    <td><p>정의된 지역은 특정 지역(예: EMEA)에서 SecurityGroups를 수집하는 데 사용됩니다.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileFolder</strong></p></td>
    <td><p>컴퓨터에서 로그 파일을 기록할 위치에 대해 정의된 경로입니다. CLSAgent는 네트워크 서비스의 컨텍스트에 따라 로그 파일을 기록하고 실행됩니다. 여기에서 %TEMP%는 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local로 확장됩니다.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>EtlFileRolloverSizeMB</strong></p></td>
    <td><p>이 매개 변수는 새 이벤트 추적 로그(.etl) 파일을 만들기 전 로그 파일의 최대 크기를 나타냅니다. EtlFileRolloverMinutes에 설정된 최대 시간에 아직 도달하지 않았어도 정의된 크기에 도달하면 새 로그 파일이 만들어집니다.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileRolloverMinutes</strong></p></td>
    <td><p>새 .etl 파일을 만들기 전에 로그에서 경과될 수 있도록 정의된 최대 시간(분)입니다. 할 수 있도록 EtlFileRolloverSizeMB에 설정된 최대 크기에 아직 도달하지 않았어도 타이머 시간이 초과되면 새 로그 파일이 만들어집니다.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>TmfFileSearchPath</strong></p></td>
    <td><p>추적 메시지 형식 파일을 검색할 위치입니다. 추적 메시지 형식 파일은 바이너리 파일을 사람이 읽을 수 있는 형식으로 변환하는 데 사용됩니다.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Cachefilelocalfolders 경로가</strong></p></td>
    <td><p>컴퓨터에서 캐시 파일을 기록할 위치에 대해 정의된 경로입니다. CLSAgent는 네트워크 서비스의 컨텍스트에 따라 캐시 파일을 기록하고 실행됩니다. 여기서 %TEMP%는 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local로 확장됩니다. 기본적으로 캐시 파일과 로그 파일은 동일한 디렉터리에 기록됩니다.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileNetworkFolder</strong></p></td>
    <td><p>로깅 작업 중 캐시 파일을 수신하기 위한 UNC(범용 명명 규칙) 경로를 정의할 수 있습니다.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Cachefilelocal보존 기간</strong></p></td>
    <td><p>캐시 파일을 보존할 수 있는 최대 시간(일)으로 정의됩니다.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileMaxDiskUsage</strong></p></td>
    <td><p>캐시 파일이 사용할 수 있는 디스크 공간 비율로 정의됩니다.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ComponentThrottleLimit</strong></p></td>
    <td><p>자동 스로틀 리미터가 트리거되기 전 구성 요소가 생성할 수 있는 초당 최대 추적 수로 정의됩니다.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ComponentThrottleSample</strong></p></td>
    <td><p>ComponentThrottleLimit를 초과할 수 있는 횟수(60초 이내)입니다.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>이상 Clsagentserviceversion</strong></p></td>
    <td><p>실행할 수 있는 CLSAgent의 최소 버전입니다. 이 요소는 Office 365을 위한 것입니다.</p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 중앙 로깅 서비스 개요](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[설정-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))  
[제거-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))  
[신규-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

