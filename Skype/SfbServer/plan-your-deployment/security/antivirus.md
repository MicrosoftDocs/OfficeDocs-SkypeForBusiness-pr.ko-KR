---
title: 비즈니스용 Skype 서버에 대 한 바이러스 백신 검색 제외
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: 비즈니스용 Skype 서버와의 바이러스 검사 프로그램 상호 운용을 간략하게 설명 합니다.
ms.openlocfilehash: 9ec13b31328744bb154c9eb5e09dff7665c4b540
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196843"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 바이러스 백신 검색 제외

비즈니스용 Skype 서버와의 바이러스 검사 프로그램 상호 운용을 간략하게 설명 합니다.

이 문서에는 Active Directory 도메인에서 바이러스 백신 소프트웨어를 사용 하는 경우 지원 되는 버전의 Microsoft Windows를 실행 하는 컴퓨터에서 발생 가능한 불안정성의 원인을 확인 하는 데 도움이 되는 권장 사항이 포함 되어 있습니다. 환경 또는 관리 비즈니스 환경

시스템을 평가 하기 위해 이러한 절차를 일시적으로 적용 하는 것이 좋습니다. 이 문서의 권장 사항에 따라 시스템 성능 또는 안정성이 향상 되는 경우 바이러스 백신 소프트웨어 공급 업체에 문의 하 여 지침을 참조 하거나 바이러스 백신 소프트웨어의 업데이트 된 버전을 제공 합니다.

이 문서에는 보안 설정을 낮추거나 컴퓨터에서 보안 기능을 일시적으로 해제 하는 방법을 보여 주는 정보가 포함 되어 있습니다. 특정 문제의 특성을 이해 하기 위해 이러한 변경 내용을 적용할 수 있습니다. 이러한 변경 작업을 수행 하기 전에 특정 환경에서이 해결 방법을 구현 하는 것과 관련 된 위험을 평가 하는 것이 좋습니다. 이 해결 방법을 구현 하는 경우 바이러스 백신 소프트웨어로 더 이상 검색 하지 않는 파일에 대해 컴퓨터를 보호 하는 적절 한 추가 단계를 수행 합니다.

바이러스 백신 스캐너가 비즈니스용 Skype 서버의 작동을 방해 하지 않도록 하려면 바이러스 검사 프로그램을 실행 하는 각 비즈니스용 Skype Server server 또는 서버 역할에 대 한 특정 프로세스 및 디렉터리를 제외 해야 합니다. 다음 프로세스 및 디렉터리는 제외 해야 합니다.

> [!NOTE]
> 아래 나열 된 폴더 및 파일 위치는 비즈니스용 Skype 서버의 기본 위치입니다. 기본값을 사용 하지 않은 위치의 경우이 항목에 지정 된 기본 위치 대신 조직에 대해 지정한 위치를 제외 합니다.

> [!IMPORTANT]
> 일부 바이러스 백신 프로그램에는 제외 목록에 대 한 상대 경로가 아닌 절대적인 필요이 있을 수 있다는 점에 유의 하세요.

- 비즈니스용 Skype 서버 프로세스:

  - ABServer .exe

  - ASMCUSvc .exe

  - AVMCUSvc .exe

  - ChannelService .exe

  - ClsAgent .exe

  - ComplianceService

  - DataMCUSvc

  - DataProxy

  - FileTransferAgent

  - HealthAgent

  - IMMCUSvc .exe
  
  - L<c13> Cbackupservices .exe

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

  - %systemroot%\system32\inetsrv\w3wp.exe

  - %systemroot%\SysWOW64\inetsrv\w3wp.exe

- SQL Server 백 엔드 프로세스:

    > [!NOTE]
    > 이러한 경로는 SQL Server 버전과 관련이 있습니다.

  - %ProgramFiles%\Microsoft SQL Server\MSSQL11. MSSQLSERVER\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe

  - %ProgramFiles%\Microsoft SQL Server\MSAS11. MSSQLSERVER\OLAP\Bin\MSMDSrv.exe

- SQL Server 프런트 엔드 프로세스:

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12. LYNCLOCAL\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12. RTCLOCAL\MSSQL\Binn\SQLServr.exe

  - Standard Edition 설치 RTC 인스턴스

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12. RTC\MSSQL\Binn\SQLServr.exe

- 디렉터리 및 파일:

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > 이러한 경로는 비즈니스용 Skype 서버 버전과 관련이 있습니다.

  - %programfiles%\Skype 비즈니스 서버 2015

  - %programfiles%\Common Files\Skype Business Server 2015 \ 감시자 노드

  - %programfiles%\Common Files\Skype for Business 서버 2015

  - 비즈니스용%programfiles%\Common Files\Skype Online

  - %SystemDrive%\RtcReplicaRoot

  - 파일 공유 저장소 (토폴로지 작성기에서 지정) 파일 저장소는 토폴로지 작성기에 지정 되어 있습니다.

  - 백 엔드 데이터베이스, 사용자 저장소, 보관 저장소, 모니터링 저장소 및 응용 프로그램 저장소를 포함 하는 SQL Server 데이터 및 로그 파일 토폴로지 작성기에서 데이터베이스 및 로그 파일을 지정할 수 있습니다. 기본 이름을 포함 하 여 각 데이터베이스의 데이터 및 로그 파일에 대 한 자세한 내용은 배포 설명서에서 [SQL Server 데이터 및 로그 파일 배치](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) 를 참조 하세요.

  - 프런트 엔드 데이터베이스, 비즈니스용 Skype 스토어, RtcDatabase 저장소 등의 SQL Server 데이터 및 로그 파일 일반적으로%localdrive%\CSData. 아래에 있습니다.


