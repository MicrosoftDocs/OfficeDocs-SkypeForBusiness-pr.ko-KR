---
title: 클라우드 커넥터 어플라이언스 준비
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Office 365 (클라우드 PBX)에서 전화 시스템을 사용 하 여 배포 하 고 사용할 수 있도록 클라우드 커넥터 기기를 준비 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 6e6cb71353dc2a2339fe92ce45d0cd3dee9f21a1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814436"
---
# <a name="prepare-your-cloud-connector-appliance"></a>클라우드 커넥터 어플라이언스 준비

Office 365 (클라우드 PBX)에서 전화 시스템을 사용 하 여 배포 하 고 사용할 수 있도록 클라우드 커넥터 기기를 준비 하는 방법에 대해 알아봅니다.

이 섹션에서는 비즈니스용 Skype 클라우드 커넥터 버전 설치 파일을 가져오고, 클라우드 커넥터 소프트웨어를 설치 하 고, 클라우드 커넥터 기기를 배포용으로 준비 하는 방법에 대해 설명 합니다. 이 섹션의 모든 단계를 완료 하면 단일 사이트 또는 여러 사이트에 대 한 클라우드 커넥터를 배포할 준비가 됩니다. 기존 클라우드 커넥터 배포가 있고 아직 클라우드 커넥터 버전 2.1으로 업그레이드 하지 않은 경우 [새 버전의 클라우드 커넥터로 업그레이드](upgrade-to-a-new-version-of-cloud-connector.md)를 참조 하세요.

> [!NOTE]
> Microsoft는 현재 버전의 클라우드 커넥터 에디션 버전 2.1을 지원 합니다. 자동 업데이트를 구성한 경우 클라우드 커넥터는 자동으로 업데이트 됩니다. 수동 업데이트를 구성한 경우 해당 릴리스의 60 일 내에 버전 2.1으로 업그레이드 해야 합니다. Microsoft는 업그레이드 시간을 허용 하도록 2.1 릴리스 이후 60 일간의 이전 버전을 지원 합니다. 

> [!NOTE]
> 클라우드 커넥터 버전 2.1 이상에서는 호스트 기기에 .NET Framework 4.6.1 이상이 설치 되어 있어야 합니다. 

> [!IMPORTANT]
> 배포를 성공적으로 수행 하기 위해 cmdlet을 실행 하 여 비즈니스용 Skype 클라우드 커넥터를 구성 하는 경우 시작 하는 것과 같은 콘솔 세션을 항상 사용 합니다. 배포 및 구성 중에 다른 세션으로 전환 하지 않도록 합니다. 

> [!NOTE]
> 배포의 첫 번째 기기 (사이트 디렉터리에 대 한 공유 만들기, 비트 다운로드), Windows Server ISO 이미지에서 VHDX (가상 하드 디스크) 파일 준비 등의 몇 가지 단계를 수행 하면 됩니다. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>비즈니스용 Skype 클라우드 Connector Edition 설치 관리자 다운로드

1. 클라우드 커넥터 Vm이 실행 될 호스트 서버에서 설치 파일을 다운로드 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)합니다. 

    > [!IMPORTANT]
    > 설치 하는 동안 추가 파일을 다운로드 하기 때문에 호스트 서버는 클라우드 커넥터 설치 중에 인터넷에 액세스할 수 있어야 합니다. 

2. 설치 하는 동안 설치 관리자를 실행 하 고 기본값을 적용 합니다.

3. 설치가 성공적으로 완료 되었는지 확인 합니다.

## <a name="verify-the-installation-and-configure-the-environment"></a>설치 확인 및 환경 구성

1. PowerShell 콘솔을 관리자로 열고 다음 cmdlet을 사용 하 여 비즈니스용 Skype Cloud Connector Edition cmdlet을 사용할 수 있는지 확인 합니다.

   ```powershell
   Get-Command *-Cc*
   ```

    이 명령은 비즈니스용 Skype 클라우드 커넥터 에디션에 대 한 cmdlet 목록을 반환 해야 합니다.

