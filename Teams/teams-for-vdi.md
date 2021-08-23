---
title: VDI(Virtualized Desktop Infrastructure)용 Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: VDI(Virtualized Desktop Infrastructure) Microsoft Teams 환경에서 실행되는 방법에 대해 자세히 알아보고
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3782d05697b602375385342d9f2a1248bbd95e3
ms.sourcegitcommit: 9fcd9a7ae78e04cef90415c2a0f30a98fbf8270f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2021
ms.locfileid: "58406957"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>VDI(Virtualized Desktop Infrastructure)용 Teams

이 문서에서는 가상화된 환경에서 Microsoft Teams 요구 사항 및 제한 사항을 설명합니다.

## <a name="what-is-vdi"></a>VDI란?

VDI(Virtual Desktop Infrastructure)는 데이터 센터의 중앙 집중식 서버에 데스크톱 운영 체제 및 애플리케이션을 호스트하는 가상화 기술입니다. 이렇게 하면 완전히 보호된 규정을 준수하는 중앙 집중식 원본을 사용하여 사용자에게 완전히 개인 설정된 데스크톱 환경을 사용할 수 있습니다.

Microsoft Teams 환경에서는 채팅 및 공동 작업을 지원합니다. 또한 Azure Virtual Desktop, Citrix 및 VMware 플랫폼을 사용하여 호출 및 모임 기능도 지원됩니다.

Teams 환경에서는 여러 구성을 지원합니다. 여기에는 VDI, 전용, 공유, 영구 및 비 영구 모드가 포함됩니다. 기능은 지속적인 개발에 있으며 정기적으로 추가되고, 기능은 다음 달과 몇 년 동안 확장될 것입니다.

가상 Teams 환경에서 사용은 가상화되지 않은 환경에서 Teams 다소 다를 수 있습니다. 예를 들어 가상화된 환경에서 일부 고급 기능을 사용할 수 없는 경우 비디오 해상도가 다를 수 있습니다.

최적의 사용자 환경을 보장하기 위해 이 문서의 지침을 따르하세요.

