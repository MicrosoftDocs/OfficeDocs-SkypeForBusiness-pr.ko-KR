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
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: 다음 표에는 간단한 설명과 함께 비즈니스용 Skype Cloud Connector Edition cmdlet이 나와 있습니다.
ms.openlocfilehash: 58fed82857138bf9716db88648344e9140b29d6f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196490"
---
# <a name="cloud-connector-cmdlet-reference"></a>클라우드 커넥터 cmdlet 참조
 
다음 표에는 간단한 설명과 함께 비즈니스용 Skype Cloud Connector Edition cmdlet이 나와 있습니다.
  
> [!NOTE]
> 클라우드 커넥터 호스트 컴퓨터에서 모든 cmdlet을 실행 해야 하며, 관리자 권한으로 PowerShell 세션을 실행 해야 합니다. 
  
|**Cmdlet 이름**|**설명**|
|:-----|:-----|
|[백업-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> 버전 1.4.2 이상  <br/> |인증 기관 서비스를 파일에 백업 하 고 사이트 공유 디렉터리 아래의 CA 폴더에 저장 합니다.     <br/> |
|[변환-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |고객 제공 Windows Server 2012 R2 ISO 파일을 사용 하 여 기본 VHDX (가상 하드 디스크 파일)를 만듭니다. VHDX 파일은 배포 ofCloud 커넥터 중에 사용 됩니다.  <br/> |
|[입력-CcUpdate](enter-ccupdate.md) <br/> |클라우드 커넥터 호스트 서버를 유지 관리 모드로 전환 하 여 업데이트 프로세스를 준비 합니다. 기기는 "배출" 됩니다. 즉, 모든 기존 통화가 완료 되지만 새로운 통화는 거부 됩니다.  <br/> |
|[끝내기-CcUpdate](exit-ccupdate.md) <br/> |클라우드 커넥터 호스트 서버에서 업데이트 유지 관리 모드를 종료 합니다.  <br/> |
|[수출-CcConfiguration](export-ccconfiguration.md) <br/> | 비즈니스용 skype 클라우드 커넥터 에디션 구성을 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버의 로컬 파일로 내보냅니다. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |클라우드 커넥터 샘플 구성 파일 (.ini)을 클라우드 커넥터 기기의 기기 디렉터리로 내보냅니다. 배포에 사용할 파일을 수정 하 고 이름을 바꿀 수 있습니다.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> 버전 1.4.2 이상  <br/> |루트 CA 인증서를 클라우드 커넥터 호스트 서버의 로컬 파일로 내보냅니다.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |클라우드 커넥터 호스트 서버에서 작업 디렉터리를 검색 합니다. 모든 배포 파일은이 디렉터리에 저장 됩니다.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |클라우드 커넥터 기기에 대 한 로그가 저장 된 현재 디렉터리를 표시 합니다.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> 버전 2.1 이상  <br/> |클라우드 커넥터 기기에 대 한 진단 정보를 제공 합니다.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |현재 클라우드 커넥터 배포의 자격 증명을 반환 합니다.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |클라우드 커넥터 배포에 대 한 외부 인증서 파일 경로를 반환 합니다. 사용자가이 인증서를 준비 합니다.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |사이트 수준 구성 파일이 저장 되는 현재 디렉터리를 표시 합니다. 폴더에는 기본 VHD 및 클라우드 커넥터 설치 파일이 포함 되어 있습니다. 이 폴더는 클라우드 커넥터 사이트의 다른 모든 기기와 공유 되어야 합니다.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |클라우드 커넥터의 사이트 수준 로그가 저장 되어 있는 현재 디렉터리를 표시 합니다.  <br/> |
|[다운로드-CcVersion](get-ccversion.md) <br/> 버전 2.0 이상  <br/> |클라우드 커넥터 인스턴스의 버전을 반환 합니다. Get-CCVersion은 클라우드 커넥터의 호스트 컴퓨터 에서만 사용할 수 있습니다.  <br/> |
|[가져오기-CcConfiguration](import-ccconfiguration.md) <br/> 버전 2.0 이상  <br/> |로컬 파일에서 클라우드 커넥터 호스트 서버로의 비즈니스용 Skype 클라우드 커넥터 에디션 구성을 가져옵니다.  <br/> |
|[설치-CcAppliance](install-ccappliance.md) <br/> |호스트 서버에서 광고, 중앙 관리 저장소, 중재 서버 및 Edge Server 가상 컴퓨터를 포함 하 여 클라우드 커넥터 기기를 설치 합니다.  <br/> |
|[게시-CcAppliance](publish-ccappliance.md) <br/> | 온라인 테 넌 트 구성에서 높은 가용성 정보를 가져오고 호스트 서버의 클라우드 커넥터 기기에 게시 합니다. <br/> |
|[등록-CcAppliance](register-ccappliance.md) <br/> | 온라인 테 넌 트 구성의 PSTN 사이트에 기기 정보를 등록 합니다. 클라우드 커넥터 관리 서비스에서 배포 하 고 관리할 수 있으려면 기기를 등록 해야 합니다. <br/> |
|[제거-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> 버전 1.4.2 이상  <br/> |클라우드 커넥터용 사이트 공유 디렉터리 아래의 CA 폴더\<에서\>인증 기관 서비스 백업 파일 "SiteRootDirectory \CA\SfB CCE Root. p12"를 제거 합니다.  <br/> |
|[제거-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> 버전 1.4.2 이상  <br/> |CcCACertificate 또는 CcServerCertificate cmdlet 갱신을 실행 한 후 중앙 관리 저장소, 중재 서버 및 Edge 서버에서 레거시 서버 인증서를 제거 합니다.  <br/> |
|[갱신-CcCACertificate](renew-cccacertificate.md) <br/> 버전 1.4.2  <br/> |새 루트 CA 인증서를 만들기 위해 인증 기관 서비스 광고 서버를 다시 설치 합니다.  <br/> |
|[갱신-CcServerCertificate](renew-ccservercertificate.md) <br/> 버전 1.4.2  <br/> |클라우드 커넥터의 만료가 거의 만료 되거나 이미 만료 된 경우 해당 인증서를 갱신 합니다.  <br/> |
|[다시 설정-CcCACertificate](reset-cccacertificate.md) <br/> 버전 1.4.2 이상  <br/> |새 인증 기관 인증서를 설치 하기 위해 인증 기관 서버를 다시 설정 합니다.  <br/> |
|[복원-CcCredentials](restore-cccredentials.md) <br/> 버전 2.1 이상  <br/> |자격 증명을 정리 하 고 현재 클라우드 커넥터 배포에 사용 된 모든 자격 증명을 다시 입력 하 라는 메시지를 표시 합니다.  <br/> |
|[검색-CcLog](search-cclog.md) <br/> |클라우드 커넥터 기기 로그 디렉터리에서 수신 및 발신 통화 로그를 검색 합니다.  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |클라우드 커넥터 호스트 서버에서 작업 디렉터리를 설정 합니다. 모든 배포 파일은이 디렉터리에 저장 됩니다.  <br/> |
|[집합-CcCredential](set-cccredential.md) <br/> |현재 클라우드 커넥터 배포의 자격 증명을 설정 합니다.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |중재 서버 또는 Edge 서버의 인증서가 저장 되는 경로를 지정 합니다.  <br/> |
|[집합-CcSiteDirectory](set-ccsitedirectory.md) <br/> |클라우드 커넥터에 대 한 사이트 수준 구성 파일이 저장 되는 디렉터리를 설정 합니다. 폴더에 기본 VHD 및 클라우드 커넥터 구성 파일이 포함 됩니다.  <br/> |
|[시작-CcDownload](start-ccdownload.md) <br/> |클라우드 커넥터 비트 및 msi 파일을 동기적으로 다운로드 합니다.  <br/> |
|[시작-CcLogging](start-cclogging.md) <br/> |클라우드 커넥터 기기에 대 한 수신 및 발신 통화 로그를 생성 합니다.  <br/> |
|[중지-CcLogging](stop-cclogging.md) <br/> |클라우드 커넥터 기기에 대 한 수신 및 발신 통화 로그 생성을 중지 합니다.  <br/> |
|[스위치-CcVersion](switch-ccversion.md) <br/> |실행 중인 기기 및 스위치를 새로 배포 또는 백업 기기로 연결을 끊습니다.  <br/> |
|[제거-CcAppliance](uninstall-ccappliance.md) <br/> |호스트 서버에서 실행 중인 클라우드 커넥터 기기를 제거 합니다.  <br/> |
|[CcAppliance 등록 취소](unregister-ccappliance.md) <br/> |온라인 테 넌 트 구성의 PSTN 사이트에서 현재 클라우드 커넥터 기기의 등록을 취소 합니다.  <br/> |
|[업데이트-CcCACertificate](update-cccacertificate.md) <br/> 버전 2.0 이상  <br/> |새 루트 CA 인증서를 만들기 위해 인증 기관 서비스 광고 서버를 다시 설치 합니다.  <br/> |
|[업데이트-CcServerCertificate](update-ccservercertificate.md) <br/> 버전 2.0 이상  <br/> |클라우드 커넥터의 만료가 거의 만료 되거나 이미 만료 된 경우 해당 인증서를 갱신 합니다.  <br/> |
   

