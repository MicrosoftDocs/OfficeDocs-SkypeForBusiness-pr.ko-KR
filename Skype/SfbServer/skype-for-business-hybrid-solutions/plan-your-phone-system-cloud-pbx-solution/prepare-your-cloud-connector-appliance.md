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
description: 클라우드 PBX(클라우드 PBX)와 함께 배포 및 사용하기 위해 클라우드 커넥터 어플라이언스를 전화 시스템 방법을 설명합니다.
ms.openlocfilehash: 58f9765f211a3961db8baf5929956feecf1eb4fd7e7744490cb21f1967dcb46f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340814"
---
# <a name="prepare-your-cloud-connector-appliance"></a>클라우드 커넥터 어플라이언스 준비

> [!Important]
> Cloud Connector Edition은 온라인과 함께 2021년 7월 31일 비즈니스용 Skype 있습니다. 조직에서 사용자 Teams 직접 라우팅을 사용하여 Teams 방법을 [확인합니다.](/MicrosoftTeams/direct-routing-landing-page)

클라우드 PBX(클라우드 PBX)와 함께 배포 및 사용하기 위해 클라우드 커넥터 어플라이언스를 전화 시스템 방법을 설명합니다.

이 섹션에서는 비즈니스용 Skype 클라우드 커넥터 버전 파일을 다운로드하고, 클라우드 커넥터 소프트웨어를 설치하고, 배포를 위해 클라우드 커넥터 어플라이언스를 준비하는 방법을 설명합니다. 이 섹션의 모든 단계를 완료하면 단일 사이트 또는 여러 사이트에 대해 클라우드 커넥터를 배포할 수 있습니다. 기존 클라우드 커넥터 배포가 있는 경우 아직 클라우드 커넥터 버전 2.1로 업그레이드하지 않은 경우 [Upgrade to a new version of Cloud Connector을 참조합니다.](upgrade-to-a-new-version-of-cloud-connector.md)

> [!NOTE]
> Microsoft는 현재 버전의 Cloud Connector Edition 버전 2.1을 지원하고 있습니다. 자동 업데이트를 구성한 경우 클라우드 커넥터가 자동으로 업데이트됩니다. 수동 업데이트를 구성한 경우 릴리스 후 60일 이내에 버전 2.1로 업그레이드해야 합니다. Microsoft는 2.1 릴리스 이후 60일 동안 이전 버전을 지원하여 업그레이드 시간을 허용합니다. 

> [!NOTE]
> 클라우드 커넥터 버전 2.1 이상의 경우 호스트 어플라이언스에 4.6.1 .NET Framework 이상이 설치되어 있어야 합니다. 

> [!IMPORTANT]
> 성공적인 배포를 위해 cmdlet을 실행하여 비즈니스용 Skype 클라우드 커넥터 버전 시작한 콘솔 세션과 항상 동일한 콘솔 세션을 사용하십시오. 배포 및 구성 중에 다른 세션으로 전환하지 않도록 합니다. 

> [!NOTE]
> 배포의 첫 번째 어플라이언스에 한해 사이트 디렉터리에 대한 공유 만들기, 비트 다운로드, Windows Server ISO 이미지에서 VHDX(가상 하드 디스크) 파일 준비 등 몇 가지 단계를 수행합니다. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>설치 비즈니스용 Skype 클라우드 커넥터 버전 다운로드

1. 클라우드 커넥터 VM이 실행될 호스트 서버에서 설치 파일을 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 다운로드합니다. . 

    > [!IMPORTANT]
    > 설치하는 동안 추가 파일이 다운로드될 수 있기 때문에 클라우드 커넥터를 설치하는 동안 호스트 서버가 인터넷에 액세스할 수 있어야 합니다. 

2. 설치 관리자를 실행하고 설치 중에 기본값을 수락합니다.

3. 설치가 성공적으로 완료 지 확인 합니다.

