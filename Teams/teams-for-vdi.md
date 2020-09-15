---
title: VDI(Virtualized Desktop Infrastructure)용 Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: VDI (가상화 데스크톱 인프라) 환경에서 Microsoft 팀을 실행 하는 방법에 대해 알아봅니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dce77f6fd2ff7d26f9452341884406fa69099a79
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766922"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>VDI(Virtualized Desktop Infrastructure)용 Teams

이 문서에서는 가상화 된 환경에서 Microsoft 팀을 사용 하는 데 필요한 요구 사항과 제한 사항에 대해 설명 합니다.

## <a name="what-is-vdi"></a>VDI 란?

VDI (가상 데스크톱 인프라)는 데스크톱 운영 체제 및 응용 프로그램을 데이터 센터의 중앙 집중식 서버에 호스팅하는 가상화 기술입니다. 이렇게 하면 완전히 안전한 중앙 집중화 된 원본을 사용 하 여 사용자에 게 개인 설정 된 데스크톱 환경이 제공 됩니다.

가상화 된 환경에서 Microsoft 팀은 채팅 및 공동 작업을 지원 합니다. 또한 Windows 가상 데스크톱, Citrix 및 VMware 플랫폼을 사용 하 여 통화 및 모임 기능도 지원 됩니다.

가상화 된 환경의 팀은 여러 구성을 지원 합니다. 여기에는 VDI, 전용, 공유, 영구, 비 영구적인 모드가 포함 됩니다. 기능은 지속적으로 개발 되 고 있으며 정기적으로 추가 되며, 제공 되는 개월 단위와 몇 년 동안 기능이 확장 됩니다.

가상화 된 환경에서 팀을 사용 하는 것은 가상화 되지 않은 환경에서 팀을 사용 하는 것과 약간 다를 수 있습니다. 예를 들어 가상화 된 환경에서는 일부 고급 기능을 사용할 수 없으며 비디오 해상도가 다를 수 있습니다.

최적의 사용자 환경을 보장 하려면이 문서의 지침을 따르세요.

## <a name="teams-on-vdi-components"></a>VDI 구성 요소의 팀

가상화 된 환경에서 팀을 사용 하려면 다음 구성 요소가 필요 합니다.

- **가상화 브로커**: Azure와 같은 가상화 공급자에 대 한 리소스 및 연결 관리자
- **가상 데스크톱**: Microsoft 팀을 실행 하는 VM (가상 컴퓨터) 스택
- **씬 클라이언트**: 사용자가 실제 인터페이스를 사용 하는 끝점
- **팀 데스크톱 앱**: 팀 데스크톱 클라이언트 앱

## <a name="teams-on-vdi-requirements"></a>VDI 요구 사항 팀

### <a name="virtualization-provider-requirements"></a>가상화 공급자 요구 사항

팀 데스크톱 앱의 유효성을 주요 가상화 솔루션 공급자로 확인 했습니다. 여러 시장 공급자를 사용 하는 경우 가상화 솔루션 공급자에 게 문의 하 여 최소 요구 사항을 충족 하는지 확인 하는 것이 좋습니다.
  
현재, AV (오디오/비디오)가 최적화 된 VDI의 팀은 Windows 가상 데스크톱, Citrix 및 VMware를 통해 인증 됩니다. 이 섹션의 정보를 검토 하 여 적절 한 기능에 대 한 모든 요구 사항을 충족 하는지 확인 합니다.

### <a name="platforms-certified-for-teams"></a>팀에 대해 인증 된 플랫폼

다음 플랫폼에는 팀을 위한 가상 데스크톱 인프라 솔루션이 있습니다.