2. Vhd, SfBBits 및 VersionInfo 파일은 **사이트 디렉터리**에 저장 됩니다.

    다음 cmdlet을 사용 하 여 **사이트 디렉터리** 의 위치를 찾을 수 있습니다.

   ```powershell
   Get-CcSiteDirectory
   ```

    명령은 파일 시스템에서 위치를 반환 해야 합니다. 위치는 로컬 폴더 또는 파일 공유 일 수 있습니다. **사이트 디렉터리** 의 기본 위치 는%USERPROFILE%\CloudConnector\SiteRoot.입니다. 기본 위치는 각 사이트에서 만든 첫 번째 기기의 파일 공유로 변경 되어야 합니다.

    다음과 같이 위치를 선택 해야 합니다.

   - 각 사이트에서 만든 첫 번째 기기에서 생성 됩니다.

   - 같은 사이트의 다른 호스트 서버 (기기)에서 액세스할 수 있는 공유 폴더

     **사이트 디렉터리** 를 기본값이 아닌 다른 위치로 설정 하려면 다음 cmdlet을 실행 합니다.

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    사이트에 대 한 HA (고가용성)를 배포 하는 경우에는 cmdlet을 실행 하 여 사이트 내의 각 호스트 서버에서 같은 위치로 **사이트 디렉터리** 를 설정 해야 합니다.

    사이트의 각 기기에 로그온 하 고 배포 하는 경우 현재 로그온 계정에 **사이트 디렉터리**에 대 한 올바른 액세스 권한이 있는지 확인 합니다.

3. **기기 디렉터리** 는 비즈니스용 Skype 클라우드 커넥터 에디션에 대 한 로컬 작업 루트 디렉터리로, 외부 인증서, 인스턴스 및 로그가 저장 되는 위치입니다. 기본 위치는 다음과 같습니다 .%USERPROFILE%\CloudConnector\ApplianceRoot.

    **기기 디렉터리**의 위치를 찾으려면 다음 cmdlet을 실행 합니다.

   ```powershell
   Get-CcApplianceDirectory
   ```

    **기기 디렉터리** 를 기본값이 아닌 다른 위치로 설정 하려면 다음 cmdlet을 실행 합니다.

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    기기 디렉터리는 기기의 로컬 폴더로 설정 해야 합니다. 비즈니스용 Skype 클라우드 커넥터 에디션 배포를 시작 하기 전에 **기기 디렉터리만** 설정 해야 합니다. 배포 후에 변경 하는 경우 호스트 서버를 다시 배포 해야 합니다.

    > [!IMPORTANT]
    > **기기 디렉터리** 경로에는 공백이 없어야 합니다.

## <a name="set-the-path-for-the-external-edge-certificate"></a>외부에 지 인증서에 대 한 경로 설정

- 다음 cmdlet을 실행 하 여 파일 이름을 포함 한 경로를 외부에 지 인증서로 설정 합니다. 예: C:\certs\cce\ap.contoso.com.pfx. 인증서에 개인 키가 포함 되어 있어야 합니다.

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > -Target 매개 변수는 버전 1.4.2 이상에 한정 된다는 점에 유의 하세요. 

    파일 이름을 포함 하 여 외부 인증서의 전체 경로를 지정 합니다. 인증서는 로컬 또는 파일 공유에 저장할 수 있습니다. 인증서가 공유 폴더에 저장 되어 있는 경우 각 사이트의 첫 번째 기기에서 공유 폴더를 만들어야 하며 같은 사이트에 속하는 다른 기기에서 액세스할 수 있어야 합니다. 이 cmdlet은 외부 인증서를 **기기 디렉터리로**복사 합니다.

    > [!IMPORTANT]
    > **클라우드 커넥터 버전 1.4.2 이상으로 업데이트 한 경우 준비 된**외부 인증서에 개인 키와 루트 ca 인증서 및 중개 ca 인증서를 포함 하 여 전체 인증서 체인이 포함 되어 있는지 확인 합니다. **클라우드 커넥터 버전 1.4.2을 아직 업데이트 하지 않은 경우 준비 된**외부 인증서에 개인 키가 포함 되어 있는지 확인 합니다. 이 외부 인증서는 기본적으로 Windows에서 신뢰할 수 있는 인증 기관에서 발급 해야 합니다.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>외부 PSTN 게이트웨이/SBC 인증서의 경로를 설정 합니다.

