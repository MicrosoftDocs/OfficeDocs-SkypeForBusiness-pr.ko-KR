---
title: 'Lync Server 2013: 바이러스 백신 검사 제외'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6f354b93bf21f054e9b5b24e3befd1787279bbe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>Lync Server 2013을 위한 바이러스 백신 검사 제외

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2015-11-02_

바이러스 백신 스캐너가 Lync Server 2013의 작동을 방해 하지 않도록 하려면 바이러스 검사 프로그램을 실행 하는 각 Lync Server 2013 서버 또는 서버 역할에 대해 특정 프로세스 및 디렉터리를 제외 해야 합니다. 다음 프로세스 및 디렉터리는 제외 해야 합니다.

<div>


> [!NOTE]  
> 아래 나열 된 폴더 및 파일 위치는 Lync Server 2013의 기본 위치입니다. 기본값을 사용 하지 않은 위치의 경우이 항목에 지정 된 기본 위치 대신 조직에 대해 지정한 위치를 제외 합니다.



</div>

<div>


> [!IMPORTANT]  
> 일부 바이러스 백신 프로그램에는 제외 목록에 대 한 상대 경로가 아닌 절대적인 필요이 있을 수 있다는 점에 유의 하세요.



</div>

  - Lync Server 2013 프로세스:
    
      - ABServer .exe
    
      - AcpMcuSvc .exe
    
      - ASMCUSvc .exe
    
      - AVMCUSvc .exe
    
      - ChannelService .exe
    
      - ClsAgent .exe
    
      - ComplianceService
    
      - DataMCUSvc
    
      - DataProxy
    
      - FileTransferAgent
    
      - IMMCUSvc .exe
    
      - LysSvc
    
      - MasterReplicatorAgent
    
      - MediaRelaySvc
    
      - MediationServerSvc
    
      - MRASSvc
    
      - OcsAppServerHost
    
      - ReplicaReplicatorAgent
    
      - ReplicationApp
    
      - RtcHost
    
      - RTCSrv
    
      - XmppProxy
    
      - XmppTGW

  - Windows Fabric Host 서비스 프로세스:
    
      - Printbrm.exe
    
      - FabricDCA
    
      - FabricHost

  - IIS 프로세스:
    
      - % systemroot%\\system32\\inetsrv\\w3wp
    
      - % systemroot%\\SysWOW64\\inetsrv\\w3wp

  - SQL Server 백 엔드 프로세스:
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. MSSQLSERVER\\MSSQL\\Binn\\sqlservr.exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSRS11. MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSAS11. MSSQLSERVER\\OLAP\\Bin\\MSMDSrv

  - SQL Server 프런트 엔드 프로세스:
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. L CLOCAL\\MSSQL\\Binn\\sqlservr.exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. RTCLOCAL\\MSSQL\\Binn\\sqlservr.exe

  - 디렉터리 및 파일:
    
      - % systemroot%\\System32\\로그 파일이 있습니다.
    
      - % systemroot%\\SysWow64\\로그 파일이 있습니다.
    
      - % systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL
    
      - % programfiles%\\Microsoft Lync Server 2013
    
      - % programfiles%\\공용 파일\\Microsoft Lync Server 2013\\감시자 노드
    
      - % programfiles%\\공용 파일\\Microsoft Lync Server 2013
    
      - %\\RtcReplicaRoot%
    
      - 파일 공유 저장소 (토폴로지 작성기에서 지정) 파일 저장소는 토폴로지 작성기에 지정 되어 있습니다.
    
      - 백 엔드 데이터베이스, 사용자 저장소, 보관 저장소, 모니터링 저장소 및 응용 프로그램 저장소를 포함 하는 SQL Server 데이터 및 로그 파일 토폴로지 작성기에서 데이터베이스 및 로그 파일을 지정할 수 있습니다. 기본 이름을 포함 하 여 각 데이터베이스의 데이터 및 로그 파일에 대 한 자세한 내용은 배포 설명서의 [Lync server 2013에 대 한 SQL Server 데이터 및 로그 파일 배치](lync-server-2013-sql-server-data-and-log-file-placement.md) 를 참조 하세요.
    
      - 프런트 엔드 데이터베이스, Lync 스토어, RtcDatabase 저장소 등의 SQL Server 데이터 및 로그 파일 일반적 으로% localdrive%\\csdata 아래에 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

