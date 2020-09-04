---
title: 클라우드 커넥터 cmdlet 참조
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: 다음 표에는 간단한 설명과 함께 비즈니스용 Skype 클라우드 Connector Edition cmdlet이 나열 되어 있으며 자세한 정보에 대 한 링크가 나와 있습니다.
ms.openlocfilehash: 8d33cd8c493c3acc165661e5af80625e773e2d0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359054"
---
# <a name="cloud-connector-cmdlet-reference"></a>클라우드 커넥터 cmdlet 참조
 
> [!Important]
> 클라우드 커넥터 버전은 비즈니스용 Skype Online과 함께 2021 년 7 월 31 일에 사용 중지 됩니다. 조직이 팀으로 업그레이드 된 후에는 [직접 라우팅을](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)사용 하 여 팀에 온-프레미스 전화 통신 네트워크를 연결 하는 방법을 알아보세요.

다음 표에는 간단한 설명과 함께 비즈니스용 Skype 클라우드 Connector Edition cmdlet이 나열 되어 있으며 자세한 정보에 대 한 링크가 나와 있습니다.
  
> [!NOTE]
> 클라우드 커넥터 호스트 컴퓨터에서 모든 cmdlet을 실행 해야 하며, 관리자 권한으로 PowerShell 세션을 실행 해야 합니다. 
  