|플랫폼|솔루션|
|----|---|
|![Microsoft를 나타내는 로고](media/microsoft-logo.png)| <a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows 가상 데스크톱</a> |
|![Citrix를 나타내는 로고](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 가상 앱 및 데스크톱</a> |
|![VMware를 나타내는 로고](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware 구간</a> |

### <a name="windows-virtual-desktop"></a>Windows 가상 데스크톱

Windows 가상 데스크톱은 VDI의 팀에 대해 AV 최적화 기능을 제공 합니다. 자세한 내용 및 요구 사항과 설치에 대 한 자세한 내용은 [Windows 가상 데스크톱에서 팀 사용](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)을 참조 하세요.

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Citrix 가상 앱 및 데스크톱 요구 사항

Citrix 가상 앱 및 데스크톱 (이전의 XenApp 및 XenDesktop)은 VDI의 팀에 대 한 AV 최적화 기능을 제공 합니다. Citrix 가상 앱 및 데스크톱을 사용 하는 경우 VDI의 팀은 채팅 및 공동 작업 외에도 통화와 모임 기능을 지원 합니다.

[Citrix 다운로드 사이트](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)에서 최신 버전의 Citrix 가상 앱 및 데스크톱을 다운로드할 수 있습니다. (먼저 로그인 해야 합니다.) 필수 구성 요소는 기본적으로 [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) 및 가상 배달 에이전트 (VDA)에 번들 됩니다. CWA 또는 VDA에 추가 구성 요소 또는 플러그인을 설치할 필요는 없습니다.

최신 서버 및 클라이언트 요구 사항은 [이 Citrix 웹 사이트](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)를 참조 하세요.

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>VMware 수평 작업 공간 및 데스크톱 요구 사항

VMware 수평은 하이브리드 클라우드에서 가상 데스크톱 및 앱을 안전 하 게 전달 하기 위한 최신 플랫폼입니다. 훌륭한 최종 사용자 환경을 제공 하기 위해 VMware 수평은 팀에 미디어 최적화 기능을 제공 합니다. 이러한 최적화는 가상 데스크톱과 앱에서 전반적인 생산성을 개선 하 고 팀을 사용 하 여 전화를 걸고 회의를 할 때 사용자 환경을 향상 시킵니다.

[Vmware 다운로드](https://my.vmware.com/web/vmware/downloads/#all_products) 페이지에서 최신 버전의 vmware 구간을 다운로드할 수 있습니다. 필수 미디어 최적화 구성 요소는 기본적으로 수평 에이전트 및 수평 클라이언트의 일부 이며, 팀에 최적화 기능을 사용 하기 위해 추가 플러그인을 설치할 필요가 없습니다.

팀에 대 한 미디어 최적화를 구성 하는 방법에 대 한 최신 요구 사항과 지침을 얻으려면 [이 VMware 웹 사이트](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)를 참조 하세요.

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>VDI에서 팀 데스크톱 앱 설치 또는 업데이트

MSI 패키지를 사용 하 여 컴퓨터별 설치 또는 사용자 단위 설치를 사용 하 여 VDI 용 팀 데스크톱 앱을 배포할 수 있습니다. 사용할 접근 방식을 결정 하는 것은 영구적이 든 비영구 설정을 사용 하 고 조직의 관련 기능 필요 여부에 따라 달라 집니다.

전용 영구적 설정의 경우 두 접근 방법이 모두 작동 합니다. 그러나 비영구 설정의 경우 팀에서 효율적으로 작업 하기 위해 컴퓨터별 설치가 필요 합니다. [비 영구적인 설정](#non-persistent-setup) 섹션을 참조 하세요.

컴퓨터 단위 설치의 경우 자동 업데이트를 사용할 수 없습니다. 즉, 팀 앱을 업데이트 하려면 최신 버전으로 업데이트 하기 위해 현재 버전을 제거 해야 합니다. 사용자 단위 설치의 경우 자동 업데이트를 사용할 수 있습니다. 대부분의 VDI 배포의 경우 시스템 단위 설치를 사용 하 여 팀을 배포 하는 것이 좋습니다.

최신 팀 버전으로 업데이트 하려면 제거 절차와 최신 팀 버전 배포를 차례로 시작 합니다.

VDI 환경에서 팀의 AV 최적화가 올바르게 작동 하려면 씬 클라이언트 끝점이 인터넷에 액세스할 수 있어야 합니다. 씬 클라이언트 끝점에서 인터넷 액세스를 사용할 수 없는 경우에는 최적화가 시작 되지 않습니다. 이는 사용자가 최적화 되지 않은 미디어 상태에 있음을 의미 합니다.

#### <a name="dedicated-persistent-setup"></a>전용 영구적 설정

전용 영구적 설정에서는 사용자가 로그 아웃 한 후 사용자의 로컬 운영 체제 변경 내용이 유지 됩니다. 영구 설치의 경우 팀은 사용자 단위 및 컴퓨터 단위 설치를 모두 지원 합니다.

다음은 권장 되는 최소 VM 구성입니다.

|매개 변수  |Workstation 운영 체제  |서버 운영 체제  |
|---------|---------|---------|
|vCPU   |    2 코어     |  4, 6 또는 8<br>기본 비 유니폼 메모리 액세스 (NUMA) 구성을 이해 하 고 그에 따라 Vm을 구성 하는 것이 중요 합니다.     |
|RAM     |   4GB      | 사용자 당 512 ~ 1024 MB        |
|저장소    | 8GB        | 40 ~ 60 GB        |

#### <a name="non-persistent-setup"></a>비 영구적인 설정

비 영구적인 설정에서는 사용자가 로그 아웃 한 후 사용자의 로컬 운영 체제 변경 내용이 보존 되지 않습니다. 이러한 설정은 일반적으로 공유 다중 사용자 세션입니다. VM 구성은 사용자 수와 사용 가능한 실제 box 리소스에 따라 달라 집니다.

비 영구적인 설정의 경우 팀 데스크톱 앱은 골든 이미지에 컴퓨터별 설치 되어 있어야 합니다. 자세히 알아보려면 [VDI에서 팀 데스크톱 앱 설치 또는 업데이트](#install-or-update-the-teams-desktop-app-on-vdi) 섹션을 참조 하세요. 이렇게 하면 사용자 세션 중에 팀 앱을 효율적으로 실행할 수가 있습니다.

비 영구적인 설정으로 팀을 사용 하려면 효율적인 팀 런타임 데이터 동기화를 위한 프로필 캐싱 관리자도 필요 합니다. 이렇게 하면 사용자의 사용자 정보 (예: 사용자 데이터, 프로필 및 설정)가 사용자 세션 중에 캐시 됩니다. 이 두 폴더의 데이터가 동기화 되는지 확인 합니다.  

- C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)
- C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)

다양 한 캐싱 관리자 솔루션을 사용할 수 있습니다. 예를 들어 [Fslogix](https://docs.microsoft.com/fslogix/overview)를 사용할 경우 특정 구성 지침은 캐싱 관리자 공급자에 게 문의 하세요.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>비 영구적인 설정에 대 한 팀 캐시 된 콘텐츠 제외 목록

팀 캐싱 폴더에서 다음을 제외 합니다 (% appdata%/Microsoft/Teams.). 이러한 항목을 제외 하면 사용자 캐싱 크기를 줄여 비영구 설정을 보다 최적화 하는 데 도움이 됩니다.

- .txt 파일
- 미디어 스택 폴더
- meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>엔터프라이즈 고려 사항에 대 한 Microsoft 365 앱

VDI에서 엔터프라이즈 용 Microsoft 365 앱을 배포 하는 경우 다음 사항을 고려 하세요.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>엔터프라이즈 용 Microsoft 365 앱을 통한 팀의 새 배포

엔터프라이즈 용 Microsoft 365 앱을 통해 팀을 배포 하기 전에 먼저 컴퓨터별 설치를 사용 하 여 배포 된 기존 팀 앱을 제거 해야 합니다.

엔터프라이즈 용 Microsoft 365 앱을 통한 팀은 사용자 단위로 설치 됩니다. 자세히 알아보려면 [VDI에서 팀 데스크톱 앱 설치 또는 업데이트](#install-or-update-the-teams-desktop-app-on-vdi) 섹션을 참조 하세요.

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>엔터프라이즈 업데이트에 대 한 Microsoft 365 앱을 통한 팀 배포

또한 enterprise 용 Microsoft 365 앱의 기존 설치에 팀이 추가 됩니다. Enterprise 용 Microsoft 365 앱은 사용자별로 팀을 설치 하므로 [VDI에서 팀 데스크톱 앱 설치 또는 업데이트](#install-or-update-the-teams-desktop-app-on-vdi) 섹션을 참조 하세요.

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>시스템 단위 설치 및 엔터프라이즈 용 Microsoft 365 앱을 사용 하는 팀

엔터프라이즈 용 Microsoft 365 앱이 팀 컴퓨터별 설치를 지원 하지 않습니다. 컴퓨터 단위 설치를 사용 하려면 enterprise 용 Microsoft 365 앱에서 팀을 제외 해야 합니다. [팀 데스크톱 앱을 VM에 배포](#deploy-the-teams-desktop-app-to-the-vm) 하는 [방법과 엔터프라이즈 섹션에 대 한 Microsoft 365 앱을 통해 팀 배포를 제외 하는 방법을](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) 참조 하세요.

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>엔터프라이즈 용 Microsoft 365 앱을 통해 팀 배포를 제외 하는 방법

Enterprise 용 microsoft 365 앱에 대 한 자세한 내용은 [엔터프라이즈의 새 365 설치에서 팀을 제외](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) 하 고 [그룹 정책을 사용 하 여 팀 설치를 제어](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)하는 방법에 대해 알아보세요.

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>VM에 팀 데스크톱 앱 배포

1. 다음 링크 중 하나를 사용 하 여 VDI VM 운영 체제와 일치 하는 팀 MSI 패키지를 다운로드 합니다.

    - [32 비트 버전](https://statics.teams.cdn.office.net/production-windows/1.3.00.21759/Teams_windows.msi)
    - [64 비트 버전](https://statics.teams.cdn.office.net/production-windows-x64/1.3.00.21759/Teams_windows_x64.msi)

    필요한 팀 데스크톱 앱의 최소 버전은 버전 1.3.00.4461입니다. (PSTN 보류가 이전 버전에서 지원 되지 않습니다.)

2. 다음 명령 중 하나를 실행 하 여이 MSI를 VDI VM에 설치 합니다.

    - 사용자별 설치 (기본값)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        이 프로세스는 '% AppData% 사용자 폴더에 팀을 설치 하는 기본 설치입니다. 이 시점에서 골든 이미지 설정이 완료 되었습니다. 비 영구적인 설정의 사용자 단위 설치에서는 팀이 제대로 작동 하지 않습니다.

    - 컴퓨터 단위 설치

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        이 프로세스는 팀을 64 비트 운영 체제의 x86 (프로그램 파일) 폴더 및 32 비트 운영 체제의 Program Files 폴더에 설치 합니다. 이 시점에서 골든 이미지 설정이 완료 되었습니다. 비 영구적인 설치에는 컴퓨터별 팀이 필요 합니다.

        다음 대화형 로그온 세션에서 팀을 시작 하 고 자격 증명을 요청 합니다.

        > [!NOTE]
        > 이 예제에서는 또한 **ALLUSERS = 1** 매개 변수를 사용 합니다. 이 매개 변수를 설정 하면 제어판의 프로그램 및 기능 및 컴퓨터의 모든 사용자에 대 한 Windows 설정의 앱 & 기능에 팀 컴퓨터 전체의 설치 관리자가 표시 됩니다. 모든 사용자가 관리자 자격 증명을 사용 하는 경우 팀을 제거할 수 있습니다.
        **ALLUSERS = 1** 과 **alluser = 1**간의 차이를 이해 하는 것이 중요 합니다. 비 VDI 및 VDI 환경에는 **ALLUSERS = 1** 매개 변수를 사용할 수 있지만 **alluser = 1** 매개 변수는 vdi 환경 에서만 사용 하 여 컴퓨터별 설치를 지정 합니다.

3. VDI VM에서 MSI를 제거 합니다.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      이 프로세스는 운영 체제 환경에 따라 x86 (프로그램 파일) 폴더 또는 프로그램 파일 폴더에서 팀을 제거 합니다.

## <a name="teams-on-vdi-performance-considerations"></a>VDI 성능 고려 사항에 대 한 팀

최적화 된 다양 한 설치 구성을 사용할 수 있으며, 여기에는 각각 다른 가상화의 포커스가 있습니다. 예를 들어, 구성은 사용자 밀도에 중점을 둘 것입니다. 계획을 수립할 때 다음 사항을 고려 하 여 조직의 작업량 요구 사항에 따라 설정을 최적화 합니다.

- 최소 요구 사항: 일부 작업의 경우 최소 요구 사항을 충족 하는 리소스를 사용 하 여 설정 해야 할 수 있습니다. 예를 들어 추가 컴퓨팅 리소스를 요구 하는 응용 프로그램을 사용 하는 개발자를 위한 작업입니다.
- 종속성: 여기에는 팀 데스크톱 앱 외부의 인프라, 작업 부하 및 기타 환경 고려 사항에 대 한 종속성이 포함 됩니다.
- VDI에서 사용할 수 없는 기능: 팀에서 VDI에 대 한 GPU 집약적 기능을 사용 하지 않도록 설정 하 여 일시적인 CPU 이용률을 향상 시킬 수 있습니다. 다음 기능은 사용할 수 없습니다.
    - 팀 CSS 애니메이션
    - Giphy 자동 시작

## <a name="teams-on-vdi-with-calling-and-meetings"></a>통화 및 모임으로 VDI의 팀

채팅 및 공동 작업 외에도, 통화와 모임이 포함 된 VDI 팀은 지원 되는 가상화 공급자 플랫폼에서 사용할 수 있습니다. 지원 되는 기능은 WebRTC 미디어 스택과 가상화 공급자 구현에 기반을 둔 것입니다. 다음 다이어그램은 아키텍처에 대 한 개요를 제공 합니다.

![VDI 아키텍처의 팀을 보여 주는 다이어그램](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> 현재 VDI에서 AV 최적화를 사용 하지 않고 팀을 실행 중 이며 최적화를 위해 아직 지원 되지 않는 기능 (예: 앱 공유 시 제어 권한 부여 및 적용)을 사용할 경우에는 팀 리디렉션을 해제 하도록 가상화 공급자 정책을 설정 해야 합니다. 즉, 팀 미디어 세션이 최적화 되지 않습니다. 팀 리디렉션을 끄려면 정책을 설정 하는 방법에 대 한 단계는 가상화 공급자에 게 문의 하세요.

### <a name="network-requirements"></a>네트워크 요구 사항

전체 클라우드 음성 및 비디오 배포에 영향을 줄 수 있는 위험 및 요구 사항을 식별 하는 환경을 평가 하는 것이 좋습니다. [비즈니스용 Skype 네트워크 평가 도구](https://www.microsoft.com/download/details.aspx?id=53885) 를 사용 하 여 네트워크가 팀에 게 준비 되었는지 여부를 테스트 합니다.

팀을 위해 네트워크를 준비 하는 방법에 대 한 자세한 내용은 [팀에 대 한 조직의 네트워크 준비](prepare-network.md)를 참조 하세요.

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>VDI의 비즈니스용 Skype에서 vdi의 팀으로 마이그레이션

Vdi의 비즈니스용 Skype에서 vdi의 팀으로 마이그레이션하는 경우, 두 응용 프로그램 간의 차이 외에 VDI도 구현 된 경우 몇 가지 차이점이 있습니다. 비즈니스용 Skype VDI에 있는 팀 VDI에서 현재 지원 되지 않는 일부 기능은 다음과 같습니다.

- 미디어 비트 전송률 제한 정책으로 VDI 호출 환경 제어
- VDI에서 일부 AV 기능을 사용 하지 않도록 설정 하는 플랫폼 단위 정책
- 앱 공유 시기 지정 및 관리
- 오디오 없이 채팅에서 화면 공유
- 동시 비디오 및 화면 공유 보내기 및 받기

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Chrome 브라우저의 팀과 VDI 용 팀 데스크톱 앱 비교

Chrome 브라우저의 팀은 AV 최적화를 사용 하는 VDI 용 팀 데스크톱 앱의 대체 기능을 제공 하지 않습니다. 채팅 및 공동 작업 환경은 예상 대로 작동 합니다. 미디어를 사용 해야 하는 경우 Chrome 브라우저에서 사용자 기대치를 충족 하지 못하는 몇 가지 환경이 있습니다.

- 오디오 및 비디오 스트리밍 환경이 최적이 아닐 수 있습니다. 사용자에 게 지연 또는 품질이 저하 될 수 있습니다.
- 브라우저 설정에서는 장치 설정을 사용할 수 없습니다.
- 장치 관리는 브라우저를 통해 처리 되며 브라우저 사이트 설정에서 여러 설정이 필요 합니다.
- Windows 장치 관리에서 장치 설정을 설정 해야 할 수도 있습니다.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>채팅 및 공동 작업을 통해 VDI의 팀

조직에서 팀의 채팅 및 공동 작업 기능만 사용 하려는 경우 팀의 통화 및 모임 기능을 해제 하도록 사용자 수준 정책을 설정할 수 있습니다. 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>정책을 설정 하 여 통화 및 모임 기능을 해제 합니다.

Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 정책을 설정할 수 있습니다. 정책 변경 내용을 전파 하는 데 시간이 걸릴 수 있습니다 (몇 시간). 지정 된 계정에 대 한 변경 내용이 즉시 표시 되지 않으면 몇 시간 후에 다시 시도 하세요.

[**호출 정책**](teams-calling-policy.md): 팀에는 모든 통화 기능을 사용 하지 않도록 설정 된 기본 제공 DisallowCalling 호출 정책이 포함 되어 있습니다. DisallowCalling 정책을 가상화 된 환경에서 팀을 사용 하는 조직의 모든 사용자에 게 할당 합니다.

[**모임 정책**](meeting-policies-in-teams.md): 팀에는 모든 모임 기능이 해제 되어 있는 기본 제공 AllOff 모임 정책이 포함 되어 있습니다. AllOff 정책을 가상화 된 환경에서 팀을 사용 하는 조직의 모든 사용자에 게 할당 합니다.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Microsoft 팀 관리 센터를 사용 하 여 정책 할당

DisallowCalling 호출 정책 및 AllOff 모임 정책을 사용자에 게 할당 하려면 다음을 수행 합니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동 합니다.
2. 사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집**을 클릭합니다.
3. 다음을 수행합니다.
    1.  **호출 정책**에서 **DisallowCalling**를 클릭 합니다.
    2.  **모임 정책**에서 **AllOff**를 클릭 합니다.
4. **적용**을 클릭 합니다.

한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자**로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.
2. **&#x2713;**(확인 표시) 열에서 사용자를 선택합니다. 모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.
3. **설정 편집**을 클릭하고 원하는 대로 변경한 다음, **적용**을 클릭합니다.

또는 다음을 수행할 수도 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 할당 하려는 정책으로 이동 합니다. 예를 들면 다음과 같습니다.
    - **음성**  >  **통화 정책**으로 이동한 다음 **DisallowCalling**를 클릭 합니다.
    - **모임**  >  **모임 정책**으로 이동한 다음 **AllOff**를 클릭 합니다.
2. **사용자 관리**를 선택합니다.
3. **사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 후 **추가**를 클릭합니다. 추가할 각 사용자에 대해 이 단계를 반복합니다.
4. 사용자 추가를 마쳤으면 **저장**을 클릭 합니다.

#### <a name="assign-policies-using-powershell"></a>PowerShell을 사용 하 여 정책 할당

다음 예제에서는 [CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) 를 사용 하 여 DisallowCalling 호출 정책을 사용자에 게 할당 하는 방법을 보여 줍니다.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

PowerShell을 사용 하 여 호출 정책을 관리 하는 방법에 대해 자세히 알아보려면 [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)을 참조 하세요.

다음 예제에서는 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) 를 사용 하 여 AllOff 모임 정책을 사용자에 게 할당 하는 방법을 보여 줍니다.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

PowerShell을 사용 하 여 모임 정책을 관리 하는 방법에 대해 자세히 알아보려면 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)을 참조 하세요.

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>통화 및 모임으로 팀을 최적화 하기 위해 채팅 및 공동 작업을 통해 VDI에서 팀 마이그레이션

사용자 수준 정책을 설정 하 여 통화 및 모임 기능을 해제 하 고 AV 최적화를 사용 하 여 팀으로 마이그레이션하는 경우 VDI에 팀의 기존 구현이 있는 경우 VDI 사용자에 게 해당 팀에 대 한 통화 및 모임 기능을 설정 하도록 정책을 설정 해야 합니다.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>통화 및 모임 기능을 켜려면 정책 설정

Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 통화 및 모임 정책을 설정 하 고 사용자에 게 할당할 수 있습니다. 정책 변경 내용을 전파 하는 데 몇 시간 정도 걸릴 수 있습니다. 지정 된 계정에 대 한 변경 내용이 즉시 표시 되지 않으면 몇 시간 후에 다시 시도 하세요.

[**호출**](teams-calling-policy.md)정책: 팀에서 정책에 대 한 호출은 사용자가 사용할 수 있는 통화 기능을 제어 합니다. 팀에는 모든 통화 기능이 설정 되어 있는 기본 제공 AllowCalling 호출 정책이 포함 됩니다. 모든 통화 기능을 설정 하려면 AllowCalling 정책을 할당 합니다. 또는 사용자 지정 호출 정책을 만들어 원하는 호출 기능을 설정 하 고 사용자에 게 할당 합니다. 

[**모임 정책**](meeting-policies-in-teams.md): 팀의 모임 정책은 사용자가 만들 수 있는 모임 유형과 조직의 사용자가 예약한 모임 참가자가 사용할 수 있는 기능을 제어 합니다. 팀에는 모든 모임 기능이 설정 되어 있는 기본 제공 된 AllOn 정책이 포함 됩니다. 모든 모임 기능을 설정 하려면 AllOn를 할당 합니다. 또는 사용자 지정 모임 정책을 만들어 원하는 모임 기능을 설정 하 고 사용자에 게 할당 합니다.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Microsoft 팀 관리 센터를 사용 하 여 정책 할당

AllowCalling 호출 정책 및 AllOn meeting policy를 사용자에 게 할당 하려면 다음을 수행 합니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동 합니다.
2. 사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집**을 클릭합니다.
3. 다음을 수행합니다.
    1.  **호출 정책**에서 **allowcalling**을 클릭 합니다.
    2.  **모임 정책**에서 **allon**을 클릭 합니다.
4. **적용**을 클릭 합니다.

한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자**로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.
2. **&#x2713;**(확인 표시) 열에서 사용자를 선택합니다. 모든 사용자를 선택 하려면 표 맨 위에 있는 **&#x2713;** (확인 표시)을 클릭 합니다.
3. **설정 편집**을 클릭하고 원하는 대로 변경한 다음, **적용**을 클릭합니다.

또는 다음을 수행할 수도 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 할당 하려는 정책으로 이동 합니다. 예를 들면 다음과 같습니다.
    - **음성**  >  **통화 정책**으로 이동한 다음 **allowcalling**를 클릭 합니다.
    - **모임**  >  **모임 정책**으로 이동한 다음, **allon**을 클릭 합니다.
2. **사용자 관리**를 선택합니다.
3. **사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 후 **추가**를 클릭합니다. 추가할 각 사용자에 대해 이 단계를 반복합니다.
4. 사용자 추가를 마쳤으면 **저장**을 클릭 합니다.

#### <a name="assign-policies-using-powershell"></a>PowerShell을 사용 하 여 정책 할당

다음 예제에서는 [CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) 를 사용 하 여 allowcalling 호출 정책을 사용자에 게 할당 하는 방법을 보여 줍니다.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

PowerShell을 사용 하 여 호출 정책을 관리 하는 방법에 대해 자세히 알아보려면 [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)을 참조 하세요.

다음 예제에서는 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) 를 사용 하 여 사용자에 게 allon 정책을 할당 하는 방법을 보여 줍니다.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

PowerShell을 사용 하 여 모임 정책을 관리 하는 방법에 대해 자세히 알아보려면 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)을 참조 하세요.

## <a name="control-fallback-mode-in-teams"></a>팀의 대체 모드 제어

사용자가 지원 되지 않는 끝점에서 연결 하는 경우 사용자는 AV에 최적화 되지 않은 대체 모드에 있습니다. 다음 레지스트리 DWORD 값 중 하나를 설정 하 여 fallback 모드를 사용 하지 않도록 설정 하거나 설정할 수 있습니다.

- HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Teams\DisableFallback
- HKEY_CURRENT_USER \SOFTWARE\Microsoft\Office\Teams\DisableFallback

Fallback 모드를 사용 하지 않도록 설정 하려면 값을 **1**로 설정 합니다. 오디오만 활성화 하려면 값을 **2**로 설정 합니다. 값이 없거나 **0** (영)으로 설정 되어 있으면 fallback 모드를 사용할 수 있습니다.

이 기능은 팀 버전 1.3.00.13565 이상에서 사용할 수 있습니다.

## <a name="known-issues-and-limitations"></a>알려진 문제점 및 제한 사항

### <a name="client-deployment-installation-and-setup"></a>클라이언트 배포, 설치 및 설정

- 컴퓨터별 설치의 경우 vdi의 팀이 비 VDI 팀 클라이언트의 방식으로 자동으로 업데이트 되지 않습니다. [VDI에서 팀 데스크톱 앱 설치 또는 업데이트](#install-or-update-the-teams-desktop-app-on-vdi) 섹션에 설명 된 대로 새 MSI를 설치 하 여 VM 이미지를 업데이트 해야 합니다. 최신 버전으로 업데이트 하려면 현재 버전을 제거 해야 합니다.
- 팀은 사용자 또는 컴퓨터 별로 배포 해야 합니다. 사용자 당 동시 및 컴퓨터 별로 팀을 배포 하는 것은 지원 되지 않습니다. 컴퓨터 또는 사용자 별로 이러한 모드 중 하나로 마이그레이션하려면 제거 절차에 따라 두 모드에 다시 배포 합니다.
- Windows 가상 데스크톱 및 VMware는 현재 MacOS 및 Linux 기반 클라이언트를 지원 하지 않습니다.
- 지금은 Citrix가 MacOs 클라이언트를 지원 하지 않습니다.
- Citrix는 끝점에 정의 된 명시적 HTTP 프록시 사용을 지원 하지 않습니다.

### <a name="calling-and-meetings"></a>통화 및 모임

다음 통화 및 모임 기능은 지원 되지 않습니다.

- 향상 된 응급 서비스
- 팀 앱과 장치 간의 HID 단추 및 LED 컨트롤
- 백그라운드 흐림 및 효과
- 브로드캐스트 및 라이브 이벤트 생산자 및 발표자 역할
- LBR (위치 기반 라우팅)
- 통화 공원
- 통화 대기열
- 공유 시스템 오디오/컴퓨터 소리
- 직접 라우팅을 위한 미디어 바이패스

> [!NOTE]
> 현재는 비 VDI 환경 에서만 사용할 수 있는 통화 및 모임 기능을 추가 하는 작업을 진행 하 고 있습니다. 여기에는 품질, 추가 화면 공유 시나리오, 최근에 팀에 추가 된 고급 기능에 대 한 더 많은 관리 제어가 포함 될 수 있습니다. 예정 된 기능에 대해 자세히 알아보려면 팀 담당자에 게 문의 하세요.

다음은 통화 및 모임에 대 한 알려진 문제점 및 제한 사항입니다.

- 비즈니스용 Skype와의 상호 운용성은 음성 통화로 제한 됩니다. 영상 형식이 없습니다.
- 모임 또는 그룹 통화에서는 하나의 수신 비디오 스트림만 지원 됩니다. 여러 사용자가 비디오를 보내면 주어진 시간에 주요 스피커 비디오만 표시 됩니다.
- 수신 및 발신 비디오 스트림 해상도는 720p 해상도로 제한 됩니다. 이것은 WebRTC 제한 사항입니다.
- 들어오는 카메라 또는 화면 공유 스트림의 비디오 스트림은 하나만 지원 됩니다. 들어오는 화면 공유가 있는 경우 기준 스피커의 비디오 대신 해당 화면 공유가 표시 됩니다.
- 보내는 화면 공유:
    - 응용 프로그램 공유가 지원 되지 않습니다.
- 제어권을 부여 하 고 컨트롤을 사용 합니다.
    - 화면 공유 또는 응용 프로그램 공유 세션 중에 지원 되지 않습니다.
    - PowerPoint 공유 세션 중에 지원 됩니다.
- Citrix 전용 제한
    - 이중 톤 다중 주파수 (DTMF) 전화 통신 시스템과의 상호 작용은 현재 지원 되지 않습니다.
    - 다중 모니터 설정에서 화면 공유 시 메인 모니터만 공유 됩니다.
    - CWA에서 높은 DPI 조정이 지원 되지 않습니다.

VDI와 관련 되지 않은 팀의 알려진 문제점은 [조직의 지원 팀](Known-issues.md)을 참조 하세요.

## <a name="troubleshooting"></a>문제 해결

### <a name="troubleshoot-citrix-components"></a>Citrix 구성 요소 문제 해결

VDA 및 CWA 문제를 해결 하는 방법에 대 한 자세한 내용은 [이 Citrix 웹 사이트](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)를 참조 하세요.

## <a name="related-topics"></a>관련 항목

- [MSI를 사용 하 여 Microsoft 팀 설치](msi-deployment.md)
- [Teams PowerShell 개요](teams-powershell-overview.md)
- [Windows 가상 데스크톱에서 Microsoft 팀 사용](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)
