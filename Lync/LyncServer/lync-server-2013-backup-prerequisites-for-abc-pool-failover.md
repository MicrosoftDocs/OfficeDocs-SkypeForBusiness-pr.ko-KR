---
title: 'Lync Server 2013: ABC 풀 장애 조치 (failover)를 위한 백업 필수 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0607a0ddc2a1b2a8249135fa1256f2cb706a250a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527035"
---
# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a>Lync Server 2013의 ABC 풀 장애 조치 (failover)를 위한 백업 필수 구성 요소

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-26_

ABC 풀 장애 조치 (failover) 절차를 사용 하 여 최대한의 이점을 얻으려면 재해 및 장애 조치 (failover)가 발생 하기 전에 특정 백업을 수행 해야 합니다.

  - **Export-cslisconfiguration** cmdlet을 사용 하 여 LIS (위치 정보 서비스) 구성 데이터를 풀 A에서 정기적으로 백업 해야 합니다.
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - **Export-csrgsconfiguration** cmdlet을 사용 하 여 풀 A의 응답 그룹 구성 데이터를 정기적으로 백업 해야 합니다.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    일반적으로는 일별 백업을 수행하는 것이 좋지만 변경 내용이 많은 경우에는 백업을 더 자주 수행하도록 예약할 수 있습니다. 재해 발생 시 손실 될 수 있는 정보의 양은 백업 빈도, 변경 빈도 및 볼륨에 따라 달라 집니다.
    
    응답 그룹 응용 프로그램은 풀 당 하나의 응용 프로그램 수준 설정 집합만 저장할 수 있습니다. 이러한 설정은 **export-csrgsconfiguration** cmdlet을 통해 액세스할 수 있습니다. 이 설정에는 기본 음악 연결 구성, 기본 음악 대기 오디오 파일, 에이전트 링 후면 유예 기간 및 통화 컨텍스트 구성이 포함 됩니다. 이러한 설정은 **ReplaceExistingSettings** 매개 변수를 사용 하 여 **export-csrgsconfiguration** cmdlet을 통해 풀 간에 전송 될 수 있지만이 작업은 대상 풀의 모든 응용 프로그램 수준 설정을 재정의 합니다.
    
    <div>
    

    > [!TIP]  
    > 별도의 위치에서 응답 그룹 응용 프로그램을 구성 하는 데 사용 된 모든 원본 오디오 파일의 백업 복사본을 보관 합니다 (즉, 모든 레코딩 또는 음악-보류 파일).

    
    </div>
    
    풀의 통화 대기에 대해 업로드 된 사용자 지정 음악 보존 파일이 있는 경우 해당 파일의 복사본을 다른 위치에 보관 해야 합니다. 이러한 파일은 Lync Server 2013 재해 복구 프로세스의 일부로 백업 되지 않으며, 풀에 업로드 된 파일이 손상 되거나 손상 되거나 지워진 경우 손실 됩니다.
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > 통화 대기 응용 프로그램은 풀 당 하나의 설정 및 사용자 지정 된 음악 대기 오디오 파일을 저장할 수 있습니다. 이러한 설정은 <STRONG>new-cscpsconfiguration</STRONG> cmdlet을 통해 액세스할 수 있습니다. 통화 대기에 대 한 재해 복구 메커니즘은 백업 풀의 통화 대기 응용 프로그램에 의존 하므로 재해 발생 시 기본 풀의 설정이 백업 되거나 보존 되지 않습니다. 기본 풀이 손실 되 면 이러한 설정을 복구할 수 없으며, 새 풀을 배포 하 여 기본 풀을 교체 하는 경우 통화 대기 설정 및 사용자 지정 된 모든 음악 연결 된 오디오 파일을 다시 구성 해야 합니다.

    
    </div>

  - 지정 되지 않은 번호 음성 기능의 일부로 알림을 구성 하는 경우 초기 구성 중에 사용 되는 원본 오디오 파일의 복사본을 다른 위치에 보관 하는 것이 좋습니다. 이 작업을 수행 하지 않은 경우에는 오디오 파일을 가져온 서버나 풀의 파일 저장소에 구성 된 오디오 파일의 복사본을 가져올 수 있습니다. 이러한 파일은 Lync Server 2013 재해 복구 프로세스의 일부로 백업 되지 않으며, 풀에 업로드 된 파일이 손상 되거나 손상 되거나 지워진 경우 손실 됩니다. 서버 또는 풀의 파일 저장소에서 지정 되지 않은 번호 음성 기능을 구성 하는 데 사용 되는 모든 오디오 파일을 복사 하려면 다음을 사용 하십시오.
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - 풀에 데이터베이스 모니터링 및 보관이 있는 경우 SQL Server 관리 도구를 사용 하 여 백업 해야 합니다. ABC 장애 조치 (failover) 절차에서 모니터링 및 보관 데이터베이스는 Lync Server 백업 서비스를 통해 백업 되지 않으므로 풀 A에 배치 된 경우 보존 되지 않습니다.

</div>

<span> </span>

</div>

</div>

</div>