> [!Note]
> 다양한 플랫폼에서 VDI Teams 대한 자세한 내용은 플랫폼 [Teams 기능을 참조하세요.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="teams-on-vdi-components"></a>Teams 구성 요소에 대한 구성 요소

가상 Teams 환경에서는 다음 구성 요소가 필요합니다.

- **가상화 브로커**: Azure와 같은 가상화 공급자에 대한 리소스 및 연결 관리자
- **가상 데스크톱:** VM(Virtual Machine) 스택에서 실행되는 Microsoft Teams
- **씬 클라이언트**: 사용자가 물리적으로 인터페이스하는 엔드포인트
- **Teams 데스크톱 앱**: Teams 데스크톱 클라이언트 앱

## <a name="teams-on-vdi-requirements"></a>Teams 요구 사항에 대한 요구 사항

### <a name="virtualization-provider-requirements"></a>가상화 공급자 요구 사항

Teams 데스크톱 앱은 선도적인 가상화 솔루션 공급자를 사용하여 유효성을 검사했습니다. 여러 시장 공급자를 사용하는 경우 최소 요구 사항을 충족하도록 가상화 솔루션 공급자를 문의하는 것이 좋습니다.
  
현재 Teams AV(오디오/비디오) 최적화를 사용하여 VDI에서 Azure Virtual Desktop, Citrix 및 VMware에 인증됩니다. 이 섹션의 정보를 검토하여 적절한 기능에 대한 모든 요구 사항을 충족하는지 확인합니다.

### <a name="platforms-certified-for-teams"></a>인증된 플랫폼 Teams

다음 플랫폼에는 가상 데스크톱 인프라 솔루션이 Teams.

|플랫폼|솔루션|
|----|---|
|![Microsoft를 나타내는 로고](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Azure Virtual Desktop</a> |
|![Citrix를 나타내는 로고](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps 및 Desktops</a> |
|![VMware를 나타내는 로고](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="azure-virtual-desktop"></a>Azure Virtual Desktop

Azure Virtual Desktop은 VDI에서 Teams AV 최적화를 제공합니다. 자세한 사항 및 요구 사항 및 설치는 Azure Virtual Desktop에서 Teams [참조하세요.](/azure/virtual-desktop/teams-on-wvd)

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Citrix Virtual Apps 및 Desktops 요구 사항

Citrix Virtual Apps 및 Desktops(이전의 XenApp 및 XenDesktop)는 VDI에 대한 AV 최적화를 Teams 제공합니다. Citrix Virtual Apps 및 데스크톱을 사용하여 VDI에서 Teams 채팅 및 공동 작업 외에도 통화 및 모임 기능을 지원합니다.

Citrix 다운로드 사이트에서 최신 버전의 Citrix Virtual Apps 및 [데스크톱을 다운로드할 수 있습니다.](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/) (먼저 로그인해야 합니다.) 필요한 구성 요소는 기본적으로 [CWA(Citrix 작업](https://www.citrix.com/downloads/workspace-app/) 영역 앱) 및 VDA(Virtual Delivery Agent)에 번들로 제공됩니다. CWA 또는 VDA에 추가 구성 요소 또는 플러그 인을 설치할 필요가 없습니다.

최신 서버 및 클라이언트 요구 사항은 [이 Citrix 웹 사이트](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)를 참조하세요.

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>VMware Horizon 작업 영역 및 데스크톱 요구 사항

VMware Horizon은 하이브리드 클라우드에서 가상 데스크톱 및 앱을 안전하게 배달하기 위한 최신 플랫폼입니다. 훌륭한 최종 사용자 환경을 제공하도록 VMware Horizon은 사용자에 대한 미디어 최적화를 Teams. 이 최적화는 가상 데스크톱 및 앱 전반에 걸쳐 전반적인 생산성을 향상하고, 가상 데스크톱을 사용하여 전화를 걸고 모임할 때 사용자 환경을 Teams.

VMware 다운로드 페이지에서 [최신 버전의 VMware](https://my.vmware.com/web/vmware/downloads/#all_products) Horizon을 다운로드할 수 있습니다. 필수 미디어 최적화 구성 요소는 기본적으로 Horizon 에이전트 및 Horizon 클라이언트의 일부로, 추가 플러그 인을 설치할 필요가 Teams.

미디어 최적화를 구성하는 방법에 대한 최신 요구 사항 및 지침을 Teams VMware 웹 사이트 [를 참조하세요.](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>VDI에 Teams 데스크톱 앱 설치 또는 업데이트

MSI 패키지를 사용하여 Teams 설치 또는 사용자당 설치를 사용하여 VDI용 데스크톱 앱을 배포할 수 있습니다. 사용할 방법을 결정하려면 영구적 또는 비영구적 설정을 사용할지 여부와 조직의 관련 기능 요구에 따라 결정됩니다.

전용 영구 설정의 경우 두 방법 중 하나를 사용할 수 있습니다. 그러나 비영구적 설치의 경우 효율적으로 Teams 컴퓨터당 설치가 필요합니다. 영구적이지 않은 설정 [섹션을 참조하세요.](#non-persistent-setup)

컴퓨터당 설치를 통해 자동 업데이트를 사용할 수 없습니다. 즉, 앱을 Teams 최신 버전으로 업데이트하려면 현재 버전을 제거해야 합니다. 사용자당 설치를 사용하면 자동 업데이트가 활성화됩니다. 대부분의 VDI 배포의 경우 컴퓨터당 설치를 사용하여 Teams 배포하는 것이 좋습니다.

최신 버전으로 Teams 제거 프로시저를 시작하고 최신 버전 배포를 Teams 합니다.

VDI Teams AV 최적화가 제대로 작동하려면 씬 클라이언트 엔드포인트가 인터넷에 액세스할 수 있어야 합니다. 씬 클라이언트 엔드포인트에서 인터넷 액세스를 사용할 수 없는 경우 최적화 시작이 성공하지 않습니다. 즉, 사용자가 최적화되지 않은 미디어 상태입니다.

#### <a name="dedicated-persistent-setup"></a>전용 영구 설정

전용 영구 설정에서 사용자의 로컬 운영 체제 변경 내용은 사용자가 로그오프한 후에 유지됩니다. 영구 설치의 경우 Teams 사용자당 및 컴퓨터당 설치를 모두 지원합니다.

권장되는 최소 VM 구성은 다음과 같습니다.

|매개 변수  |Workstation 운영 체제  |서버 운영 체제  |
|---------|---------|---------|
|vCPU   |    코어 2개     |  4,6 또는 8<br>기본 NUMA(비 균일하지 않은 메모리 액세스) 구성을 이해하고 이에 따라 VM을 구성하는 것이 중요합니다.     |
|RAM     |   4GB      | 사용자당 512~1024MB        |
|저장소    | 8GB        | 40~60GB        |

#### <a name="non-persistent-setup"></a>영구적이지 않은 설정

영구적이지 않은 설정에서 사용자의 로컬 운영 체제 변경 내용은 사용자가 로그오프한 후에 유지되지 않습니다. 이러한 설정은 일반적으로 공유 다중 사용자 세션입니다. VM 구성은 사용자 수 및 사용 가능한 물리적 상자 리소스에 따라 다릅니다.

영구적이지 않은 설정의 경우 Teams 데스크톱 앱을 골든 이미지에 컴퓨터당 설치해야 합니다. (자세한 내용은 [VDI에서](#install-or-update-the-teams-desktop-app-on-vdi) 데스크톱 앱 설치 또는 Teams 섹션을 참조하세요.) 이렇게 하면 사용자 세션 동안 Teams 앱을 효율적으로 실행합니다.

비 Teams 런타임 데이터 동기화를 위해 프로필 캐싱 관리자도 Teams 필요합니다. 효율적인 데이터 동기화를 통해 사용자의 세션 중에 적절한 사용자별 정보(예: 사용자의 데이터, 프로필 또는 설정)가 캐시됩니다. 다음 두 폴더의 데이터가 동기화된지 확인합니다.<br>

- C:\Users\username\AppData\Local\Microsoft\IdentityCache(%localAppdata%\Microsoft\IdentityCache)
- C:\Users\username\AppData\Roaming\Microsoft\Teams(%appdata%\Microsoft\Teams)

> [!NOTE]
> 로밍 폴더(또는 폴더 리디렉션을 사용하는 경우 캐싱 관리자)는 애플리케이션을 실행하기 위해 Teams 런타임 데이터와 파일이 있는지 확인해야 합니다. 이 문제는 네트워크 대기 시간 문제 또는 네트워크 문제의 완화를 위해 필요하며, 그렇지 않으면 애플리케이션 오류 및 사용할 수 없는 데이터 및 파일로 인해 환경이 느려질 수 있습니다.

다양한 캐싱 관리자 솔루션을 사용할 수 있습니다. 예를 들어 [FSLogix](/fslogix/overview). 특정 구성 지침은 캐싱 관리자 공급자에게 문의하세요.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Teams 설정에 대한 캐시된 콘텐츠 제외 목록

캐싱 폴더, %appdata%/Microsoft/Teams 폴더에서 다음을 Teams. 이러한 항목을 제외하면 사용자 캐싱 크기를 줄여 비영구적 설정을 더욱 최적화할 수 있습니다.

- .txt 파일
- 미디어 스택 폴더
- meeting-addin\Cache(%appdata%\Microsoft\Teams\meeting-addin\Cache)

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>엔터프라이즈용 Microsoft 365 앱 고려 사항

VDI에서 Teams 배포할 엔터프라이즈용 Microsoft 365 앱 고려합니다.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>새 배포 Teams 엔터프라이즈용 Microsoft 365 앱

Teams 엔터프라이즈용 Microsoft 365 앱 배포하기 전에 먼저 컴퓨터당 설치를 사용하여 배포된 Teams 기존 앱의 제거를 먼저 제거해야 합니다.

Teams 엔터프라이즈용 Microsoft 365 앱 설치됩니다. 자세한 내용은 [VDI에서](#install-or-update-the-teams-desktop-app-on-vdi) Teams 데스크톱 앱 설치 또는 업데이트 섹션을 참조하세요.

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Teams 업데이트를 통한 엔터프라이즈용 Microsoft 365 앱 배포

Teams 설치에 엔터프라이즈용 Microsoft 365 앱. 사용자 엔터프라이즈용 Microsoft 365 앱 Teams 설치하기 때문에 [VDI에](#install-or-update-the-teams-desktop-app-on-vdi) Teams 데스크톱 앱 설치 또는 업데이트 섹션을 참조하세요.

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>컴퓨터 Teams 설치 및 엔터프라이즈용 Microsoft 365 앱

엔터프라이즈용 Microsoft 365 앱 컴퓨터당 설치를 지원하지 Teams. 컴퓨터당 설치를 사용하려면 시스템 Teams 제외해야 엔터프라이즈용 Microsoft 365 앱. [VM에](#deploy-the-teams-desktop-app-to-the-vm) Teams 데스크톱 앱 배포 및 Teams 섹션을 통해 배포를 제외하는 [엔터프라이즈용 Microsoft 365 앱](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) 참조하세요.

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>배포를 Teams 제외하는 엔터프라이즈용 Microsoft 365 앱

Teams 및 엔터프라이즈용 Microsoft 365 앱 방법에 대한 자세한 내용은 Teams [](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) 새 설치에서 제외하는 엔터프라이즈용 Microsoft 365 앱 및 그룹 정책 사용 을 참조하여 [Teams.](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>VM에 Teams 데스크톱 앱 배포

1. 다음 링크 Teams VDI VM 운영 체제와 일치하는 MSI 패키지를 다운로드합니다.

    - [32비트 버전](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [64비트 버전](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > 정부 클라우드의 경우 [MSI](msi-deployment.md) Microsoft Teams Microsoft Endpoint Configuration Manager 다운로드 링크를 사용하여 Microsoft Endpoint Configuration Manager 설치를 참조하세요.

    필요한 데스크톱 앱의 최소 Teams 버전은 버전 1.3.00.4461입니다. (이전 버전에서는 PSTN 보류가 지원되지 않습니다.)

2. 다음 명령 중 하나를 실행하여 VDI VM에 MSI를 설치합니다.

    - 사용자당 설치(기본값)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        이 프로세스는 %AppData% 사용자 폴더에 Teams 설치하는 기본 설치입니다. 이 시점에서 골든 이미지 설정이 완료되었습니다. Teams 설치 시 사용자당 설치가 제대로 작동하지 않습니다.

    - 컴퓨터당 설치

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        이 프로세스는 컴퓨터에 필요한 레지스트리 키를 추가하여 Teams 설치 관리자에게 VDI 인스턴스인지 알 수 있습니다.  이 설정이 없는 경우 설치 관리자가 오류가 발생하여 "설치가 실패했습니다.  VDI 환경이 검색되지 않은 경우 모든 사용자에게 설치할 수 없습니다."

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        이 프로세스는 Teams 64비트 운영 체제의 프로그램 파일(x86) 폴더 및 32비트 운영 체제의 프로그램 파일 폴더에 설치됩니다. 이 시점에서 골든 이미지 설정이 완료되었습니다. 비 Teams 설정에 대해 컴퓨터당 Teams 설치해야 합니다.

        다음 대화형 로그온 세션은 Teams 시작하고 자격 증명을 요청합니다.

        > [!NOTE]
        > 또한 이러한 예제에서는 **ALLUSERS=1 매개 변수를** 사용합니다. 이 매개 변수를 설정하면 Teams Machine-Wide 프로그램의 프로그램 및 기능에 설치 관리자를 & 앱의 Windows 설정 모든 사용자에 대해 표시됩니다. 그런 다음 모든 사용자가 관리자 자격 증명이 있는 Teams 제거할 수 있습니다.
        **ALLUSERS=1과 ALLUSER=1의** **차이점을** 이해하는 것이 중요합니다. **ALLUSERS=1** 매개 변수는 VDI가 아닌 VDI 환경에서 사용할 수 **있으며, ALLUSER=1** 매개 변수는 VDI 환경에서만 사용하여 컴퓨터당 설치를 지정합니다.

3. VDI VM에서 MSI를 제거합니다. 두 가지 방법으로 Teams.

    - PowerShell 스크립트: 이 [PowerShell](scripts/powershell-script-deployment-cleanup.md) 스크립트를 사용하여 사용자에 대한 Teams 제거하고 Teams 폴더를 제거할 수 있습니다. 컴퓨터에 설치된 각 사용자 Teams 스크립트를 실행합니다.
    - 명령줄: 다음 명령을 실행합니다.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      이 프로세스는 운영 체제 환경에 Teams 프로그램 파일(x86) 폴더 또는 프로그램 파일 폴더에서 제거합니다.

## <a name="teams-on-vdi-performance-considerations"></a>Teams 성능 고려 사항의 설명

다양한 가상화된 설정 구성이 있습니다. 각각 최적화에 대한 포커스가 다릅니다. 예를 들어 구성은 사용자 밀도에 집중할 수 있습니다. 계획할 때 조직의 워크로드 요구에 따라 설정을 최적화하는 데 도움이 되는 다음을 고려합니다.

- 최소 요구 사항: 일부 워크로드에는 최소 요구 사항 이상인 리소스를 사용하여 설정이 필요할 수 있습니다. 예를 들어 더 많은 컴퓨팅 리소스를 요구하는 애플리케이션을 사용하는 개발자를 위한 워크로드입니다.
- 종속성: 데스크톱 앱 외부의 인프라, 워크로드 및 기타 환경 고려 사항의 종속성 Teams 포함됩니다.
- VDI의 비활성화 기능: Teams GPU 집약적 기능을 사용하지 않도록 설정하여 일시적인 CPU 사용률을 개선하는 데 도움이 될 수 있습니다. 다음 기능은 사용하지 않도록 설정됩니다.
    - Teams CSS 애니메이션
    - Giphy 자동 시작

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams 및 모임을 통해 VDI에서 사용

채팅 및 공동 작업 외에도 Teams 및 모임을 통해 VDI에서 지원되는 가상화 공급자 플랫폼에서 사용할 수 있습니다. 지원되는 기능은 WebRTC 미디어 스택 및 가상화 공급자 구현을 기반으로 합니다. 다음 다이어그램에서는 아키텍처에 대한 개요를 제공합니다.

![VDI 아키텍처에 Teams 다이어그램](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> 현재 VDI에서 AV 최적화 없이 Teams 실행하고 최적화를 위해 아직 지원되지 않는 기능을 사용하는 경우(예: 앱 공유 시 제공 및 제어) 가상화 공급자 정책을 설정하여 Teams 리디렉션을 해제해야 합니다. 즉, Teams 미디어 세션이 최적화되지 않습니다. 리디렉션을 해제하는 정책을 설정하는 방법에 대한 Teams 가상화 공급자에 문의하세요.

### <a name="network-requirements"></a>네트워크 요구 사항

환경을 평가하여 전체 클라우드 음성 및 비디오 배포에 영향을 줄 수 있는 위험 및 요구 사항을 식별하는 것이 좋습니다. 네트워크 [비즈니스용 Skype](https://www.microsoft.com/download/details.aspx?id=53885) 평가 도구를 사용하여 네트워크가 Teams.

네트워크 준비 방법에 대한 자세한 내용은 Teams 에 대한 조직의 네트워크 [준비를 Teams.](prepare-network.md)

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>VDI의 비즈니스용 Skype VDI에서 VDI로 Teams 마이그레이션

VDI의 비즈니스용 Skype VDI에서 VDI로 Teams 경우 두 애플리케이션 간의 차이점 외에도 VDI가 구현될 때 몇 가지 차이점이 있습니다. VDI에 있는 VDI에서 현재 지원되지 Teams VDI에 비즈니스용 Skype 기능은 다음과 같습니다.

- VDI에서 일부 AV 기능을 사용하지 않도록 설정하는 플랫폼당 정책
- 앱 공유 시 제어권 제공 및 제어
- 오디오가 없는 채팅에서 화면 공유
- 동시 비디오 및 화면 공유 보내기 및 수신

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Teams용 데스크톱 앱과 Chrome 브라우저에서 Teams 데스크톱 앱

Teams 브라우저에서 AV 최적화를 사용하여 VDI용 Teams 데스크톱 앱의 대체를 제공하지 않습니다. 채팅 및 공동 작업 환경은 예상대로 작동합니다. 미디어가 필요한 경우 Chrome 브라우저에서 사용자 기대를 충족하지 않을 수 있는 몇 가지 환경이 있습니다.

- 오디오 및 비디오 스트리밍 환경이 최적화되지 않을 수 있습니다. 사용자가 지연되거나 품질이 낮아질 수 있습니다.
- 브라우저 설정에서 디바이스 설정을 사용할 수 없습니다.
- 디바이스 관리는 브라우저를 통해 처리하며 브라우저 사이트 설정에서 여러 설정이 필요합니다.
- 디바이스 설정은 디바이스 관리에서 Windows 수 있습니다.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams 및 공동 작업을 통해 VDI에서 작업

조직에서 채팅 및 공동 작업 기능만 사용하려는 Teams 사용자 수준 정책을 설정하여 통화 및 모임 기능을 Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>통화 및 모임 기능을 해제하기 위한 정책 설정

관리자 센터 또는 PowerShell을 사용하여 정책을 Microsoft Teams 수 있습니다. 정책 변경이 전파하는 데 몇 시간(몇 시간)이 걸릴 수 있습니다. 특정 계정에 대한 변경 내용이 즉시 표시되지 않는 경우 몇 시간 후에 다시 시도하세요.

[**호출 경찰**](teams-calling-policy.md): Teams 모든 호출 기능이 꺼져 있는 기본 제공 DisallowCalling 호출 정책이 포함되어 있습니다. 가상화된 환경에서 사용자를 사용하는 조직의 모든 Teams DisallowCalling 정책을 할당합니다.

[**모임 정책**](meeting-policies-in-teams.md): Teams 모든 모임 기능을 해제하는 기본 제공 AllOff 모임 정책이 포함됩니다. 가상화된 환경에서 모든 사용자를 사용하는 Teams AllOff 정책을 할당합니다.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>관리 센터를 사용하여 Microsoft Teams 할당

DisallowCalling 호출 정책 및 AllOff 모임 정책을 사용자에게 할당하는 경우:

1. 관리 센터의 왼쪽 Microsoft Teams 사용자로 **이동하세요.**
2. 사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집** 을 클릭합니다.
3. 다음을 수행합니다.
    1. 통화 **정책에서** **를** 클릭합니다.
    2. 모임 **정책에서** **AllOff 를 클릭합니다.**
4. 적용 **을 클릭합니다.**

한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자** 로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.
2. **&#x2713;**(확인 표시) 열에서 사용자를 선택합니다. 모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.
3. **설정 편집** 을 클릭하고 원하는 대로 변경한 다음, **적용** 을 클릭합니다.

또는 다음을 할 수도 있습니다.

1. 관리 센터의 왼쪽 Microsoft Teams 할당할 정책으로 이동하세요. 예를 들면 다음과 같습니다.
    - 음성 통화  >  **정책으로 이동한** **다음, DisallowCalling 을 클릭합니다.**
    - 모임 모임 **정책으로**  >  이동한 다음 **AllOff 를 클릭합니다.**
2. **사용자 관리** 를 선택합니다.
3. **사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 후 **추가** 를 클릭합니다. 추가할 각 사용자에 대해 이 단계를 반복합니다.
4. 사용자 추가가 완료되면 저장 을 **클릭합니다.**

#### <a name="assign-policies-using-powershell"></a>PowerShell을 사용하여 정책 할당

다음 예제에서는 [Grant-CsTeamsCallingPolicy를](/powershell/module/skype/grant-csteamscallingpolicy) 사용하여 사용자에게 DisallowCalling 호출 정책을 할당하는 방법을 보여줍니다.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

PowerShell을 사용하여 통화 정책을 관리하는 데 대한 자세한 내용은 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)를 참조합니다.

다음 예제에서는 [Grant-CsTeamsMeetingPolicy를](/powershell/module/skype/grant-csteamsmeetingpolicy) 사용하여 AllOff 모임 정책을 사용자에게 할당하는 방법을 보여줍니다.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

PowerShell을 사용하여 모임 정책을 관리하는 데 대한 자세한 내용은 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)를 참조합니다.

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>채팅 및 Teams VDI에서 마이그레이션하여 통화 및 Teams 최적화

채팅 및 Teams 및 공동 작업을 사용하여 VDI에 대한 기존 구현이 있는 경우 사용자 수준 정책을 설정하여 통화 및 모임 기능을 해제하고 AV 최적화를 사용하여 Teams VDI 사용자에 대한 호출 및 모임 기능을 설정하도록 정책을 Teams 설정해야 합니다.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>통화 및 모임 기능을 켜기 위한 정책 설정

관리자 센터 또는 Microsoft Teams PowerShell을 사용하여 사용자에게 통화 및 모임 정책을 설정하고 할당할 수 있습니다. 정책 변경이 전파하는 데 다소 시간이 걸릴 수 있습니다(몇 시간). 특정 계정에 대한 변경 내용이 즉시 표시되지 않는 경우 몇 시간 후에 다시 시도하세요.

[**호출 경찰**](teams-calling-policy.md): 사용자가 사용할 수 있는 Teams 제어하는 정책 호출 정책입니다. Teams 모든 호출 기능이 켜져 있는 기본 제공 AllowCalling 호출 정책이 포함되어 있습니다. 모든 호출 기능을 켜기 위해 AllowCalling 정책을 할당합니다. 또는 사용자 지정 호출 정책을 만들어 원하는 호출 기능을 켜고 사용자에게 할당합니다.

[**모임 정책**](meeting-policies-in-teams.md): Teams 사용자가 만들 수 있는 모임 유형 및 조직의 사용자가 예약한 모임 참가자에 사용할 수 있는 기능을 제어합니다. Teams 모든 모임 기능이 켜져 있는 기본 제공 AllOn 모임 정책이 포함되어 있습니다. 모든 모임 기능을 켜기 위해 AllOn 정책을 할당합니다. 또는 사용자 지정 모임 정책을 만들어 원하는 모임 기능을 켜고 사용자를 할당합니다.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>관리 센터를 사용하여 Microsoft Teams 할당

AllowCalling 호출 정책 및 AllOn 모임 정책을 사용자에게 할당하는 경우:

1. 관리 센터의 왼쪽 Microsoft Teams 사용자로 **이동하세요.**
2. 사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집** 을 클릭합니다.
3. 다음을 수행합니다.
    1. 통화 **정책에서** 허용 **을 클릭합니다.**
    2. 모임 **정책에서** **AllOn 을 클릭합니다.**
4. 적용 **을 클릭합니다.**

한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자** 로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.
2. **&#x2713;**(확인 표시) 열에서 사용자를 선택합니다. 모든 사용자를 선택하려면 &#x2713;(확인 표시)를 클릭합니다.
3. **설정 편집** 을 클릭하고 원하는 대로 변경한 다음, **적용** 을 클릭합니다.

또는 다음을 할 수도 있습니다.

1. 관리 센터의 왼쪽 Microsoft Teams 할당할 정책으로 이동하세요. 예를 들면 다음과 같습니다.
    - 음성 통화  >  **정책으로 이동한** 다음 **허용 을 클릭합니다.**
    - 모임 **모임 정책으로**  >  이동한 다음 **AllOn 을 클릭합니다.**
2. **사용자 관리** 를 선택합니다.
3. **사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 후 **추가** 를 클릭합니다. 추가할 각 사용자에 대해 이 단계를 반복합니다.
4. 사용자 추가가 완료되면 저장 을 **클릭합니다.**

#### <a name="assign-policies-using-powershell"></a>PowerShell을 사용하여 정책 할당

다음 예제에서는 [Grant-CsTeamsCallingPolicy를](/powershell/module/skype/grant-csteamscallingpolicy) 사용하여 사용자에게 AllowCalling 호출 정책을 할당하는 방법을 보여줍니다.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

PowerShell을 사용하여 통화 정책을 관리하는 데 대한 자세한 내용은 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)를 참조합니다.

다음 예제에서는 [Grant-CsTeamsMeetingPolicy를](/powershell/module/skype/grant-csteamsmeetingpolicy) 사용하여 AllOn 모임 정책을 사용자에게 할당하는 방법을 보여줍니다.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

PowerShell을 사용하여 모임 정책을 관리하는 데 대한 자세한 내용은 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)를 참조합니다.

## <a name="control-fallback-mode-in-teams"></a>제어 폴백 모드 Teams

지원되지 않는 엔드포인트에서 사용자가 연결하면 사용자가 AV가 최적화되지 않은 폴백 모드에 있습니다. 다음 레지스트리 DWORD 값 중 하나를 설정하여 폴백 모드를 사용하지 않도록 설정하거나 설정할 수 있습니다.

- HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback
- HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback

폴백 모드를 사용하지 않도록 설정하고 값을 **1로 설정합니다.** 오디오만 사용하도록 설정하려면 값을 **2로 설정합니다.** 값이 존재하지 않는 경우 또는 **0(0)으로** 설정되어 있는 경우 폴백 모드가 활성화됩니다.

이 기능은 1.3.00.13565 Teams 버전에서 사용할 수 있습니다.

## <a name="disable-audio-and-video-settings-for-vdi"></a>VDI에 대한 오디오 및 비디오 설정을 사용하지 않도록 설정

Teams VDI 정책은 Microsoft Teams 있습니다. 이러한 정책은 최적화되지 않은 VDI 환경에서 활성화되어 적용됩니다.

- New-CsTeamsVdiPolicy  
- Grant-CsTeamsVdiPolicy
- Remove-CsTeamsVdiPolicy
- Set-CsTeamsVdiPolicy

> [!NOTE]
> 최적화되지 않은 환경에만 해당합니다.

### <a name="update-a-module-name"></a>모듈 이름 업데이트

update-Module -Name MicrosoftTeams -AllowPrerelease

```PowerShell
<# Import and connect to online (CSOnline runs the policies) #>
Import-Module microsoftTeams
if( -not $sess){
    $session = New-CsOnlineSession
    $pss = Import-PSSession $session
}
<# Check out the commands #>
Get-Command -Noun *VDI*
<#
```

### <a name="set-policies-to-limit-calling-features"></a>통화 기능을 제한하기 위해 정책 설정

이 VDI 정책 설정 -DisableCallsAndMeetings를 $true VDI에 로그인하기 위해 Teams 사용자가 다음을 할 수 없습니다.

- 전화를 걸 수 있습니다.
- 모임에 참가합니다.
- 채팅에서 화면 공유를 합니다.

모든 유형의 호출을 사용하지 않도록 설정해야 합니다.

> [!NOTE]
> 최적화되지 않은 환경에만 해당합니다.

```PowerShell
#>
New-CsTeamsVdiPolicy -Identity DisableCallsAndMeetingsTrue -DisableCallsAndMeetings $true -DisableAudioVideoInCallsAndMeetings $false
<# Assign Policy #>
$user = 'meganb@jvteams.xyz'
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName DisableCallsAndMeetingsTrue
<# wait for some time until the policy is applied #>
get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*
<#
Show all Policies  
#>
Get-CsTeamsVdiPolicy | FT Iden*, Disable*
<#
```

VDI 정책 설정 -DisableAudioVideoInCallsAndMeetings를 사용하여 VDI에 $true 로그인할 Teams 다음을 할 수 있습니다.

- 채팅에서 화면 공유를 합니다.
- 모임에 참가하고 화면을 공유합니다. 오디오를 휴대폰으로 이동합니다.
- 사용자는 VDI에서 사람 대 사람 오디오 및 비디오 통화를 할 수 없습니다.

> [!NOTE]
> 최적화되지 않은 환경에만 해당합니다.

```powershell
#>
$PolName = "DisableCallsAndMeetingsAV"
New-CsTeamsVdiPolicy -Identity $PolName -DisableCallsAndMeetings $false -DisableAudioVideoInCallsAndMeetings $true
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $PolName
<# wait for some time until the policy is applied #>
get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*
<# ## Cleanup afterwards #>
$cleanup = $false
if($cleanup){
    "Doing cleanup"
    # de-assign policy from user  
    Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $null
    get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*
    # remove Policies
    Get-CsTeamsVdiPolicy | ?{$_.identity -ne 'Global'} | remove-csTeamsVdiPolicy
}
```

## <a name="known-issues-and-limitations"></a>알려진 문제 및 제한 사항

### <a name="client-deployment-installation-and-setup"></a>클라이언트 배포, 설치 및 설치

- 컴퓨터당 설치를 Teams VDI가 아닌 클라이언트가 있는 방식으로 VDI의 Teams 없습니다. [VDI의](#install-or-update-the-teams-desktop-app-on-vdi) 데스크톱 앱 설치 또는 업데이트 섹션에 설명된 Teams VM 이미지를 업데이트해야 합니다. 최신 버전으로 업데이트하려면 현재 버전을 제거해야 합니다.
- Citrix 환경에서 사용자가 가상 머신을 Teams 경우 업데이트가 Teams 다시 연결할 때 사용자가 AV에 대해 최적화되지 않은 상태로 될 수 있습니다. 이 시나리오를 피하기 위해 사용자가 Citrix Virtual Machine에서 Teams 전에 연결을 종료하는 것이 좋습니다.
- Teams 사용자당 또는 컴퓨터당 배포해야 합니다. 사용자 Teams 및 컴퓨터당 동시 배포는 지원되지 않습니다. 컴퓨터당 또는 사용자당을 이러한 모드 중 하나로 마이그레이션하려면 제거 프로시저를 따라 두 모드로 다시 재배포합니다.
- Azure Virtual Desktop은 현재 macOS 및 Linux 기반 클라이언트를 지원하지 않습니다.
- 빠른 테넌트 스위치는 화면 공유를 사용할 수 없는 경우, 잘못된 참가자 목록이 표시되는 등 VDI에서 호출 관련 문제가 될 수 있습니다. 클라이언트를 다시 시작하면 이러한 문제가 완화됩니다.

### <a name="calling-and-meetings"></a>통화 및 모임

다음 호출 및 모임 기능은 지원되지 않습니다.

- 새 모임 환경 또는 새 모임 환경과 함께 제공된 기능과 같은 모든 다중 창 기능
- 향상된 응급 서비스
- 앱과 디바이스 간의 HID Teams LED 컨트롤
- 배경 흐림 및 효과
- 브로드캐스트 및 라이브 이벤트 생산자 및 발표자 역할
- Location-Based(LBR)
- PSTN 콜링백 톤
- 공유 시스템 오디오/컴퓨터 소리
- 직접 라우팅을 위한 미디어 바이패스
- 통화 공원
- 확대/축소 제어

> [!NOTE]
> 현재 VDI가 아닌 환경에서만 사용할 수 있는 호출 및 모임 기능을 추가하는 작업을 진행하고 있습니다. 여기에는 품질에 대한 더 많은 관리 제어, 추가 화면 공유 시나리오 및 최근에 추가된 고급 기능이 Teams. 다가오는 기능에 Teams 자세한 내용은 담당자에게 문의합니다.

다음은 호출 및 모임에 대한 알려진 문제 및 제한 사항입니다.

- 비즈니스용 Skype 상호 연동성은 오디오 호출로 제한됩니다. 비디오 모달리티가 있습니다.
- 수신 및 발신 비디오 스트림 해상도는 720p 해상도로 제한됩니다.
- 들어오는 카메라 또는 화면 공유 스트림에서 하나의 비디오 스트림만 지원됩니다. 들어오는 화면 공유가 있는 경우 주된 스피커의 비디오 대신 화면 공유가 표시됩니다.
- Teams 연결이 끊어진 경우 사용자가 선택한 마지막 오디오 디바이스를 사용하도록 전환하지 않은 다음 다시 연결합니다.
- 라이브 이벤트는 최적화되지 않습니다.
- 외출 화면 공유:
    - 애플리케이션 공유는 지원되지 않습니다.
- 제어권 및 제어권:
    - 화면 공유 또는 애플리케이션 공유 세션 중에 지원되지 않습니다.
    - 공유 세션 동안 PowerPoint 지원됩니다.
- Citrix 전용 제한 사항
   - CWA의 높은 DPI 크기 조정은 지원되지 않습니다.

VDI와 Teams 알려진 문제에 대한 자세한 내용은 조직의 지원 Teams [를 참조합니다.](/MicrosoftTeams/troubleshoot/teams-welcome)

## <a name="troubleshooting"></a>문제 해결

### <a name="troubleshoot-citrix-components"></a>Citrix 구성 요소 문제 해결

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams 또는 Teams 화면이 비어 있습니다.

Citrix VDA 버전 1906 및 1909에 알려진 문제입니다. 이 문제를 해결하기 위해 다음 레지스트리 DWORD 값을 추가하고 204(hexadecimal)로 설정합니다.

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

그런 다음 VDA를 다시 시작합니다. 자세한 내용은 이 Citrix 지원 문서, 에 대한 [HDX 최적화 문제 해결 Teams.](https://support.citrix.com/article/CTX253754)

## <a name="related-topics"></a>관련 항목

- [MSI를 Microsoft Teams 설치](msi-deployment.md)
- [Teams PowerShell 개요](teams-powershell-overview.md)
- [Azure Virtual Desktop에서 Microsoft Teams 사용](/azure/virtual-desktop/teams-on-wvd)
