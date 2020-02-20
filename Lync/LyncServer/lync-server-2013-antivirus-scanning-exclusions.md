---
title: 'Lync Server 2013: 바이러스 백신 검사 제외'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3a67d7777017c004b0cfcc59a46cd27baf5c209
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>Lync Server 2013에 대 한 바이러스 백신 검사 제외

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-11-02_

바이러스 백신 스캐너가 Lync Server 2013의 작업을 방해 하지 않도록 하려면 바이러스 검사 프로그램을 실행 하는 각 Lync Server 2013 서버 또는 서버 역할에 대해 특정 프로세스 및 디렉터리를 제외 해야 합니다. 다음과 같은 프로세스 및 디렉터리를 제외해야 합니다.

<div>


> [!NOTE]  
> 아래에 나열 된 폴더 및 파일 위치는 Lync Server 2013의 기본 위치입니다. 기본값을 그대로 사용하지 않은 위치의 경우 이 항목에 지정된 기본 위치 대신 조직에서 사용자가 지정한 위치를 제외하십시오.



</div>

<div>


> [!IMPORTANT]  
> 일부 바이러스 백신 프로그램은 제외 목록에 대 한 절대 상대 경로가 필요 하지 않을 수 있습니다.



</div>

  - Lync Server 2013 프로세스:
    
      - ABServer .exe
    
      - AcpMcuSvc
    
      - ASMCUSvc
    
      - AVMCUSvc
    
      - ChannelService
    
      - ClsAgent
    
      - ComplianceService
    
      - DataMCUSvc
    
      - DataProxy
    
      - FileTransferAgent
    
      - IMMCUSvc
    
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

  - Windows Fabric 호스트 서비스 프로세스:
    
      - Printbrm.exe
    
      - FabricDCA
    
      - FabricHost

  - IIS 프로세스:
    
      - % systemroot%\\system32\\inetsrv\\.
    
      - % systemroot%\\SysWOW64\\inetsrv\\w3wp

  - SQL Server 백 엔드 프로세스:
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. MSSQLSERVER\\MSSQL\\Binn\\sqlservr.exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSRS11. MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSAS11. MSSQLSERVER\\OLAP\\Bin\\msmdsrv.ini

  - SQL Server 프런트 엔드 프로세스:
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. LYNCLOCAL\\MSSQL\\Binn\\sqlservr.exe
    
      - % ProgramFiles%\\Microsoft SQL Server\\MSSQL11. RTCLOCAL\\MSSQL\\Binn\\sqlservr.exe

  - 디렉터리 및 파일:
    
      - % systemroot%\\System32\\LogFiles
    
      - % systemroot%\\SysWow64\\LogFiles
    
      - % systemroot%\\Microsoft.NET\\어셈블리\\GAC\_MSIL
    
      - % programfiles%\\Microsoft Lync Server 2013
    
      - % programfiles%\\Common Files\\Microsoft Lync Server 2013\\감시자 노드
    
      - % programfiles%\\Common Files\\Microsoft Lync Server 2013
    
      - %\\RtcReplicaRoot (%)
    
      - 파일 공유 저장소(토폴로지 작성기에서 지정). 파일 저장소는 토폴로지 작성기에서 지정됩니다.
    
      - 백 엔드 데이터베이스, 사용자 저장소, 보관 저장소, 모니터링 저장소 및 응용 프로그램 저장소에 대한 항목을 포함하는 SQL Server 데이터 및 로그 파일. 데이터베이스 및 로그 파일은 토폴로지 작성기에서 지정할 수 있습니다. 기본 이름을 비롯 하 여 각 데이터베이스의 데이터 및 로그 파일에 대 한 자세한 내용은 배포 설명서에서 [SQL Server 데이터 및 Lync Server 2013에 대 한 로그 파일 배치](lync-server-2013-sql-server-data-and-log-file-placement.md) 를 참조 하십시오.
    
      - SQL Server 데이터 및 로그 파일 (프런트 엔드 데이터베이스, Lync store 및 RtcDatabase 저장소 포함) 일반적 으로% localdrive%\\csdata에 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

