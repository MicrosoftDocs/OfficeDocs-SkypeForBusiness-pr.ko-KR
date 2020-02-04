---
title: 중앙 로깅 서비스 구성 설정 이해
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
ms.openlocfilehash: a766756f082e6666d37dff793c457cb335736fe0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Lync Server 2013의 중앙 로깅 서비스 구성 설정 이해

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

중앙 로깅 서비스는 로깅 서비스를 수집 하는 방법, 수집 하는 방법, 수집 하는 위치, 로그 설정에 대해 정의 하도록 구성 됩니다. 이러한 설정은 전체적으로 (즉, 전체 배포의 경우) 또는 사이트 (즉, 배포의 명명 된 사이트)에 정의 합니다. 정의한 모든 로깅은 로그 시작, 중지, 플러시, 검색 명령에 사용 하는 id에 적합 한 설정을 사용 합니다.

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a>현재 중앙 집중화 된 로깅 서비스 구성을 표시 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  명령줄 프롬프트에 다음을 입력 합니다.
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > "Site: Redmond"와 같이 정의 <CODE>-Identity</CODE> 및 범위를 통해 반환 되는 구성 설정의 범위를 좁히거나 확장 하 여 사이트 Redmond에 대 한 CsClsConfiguration만 반환할 수 있습니다. 구성의 지정 된 부분에 대 한 세부 정보를 원하는 경우 다른 Windows PowerShell cmdlet에 출력을 파이프 할 수 있습니다. 예를 들어 "Redmond" 사이트의 구성에 정의 된 시나리오에 대 한 세부 정보를 보려면 다음을 입력 합니다.<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE>

    
    </div>
    
    ![Get-CsClsConfiguration의 샘플 출력.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Get-CsClsConfiguration의 샘플 출력.")
    
    Cmdlet의 결과에는 중앙 로깅 서비스의 현재 구성이 표시 됩니다.
    
    
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
    <td><p><strong>Identity</strong></p></td>
    <td><p>이 구성의 범위 및 이름을 식별 합니다. 글로벌 구성은 한 개, 사이트별 구성은 하나만 있습니다.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>시나리오</strong></p></td>
    <td><p>이 구성에 대해 정의 된 모든 시나리오의 목록입니다.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>SearchTerms</strong></p></td>
    <td><p>구성에 대 한 정의 된 검색 용어입니다. Office 365, 온-프레미스 배포가 아닙니다.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>SecurityGroups</strong></p></td>
    <td><p>사용자 (즉, 보안 그룹의 구성원)를 제어 하는 정의 된 보안 그룹은 자신이 위치한 사이트를 기반으로 하는 컴퓨터를 볼 수 있습니다. 이 컨텍스트에서 사이트는 토폴로지 작성기에 정의 된 사이트입니다.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>영역과</strong></p></td>
    <td><p>정의 된 지역은 지역 (예: EMEA)에 SecurityGroups를 수집 하는 데 사용 됩니다.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileFolder</strong></p></td>
    <td><p>컴퓨터에서 로그 파일이 기록 되는 위치의 정의 된 경로입니다. CLSAgent는 로그 파일을 기록 하 고 네트워크 서비스의 컨텍스트에서 실행 됩니다. 이 경우에 는% TEMP% 를%WINDIR%\ServiceProfiles\NetworkService\AppData\Local로 확장 합니다.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>EtlFileRolloverSizeMB</strong></p></td>
    <td><p>매개 변수는 새 이벤트 추적 로그 (.etl) 파일이 만들어지기 전에 로그 파일의 최대 크기를 나타냅니다. EtlFileRolloverMinutes에 설정 된 최대 시간이 아직 도달 하지 않은 경우에도 정의 된 크기에 도달 하면 새 로그 파일이 만들어집니다.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileRolloverMinutes</strong></p></td>
    <td><p>새 .etl 파일을 만들기 전에 로그가 대기할 수 있는 최대 시간 (분)을 정의 합니다. EtlFileRolloverSizeMB에 설정 된 최대 크기에 도달 하지 않은 경우에도 타이머가 만료 될 때 새 로그 파일이 만들어집니다.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>TmfFileSearchPath</strong></p></td>
    <td><p>추적 메시지 형식 파일을 검색 하는 위치입니다. 추적 메시지 형식 파일은 이진 파일을 사람이 읽을 수 있는 형식으로 변환 하는 데 사용 됩니다.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalFolders</strong></p></td>
    <td><p>컴퓨터에 캐시 파일이 기록 되는 위치에 대 한 정의 된 경로입니다. CLSAgent는 캐시 파일을 기록 하 고 네트워크 서비스의 컨텍스트에서 실행 됩니다. 이 경우에 는% TEMP% 를%WINDIR%\ServiceProfiles\NetworkService\AppData\Local.로 확장 합니다. 기본적으로 캐시 파일 및 로그 파일은 동일한 디렉터리에 기록 됩니다.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileNetworkFolder</strong></p></td>
    <td><p>로깅 작업 중 캐시 파일을 받을 UNC (범용 명명 규칙) 경로를 정의할 수 있습니다.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Cachefilelocal보존 기간</strong></p></td>
    <td><p>캐시 파일이 유지 되는 최대 시간 (일)으로 정의 됩니다.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileMaxDiskUsage</strong></p></td>
    <td><p>캐시 파일에서 사용할 수 있는 디스크 공간의 백분율로 정의 됩니다.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ComponentThrottleLimit</strong></p></td>
    <td><p>자동 스로틀 limiter 트리거되기 전에 구성 요소가 생성할 수 있는 초당 최대 추적 수로 정의 됩니다.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ComponentThrottleSample</strong></p></td>
    <td><p>ComponentThrottleLimit를 초과할 수 있는 60 초의 시간 수입니다.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>이상 Clsagentserviceversion</strong></p></td>
    <td><p>실행할 수 있는 CLSAgent의 최소 버전입니다. 이 요소는 Office 365를 대상으로 합니다.</p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 중앙 집중화 된 로깅 서비스 개요](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))  
[-CsClsConfiguration 제거](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

