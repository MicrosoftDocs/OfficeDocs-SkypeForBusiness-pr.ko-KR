---
title: 'Lync Server 2013: 모니터링 보고서와 미러 데이터베이스 연결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82d1ec6b1256326cca9e74d47d27820529050721
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a>Lync Server 2013에서 모니터링 보고서와 미러 데이터베이스 연결

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-07_

모니터링 데이터베이스에 대 한 미러를 구성 하는 경우 장애 조치 (failover)가 발생 하는 경우 미러 데이터베이스가 기본 데이터베이스로 사용 됩니다. 그러나 Lync Server 모니터링 보고서를 사용 하는 경우 장애 조치 (failover)가 수행 되는 경우 모니터링 보고서가 미러 데이터베이스에 연결 되어 있지 않을 수 있습니다. 모니터링 보고서를 설치할 때 기본 데이터베이스의 위치만 지정 하기 때문입니다. 미러 데이터베이스의 위치를 지정 하지 않습니다.

모니터링 보고서에서 미러 데이터베이스에 대해 자동으로 장애 조치 (failover)를 수행 하려면 모니터링 보고서에 사용 되는 두 데이터베이스, 즉 통화 정보 레코드 데이터에 대 한 데이터베이스 한 개와 다음 품질을 위해 미러 데이터베이스를 "장애 조치 (failover) 파트너"로 추가 해야 합니다. Experience (QoE) 데이터). 이 단계는 모니터링 보고서를 설치한 후에 수행 해야 합니다. 이러한 두 데이터베이스에서 사용 하는 연결 문자열 값을 수동으로 편집 하 여 장애 조치 (failover) 파트너 정보를 추가할 수 있습니다. 이렇게 하려면 다음 절차를 완료합니다.

1.  Internet Explorer를 사용 하 여 **SQL Server Reporting Services** 홈 페이지를 엽니다. Reporting Services 홈 페이지 URL에는 다음이 포함 됩니다.
    
      - **Http:** 접두사입니다.
    
      - Reporting Services가 설치 된 컴퓨터의 FQDN (정규화 된 도메인 이름) (예: **atl-sql-001.litwareinc.com**)입니다.
    
      - 문자열 **/보고서\_**
    
      - 모니터링 보고서가 설치 되는 데이터베이스 인스턴스의 이름 (예: **은**)입니다.
    
    예를 들어 SQL Server Reporting Services가 컴퓨터 atl-sql-001.litwareinc.com에 설치 되어 있고 모니터링 보고서에 데이터베이스 인스턴스은가 사용 되는 경우 홈 페이지 URL은 다음과 같습니다.
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  Reporting Services 홈 페이지에 액세스 한 후에는 **Lyncserverreports**를 클릭 한 다음 **보고서\_콘텐츠**를 클릭 합니다. 그러면 Lync Server 모니터링 보고서에 대 한 **보고서\_콘텐츠** 페이지로 이동 됩니다.

3.  **보고서\_콘텐츠** 페이지에서 **cdrdb** 데이터 원본을 클릭 합니다.

4.  **Cdrdb** 페이지의 **속성** 탭에서 **연결 문자열**이라는 텍스트 상자를 찾습니다. 현재 연결 문자열은 다음과 같습니다.
    
    **데이터 원본 = (로컬)\\은, 초기 카탈로그 = LcsCDR**

5.  미러 데이터베이스에 대 한 서버 이름 및 데이터베이스 인스턴스를 포함 하도록 연결 문자열을 편집 합니다. 예를 들어 서버 이름이 s s s-a s s-a s s-001이 고 미러 데이터베이스가은 인스턴스에 있는 경우 다음 구문을 사용 하 여 미러 데이터베이스를 지정 하려면 추가 해야 합니다.
    
    **장애 조치 (Failover) 파트너 = a\\-미러-001은**
    
    편집한 연결 문자열은 다음과 같습니다.
    
    **데이터 원본 = (로컬)\\은; 장애 조치 (Failover) 파트너 = a\\-mirror-001은; 초기 카탈로그 = LcsCDR**

6.  연결 문자열을 업데이트 한 후 **적용**을 클릭 합니다.

7.  **Cdrdb** 페이지에서 **\_콘텐츠 보고서** 링크를 클릭 합니다. **Qmsdb** 데이터 원본을 클릭 하 고 QoE 데이터베이스에 대 한 연결 문자열을 편집 합니다. 예:
    
    **데이터 원본 = (로컬)\\은; 장애 조치 (Failover) 파트너 = a\\-mirror-001은; 초기 카탈로그 = QoEMetrics**

8.  **적용**을 클릭합니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013 모니터링 보고서 설치](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[Lync Server 2013에서 모니터링 보고서 사용](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

