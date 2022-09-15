---
title: VDI(Virtualized Desktop Infrastructure)용 Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: VDI(가상화된 데스크톱 인프라) 환경에서 Microsoft Teams를 실행하는 방법을 알아봅니다.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 92d46cacd510f448943deba86a6ed25d4f4360ab
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706515"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>VDI(Virtualized Desktop Infrastructure)용 Teams

이 문서에서는 가상화된 환경에서 Microsoft Teams를 사용하는 데 대한 요구 사항 및 제한 사항에 대해 설명합니다.

## <a name="what-is-vdi"></a>VDI란?

VDI(Virtual Desktop Infrastructure)는 데이터 센터의 중앙 서버에서 데스크톱 운영 체제 및 애플리케이션을 호스트하는 가상화 기술입니다. 이렇게 하면 완전히 보호되고 규정을 준수하는 중앙 집중식 원본을 사용하는 사용자에게 완전하고 개인 설정된 데스크톱 환경을 사용할 수 있습니다.

가상화된 환경의 팀은 채팅 및 공동 작업을 지원합니다. 또한 Azure Virtual Desktop, Citrix 및 VMware 플랫폼을 사용하면 통화 및 모임 기능도 지원됩니다.

또한 Teams는 가상 환경에서 여러 구성을 지원합니다. 여기에는 VDI, 전용, 공유, 영구 및 비영구 모드가 포함됩니다. 기능은 지속적으로 개발 중이며 정기적으로 추가되며, 기능은 시간이 지남에 따라 확장됩니다.

가상화된 환경에서 Teams를 사용하는 것은 가상화되지 않은 환경에서 Teams를 사용하는 경우와 다소 다를 수 있습니다. 예를 들어 일부 고급 기능은 가상화된 환경에서 사용할 수 없으며 비디오 해상도가 다를 수 있습니다.

최적의 사용자 환경을 보장하려면 이 문서의 지침을 따르세요.

> [!Note]
> 다양한 플랫폼의 Teams VDI에 대한 자세한 내용은 [플랫폼별 Teams 기능을](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3) 참조하세요.

## <a name="teams-on-vdi-components"></a>VDI 구성 요소의 Teams

가상화된 환경에서 Teams를 사용하려면 다음 구성 요소가 필요합니다.

- **가상화 브로커**: Azure와 같은 가상화 공급자에 대한 리소스 및 연결 관리자
- **가상 데스크톱**: Teams를 실행하는 VM(Virtual Machine) 스택
- **씬 클라이언트**: 사용자가 물리적으로 인터페이스하는 디바이스
- **Teams 데스크톱 앱**: Teams 데스크톱 클라이언트 앱

## <a name="teams-on-vdi-requirements"></a>VDI 요구 사항의 Teams

### <a name="virtualization-provider-requirements"></a>가상화 공급자 요구 사항

Teams 데스크톱 앱은 주요 가상화 솔루션 공급자를 통해 유효성을 검사했습니다. 여러 시장 공급자를 사용하면 가상화 솔루션 공급자에게 문의하여 최소 요구 사항을 충족하는지 확인하는 것이 좋습니다.
  
현재 AV(오디오/비디오) 최적화가 있는 VDI의 Teams는 Azure Virtual Desktop, Citrix 및 VMware를 사용하여 인증을 받았습니다. 이 섹션의 정보를 검토하여 적절한 기능에 대한 모든 요구 사항을 충족하는지 확인합니다.

### <a name="platforms-certified-for-teams"></a>Teams용으로 인증된 플랫폼

다음 플랫폼에는 Teams용 가상 데스크톱 인프라 솔루션이 있습니다.