중재 서버와 PSTN 게이트웨이/SBC 간에 TLS를 사용 하는 경우 다음 cmdlet을 실행 하 여 파일 이름을 포함 한 경로를 게이트웨이 인증서로 설정 합니다. 예: C:\certs\cce\sbc.contoso.com.cer. 인증서에는 게이트웨이에 할당 된 인증서에 대 한 루트 CA 및 중간 체인이 포함 되어야 합니다.

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> -Target 매개 변수는 버전 1.4.2 이상에 한정 된다는 점에 유의 하세요. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Hyper-v 관리자에서 가상 스위치 만들기

1. **Hyper-v 관리자** > **가상 스위치 관리자**를 열고 **새 가상 스위치 관리자**를 선택 합니다.

2. 외부 가상 스위치를 만들고 내부 네트워크 도메인에 연결 된 실제 네트워크 어댑터에 바인딩합니다.

    관리 운영 체제에서이 가상 스위치에 대해 **이 네트워크 어댑터를 공유 하도록 허용을** 선택 합니다.

3. 외부 가상 스위치를 만들어 인터넷에 라우팅된 실제 네트워크 어댑터에 바인딩합니다.

    관리 운영 체제에서이 가상 스위치에 대해 **이 네트워크 어댑터를 공유 하도록 허용** 선택을 취소 합니다.

4. 경계 네트워크를 내부 네트워크 도메인 **SFB CCE Corpnet 스위치**에 연결 하는 스위치의 이름을 설정 합니다.

    경계 네트워크를 인터넷 **SFB CCE 인터넷 스위치**에 연결 하는 스위치의 이름을 설정 합니다.

## <a name="update-the-cloudconnectorini-configuration-file"></a>CloudConnector .ini 구성 파일 업데이트

[비즈니스용 Skype 클라우드 커넥터 에디션 계획](plan-skype-for-business-cloud-connector-edition.md) 의 [배포 매개 변수를 확인](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) 하기 위해 수집한 정보를 사용 하 여 cloudconnector .ini 파일을 준비 합니다.

파일을 업데이트 하려면 먼저 다음 cmdlet을 실행 하 여 샘플 서식 파일 (CloudConnector: .Sample)을 가져옵니다.

```powershell
Export-CcConfigurationSampleFile
```

샘플 템플릿은 **기기 디렉터리**에 저장 됩니다.

환경의 값을 사용 하 여 업데이트 한 후에는 **기기 디렉터리**에 파일을 cloudconnector .ini로 저장 합니다. **CcApplianceDirectory** 를 실행 하 여 **기기 디렉터리**의 경로를 확인할 수 있습니다.

.Ini 파일을 업데이트 하는 경우 다음 사항을 고려 하세요.

> [!NOTE]
> 이 섹션에서는 .ini 파일의 모든 값에 대해 설명 하지는 않지만 특별 한 고려 사항이 있는 경우에만 적용 됩니다. 전체 목록은 [비즈니스용 Skype 클라우드 커넥터 에디션 계획](plan-skype-for-business-cloud-connector-edition.md) 의 [배포 매개 변수 결정](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) 섹션을 참조 하세요. 추가 어플라이언스 또는 새 사이트에 대해 변경 해야 하는 값에 대 한 자세한 내용은 [클라우드 커넥터의 여러 사이트 배포](deploy-multiple-sites-in-cloud-connector.md)항목의 [멀티 사이트 배포와 비교 하 여 고가용성 (고가용성)이 포함 된 단일 사이트](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) 를 참조 하세요. 