## <a name="verify-the-installation-and-configure-the-environment"></a>설치 확인 및 환경 구성

1. 관리자 권한으로 PowerShell 콘솔을 열고 다음 cmdlet을 비즈니스용 Skype 클라우드 커넥터 버전 cmdlet을 사용할 수 있도록 합니다.

   ```powershell
   Get-Command *-Cc*
   ```

    명령은 명령에 대한 cmdlet 목록을 반환해야 비즈니스용 Skype 클라우드 커넥터 버전.

2. VHD, SfBBits 및 VersionInfo 파일은 사이트 디렉터리에 **저장됩니다.**

    다음 cmdlet을 사용하여 **사이트** 디렉터리의 위치를 찾을 수 있습니다.

   ```powershell
   Get-CcSiteDirectory
   ```

    명령은 파일 시스템의 위치를 반환해야 합니다. 위치는 로컬 폴더 또는 파일 공유일 수 있습니다. 사이트 디렉터리의 기본 **위치는** %USERPROFILE%\CloudConnector\SiteRoot입니다. 기본 위치는 각 사이트에서 만든 첫 번째 어플라이언스에서 파일 공유로 변경해야 합니다.

    선택한 위치는 다음을 선택해야 합니다.

   - 각 사이트에서 만든 첫 번째 어플라이언스에 만들어집니다.

   - 같은 사이트의 다른 호스트 서버(어플라이언스)에서 액세스할 수 있는 공유 폴더입니다.

     사이트 **디렉터리를** 기본값이 다른 위치로 설정하기 위해 다음 cmdlet을 실행합니다.

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    사이트에 대해 HA(고가용성)를 배포하는 경우 cmdlet을 실행하여 사이트 디렉터리를 사이트 내의 각 호스트 서버의 동일한 위치로 설정해야 합니다. 

    사이트에 로그온하여 각 어플라이언스를 배포할 때 현재 로그온 계정에 사이트 디렉터리에 대한 올바른 액세스 **권한이 있는지 확인합니다.**

3. **Appliance Directory는** 외부 인증서, 인스턴스 비즈니스용 Skype 클라우드 커넥터 버전 저장되는 위치의 로컬 작업 루트 디렉터리입니다. 기본 위치는 %USERPROFILE%\CloudConnector\ApplianceRoot입니다.

    **Appliance Directory의** 위치를 찾으면 다음 cmdlet을 실행합니다.

   ```powershell
   Get-CcApplianceDirectory
   ```

    **Appliance Directory를** 기본값이 다른 위치로 설정하기 위해 다음 cmdlet을 실행합니다.

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    Appliance Directory는 어플라이언스의 로컬 폴더로 설정해야 합니다. 배포를 시작하기 전에 **Appliance 디렉터리만** 비즈니스용 Skype 클라우드 커넥터 버전 합니다. 배포 후에 변경하는 경우 호스트 서버를 다시 배포해야 합니다.

    > [!IMPORTANT]
    > Appliance Directory **경로에는** 공백이 포함되어 있지 않을 수 있습니다.

## <a name="set-the-path-for-the-external-edge-certificate"></a>외부 에지 인증서의 경로 설정

- 다음 cmdlet을 실행하여 파일 이름을 비롯한 경로를 외부 에지 인증서로 설정할 수 있습니다. 예: C:\certs\cce\ap.contoso.com.pfx. 인증서는 개인 키를 포함해야 합니다.

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > -Target 매개 변수는 버전 1.4.2 이상과 관련이 있습니다. 

    파일 이름을 포함하여 외부 인증서의 전체 경로를 지정합니다. 인증서는 로컬 또는 파일 공유에 저장할 수 있습니다. 인증서가 공유 폴더에 저장된 경우 각 사이트의 첫 번째 어플라이언스에 공유 폴더를 만들어야 하며 동일한 사이트에 속하는 다른 어플라이언스에서 공유 폴더에 액세스할 수 있어야 합니다. 이 cmdlet은 외부 인증서를 **Appliance Directory에 복사합니다.**

    > [!IMPORTANT]
    > 클라우드 커넥터 버전 **1.4.2** 이상으로 업데이트한 경우 준비된 외부 인증서에 개인 키와 루트 CA 인증서 및 중간 CA 인증서를 포함한 전체 인증서 체인이 포함되어 있는지 확인 **아직 클라우드 커넥터 버전 1.4.2로** 업데이트하지 않은 경우 준비된 외부 인증서에 개인 키가 포함되어 있는지 확인 이 외부 인증서는 기본적으로 인증 기관에서 신뢰하는 인증 기관에서 Windows 합니다.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>외부 PSTN 게이트웨이/SBC 인증서의 경로 설정