|플랫폼|솔루션|
|----|---|
|![Microsoft를 나타내는 로고입니다.](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Azure Virtual Desktop</a>, <a href="/windows-365/enterprise/teams-on-cloud-pc" target="_blank">Windows 365</a> |
|![Citrix를 나타내는 로고입니다.](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps 및 데스크톱</a> |
|![VMware를 나타내는 로고입니다.](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="azure-virtual-desktop"></a>Azure Virtual Desktop

Azure Virtual Desktop은 VDI의 Teams에 대한 AV 최적화를 제공합니다. 요구 사항 및 설치에 대한 자세한 내용은 [Azure Virtual Desktop에서 Teams 사용을 참조하세요](/azure/virtual-desktop/teams-on-wvd).

### <a name="windows-365"></a>Windows 365

Windows 365 Azure Virtual Desktop에서 제공하는 AV 최적화를 사용하여 클라우드 PC에서 최적의 Teams 환경을 보장합니다. 요구 사항 및 설치에 대한 자세한 내용은 [클라우드 PC에서 Teams 사용을](/windows-365/enterprise/teams-on-cloud-pc) 참조하세요.

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Citrix Virtual Apps 및 데스크톱 요구 사항

Citrix Virtual Apps 및 데스크톱(이전의 XenApp 및 XenDesktop)은 VDI의 Teams에 대한 AV 최적화를 제공합니다. Citrix Virtual Apps 및 데스크톱을 통해 VDI의 Teams는 채팅 및 공동 작업 외에도 통화 및 모임 기능을 지원합니다.

Citrix 다운로드 사이트에서 최신 버전의 Citrix Virtual Apps 및 데스크톱 [을 다운로드할 수 있습니다](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/). (먼저 로그인해야 합니다.) 필요한 구성 요소는 기본적으로 [CWA(Citrix 작업 영역 앱)](https://www.citrix.com/downloads/workspace-app/) 및 VDA(가상 배달 에이전트)에 번들로 제공됩니다. CWA 또는 VDA에 추가 구성 요소 또는 플러그 인을 설치할 필요가 없습니다.

최신 서버 및 클라이언트 요구 사항은 Citrix 웹 사이트의 [Microsoft Teams 최적화](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html) 문서를 참조하세요.

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>VMware Horizon 작업 영역 및 데스크톱 요구 사항

VMware Horizon은 하이브리드 클라우드에서 가상 데스크톱 및 앱을 안전하게 배달하기 위한 최신 플랫폼입니다. 뛰어난 최종 사용자 환경을 제공하기 위해 VMware Horizon은 Teams에 대한 미디어 최적화를 제공합니다. 이 최적화는 가상 데스크톱 및 앱 전체의 전반적인 생산성을 향상시키고 Teams를 사용하여 통화 및 모임을 할 때 사용자 환경을 향상시킵니다.

VMware 다운로드 페이지에서 최신 버전의 [VMware](https://customerconnect.vmware.com/downloads/#all_products) Horizon을 다운로드할 수 있습니다. 필요한 미디어 최적화 구성 요소는 기본적으로 Horizon 에이전트 및 Horizon 클라이언트의 일부이며 Teams 최적화 기능을 사용하기 위해 추가 플러그 인을 설치할 필요가 없습니다.

Teams에 대한 미디어 최적화를 구성하는 방법에 대한 최신 요구 사항 및 지침을 얻으려면 VMware 웹 사이트의 [Microsoft Teams용 미디어 최적화 구성](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html) 문서를 참조하세요.

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>VDI에서 Teams 데스크톱 앱 설치 또는 업데이트

MSI 패키지를 사용하여 컴퓨터별 설치 또는 사용자별 설치를 사용하여 VDI용 Teams 데스크톱 앱을 배포할 수 있습니다. 사용할 방법을 결정하는 방법은 영구 설정 또는 비영구 설정 사용 여부와 조직의 관련 기능 요구 사항에 따라 달라집니다.

전용 영구 설정의 경우 컴퓨터별 및 사용자별 설치가 모두 작동합니다. 그러나 비영구 설정의 경우 Teams는 효율적으로 작동하려면 컴퓨터별 설치가 필요합니다. [비영구 설정 섹션을](#non-persistent-setup) 참조하세요.

컴퓨터별 설치를 사용하면 자동 업데이트가 비활성화됩니다. 즉, Teams 앱을 업데이트하려면 최신 버전으로 업데이트하려면 현재 버전을 제거해야 합니다. 사용자별 설치를 사용하면 자동 업데이트가 사용하도록 설정됩니다.

> [!IMPORTANT]
> VDI 환경에서 Teams 데스크톱 앱을 최신 상태로 유지합니다. 릴리스 날짜가 현재 버전의 릴리스 날짜보다 90일 이상 오래된 Teams 데스크톱 앱 [버전은](/officeupdates/teams-app-versioning) 지원되지 않습니다. 지원되지 않는 Teams 데스크톱 앱 버전은 사용자에게 차단 페이지를 표시하고 앱을 업데이트하도록 요청합니다.

대부분의 VDI 배포의 경우 컴퓨터별 설치를 사용하여 Teams를 배포하는 것이 좋습니다. 최신 Teams 버전으로 업데이트하려면 제거 절차와 최신 Teams 버전 배포를 시작합니다.

VDI 환경에서 Teams AV 최적화가 제대로 작동하려면 씬 클라이언트 디바이스가 인터넷에 액세스할 수 있어야 합니다. 씬 클라이언트 디바이스에서 인터넷 액세스를 사용할 수 없는 경우 최적화 시작에 성공하지 못합니다. 즉, 사용자가 최적화되지 않은 미디어 상태에 있습니다.

#### <a name="dedicated-persistent-setup"></a>전용 영구 설정

전용 영구 설정에서는 사용자가 로그오프한 후 사용자의 로컬 운영 체제 변경 내용이 유지됩니다. 영구 설치를 위해 Teams는 사용자별 및 컴퓨터별 설치를 모두 지원합니다.

다음은 권장되는 최소 VM 구성입니다.

|매개 변수  |워크스테이션 운영 체제  |서버 운영 체제  |
|---------|---------|---------|
|vCPU   |    코어 2개     |  4, 6 또는 8코어<br>기본 NUMA(비일률 메모리 액세스) 구성을 이해하고 그에 따라 VM을 구성하는 것이 중요합니다.     |
|RAM     |   4gb      | 사용자당 512MB~1GB        |
|저장소    | 8GB        | 40GB ~60GB        |

#### <a name="non-persistent-setup"></a>비영구 설정

비영구 설정에서는 사용자가 로그오프한 후 사용자의 로컬 운영 체제 변경 내용이 유지되지 않습니다. 이러한 설정은 일반적으로 공유되는 다중 사용자 세션입니다. VM 구성은 사용자 수와 사용 가능한 물리적 서버 리소스에 따라 달라집니다.

비영구 설정의 경우 Teams 데스크톱 앱을 컴퓨터별로 골든 이미지에 설치해야 합니다. 이렇게 하면 사용자 세션 중에 Teams 앱을 효율적으로 시작할 수 있습니다. 자세한 내용은 [VDI에서 Teams 데스크톱 앱 설치 또는 업데이트를](#install-or-update-the-teams-desktop-app-on-vdi) 참조하세요.

비영구 설정에서 Teams를 사용하려면 효율적인 Teams 런타임 데이터 동기화를 위해 프로필 캐싱 관리자가 필요합니다. 효율적인 데이터 동기화를 통해 사용자 세션 중에 적절한 사용자별 정보(예: 사용자의 데이터, 프로필 또는 설정)가 캐시됩니다. 다음 두 폴더의 데이터가 동기화되었는지 확인합니다.<br>

- `C:\Users\username\AppData\Local\Microsoft\IdentityCache (%LocalAppData%\Microsoft\IdentityCache)`
- `C:\Users\username\AppData\Roaming\Microsoft\Teams (%AppData%\Microsoft\Teams)`

> [!NOTE]
> Teams 앱에 애플리케이션을 실행하는 데 필요한 런타임 데이터와 파일이 있는지 확인하려면 로밍 폴더(또는 폴더 리디렉션을 사용하는 경우 캐싱 관리자)가 필요합니다. 이는 네트워크 대기 시간 문제 또는 네트워크 결함을 완화하는 데 필요하며, 이로 인해 사용할 수 없는 데이터 및 파일로 인해 애플리케이션 오류와 느린 환경이 발생합니다.

[FSLogix](/fslogix/overview)와 같은 다양한 캐싱 관리자 솔루션을 사용할 수 있습니다. 특정 구성 지침은 캐싱 관리자 공급자에게 문의하세요.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>비영구 설정에 대한 Teams 캐시된 콘텐츠 제외 목록

Teams 캐싱 폴더 `%AppData%/Microsoft/Teams`에서 다음을 제외합니다. 이러한 항목을 제외하면 사용자 캐싱 크기를 줄여 비영구 설정을 더욱 최적화할 수 있습니다.

- 파일 .txt
- 미디어 스택 폴더
- `%AppData%\Microsoft\Teams\meeting-addin\Cache`

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>엔터프라이즈용 Microsoft 365 앱 고려 사항

VDI에서 엔터프라이즈용 Microsoft 365 앱 사용하여 Teams를 배포할 때 다음을 고려합니다.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>엔터프라이즈용 Microsoft 365 앱 통해 Teams의 새 배포

엔터프라이즈용 Microsoft 365 앱 통해 Teams를 배포하기 전에 컴퓨터별 설치를 사용하여 배포된 경우 기존 Teams 앱을 먼저 제거해야 합니다.

엔터프라이즈용 Microsoft 365 앱 통한 Teams는 사용자별로 설치됩니다. 자세한 내용은 [VDI에서 Teams 데스크톱 앱 설치 또는 업데이트를](#install-or-update-the-teams-desktop-app-on-vdi) 참조하세요.

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>엔터프라이즈용 Microsoft 365 앱 업데이트를 통한 Teams 배포

Teams도 기존 엔터프라이즈용 Microsoft 365 앱 설치에 추가되고 있습니다. 엔터프라이즈용 Microsoft 365 앱 사용자별 Teams만 설치하므로 [VDI 섹션에서 Teams 데스크톱 앱 설치 또는 업데이트를](#install-or-update-the-teams-desktop-app-on-vdi) 참조하세요.

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>컴퓨터별 설치 및 엔터프라이즈용 Microsoft 365 앱 Teams 사용

엔터프라이즈용 Microsoft 365 앱 Teams의 컴퓨터별 설치를 지원하지 않습니다. 컴퓨터별 설치를 사용하려면 엔터프라이즈용 Microsoft 365 앱 Teams를 제외해야 합니다. [VM에 Teams 데스크톱 앱 배포](#deploy-the-teams-desktop-app-to-the-vm) 및 [엔터프라이즈용 Microsoft 365 앱 섹션을 통해 Teams 배포를 제외하는 방법을](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) 참조하세요.

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>엔터프라이즈용 Microsoft 365 앱 통해 Teams 배포를 제외하는 방법

Teams 및 엔터프라이즈용 Microsoft 365 앱 대한 자세한 내용은 엔터프라이즈용 Microsoft 365 앱 및 [그룹 정책 사용하여 Teams 설치를 제어하는](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams) [새로운 설치에서](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-microsoft-365-apps) Teams를 제외하는 방법을 참조하세요.

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>VM에 Teams 데스크톱 앱 배포

⁠1. 다음 링크 중 하나를 사용하여 VDI VM 운영 체제와 일치하는 Teams MSI 패키지를 다운로드합니다.
    - [32비트 버전](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [64비트 버전](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)
    > [!NOTE]
    > 정부 클라우드의 경우 MSI 파일에 대한 다운로드 링크 [는 MSI(Windows Installer)를 사용하여 Teams 대량 설치](msi-deployment.md) 를 참조하세요.

2. 다음 명령 중 하나를 실행하여 VDI VM에 MSI를 설치합니다.

    - 사용자별 설치(기본값)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        이 프로세스는 사용자 폴더에 Teams `%AppData%` 를 설치하는 기본 설치입니다. 이 시점에서 골든 이미지 설정이 완료되었습니다.

        > [!IMPORTANT]
        > Teams는 비영구 설정에서 사용자별 설치와 제대로 작동하지 않습니다.

    - 컴퓨터별 설치

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        이 프로세스는 필요한 레지스트리 키를 컴퓨터에 추가하여 Teams 설치 관리자가 VDI 인스턴스임을 알 수 있도록 합니다.  설치 프로그램이 없으면 설치 관리자가 "설치에 실패했습니다.  VDI 환경이 검색되지 않은 경우 모든 사용자에 대해 설치할 수 없습니다."

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        이 프로세스는 Teams를 `%ProgramFiles(x86)%` 32비트 운영 체제의 폴더와 64비트 운영 체제의 `%ProgramFiles%` 폴더에 설치합니다. 이 시점에서 골든 이미지 설정이 완료되었습니다.

        > [!IMPORTANT]
        >  비영구 설정에는 컴퓨터당 Teams를 설치해야 합니다.

        다음 대화형 로그온 세션이 시작되면 Teams가 시작되고 자격 증명을 요청합니다.

        > [!NOTE]
        > 이러한 예제에서는 매개 변수도 사용합니다 `ALLUSERS=1` . 이 매개 변수를 설정하면 **Teams Machine-Wide Installer** 가 **제어판** **프로그램 및 기능** 및 컴퓨터의 모든 사용자에 대한 **Windows 설정** 의 **앱 & 기능에** 표시됩니다. 그러면 관리자 자격 증명이 있는 경우 모든 사용자가 Teams를 제거할 수 있습니다.
        >
        > 의 차이점 `ALLUSERS=1` 을 이해하는 것이 중요합니다 `ALLUSER=1`. 이 매개 변수는 `ALLUSERS=1` 비 VDI 및 VDI 환경에서 사용할 수 있지만 `ALLUSER=1` , 이 매개 변수는 VDI 환경에서만 컴퓨터별 설치를 지정하는 데 사용됩니다.

3. VDI VM에서 MSI를 제거합니다. Teams를 제거하는 방법에는 두 가지가 있습니다.

    - **PowerShell 스크립트**: [Teams 배포 정리](scripts/powershell-script-deployment-cleanup.md) PowerShell 스크립트를 사용하여 Teams를 제거하고 사용자에 대한 Teams 폴더를 제거할 수 있습니다. 컴퓨터에 Teams가 설치된 각 사용자 프로필에 대한 스크립트를 실행합니다.
    - **명령줄**: 다음 명령을 실행합니다.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      이 프로세스는 운영 체제 환경에 따라 폴더 또는 `%ProgramFiles%` 폴더에서 `%ProgramFiles(x86)%` Teams를 제거합니다.

## <a name="teams-on-vdi-performance-considerations"></a>VDI에 대한 Teams 성능 고려 사항

다양한 가상화된 설정 구성이 있으며, 각각 최적화에 중점을 두고 있습니다. 예를 들어 구성은 사용자 밀도에 초점을 맞출 수 있습니다. 계획할 때 조직의 워크로드 요구 사항에 따라 설정을 최적화하는 데 도움이 되도록 다음을 고려하세요.

- **최소 요구 사항**: 일부 워크로드에는 최소 요구 사항을 초과하는 리소스를 사용하는 설정이 필요할 수 있습니다. 예를 들어 더 많은 컴퓨팅 리소스를 요구하는 애플리케이션을 사용하는 개발자를 위한 워크로드입니다.
- **종속성**: 여기에는 인프라, 워크로드 및 Teams 데스크톱 앱 외부의 기타 환경 고려 사항에 대한 종속성이 포함됩니다.
- **VDI에서 비활성화된 기능**: Teams는 일시적인 CPU 사용률을 개선하는 데 도움이 될 수 있는 VDI에 GPU 집약적 기능을 사용하지 않도록 설정합니다. 사용할 수 없는 기능은 다음과 같습니다.
    - Teams CSS 애니메이션
    - Giphy 자동 시작

## <a name="teams-on-vdi-with-calling-and-meetings"></a>통화 및 모임이 있는 VDI의 Teams

채팅 및 공동 작업 외에도 통화 및 모임이 있는 VDI의 Teams는 지원되는 가상화 공급자 플랫폼에서 사용할 수 있습니다. 지원되는 기능은 WebRTC 미디어 스택 및 가상화 공급자 구현을 기반으로 합니다. 다음 다이어그램에서는 아키텍처에 대한 개요를 제공합니다.

![VDI 아키텍처의 Teams를 보여 주는 다이어그램](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> 현재 VDI에서 AV 최적화 없이 Teams를 실행하고 최적화에 아직 지원되지 않는 기능(예: 앱 공유 시 제공 및 제어)을 사용하는 경우 Teams 리디렉션을 해제하도록 가상화 공급자 정책을 설정해야 합니다. 즉, Teams 미디어 세션이 최적화되지 않습니다. Teams 리디렉션을 해제하는 정책을 설정하는 방법에 대한 단계는 가상화 공급자에게 문의하세요.

### <a name="network-requirements"></a>네트워크 요구 사항

환경을 평가하여 전체 클라우드 음성 및 비디오 배포에 영향을 줄 수 있는 위험 및 요구 사항을 식별하는 것이 좋습니다. [비즈니스용 Skype 네트워크 평가 도구를](https://www.microsoft.com/download/details.aspx?id=53885) 사용하여 네트워크가 Teams에 대한 준비가 되었는지 테스트합니다.

Teams용 네트워크를 준비하는 방법에 대한 자세한 내용은 Teams에 대한 [조직의 네트워크 준비를 참조하세요](prepare-network.md).

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>VDI의 비즈니스용 Skype VDI의 Teams로 마이그레이션

VDI의 비즈니스용 Skype VDI의 Teams로 마이그레이션하는 경우 두 애플리케이션 간의 차이점 외에도 VDI가 구현될 때 몇 가지 차이점이 있습니다. 현재 비즈니스용 Skype VDI에 있는 Teams VDI에서 지원되지 않는 일부 기능은 다음과 같습니다.

- VDI에서 일부 AV 기능을 사용하지 않도록 설정하는 플랫폼별 정책
- 앱 공유 시 제어 권한 부여 및 제어
- 오디오 없이 채팅에서 화면 공유
- 동시 비디오 및 화면 공유 보내기 및 받기

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Chrome 브라우저의 Teams 및 VDI용 Teams 데스크톱 앱

Chrome 브라우저의 Teams는 AV 최적화를 사용하여 VDI용 Teams 데스크톱 앱을 대체하지 않습니다. 채팅 및 공동 작업 환경은 예상대로 작동합니다. 미디어가 필요한 경우 Chrome 브라우저에서 사용자 기대치를 충족하지 못할 수 있는 몇 가지 환경이 있습니다.

- 오디오 및 비디오 스트리밍 환경이 최적이 아닐 수 있습니다. 사용자가 지연되거나 품질이 저하될 수 있습니다.
- 브라우저 설정에서는 디바이스 설정을 사용할 수 없습니다.
- 디바이스 관리는 브라우저를 통해 처리되며 브라우저 사이트 설정에서 여러 설정이 필요합니다.
- Windows 디바이스 관리에서 디바이스 설정을 설정해야 할 수도 있습니다.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>채팅 및 공동 작업을 사용하여 VDI의 Teams

조직에서 Teams에서 채팅 및 공동 작업 기능만 사용하려는 경우 Teams에서 통화 및 모임 기능을 해제하도록 사용자 수준 정책을 설정할 수 있습니다.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>통화 및 모임 기능을 해제하는 정책 설정

Teams 관리 센터 또는 PowerShell을 사용하여 정책을 설정할 수 있습니다. 정책 변경 내용이 전파되는 데 최대 몇 시간이 걸립니다. 지정된 계정에 대한 변경 내용이 즉시 표시되지 않으면 몇 시간 후에 다시 시도하세요.

[**통화 정책**](teams-calling-policy.md): Teams에는 모든 통화 기능이 꺼져 있는 기본 제공 **DisallowCalling** 통화 정책이 포함되어 있습니다. 가상화된 환경에서 Teams를 사용하는 조직의 모든 사용자에게 **DisallowCalling** 정책을 할당합니다.

[**모임 정책**](meeting-policies-overview.md): Teams에는 모든 모임 기능이 꺼져 있는 기본 제공 **AllOff** 모임 정책이 포함되어 있습니다. 가상화된 환경에서 Teams를 사용하는 조직의 모든 사용자에게 **AllOff** 정책을 할당합니다.

#### <a name="assign-policies-using-the-teams-admin-center"></a>Teams 관리 센터를 사용하여 정책 할당

**사용자에게 DisallowCalling** 통화 정책 및 **AllOff** 모임 정책을 할당하려면 다음을 수행합니다.

1. Teams 관리 센터의 왼쪽 탐색에서 **사용자** 로 이동합니다.
2. 사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집** 을 클릭합니다.
3. 다음을 수행합니다.
    1. **통화 정책** 에서 **DisallowCalling을** 클릭합니다.
    2. **모임 정책** 에서 **AllOff** 를 클릭합니다.
4. **적용** 을 클릭합니다.

한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.

1. Teams 관리 센터의 왼쪽 탐색에서 **사용자** 로 이동한 다음 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.
2. **&#x2713;**(확인 표시) 열에서 사용자를 선택합니다. 모든 사용자를 선택하려면 테이블 맨 위에 있는 **&#x2713;** (확인 표시)를 클릭합니다.
3. **설정 편집** 을 클릭하고 원하는 대로 변경한 다음, **적용** 을 클릭합니다.

또는 다음을 수행할 수도 있습니다.

1. Teams 관리 센터의 왼쪽 탐색 영역에서 할당하려는 정책으로 이동합니다. 예를 들면 다음과 같습니다.
    - **음성** > **통화 정책** 으로 이동한 다음 **DisallowCalling을** 클릭합니다.
    - 모임 **모임 정책****으로** >  이동한 다음 **AllOff** 를 클릭합니다.
2. **사용자 관리** 를 선택합니다.
3. **사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 후 **추가** 를 클릭합니다. 추가할 각 사용자에 대해 이 단계를 반복합니다.
4. 사용자 추가가 완료되면 **저장** 을 클릭합니다.

#### <a name="assign-policies-using-powershell"></a>PowerShell을 사용하여 정책 할당

다음 예제에서는 [Grant-CsTeamsCallingPolicy를](/powershell/module/skype/grant-csteamscallingpolicy) 사용하여 사용자에게 호출 정책을 할당 `DisallowCalling` 하는 방법을 보여 줍니다.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

PowerShell을 사용하여 통화 정책을 관리하는 방법에 대한 자세한 내용은 [Set-CsTeamsCallingPolicy를 참조하세요](/powershell/module/skype/set-csteamscallingpolicy).

다음 예제에서는 [Grant-CsTeamsMeetingPolicy를](/powershell/module/skype/grant-csteamsmeetingpolicy) 사용하여 사용자에게 모임 정책을 할당 `AllOff` 하는 방법을 보여 줍니다.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

PowerShell을 사용하여 모임 정책을 관리하는 방법에 대한 자세한 내용은 [Set-CsTeamsMeetingPolicy를 참조하세요](/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>채팅 및 협업을 사용하여 VDI의 Teams 마이그레이션을 통해 통화 및 모임을 통해 Teams 최적화

통화 및 모임 기능을 해제하도록 사용자 수준 정책을 설정하고 AV 최적화를 사용하여 Teams로 마이그레이션하는 채팅 및 공동 작업을 사용하여 VDI에서 Teams의 기존 구현이 있는 경우 VDI 사용자에 대한 해당 Teams의 통화 및 모임 기능을 켜는 정책을 설정해야 합니다.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>통화 및 모임 기능을 켜는 정책 설정

Teams 관리 센터 또는 PowerShell을 사용하여 통화 및 모임 정책을 설정하고 사용자에게 할당할 수 있습니다. 정책 변경 내용이 전파되는 데 몇 시간(몇 시간)이 걸릴 수 있습니다. 지정된 계정에 대한 변경 내용이 즉시 표시되지 않으면 몇 시간 후에 다시 시도하세요.

[**통화 정책**](teams-calling-policy.md): Teams의 통화 정책은 사용자가 사용할 수 있는 통화 기능을 제어합니다. Teams에는 모든 통화 기능이 켜져 있는 기본 제공 **AllowCalling** 통화 정책이 포함되어 있습니다. 모든 호출 기능을 켜려면 **AllowCalling** 정책을 할당합니다. 또는 원하는 통화 기능을 켜고 사용자에게 할당하는 사용자 지정 통화 정책을 만듭니다.

[**모임 정책**](meeting-policies-overview.md): Teams의 모임 정책은 사용자가 만들 수 있는 모임 유형과 조직의 사용자가 예약한 모임 참가자가 사용할 수 있는 기능을 제어합니다. Teams에는 모든 모임 기능이 켜져 있는 기본 제공 **AllOn** 모임 정책이 포함되어 있습니다. 모든 모임 기능을 켜려면 **AllOn** 정책을 할당합니다. 또는 원하는 모임 기능을 켜고 사용자에게 할당하는 사용자 지정 모임 정책을 만듭니다.

#### <a name="assign-policies-using-the-teams-admin-center"></a>Teams 관리 센터를 사용하여 정책 할당

**AllowCalling** 통화 정책 및 **AllOn** 모임 정책을 사용자에게 할당하려면 다음을 수행합니다.

1. Teams 관리 센터의 왼쪽 탐색에서 **사용자** 로 이동합니다.
2. 사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집** 을 클릭합니다.
3. 다음을 수행합니다.
    1. **통화 정책** 에서 **AllowCalling을** 클릭합니다.
    2. **모임 정책** 에서 **AllOn** 을 클릭합니다.
4. **적용** 을 클릭합니다.

한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.

1. Teams 관리 센터의 왼쪽 탐색에서 **사용자** 로 이동한 다음 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.
2. **&#x2713;**(확인 표시) 열에서 사용자를 선택합니다. 모든 사용자를 선택하려면 테이블 맨 위에 있는 **&#x2713;** (확인 표시)를 클릭합니다.
3. **설정 편집** 을 클릭하고 원하는 대로 변경한 다음, **적용** 을 클릭합니다.

또는 다음을 수행할 수도 있습니다.

1. Teams 관리 센터의 왼쪽 탐색 영역에서 할당하려는 정책으로 이동합니다. 예를 들면 다음과 같습니다.
    - **음성** > **통화 정책** 으로 이동한 다음 **AllowCalling을** 클릭합니다.
    - 모임 **모임 정책****으로** >  이동한 다음 **AllOn** 을 클릭합니다.
2. **사용자 관리** 를 선택합니다.
3. **사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 후 **추가** 를 클릭합니다. 추가할 각 사용자에 대해 이 단계를 반복합니다.
4. 사용자 추가가 완료되면 **저장** 을 클릭합니다.

#### <a name="assign-policies-using-powershell"></a>PowerShell을 사용하여 정책 할당

다음 예제에서는 [Grant-CsTeamsCallingPolicy를](/powershell/module/skype/grant-csteamscallingpolicy) 사용하여 사용자에게 호출 정책을 할당 `AllowCalling` 하는 방법을 보여 줍니다.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

PowerShell을 사용하여 통화 정책을 관리하는 방법에 대한 자세한 내용은 [Set-CsTeamsCallingPolicy를 참조하세요](/powershell/module/skype/set-csteamscallingpolicy).

다음 예제에서는 [Grant-CsTeamsMeetingPolicy를](/powershell/module/skype/grant-csteamsmeetingpolicy) 사용하여 사용자에게 모임 정책을 할당 `AllOn` 하는 방법을 보여 줍니다.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

PowerShell을 사용하여 모임 정책을 관리하는 방법에 대한 자세한 내용은 [Set-CsTeamsMeetingPolicy를 참조하세요](/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="control-fallback-mode-in-teams"></a>Teams에서 대체 모드 제어

사용자가 지원되지 않는 엔드포인트에서 연결하는 경우 사용자는 AV가 최적화되지 않은 대체 모드에 있습니다. 다음 레지스트리 `DWORD` 값 중 하나를 설정하여 대체 모드를 사용하지 않도록 설정하거나 사용하도록 설정할 수 있습니다.

- `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback`
- `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback`

대체 모드를 사용하지 않도록 설정하려면 값을 **1** 로 설정합니다. 오디오만 사용하려면 값을 **2** 로 설정합니다. 값이 없거나 **0** 으로 설정된 경우 대체 모드가 활성화됩니다.

이 기능은 Teams 버전 1.3.00.13565 이상에서 사용할 수 있습니다.

## <a name="disable-audio-and-video-settings-for-vdi"></a>VDI에 대한 오디오 및 비디오 설정 사용 안 함

Teams VDI 정책은 Teams 모듈에서 사용할 수 있습니다. 이러한 정책은 활성 상태이며 최적화되지 않은 VDI 환경에 적용됩니다.

- `New-CsTeamsVdiPolicy`
- `Grant-CsTeamsVdiPolicy`
- `Remove-CsTeamsVdiPolicy`
- `Set-CsTeamsVdiPolicy`

> [!NOTE]
> 이는 최적화되지 않은 환경에만 해당됩니다.

### <a name="connect-to-microsoft-teams-powershell"></a>Microsoft Teams PowerShell에 연결

[Microsoft Teams PowerShell 모듈 설치](/Teams/teams-powershell-install.md)의 지침에 따라 Microsoft Teams PowerShell 모듈에 연결합니다. 그런 다음, 다음 명령을 실행하여 모든 VDI cmdlet을 사용할 수 있는지 확인합니다.

```PowerShell
Get-Command -Noun *VDI*
```

### <a name="set-policies-to-limit-calling-features"></a>통화 기능을 제한하는 정책 설정

VDI 정책이 VDI `DisableCallsAndMeetings` 에서 Teams에 로그인하도록 `$true` 설정된 사용자는 다음을 수행할 수 없습니다.

- 전화를 걸 수 있습니다.
- 모임에 참가합니다.
- 채팅에서 화면 공유.

모든 유형의 호출을 사용하지 않도록 설정해야 합니다.

> [!NOTE]
> 이는 최적화되지 않은 환경에만 해당됩니다.

```PowerShell
New-CsTeamsVdiPolicy -Identity DisableCallsAndMeetingsTrue -DisableCallsAndMeetings $true -DisableAudioVideoInCallsAndMeetings $false

<# Assign policy #>
$user = 'meganb@jvteams.xyz'
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName DisableCallsAndMeetingsTrue

<# Wait for some time until the policy is applied #>
Get-CSOnlineUser -Identity $user | FL UserPrincipalName, *vdi*

<# Show all policies #>
Get-CsTeamsVdiPolicy | FT Iden*, Disable*
```

VDI 정책이 VDI `DisableAudioVideoInCallsAndMeetings` 에서 Teams에 로그인하도록 `$true` 설정된 사용자는 다음을 수행합니다.

- 채팅에서 공유를 화면으로 표시할 수 있습니다.
- 모임에 참가하고 화면을 공유하고 오디오를 휴대폰으로 이동할 수 있습니다.
- VDI에서 개인 간 오디오 및 비디오 통화를 저장할 수 없습니다.

> [!NOTE]
> 이는 최적화되지 않은 환경에만 해당됩니다.

```powershell
$PolName = "DisableCallsAndMeetingsAV"

New-CsTeamsVdiPolicy -Identity $PolName -DisableCallsAndMeetings $false -DisableAudioVideoInCallsAndMeetings $true
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $PolName

<# Wait for some time until the policy is applied #>
Get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*

<# Cleanup afterwards #>
$cleanup = $false
if($cleanup){

    "Doing cleanup"

    # De-assign policy from user  
    Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $null
    Get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*

    # Remove policies
    Get-CsTeamsVdiPolicy | ?{$_.identity -ne 'Global'} | remove-csTeamsVdiPolicy
}
```

## <a name="known-issues-and-limitations"></a>알려진 문제 및 제한 사항

### <a name="client-deployment-installation-and-setup"></a>클라이언트 배포, 설치 및 설정

- 컴퓨터별 설치를 통해 VDI의 Teams는 비 VDI Teams 클라이언트와 같은 방식으로 자동으로 업데이트되지 않습니다. [VDI의 Teams 데스크톱 앱 설치 또는 업데이트](#install-or-update-the-teams-desktop-app-on-vdi) 섹션에 설명된 대로 새 MSI를 설치하여 VM 이미지를 업데이트해야 합니다. 최신 버전으로 업데이트하려면 현재 버전을 제거해야 합니다.
- Citrix 환경에서 Teams가 실행되는 동안 사용자가 Virtual Machine에서 연결을 끊으면 Teams 업데이트로 인해 사용자가 다시 연결할 때 AV에 최적화되지 않은 상태가 될 수 있습니다. 이 시나리오를 방지하려면 Citrix Virtual Machine에서 연결을 끊기 전에 Teams를 종료하는 것이 좋습니다.
- Teams는 사용자당 또는 컴퓨터별로 배포해야 합니다. 사용자 및 컴퓨터당 동시 Teams 배포는 지원되지 않습니다. 컴퓨터당 또는 사용자별로 이러한 모드 중 하나로 마이그레이션하려면 제거 절차에 따라 두 모드 중 하나로 다시 배포합니다.
- 현재 Azure Virtual Desktop은 Linux 기반 클라이언트를 지원하지 않습니다.
- 빠른 테넌트 전환으로 인해 VDI에서 화면 공유를 사용할 수 없는 등의 호출 관련 문제가 발생할 수 있습니다. 클라이언트를 다시 시작하면 이러한 문제가 완화됩니다.

### <a name="notifications"></a>알림을

- Windows 작업 표시줄의 메시지 수 알림 및 현재 상태는 Windows Server 2016 호스트에서 지원되지 않습니다.

### <a name="calling-and-meetings"></a>통화 및 모임

다음 통화 및 모임 기능은 지원되지 않습니다.

- Citrix 및 VMware용 Teams 앱과 디바이스 간의 HID 단추 및 LED 컨트롤
- Citrix 및 VMware에 대한 배경 흐림 및 효과
- 브로드캐스트 및 라이브 이벤트 프로듀서 및 발표자 역할
- LBR(Location-Based 라우팅)
- PSTN 콜 링백 톤
- 공유 시스템 오디오/컴퓨터 소리
- 직접 라우팅을 위한 미디어 바이패스
- 확대/축소 컨트롤

> [!NOTE]
> 현재 비 VDI 환경에서만 사용할 수 있는 통화 및 모임 기능을 추가하기 위해 노력하고 있습니다. 여기에는 품질에 대한 관리자 제어, 추가 화면 공유 시나리오 및 최근에 Teams에 추가된 고급 기능이 포함될 수 있습니다. 예정된 기능에 대해 자세히 알아보려면 Teams 담당자에게 문의하세요.

다음은 통화 및 모임에 대한 알려진 문제 및 제한 사항입니다.

- 비즈니스용 Skype 상호 운용성은 오디오 호출로 제한되며 비디오 형식은 없습니다.
- 들어오고 나가는 비디오 스트림 해상도는 720p 해상도로 제한됩니다.
- Teams는 사용자가 선택한 마지막 오디오 디바이스를 사용하도록 전환하지 않습니다. 디바이스의 연결이 끊긴 후 다시 연결됩니다.
- 라이브 이벤트는 최적화되지 않습니다.
- 나가는 화면 공유:
  - VMware 및 AVD/W365에는 애플리케이션 공유가 지원되지 않습니다.
- 제어권을 부여하고 제어할 수 있습니다.
  - 애플리케이션 공유 세션 중에 지원되지 않습니다.

VDI와 관련이 없는 Teams 알려진 문제는 [조직의 지원 팀을 참조하세요](/MicrosoftTeams/troubleshoot/teams-welcome).

## <a name="troubleshooting"></a>문제 해결

### <a name="troubleshoot-citrix-components"></a>Citrix 구성 요소 문제 해결

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams가 충돌하거나 Teams 로그인 화면이 비어 있음

이는 Citrix VDA 버전 1906 및 1909의 알려진 문제입니다. 이 문제를 해결하려면 다음 레지스트리 `DWORD` 값을 추가하고 16진수로 `204` 설정합니다.

```console

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

```

그런 다음, VDA를 다시 시작합니다. 자세한 내용은 [Microsoft Teams용 HDX 최적화 문제 해결에 대한](https://support.citrix.com/article/CTX253754) Citrix 지원 문서를 참조하세요.

## <a name="related-topics"></a>관련 주제

- [MSI(Windows Installer)를 사용하여 Teams 대량 설치](msi-deployment.md)
- [Teams PowerShell 개요](teams-powershell-overview.md)
- [Azure Virtual Desktop에서 Microsoft Teams 사용](/azure/virtual-desktop/teams-on-wvd)