- **SiteName:** 기본 값은 **Site1**입니다. 클라우드 커넥터를 업데이트 해야 합니다. **등록-CcAppliance** 를 실행 하 여 기기를 기존 또는 새 사이트에 등록 하는 경우, Cmdlet은 **SiteName** 을 사용 하 여 등록할 사이트를 결정 합니다.

     새 사이트에 기기를 등록 하려는 경우 **SiteName** 의 값은 고유 하 고 기존 사이트와 달라 야 합니다. 기기를 기존 사이트에 등록 하려는 경우 .ini 파일의 **SiteName** 에 대 한 값이 Office 365 테 넌 트 구성에 정의 된 이름과 일치 해야 합니다. 한 사이트에서 다른 사이트로 구성 파일을 복사 하는 경우에는 각 사이트의 **SiteName** 에 대 한 값을 적절 하 게 업데이트 해야 합니다.

- **ServerName:** 서버 이름에는 도메인 이름을 포함할 수 없으며 15 자로 제한 해야 합니다.

- **하드 다시 입력:** 값을 null로 설정 하거나 비워 두지 않으면 기본값인 **Normal** 이 사용 됩니다. [비즈니스용 Skype 클라우드 커넥터 에디션 계획](plan-skype-for-business-cloud-connector-edition.md)에 설명 된 대로 호스트 컴퓨터 당 500 동시 통화를 지원 하기 위해 더 많은 버전의 클라우드 커넥터를 배포 하려는 경우 **Normal** 을 사용 합니다. 50 동시 통화를 지 원하는 작은 배포의 경우 **최소값** 을 사용 합니다.

- **Internet/Corpnet/관리 가상 스위치:**: 만든 가상 스위치의 이름을 추가 합니다. 관리 가상 스위치의 경우 기본값을 유지 합니다. 배포 스크립트는 배포 시작 부분에 관리 가상 스위치를 만들고 배포가 완료 되 면 삭제 합니다.

- **ManagementIPPrefix:** 네트워크 섹션의 ManagementIPPrefix는 다른 내부 Ip와 다른 서브넷 이어야 합니다. 예를 들어 기본 값이 표시 되는 경우 ManagementIPPrefix는 192.168.213.0이 고 광고 IPAddress는 192.168.0.238입니다.

    배포 스크립트는 각 가상 컴퓨터에 관리 네트워크 어댑터를 만들고 관리 IP를 할당 한 다음 관리 가상 스위치에 연결 합니다. 이렇게 하면 호스트 서버가이 관리 네트워크를 통해 각 가상 컴퓨터에 연결 하 고 관리할 수 있습니다. 배포가 완료 되 면 관리 가상 스위치가 삭제 됩니다.

- **기본 VM 특정 구성:** 이 섹션의 설정은 **Convert-CcIsoToVhdx** cmdlet에 대해 구성 되어야 합니다.

    기본 VM 이미지를 준비 하는 동안 기본 VM이 내부 네트워크 스위치에 연결 됩니다. VM이 인터넷에 액세스할 수 있으려면 다음 설정이 매우 중요 합니다.

  - 가지 BaseVMIP: 기본 VM에 할당할 corpnet IP 주소입니다.

  - 사설망 CorpnetDefaultGateway: 기본 VM에 할당할 기본 게이트웨이

  - 사설망 CorpnetDNSIPAddress: 기본 VM에 할당할 DNS IP 주소입니다.

  - 사설망 WSUSServer: Windows Server 업데이트 서비스의 IP 주소입니다.

  - 사설망 WSUSStatusServer: Windows Server 업데이트 서비스 상태 서버의 IP 주소입니다.

  - 사설망 EnableReferSupport:이는 SIP가 사용자의 트렁크 구성에서 지원 되는지 여부를 정의 합니다 (IP/PBX로 설정).

- **내부 Ip:**

  - 서브넷 마스크 CorpnetIPPrefixLength이 올바른지 확인 합니다.

  - 이러한 내부 Ip에 대 한 IP 충돌이 없는지 확인 합니다.