중재 서버와 PSTN 게이트웨이/SBC 간에 TLS를 사용하는 경우 다음 cmdlet을 실행하여 파일 이름을 비롯한 경로를 게이트웨이 인증서로 설정합니다. 예: C:\certs\cce\sbc.contoso.com.cer. 인증서는 게이트웨이에 할당된 인증서에 대한 루트 CA 및 중간 체인을 포함해야 합니다.

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> -Target 매개 변수는 버전 1.4.2 이상과 관련이 있습니다. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Hyper-V 관리자에서 가상 스위치 만들기

1. Hyper-V **관리자** 가상 스위치 관리자를  >  **열고** 새 가상 스위치 **관리자 를 선택합니다.**

2. 외부 가상 스위치를 만들고 내부 네트워크 도메인에 연결된 실제 네트워크 어댑터에 바인딩합니다.

    이 가상 스위치에 대해 관리 **운영 체제에서** 이 네트워크 어댑터를 공유하도록 허용을 선택합니다.

3. 외부 가상 스위치를 만들고 인터넷으로 라우팅된 실제 네트워크 어댑터에 바인딩합니다.

    관리 운영 체제가 이 가상 스위치에 대해 이 **네트워크** 어댑터를 공유할 수 있도록 허용을 선택하지 않습니다.

4. 경계 네트워크를 내부 네트워크 도메인 **SfB CCE Corpnet 스위치에** 연결하는 스위치의 이름을 설정하십시오.

    경계 네트워크를 인터넷 **SfB CCE** 인터넷 스위치에 연결하는 스위치의 이름을 설정하십시오.

## <a name="update-the-cloudconnectorini-configuration-file"></a>구성 CloudConnector.ini 업데이트

Plan [for](plan-skype-for-business-cloud-connector-edition.md) CloudConnector.ini 항목의 [배포](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) 매개 변수 결정에서 수집한 정보를 사용하여 비즈니스용 Skype 클라우드 커넥터 버전 준비합니다.

