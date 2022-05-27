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
ms.localizationpriority: medium
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: 다음 표에서는 간단한 설명과 자세한 정보 링크가 있는 비즈니스용 Skype 클라우드 커넥터 버전 cmdlet을 나열합니다.
ms.openlocfilehash: efe4a048e939b6491acc93b7ccd4717ffc9aca8b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676170"
---
# <a name="cloud-connector-cmdlet-reference"></a>클라우드 커넥터 cmdlet 참조

> [!Important]
> Cloud Connector Edition은 비즈니스용 Skype Online과 함께 2021년 7월 31일 사용 중지됩니다. 조직이 Teams 업그레이드되면 [직접 라우팅](/MicrosoftTeams/direct-routing-landing-page)을 사용하여 온-프레미스 전화 통신 네트워크를 Teams 연결하는 방법을 알아봅니다.

다음 표에서는 간단한 설명과 자세한 정보 링크가 있는 비즈니스용 Skype 클라우드 커넥터 버전 cmdlet을 나열합니다.
  
> [!NOTE]
> Cloud Connector 호스트 컴퓨터에서 모든 cmdlet을 실행해야 하며 PowerShell 세션을 관리자 권한으로 실행해야 합니다. 
  
|Cmdlet 이름**|설명|
|---|---|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <p> 버전 1.4.2 이상|인증 기관 서비스를 파일에 백업하고 사이트 공유 디렉터리 아래의 CA 폴더에 저장합니다.|
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md)|고객이 제공한 Windows Server 2012 R2 ISO 파일을 사용하여 기본 VHDX(가상 하드 디스크 파일)를 만듭니다. VHDX 파일은Cloud Connector를 배포하는 동안 사용됩니다.|
|[Enter-CcUpdate](enter-ccupdate.md)|클라우드 커넥터 호스트 서버를 유지 관리 모드로 전환하여 업데이트 프로세스를 준비합니다. 어플라이언스는 "드레이닝"됩니다. 즉, 모든 기존 호출이 완료되지만 새 호출은 거부됩니다.|
|[Exit-CcUpdate](exit-ccupdate.md)|Cloud Connector 호스트 서버에서 업데이트 유지 관리 모드를 종료합니다.|
|[Export-CcConfiguration](export-ccconfiguration.md)|비즈니스용 Skype 클라우드 커넥터 버전 구성을 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버의 로컬 파일로 내보냅니다.|
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md)|클라우드 커넥터 샘플 구성 파일(.ini)을 Cloud Connector 어플라이언스의 어플라이언스 디렉터리로 내보냅니다. 배포에 사용할 파일을 수정하고 이름을 바꿀 수 있습니다.|
|[Export-CcRootCertificate](export-ccrootcertificate.md) <p> 버전 1.4.2 이상|루트 CA 인증서를 Cloud Connector 호스트 서버의 로컬 파일로 내보냅니다.|
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md)|Cloud Connector 호스트 서버에서 작업 디렉터리를 검색합니다. 모든 배포 파일은 이 디렉터리에 저장됩니다.|
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md)|Cloud Connector 어플라이언스에 대한 로그가 저장되는 현재 디렉터리를 표시합니다.|
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <p> 버전 2.1 이상|Cloud Connector 어플라이언스 진단 정보를 제공합니다.|
|[Get-CcCredential](get-cccredential.md)|현재 Cloud Connector 배포의 자격 증명을 반환합니다.|
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)|클라우드 커넥터 배포에 대한 외부 인증서 파일 경로를 반환합니다. 사용자가 이 인증서를 준비합니다.|
|[Get-CcSiteDirectory](get-ccsitedirectory.md)|사이트 수준 구성 파일이 저장되는 현재 디렉터리를 표시합니다. 폴더에는 기본 VHD 및 클라우드 커넥터 설치 파일이 포함되어 있습니다. 이 폴더는 Cloud Connector 사이트의 다른 모든 어플라이언스와 공유되어야 합니다.|
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md)|Cloud Connector에 대한 사이트 수준 로그가 저장되는 현재 디렉터리를 표시합니다.|
|[Get-CcVersion](get-ccversion.md) <p> 버전 2.0 이상|Cloud Connector 인스턴스에서 버전을 반환합니다. Get-CCVersion Cloud Connector의 호스트 머신에서만 사용할 수 있습니다.|
|[Import-CcConfiguration](import-ccconfiguration.md) <p> 버전 2.0 이상|로컬 파일에서 Cloud Connector 호스트 서버로 비즈니스용 Skype 클라우드 커넥터 버전 구성을 가져옵니다.|
|[Install-CcAppliance](install-ccappliance.md)|호스트 서버에 AD, 중앙 관리 Microsoft Store, 중재 서버 및 에지 서버 가상 머신을 포함한 클라우드 커넥터 어플라이언스를 설치합니다.|
|[Publish-CcAppliance](publish-ccappliance.md)|온라인 테넌트 구성에서 고가용성 정보를 가져오고 호스트 서버의 클라우드 커넥터 어플라이언스에 게시합니다.|
|[Register-CcAppliance](register-ccappliance.md)|온라인 테넌트 구성에서 PSTN 사이트에 어플라이언스 정보를 등록합니다. 어플라이언스는 클라우드 커넥터 관리 서비스에서 배포 및 관리하기 전에 등록해야 합니다.|
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <p> 버전 1.4.2 이상|Cloud Connector에 대한 사이트 공유 디렉터리 아래의 CA 폴더에서 인증 기관 서비스 백업 파일 "\<SiteRootDirectory\>\CA\SfB CCE Root.p12"를 제거합니다.|
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <p> 버전 1.4.2 이상|Renew-CcCACertificate 실행하거나 CcServerCertificate cmdlet을 갱신한 후 중앙 관리 Microsoft Store, 중재 서버 및 에지 서버에서 레거시 서버 인증서를 제거합니다.|
|[Renew-CcCACertificate](renew-cccacertificate.md) <p> 버전 1.4.2만|인증 기관 서비스 AD 서버를 다시 설치하여 새 루트 CA 인증서를 만듭니다.|
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <p> 버전 1.4.2만|만료가 가까워지거나 이미 만료된 경우 Cloud Connector에 대한 인증서를 갱신합니다.|
|[Reset-CcCACertificate](reset-cccacertificate.md) <p> 버전 1.4.2 이상|새 인증 기관 인증서를 설치하도록 인증 기관 서버를 다시 설정합니다.|
|[Restore-CcCredentials](restore-cccredentials.md) <p> 버전 2.1 이상|자격 증명을 정리하고 현재 Cloud Connector 배포에 사용되는 모든 자격 증명을 다시 입력하라는 메시지를 표시합니다.|
|[Search-CcLog](search-cclog.md)|Cloud Connector 어플라이언스 로그 디렉터리에서 들어오고 나가는 통화 로그를 검색합니다.|
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md)|Cloud Connector 호스트 서버에서 작업 디렉터리를 설정합니다. 모든 배포 파일은 이 디렉터리에 저장됩니다.|
|[Set-CcCredential](set-cccredential.md)|현재 클라우드 커넥터 배포의 자격 증명을 설정합니다.|
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)|중재 서버 또는 에지 서버에 대한 인증서가 저장되는 경로를 지정합니다.|
|[Set-CcSiteDirectory](set-ccsitedirectory.md)|Cloud Connector에 대한 사이트 수준 구성 파일이 저장될 디렉터리를 설정합니다. 폴더에는 기본 VHD 및 Cloud Connector 구성 파일이 포함됩니다.|
|[Start-CcDownload](start-ccdownload.md)|클라우드 커넥터 비트 및 msi 파일을 동기적으로 다운로드합니다.|
|[Start-CcLogging](start-cclogging.md)|Cloud Connector 어플라이언스에 대한 수신 및 발신 호출 로그를 생성합니다.|
|[Stop-CcLogging](stop-cclogging.md)|Cloud Connector 어플라이언스용 수신 및 발신 호출 로그 생성을 중지합니다.|
|[Switch-CcVersion](switch-ccversion.md)|실행 중인 어플라이언스의 연결을 끊고 새로 배포된 또는 백업 어플라이언스로 전환합니다.|
|[Uninstall-CcAppliance](uninstall-ccappliance.md)|호스트 서버에서 실행 중인 Cloud Connector 어플라이언스를 제거합니다.|
|[Unregister-CcAppliance](unregister-ccappliance.md)|온라인 테넌트 구성의 PSTN 사이트에서 현재 Cloud Connector 어플라이언스를 등록 취소합니다.|
|[Update-CcCACertificate](update-cccacertificate.md) <p> 버전 2.0 이상|인증 기관 서비스 AD 서버를 다시 설치하여 새 루트 CA 인증서를 만듭니다.|
|[Update-CcServerCertificate](update-ccservercertificate.md) <p> 버전 2.0 이상|만료가 가까워지거나 이미 만료된 경우 Cloud Connector에 대한 인증서를 갱신합니다.|