- **외부 Ip:**

  - MR 공개 IP: nat에 대해 ExternalMRIPs를 지정 하거나 NAT에 대해 ExternalMRPublicIPs를 지정할 수도 있습니다.

  - ExternalSIPIPs 및 ExternalMRIPs는 동일 하 게 사용할 수 있습니다.

  - 서브넷 마스크 InternetIPPrefixLength이 올바른지 확인 합니다.

  - 외부 ip에 대 한 IP 충돌이 없는지 확인 합니다.

- **인터페이스가**

  - 게이트웨이가 하나만 있는 경우 보조 게이트웨이의 섹션을 제거 합니다. 게이트웨이가 두 개 이상 있는 경우 기존 항목을 복사 하 여 붙여 넣은 다음 업데이트 하 여 추가 섹션을 만듭니다.

  - 게이트웨이의 IP 주소와 포트가 올바른지 확인 합니다.

  - PSTN 게이트웨이 수준 HA를 지원 하려면 보조 게이트웨이를 종료 하 고 사용할 추가 게이트웨이를 추가 합니다. 기존 항목을 복사 하 여 붙여 넣은 다음 업데이트할 수 있습니다.

- 필요에 따라 LocalRoute 값을 업데이트 하 여 아웃 바운드 통화 번호를 제한할 수 있습니다.

## <a name="download-the-bits-to-the-site-directory"></a>사이트 디렉터리로 비트 다운로드

다음 cmdlet을 실행 하 여 bits 및 버전 정보 파일을 **사이트 디렉터리**에 다운로드 합니다.

```powershell
Start-CcDownload
```

> [!NOTE]
> 첫 번째 기기에 대해서만이 단계를 수행 해야 합니다. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>다운로드 한 ISO 파일에서 VHDX (기본 가상 디스크) 준비

이 단계에서는 Windows Server 2012 ISO 이미지에서 VHDX (가상 하드 디스크) 파일을 준비 합니다. VHDX는 배포 중에 가상 컴퓨터를 만드는 데 사용 됩니다. 기본 VM (임시 가상 머신)이 만들어지고 Windows Server 2012이 ISO 파일에서 설치 됩니다. VM을 만든 후에는 필요한 일부 구성 요소가 설치 되 고 최신 Windows 업데이트가 적용 됩니다. 결과적으로 기본 VM은 생성 된 가상 디스크 파일만 남겨 두어 일반화 (sysprep) 되 고 정리 됩니다.

> [!NOTE]
> 첫 번째 기기에 대해서만이 단계를 수행 해야 합니다. 

이 단계를 진행 하기 전에 corpnet 스위치가 생성 되었는지 확인 합니다. 또한 CloudConnector .ini 파일에 다음 설정이 올바르게 구성 되어 있는지 확인 합니다.

- 사설망 CorpnetSwitchName

- 가지 BaseVMIP

- 사설망 CorpnetIPPrefixLength

- 사설망 CorpnetDefaultGateway

- 사설망 CorpnetDNSIPAddress

PowerShell 콘솔을 관리자로 시작 하 고 다음 cmdlet을 실행 하 여 ISO 이미지를 VHD (가상 하드 디스크)로 변환 합니다.

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

ISO 이미지에 대 한 전체 경로 (파일 이름 포함)를 지정 합니다. 예: C:\ISO\WindowsServer2012R2.iso.

생성 된 VHD 파일은 **Site Directory** \Bits\vhd 폴더에 저장 됩니다. **Get-CcSiteDirectory**를 실행 하 여 **사이트 디렉터리** 의 경로를 가져올 수 있습니다.

> [!IMPORTANT]
> 기본적으로 기본 VM에는 프록시 설정이 구성 되어 있지 않습니다. 네트워크 환경에서 Windows Update를 통해 VM을 업데이트 하기 위해 프록시가 필요한 경우 "Convert-CcIsoToVhdx"를 실행할 때-PauseBeforeUpdate 스위치를 추가 해야 합니다. Windows 업데이트 전에 스크립트가 일시 중지 되 고 VM에서 프록시를 수동으로 설정할 기회가 생깁니다. 프록시를 설정 하 고 VM에서 인터넷에 액세스할 수 있게 되 면 스크립트를 다시 시작 하 여 나머지 단계를 완료할 수 있습니다. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>다중 사이트 배포를 위한 Vhd 만들기

