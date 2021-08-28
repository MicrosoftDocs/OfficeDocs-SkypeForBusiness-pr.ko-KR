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
description: 다음 표에는 비즈니스용 Skype 클라우드 커넥터 버전 설명과 추가 정보 링크가 있는 cmdlet이 나열되어 있습니다.
ms.openlocfilehash: 19fc33912075e7737a4fa7fc242e74dd1de92289
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583732"
---
# <a name="cloud-connector-cmdlet-reference"></a>클라우드 커넥터 cmdlet 참조
 
> [!Important]
> Cloud Connector Edition은 온라인과 함께 2021년 7월 31일 비즈니스용 Skype 있습니다. 조직에서 사용자 Teams 직접 라우팅을 사용하여 Teams 방법을 [확인합니다.](/MicrosoftTeams/direct-routing-landing-page)

다음 표에는 비즈니스용 Skype 클라우드 커넥터 버전 설명과 추가 정보 링크가 있는 cmdlet이 나열되어 있습니다.
  
> [!NOTE]
> 클라우드 커넥터 호스트 컴퓨터의 모든 cmdlet을 실행하고 PowerShell 세션을 관리자 권한으로 실행해야 합니다. 
  
|**cmdlet 이름**|**설명**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> 버전 1.4.2 이상  <br/> |인증 기관 서비스를 파일에 백업하고 사이트 공유 디렉터리의 CA 폴더에 저장합니다.     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |R2 ISO 파일에서 제공한 고객을 사용하여 기본 VHDX(Windows Server 2012 하드 디스크 파일)를 만듭니다. VHDX 파일은Cloud 커넥터 배포 중에 사용됩니다.  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |클라우드 커넥터 호스트 서버를 유지 관리 모드로 설정하여 업데이트 프로세스를 준비합니다. 어플라이언스가 "드레인"입니다. 즉, 모든 기존 통화가 완료되지만 새 통화는 거부됩니다.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |클라우드 커넥터 호스트 서버에서 업데이트 유지 관리 모드를 종료합니다.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | 비즈니스용 Skype 클라우드 커넥터 버전 구성을 비즈니스용 Skype 클라우드 커넥터 버전 로컬 파일로 내보낼 수 있습니다. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |클라우드 커넥터 샘플 구성 파일(.ini)을 Cloud Connector 어플라이언스 디렉터리로 내보낼 수 있습니다. 배포에 사용할 파일을 수정하고 이름을 변경할 수 있습니다.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> 버전 1.4.2 이상  <br/> |루트 CA 인증서를 클라우드 커넥터 호스트 서버의 로컬 파일로 내보낼 수 있습니다.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |클라우드 커넥터 호스트 서버에서 작업 디렉터리를 검색합니다. 모든 배포 파일은 이 디렉터리에 저장됩니다.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |클라우드 커넥터 어플라이언스에 대한 로그가 저장되는 현재 디렉터리를 나타냅니다.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> 버전 2.1 이상  <br/> |Cloud Connector 어플라이언스에 대한 진단 정보를 제공합니다.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |현재 클라우드 커넥터 배포의 자격 증명을 반환합니다.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |클라우드 커넥터 배포에 대한 외부 인증서 파일 경로를 반환합니다. 사용자가 이 인증서를 준비합니다.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |사이트 수준 구성 파일이 저장되는 현재 디렉터리를 나타냅니다. 폴더에는 기본 VHD 및 클라우드 커넥터 설치 파일이 포함되어 있습니다. 이 폴더는 클라우드 커넥터 사이트의 다른 모든 어플라이언스와 공유해야 합니다.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |클라우드 커넥터에 대한 사이트 수준 로그가 저장되는 현재 디렉터리를 나타냅니다.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> 버전 2.0 이상  <br/> |클라우드 커넥터 인스턴스의 버전을 반환합니다. Get-CCVersion 커넥터의 호스트 머신에서만 사용할 수 있습니다.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> 버전 2.0 이상  <br/> |로컬 비즈니스용 Skype 클라우드 커넥터 버전 구성을 클라우드 커넥터 호스트 서버로 가져올 수 있습니다.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |호스트 서버에 AD, 중앙 관리 저장소, 중재 서버 및 에지 서버 가상 컴퓨터를 비롯한 클라우드 커넥터 어플라이언스를 설치합니다.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | 온라인 테넌트 구성에서 고가용성 정보를 확인하여 호스트 서버의 클라우드 커넥터 어플라이언스에 게시합니다. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | 온라인 테넌트 구성에서 PSTN 사이트에 어플라이언스 정보를 등록합니다. 클라우드 커넥터 관리 서비스를 통해 어플라이언스를 배포하고 관리하려면 먼저 어플라이언스를 등록해야 합니다. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> 버전 1.4.2 이상  <br/> |클라우드 커넥터의 사이트 공유 디렉터리 아래에 있는 CA 폴더에서 인증 기관 서비스 백업 파일 " \<SiteRootDirectory\> \CA\SfB CCE Root.p12"를 제거합니다.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> 버전 1.4.2 이상  <br/> |CcServerCertificate cmdlet을 실행하거나 CcServerCertificate cmdlet을 Renew-CcCACertificate 후 중앙 관리 저장소, 중재 서버 및 에지 서버에서 레거시 서버 인증서를 제거합니다.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> 버전 1.4.2만 해당  <br/> |인증 기관 서비스 AD 서버를 다시 설치하여 새 루트 CA 인증서를 생성합니다.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> 버전 1.4.2만 해당  <br/> |만료 날짜가 다가오거나 이미 만료된 경우 클라우드 커넥터에 대한 인증서를 갱신합니다.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> 버전 1.4.2 이상  <br/> |새 인증 기관 인증서를 설치하도록 인증 기관 서버를 다시 설정합니다.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> 버전 2.1 이상  <br/> |자격 증명을 정리하고 현재 클라우드 커넥터 배포에 사용되는 모든 자격 증명을 다시 입력하라는 메시지가 표시될 수 있습니다.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Cloud Connector appliance 로그 디렉터리에서 수신 및 발신 전화 로그 검색  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |클라우드 커넥터 호스트 서버에서 작업 디렉터리를 설정합니다. 모든 배포 파일은 이 디렉터리에 저장됩니다.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |현재 클라우드 커넥터 배포의 자격 증명을 설정합니다.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |중재 서버 또는 에지 서버의 인증서가 저장되는 경로를 지정합니다.  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |클라우드 커넥터의 사이트 수준 구성 파일이 저장될 디렉터리를 설정합니다. 폴더에는 기본 VHD 및 클라우드 커넥터 구성 파일이 포함되어 있습니다.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |클라우드 커넥터 비트 및 msi 파일을 동기적으로 다운로드합니다.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Cloud Connector 어플라이언스에 대한 수신 및 발신 통화 로그를 생성합니다.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Cloud Connector 어플라이언스에 대한 수신 및 발신 통화 로그 생성을 중지합니다.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |실행 중인 어플라이언스를 분리하고 새로 배포된 어플라이언스 또는 백업 어플라이언스로 전환합니다.  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |호스트 서버에서 실행 중인 클라우드 커넥터 어플라이언스를 제거합니다.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |온라인 테넌트 구성의 PSTN 사이트에서 현재 클라우드 커넥터 어플라이언스 등록을 등록을 언니 다.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> 버전 2.0 이상  <br/> |인증 기관 서비스 AD 서버를 다시 설치하여 새 루트 CA 인증서를 생성합니다.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> 버전 2.0 이상  <br/> |만료 날짜가 다가오거나 이미 만료된 경우 클라우드 커넥터에 대한 인증서를 갱신합니다.  <br/> |