파일을 업데이트하기 위해 먼저 다음 cmdlet을 실행하여 샘플 템플릿(CloudConnector.Sample.ini.

```powershell
Export-CcConfigurationSampleFile
```

샘플 템플릿은 **Appliance Directory 에 저장됩니다.**

환경의 값으로 업데이트한 후 파일을 Appliance Directory CloudConnector.ini **저장합니다.** **Get-CcApplianceDirectory를** 실행하여 Appliance 디렉터리의 경로를 **확인할 수 있습니다.**

파일 .ini 업데이트할 때 다음을 고려합니다.

> [!NOTE]
> 이 섹션에서는 .ini 파일에 대한 일부 값에 대해 설명하지는 않습니다. 여기서는 특별한 고려 사항이 있는 값만 설명합니다. 전체 목록은 Plan for [비즈니스용 Skype 클라우드 커넥터 버전](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) [참조하십시오.](plan-skype-for-business-cloud-connector-edition.md) 추가 어플라이언스 또는 새 사이트에 대해 변경해야 하는 값에 대한 자세한 내용은 Deploy multiple sites in Cloud Connector 항목의 [HA(고가용성)가](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) 포함된 단일 사이트와 다중 사이트 배포를 [참조하세요.](deploy-multiple-sites-in-cloud-connector.md) 

- **SiteName:** 기본값은 **Site1입니다.** **Register-CcAppliance를** 실행하여 기존 또는 새 사이트에 어플라이언스를 등록할 때 Cmdlet은 **SiteName을** 사용하여 등록할 사이트를 결정하기 때문에 클라우드 커넥터를 배포하기 전에 업데이트해야 합니다.

     어플라이언스를 새 사이트에 등록하려면 **SiteName** 값이 고유해야 하고 기존 사이트와 달라야 합니다. 기존 사이트에 어플라이언스를 등록하려는 경우 .ini 파일의 **SiteName** 값은 조직 구성 또는 조직 구성에 정의된 Microsoft 365 Office 365 합니다. 한 사이트에서 다른 사이트로 구성 파일을 복사하는 경우 그에 따라 각 사이트에 **대해 SiteName** 값을 업데이트해야 합니다.

- **ServerName:** 서버 이름은 도메인 이름을 포함하지 말고 15자로 제한해야 합니다.

- **HardwareType:** 값을 null로 설정하거나 설정하지 않은 경우 **Normal의** 기본값이 사용됩니다. Plan  for 비즈니스용 Skype 클라우드 커넥터 버전.에 설명된 바와 같이 더 큰 버전의 클라우드 커넥터를 배포하여 호스트 컴퓨터당 500개 동시 [통화를 비즈니스용 Skype 클라우드 커넥터 버전.](plan-skype-for-business-cloud-connector-edition.md) **동시** 통화 50회를 지원하는 소규모 배포에는 최소를 사용 합니다.

- **인터넷/Corpnet/Management 가상 스위치:** 만든 가상 스위치의 이름을 추가합니다. 관리 가상 스위치의 경우 기본값을 그대로 두면 됩니다. 배포 스크립트는 배포 시작 시 관리 가상 스위치를 만들고 배포가 완료되면 삭제합니다.

- **ManagementIPPrefix:** 네트워크 섹션의 ManagementIPPrefix는 다른 내부 IP와 다른 서브넷이 되어야 합니다. 예를 들어 기본값에 따르면 ManagementIPPrefix는 192.168.213.0인 반면 AD IPAddress는 192.168.0.238입니다.

    배포 스크립트는 각 가상 컴퓨터에 관리 네트워크 어댑터를 만들고 관리 IP를 할당한 다음 관리 가상 스위치에 연결합니다. 이렇게 하면 호스트 서버가 이 관리 네트워크를 통해 각 가상 컴퓨터에 연결하고 관리할 수 있습니다. 배포가 완료되면 관리 가상 스위치가 삭제됩니다.

- **기본 VM** 특정 구성: 설정 변환-CcIsoToVhdx cmdlet에 대해 구성해야 합니다. 

    기본 VM 이미지 준비 중에는 기본 VM이 내부 네트워크 스위치에 연결됩니다. 다음 설정은 VM이 인터넷에 액세스할 수 있도록 하는 데 중요합니다.

  - [Common] BaseVMIP: 기본 VM에 할당할 corpnet IP 주소입니다.

  - [네트워크] CorpnetDefaultGateway: 기본 VM에 할당할 기본 게이트웨이입니다.

  - [네트워크] CorpnetDNSIPAddress: 기본 VM에 할당할 DNS IP 주소입니다.

  - [네트워크] WSUSServer: Windows 서버 업데이트 서비스의 IP 주소입니다.

  - [네트워크] WSUSStatusServer: Windows 서버 업데이트 서비스 상태 서버의 IP 주소입니다.

  - [네트워크] EnableReferSupport: IP/PBX에 대한 트렁크 구성에서 SIP REFER 지원을 사용할지 여부를 정의합니다.

- **내부 IPS:**

  - 서브넷 마스크 CorpnetIPPrefixLength가 올바른지 확인합니다.

  - 이러한 내부 IP에 대한 IP 충돌이 없는지 확인

- **외부 IPS:**

  - MR 공용 IP의 경우: NAT가 아닌 경우 ExternalMRIP 또는 NAT용 ExternalMRPublicIP를 지정합니다.

  - ExternalSIPIP와 ExternalMRIP는 동일할 수 있습니다.

  - 서브넷 마스크 InternetIPPrefixLength가 올바른지 확인합니다.

  - 이러한 외부 IP에 대한 IP 충돌이 없는지 확인

- **게이트웨이:**

  - 게이트웨이가 하나뿐인 경우 보조 게이트웨이에 대한 섹션을 제거합니다. 게이트웨이가 두 개 이상인 경우 기존 게이트웨이를 복사하여 붙여넣은 다음 업데이트하여 추가 섹션을 만드십시오.

  - 게이트웨이의 IP 주소와 포트가 올바른지 확인합니다.

  - PSTN 게이트웨이 수준 HA를 지원하기 위해 보조 게이트웨이를 그대로 두고 사용할 게이트웨이를 더 추가합니다. 기존 항목을 복사하여 붙여넣은 다음 업데이트할 수 있습니다.

- 원하는 경우 LocalRoute 값을 업데이트하여 아웃바운드 통화 번호를 제한할 수 있습니다.

## <a name="download-the-bits-to-the-site-directory"></a>비트를 사이트 디렉터리로 다운로드

다음 cmdlet을 실행하여 비트 및 버전 정보 파일을 사이트 디렉터리에 **다운로드합니다.**

```powershell
Start-CcDownload
```

> [!NOTE]
> 첫 번째 어플라이언스에만 이 단계를 수행해야 합니다. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>다운로드한 ISO 파일에서 기본 VHDX(가상 디스크) 준비

이 단계에서는 ISO 이미지의 VHDX(가상 하드 디스크) Windows Server 2012 준비합니다. VHDX는 배포 중에 가상 컴퓨터를 만드는 데 사용됩니다. 임시 가상 컴퓨터(기본 VM)가 만들어지며 Windows Server 2012 ISO 파일에서 설치됩니다. VM을 만든 후 몇 가지 필수 구성 요소가 설치되고 최신 Windows 업데이트가 적용됩니다. 결국 기본 VM이 일반화되고(sysprep) 정리되고 생성된 가상 디스크 파일만 남게 됩니다.

> [!NOTE]
> 첫 번째 어플라이언스에만 이 단계를 수행해야 합니다. 

이 단계를 진행하기 전에 corpnet 스위치를 만들어야 합니다. 또한 다음 설정이 파일에서 올바르게 CloudConnector.ini 확인합니다.

- [네트워크] CorpnetSwitchName

- [Common] BaseVMIP

- [네트워크] CorpnetIPPrefixLength

- [네트워크] CorpnetDefaultGateway

- [네트워크] CorpnetDNSIPAddress

관리자 권한으로 PowerShell 콘솔을 시작하고 다음 cmdlet을 실행하여 ISO 이미지를 VHD(가상 하드 디스크)로 변환합니다.

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

파일 이름을 포함하여 ISO 이미지에 대한 전체 경로를 지정합니다. 예: C:\ISO\WindowsServer2012R2.iso.

생성된 VHD 파일은 사이트 디렉터리  \Bits\VHD 폴더에 저장됩니다. **Get-CcSiteDirectory 를** 실행하여 사이트 디렉터리의 경로를 얻을 수 있습니다. 

> [!IMPORTANT]
> 기본적으로 프록시 설정은 기본 VM에서 구성되지 않습니다. 네트워크 환경에서 Windows 업데이트를 통해 VM을 업데이트하기 위해 프록시가 필요한 경우 "Convert-CcIsoToVhdx"를 실행할 때 -PauseBeforeUpdate 스위치를 추가해야 합니다. 스크립트는 업데이트가 Windows 전에 일시 중지됩니다. VM에서 프록시를 수동으로 설정할 수 있습니다. 프록시를 설정하고 VM이 인터넷에 액세스할 수 있는 후 스크립트를 다시 시작하여 나머지 단계를 완료할 수 있습니다. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>다중 사이트 배포를 위한 VHD 만들기

이 단계는 다중 사이트 배포에만 적용되는 선택적 단계입니다.

다중 사이트 배포를 배포하는 경우 각 사이트의 VHD로 ISO를 변환할 필요가 없습니다. 첫 번째 사이트에 대해 만든 VHDX를 두 번째 사이트의 호스트 서버에 복사할 수 있습니다.

 추가 사이트의 경우 호스트 서버에서 동일한 파일 **위치(Site Directory** \Bits\VHD 폴더)에 파일을 복사합니다.

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>PowerShell 실행 정책을 RemoteSigned로 설정

제공된 PowerShell 스크립트를 사용하려면 실행 정책을 RemoteSigned로 설정해야 합니다. 현재 설정을 표시하기 위해 관리자 권한으로 PowerShell 콘솔을 열고 다음 cmdlet을 실행합니다.

```powershell
Get-ExecutionPolicy
```

"RemoteSigned"로 설정되지 않은 경우 다음 cmdlet을 실행하여 변경합니다.

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>호스트 컴퓨터의 로컬 그룹 정책 변경(버전 1.4.1 이전 버전)

> [!NOTE]
> 클라우드 커넥터 버전 1.4.2 이상에서는 이 작업이 필요하지 않습니다. 

CceService 계정은 배포 중에 비즈니스용 Skype 클라우드 커넥터 버전 생성됩니다. 클라우드 커넥터 관리 서비스를 실행하며 클라우드 커넥터 관리 서비스를 제거하기 위한 권한이 cloudconnector.msi. 사용자가 로그오프할 때 사용자 레지스트리를 언로드하지 못하도록 지정하려면 클라우드 커넥터 호스트 컴퓨터의 그룹 정책 설정을 변경해야 합니다. 아래 단계를 따릅니다.

### <a name="to-change-the-group-policy-setting"></a>그룹 정책 설정을 변경합니다.

1. gpedit.msc를 실행하여 그룹 정책 편집기를 열 수 있습니다. 

2. 그룹 **정책 편집기에서** 관리 템플릿 > > UserProfile > 로그오프 시 사용자 레지스트리를 강제로 언로드하지 않습니다. 

3. 해당 값을 사용으로 **설정합니다.**

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a>조직 또는 Microsoft 365 Office 365 설정

온라인 Microsoft 365 Office 365 조직 또는 비즈니스용 Skype 조직이 전화 시스템 필요합니다. 클라우드 커넥터를 사용하기 전에 테넌트가 설정 및 구성되어 있는지 확인

일부 Microsoft 365 및 Office 365 단계에 따라 TRPS(테넌트 원격 PowerShell)를 사용하여 조직 또는 Microsoft 365 Office 365 구성해야 합니다. **이 서버는 호스트 서버에 설치해야 합니다.** PowerShell용 비즈니스용 Skype 온라인 모듈을 다운로드할 수 있습니다. [비즈니스용 Skype Online,](https://www.microsoft.com/download/details.aspx?id=39366)Windows PowerShell 있습니다.

클라우드 커넥터 비즈니스용 Skype 관리에 대한 전용 관리자 계정(예: CceOnlineManagmentAdministrator)을 만들 수 있습니다. 이 계정은 어플라이언스를 추가 또는 제거하고, 자동 OS 업데이트를 사용 또는 사용하지 않도록 설정하고, 자동 이진 업데이트를 사용 또는 사용하지 않도록 설정하는 데 사용됩니다. 만료될 때마다 서비스에 대해 암호를 변경할 필요가 있도록 이 계정의 암호를 만료되지 않습니다.