이 단계는 다중 사이트 배포에만 적용 되는 선택 사항입니다.

다중 사이트 배포를 배포 하는 경우 ISO를 각 사이트의 VHD로 변환할 필요가 없습니다. 첫 번째 사이트에 대해 생성 된 VHDX를 두 번째 사이트의 호스트 서버로 복사할 수 있습니다.

 파일을 다른 사이트의 호스트 서버에서 같은 파일 위치 ( **사이트 디렉터리** \Bitente.vhd 폴더)와 같은 파일 이름으로 복사 합니다.

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>PowerShell 실행 정책을 RemoteSigned로 설정

제공 된 PowerShell 스크립트는 실행 정책을 RemoteSigned로 설정 해야 합니다. 현재 설정을 보려면 PowerShell 콘솔을 관리자로 열고 다음 cmdlet을 실행 합니다.

```powershell
Get-ExecutionPolicy
```

"RemoteSigned"으로 설정 되지 않은 경우 다음 cmdlet을 실행 하 여 변경 합니다.

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>호스트 컴퓨터 (버전 1.4.1 이상)에서 로컬 그룹 정책 변경

> [!NOTE]
> 이 작업은 클라우드 커넥터 버전 1.4.2 이상에는 필요 하지 않습니다. 

CceService 계정은 비즈니스용 Skype 클라우드 커넥터 에디션 배포 중에 만들어집니다. 클라우드 커넥터 관리 서비스를 실행 하 고 cloudconnector .msi를 제거 하는 권한이 필요 합니다. 사용자가 로그 오프할 때 사용자 레지스트리가 언로드되지 않도록 지정 하려면 클라우드 커넥터 호스트 컴퓨터에서 그룹 정책 설정을 변경 해야 합니다. 다음 단계를 따르세요.

### <a name="to-change-the-group-policy-setting"></a>그룹 정책 설정을 변경 하려면

1. Gpedit.msc를 실행 하 여 **그룹 정책 편집기** 를 엽니다.

2. **그룹 정책 편집기**에서 관리 템플릿으로 이동 > 시스템 > UserProfile > 사용자가 로그 오프할 때 사용자 레지스트리를 강제로 언로드하지 않습니다. 

3. 값을 **Enabled**로 설정 합니다.

## <a name="set-up-your-office-365-tenant"></a>Office 365 테 넌 트 설정

비즈니스용 Skype Online 및 Office 365의 전화 시스템을 사용 하는 Office 365 테 넌 트가 필요 합니다. 클라우드 커넥터 사용을 시도 하기 전에 테 넌 트가 설정 및 구성 되었는지 확인 합니다.

일부 Office 365 설정 단계에서는 테 넌 트 원격 PowerShell (TRPS)을 사용 하 여 Office 365 테 넌 트를 구성 해야 합니다. **호스트 서버에 설치 되어 있어야 합니다.** 비즈니스용 skype online [, Windows Powershell 모듈](https://www.microsoft.com/en-us/download/details.aspx?id=39366)에서 PowerShell For 비즈니스용 skype online 모듈을 다운로드할 수 있습니다.

클라우드 커넥터 온라인 관리를 위해 전용 Skype for Business 관리자 계정을 만듭니다 (예: CceOnlineManagmentAdministrator). 기기에서 기기를 추가 또는 제거 하 고 자동 OS 업데이트를 사용 하거나 사용 하지 않도록 설정 하거나 자동 바이너리 업데이트를 사용 하거나 사용 하지 않도록 설정 하려면이 계정이 사용 됩니다. 만료 될 때마다 서비스에 대해 변경할 필요가 없도록이 계정의 암호가 만료 되지 않도록 설정 합니다.


