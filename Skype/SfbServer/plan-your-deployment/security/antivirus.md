---
title: 비즈니스용 Skype 서버에 대한 바이러스 백신 검사 제외
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: 비즈니스용 Skype 서버와의 바이러스 백신 스캐너 상호 작동 개요.
ms.openlocfilehash: b59a5c474a96d312ebe3a648536ebe827e684931
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832268"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대한 바이러스 백신 검사 제외

비즈니스용 Skype 서버와의 바이러스 백신 스캐너 상호 작동 개요.

바이러스 백신 스캐너가 비즈니스용 Skype 서버의 작동을 방해하지 않도록 하기 위해 바이러스 백신 스캐너를 실행한 각 비즈니스용 Skype 서버 서버 또는 서버 역할에 대한 특정 프로세스 및 Directories를 제외해야 합니다. 다음과 같은 프로세스 및 디렉터리를 제외해야 합니다.

> [!NOTE]
> 아래에 나열된 폴더 및 파일 위치는 비즈니스용 Skype 서버의 기본 위치입니다. 기본값을 그대로 사용하지 않은 위치의 경우 이 항목에 지정된 기본 위치 대신 조직에서 사용자가 지정한 위치를 제외하십시오.

> [!IMPORTANT]
> 일부 바이러스 백신 프로그램은 제외 목록에 상대 경로가 아닌 절대 경로가 필요할 수 있습니다.

- 비즈니스용 Skype 서버 프로세스:

  - ABServer.exe

  - ASMCUSvc.exe

  - AVMCUSvc.exe

  - ChannelService.exe

  - ClsAgent.exe

  - ComplianceService.exe

  - DataMCUSvc.exe

  - DataProxy.exe

  - FileTransferAgent.exe

  - HealthAgent.exe

  - IMMCUSvc.exe
  
  - LyncBackupService.exe

  - LysSvc.exe

  - MasterReplicatorAgent.exe

  - MediaRelaySvc.exe

  - MediationServerSvc.exe

  - MRASSvc.exe

  - OcsAppServerHost.exe

  - ReplicaReplicatorAgent.exe

  - ReplicationApp.exe

  - RtcHost.exe

  - RTCSrv.exe

  - XmppProxy.exe

  - XmppTGW.exe

- Windows Fabric 호스트 서비스 프로세스:

  - Fabric.exe

  - FabricDCA.exe

  - FabricHost.exe

- IIS 프로세스:

  - %systemroot%\system32\inetsrv\w3wp.exe

  - %systemroot%\SysWOW64\inetsrv\w3wp.exe

- SQL Server Back-End 프로세스:

    > [!NOTE]
    > 이러한 경로는 특정 버전과 SQL Server 있습니다.

  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe

  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe

- SQL Server Front-End 프로세스:

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe

  - Standard Edition 설치 RTC 인스턴스

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe

- 디렉터리 및 파일:

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > 이러한 경로는 비즈니스용 Skype 서버 버전과 관련이 있습니다.

  - %programfiles%\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - 파일 공유 저장소(토폴로지 작성기에서 지정). 파일 저장소는 토폴로지 작성기에서 지정됩니다.

  - 백 엔드 데이터베이스, 사용자 저장소, 보관 저장소, 모니터링 저장소 및 응용 프로그램 저장소에 대한 항목을 포함하는 SQL Server 데이터 및 로그 파일. 데이터베이스 및 로그 파일은 토폴로지 작성기에서 지정할 수 있습니다. 기본 이름을 포함하여 각 데이터베이스의 데이터 및 로그 파일에 대한 자세한 내용은 배포 설명서의 [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)를 참조하십시오.

  - SQL Server 데이터베이스, 비즈니스용 Skype 저장소 및 RtcDatabase 저장소를 비롯한 데이터 및 로그 파일을 저장할 수 있습니다. 일반적으로 %localdrive%\CSData 아래에 있습니다.