|**cmdlet 이름**|**설명**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> 버전 1.4.2 이상  <br/> |인증 기관 서비스를 파일에 백업 하 고이를 사이트 공유 디렉터리 아래의 CA 폴더에 저장 합니다.     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |고객이 제공한 Windows Server 2012 R2 ISO 파일을 사용 하 여 기본 VHDX (가상 하드 디스크 파일)를 만듭니다. VHDX 파일은 ofCloud Connector 배포 중에 사용 됩니다.  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |클라우드 커넥터 호스트 서버를 유지 관리 모드로 전환 하 여 업데이트 프로세스를 준비 합니다. 기기는 "배출" 됩니다. 즉, 모든 기존 통화가 완료 되지만 새 통화는 거부 됩니다.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |클라우드 커넥터 호스트 서버에서 업데이트 유지 관리 모드를 종료 합니다.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | 비즈니스용 skype 클라우드 커넥터 에디션 구성을 Skype 클라우드 커넥터 에디션 호스트 서버의 로컬 파일로 내보냅니다. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |클라우드 커넥터 예제 구성 파일 (.ini)을 클라우드 커넥터 기기의 기기 디렉터리로 내보냅니다. 배포에 사용할 파일을 수정 하 고 이름을 바꿀 수 있습니다.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> 버전 1.4.2 이상  <br/> |루트 CA 인증서를 클라우드 커넥터 호스트 서버의 로컬 파일로 내보냅니다.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |클라우드 커넥터 호스트 서버에서 작업 디렉터리를 검색 합니다. 모든 배포 파일은이 디렉터리에 저장 됩니다.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |클라우드 커넥터 기기에 대 한 로그가 저장 되는 현재 디렉터리를 표시 합니다.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> 버전 2.1 이상  <br/> |클라우드 커넥터 기기에 대 한 진단 정보를 제공 합니다.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |현재 클라우드 커넥터 배포의 자격 증명을 반환 합니다.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |클라우드 커넥터 배포에 대 한 외부 인증서 파일 경로를 반환 합니다. 사용자가이 인증서를 준비 합니다.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |사이트 수준 구성 파일이 저장 되는 현재 디렉터리를 표시 합니다. 폴더에는 기본 VHD 및 클라우드 커넥터 설치 파일이 포함 되어 있습니다. 이 폴더는 클라우드 커넥터 사이트의 다른 모든 기기와 공유 되어야 합니다.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |클라우드 커넥터의 사이트 수준 로그가 저장 되는 현재 디렉터리를 표시 합니다.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> 버전 2.0 이상  <br/> |클라우드 커넥터 인스턴스의 버전을 반환 합니다. Get-CCVersion은 클라우드 커넥터의 호스트 컴퓨터 에서만 사용할 수 있습니다.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> 버전 2.0 이상  <br/> |비즈니스용 Skype 클라우드 커넥터 에디션 구성을 로컬 파일에서 클라우드 커넥터 호스트 서버로 가져옵니다.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |호스트 서버에 AD, 중앙 관리 저장소, 중재 서버 및에 지 서버 가상 컴퓨터를 포함 하 여 클라우드 커넥터 기기를 설치 합니다.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | 온라인 테 넌 트 구성에서 고가용성 정보를 가져오고 호스트 서버의 클라우드 커넥터 기기에 게시 합니다. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | 온라인 테 넌 트 구성에서 PSTN 사이트에 기기 정보를 등록 합니다. 클라우드 커넥터 관리 서비스에서 장비를 배포 하 고 관리 하려면 먼저 기기를 등록 해야 합니다. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> 버전 1.4.2 이상  <br/> |\<SiteRootDirectory\>클라우드 커넥터에 대 한 사이트 공유 디렉터리 아래의 CA 폴더에서 "\CA\SFB CCE Root. p12" 인증 기관 서비스 백업 파일을 제거 합니다.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> 버전 1.4.2 이상  <br/> |CcCACertificate를 실행 하거나 CcServerCertificate cmdlet을 갱신 한 후 중앙 관리 저장소, 중재 서버 및에 지 서버에서 레거시 서버 인증서를 제거 합니다.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> 버전 1.4.2  <br/> |새 루트 CA 인증서를 만들기 위해 인증 기관 서비스 AD 서버를 다시 설치 합니다.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> 버전 1.4.2  <br/> |곧 만료 되거나 이미 만료 된 경우 클라우드 커넥터에 대 한 인증서를 갱신 합니다.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> 버전 1.4.2 이상  <br/> |새 인증 기관 인증서를 설치 하기 위해 인증 기관 서버를 다시 설정 합니다.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> 버전 2.1 이상  <br/> |자격 증명을 정리 하 고 현재 클라우드 커넥터 배포에 사용 되는 모든 자격 증명을 다시 입력 하 라는 메시지를 표시 합니다.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |클라우드 커넥터 기기 로그 디렉터리에서 들어오는 및 나가는 호출 로그를 검색 합니다.  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |클라우드 커넥터 호스트 서버에서 작업 디렉터리를 설정 합니다. 모든 배포 파일은이 디렉터리에 저장 됩니다.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |현재 클라우드 커넥터 배포의 자격 증명을 설정 합니다.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |중재 서버 또는에 지 서버에 대 한 인증서가 저장 되는 경로를 지정 합니다.  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |클라우드 커넥터에 대 한 사이트 수준 구성 파일이 저장 되는 디렉터리를 설정 합니다. 이 폴더에는 기본 VHD 및 클라우드 커넥터 구성 파일이 포함 됩니다.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |클라우드 커넥터 비트 및 msi 파일을 동기식으로 다운로드 합니다.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |클라우드 커넥터 기기에 대 한 수신 및 나가는 호출 로그를 생성 합니다.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |클라우드 커넥터 기기에 대 한 들어오고 나가는 호출 로그 생성을 중지 합니다.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |실행 중인 기기와 스위치를 새로 배포 된 기기나 백업 기기로 연결을 끊습니다.  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |호스트 서버에서 실행 중인 클라우드 커넥터 어플라이언스를 제거 합니다.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |온라인 테 넌 트 구성의 PSTN 사이트에서 현재 클라우드 커넥터 기기의 등록을 취소 합니다.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> 버전 2.0 이상  <br/> |새 루트 CA 인증서를 만들기 위해 인증 기관 서비스 AD 서버를 다시 설치 합니다.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> 버전 2.0 이상  <br/> |곧 만료 되거나 이미 만료 된 경우 클라우드 커넥터에 대 한 인증서를 갱신 합니다.  <br/> |
   

