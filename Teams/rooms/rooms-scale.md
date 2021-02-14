---
title: Microsoft Endpoint Configuration Manager를 사용하여 Microsoft Teams 회의실 배포
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Microsoft Endpoint Configuration Manager를 사용하여 대규모 배포에서 Microsoft Teams 회의실을 배포하는 방법을 설명합니다.
no-loc:
- Microsoft
- Microsoft Corporation
- Microsoft Teams Rooms
- Microsoft Teams Room
- System Center
- Configuration Manager
- Windows
- Surface
- Surface Pro
- Windows PE
- Windows 10
- Windows 10 Enterprise
- Azure
- Azure Monitor
- Log Analytics
- Operations Management Suite
ms.openlocfilehash: 1d8fc0090264a7a39051cfedb9c3584a08e3ebb9
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662423"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager를 사용하여 Microsoft Teams 회의실 배포

이 문서에서는 Microsoft Endpoint Configuration Manager를 사용하여 Microsoft Teams Rooms 배포를 만드는 데 필요한 모든 정보를 제공합니다.

Configuration Manager에서 제공하는 사용하기 쉬운 메서드를 사용하여 운영 체제 및 기타 애플리케이션을 여러 대상 디바이스에 배포할 수 있습니다.

아래 설명된 방법을 사용하여 구성 관리자 구성을 안내하고, 조직에 필요한 경우 이 지침 전체에 제공된 샘플 패키지 및 스크립트를 사용자 지정합니다.

![구성 관리자를 사용한 Microsoft Teams Rooms 배포 프로세스](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> 이 솔루션은 Surface Pro 기반 배포에서만 테스트했습니다. Surface Pro를 기반으로 하지 않는 구성에 대한 제조업체의 지침을 따릅니다.

## <a name="validate-prerequisites"></a>전제성 유효성 검사

구성 관리자를 통해 Microsoft Teams 회의실을 배포하려면 다음의 전제 조건 및 요구 사항을 충족하는지 확인합니다.

### <a name="microsoft-endpoint-configuration-manager-requirements"></a>Microsoft Endpoint Configuration Manager 요구 사항

-   Microsoft Endpoint Configuration Manager 버전은 1706 이상이 되어야 합니다. 1710 이상을 사용하는 것이 좋습니다. Configuration [Manager에서 Windows 10에](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) 대한 지원을 확인하여 Configuration Manager에서 지원하는 Windows 10 버전에 대해 자세히 알아보는 것이 좋습니다.

-   Windows 10용 지원되는 ADK(Windows 평가 및 배포 키트)를 설치해야 합니다. 다양한 버전의 Configuration Manager에서 사용할 수 있는 [Windows 10 ADK](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) 버전을 참조하고 배포에 올바른 버전이 포함되어야 합니다.

-   사이트 시스템 서버에 배포 지점 역할이 할당되어야 합니다. 네트워크 시작 배포를 사용하도록 설정하려면 부팅 이미지를 [PXE(사전](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) 부팅 실행 환경) 지원에 사용하도록 설정해야 합니다. PXE 지원을 사용하도록 설정하지 않은 경우 배포에 부팅 가능한 [미디어를](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) 사용할 수 있습니다.

-   새 컴퓨터(베어 메탈) 배포 시나리오를 지원하도록 네트워크 액세스 계정을 구성해야 합니다. 네트워크 액세스 계정의 구성에 대한 자세한 내용은 [Configuration Manager에서 사용되는 계정을 참조하세요.](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)

-   동일한 Microsoft Teams [](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)회의실 이미지를 여러 단위에 동시에 배포할 가능성이 있는 경우 멀티캐스트 지원을 사용하도록 설정하는 것이 좋습니다.

### <a name="networking-requirements"></a>네트워킹 요구 사항

-   네트워크에는 Microsoft Teams 회의실 단위가 배포될 서브넷에 대한 자동 IP 주소 배포를 위해 구성된 DHCP(동적 호스트 구성 프로토콜) 서버가 필요합니다.

    > [!NOTE]
    > DHCP 임대 기간은 이미지 배포 기간보다 긴 값으로 설정해야 합니다. 그렇지 않으면 배포가 실패할 수 있습니다.

-   스위치 및 VLA(가상 런)를 포함한 네트워크는 PXE를 지원하도록 구성해야 합니다. IP 도우미 및 PXE 구성에 대한 자세한 내용은 네트워크 공급업체를 참조하세요. 또는 PXE [](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) 지원을 사용하도록 설정하지 않은 경우 배포에 부팅 가능한 미디어를 사용할 수 있습니다.

    > [!NOTE]
    > Surface Pro 장치의 경우 Microsoft의 이더넷 어댑터 또는 도킹 스테이션을 사용하는 경우 네트워크에서 부팅(PXE 부팅)이 지원됩니다. 타사 이더넷 어댑터는 Surface Pro에서 PXE 부팅을 지원하지 않습니다. 자세한 [내용은 이더넷 어댑터](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) 및 Surface 배포를 참조하세요.

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a>운영 체제 배포를 위한 Microsoft Endpoint Configuration Manager 구성

이 문서에서는 이미 정상 구성 관리자 배포가 있으며 구성 관리자를 처음부터 배포하고 구성하는 데 필요한 모든 단계를 자세히 설명하지는 않습니다. Microsoft [](https://docs.microsoft.com/configmgr/) Endpoint Configuration Manager에 대한 설명서 및 구성 지침은 훌륭한 리소스입니다. 아직 Configuration Manager를 배포하지 않은 경우 이러한 리소스로 시작하는 것이 좋습니다.

다음 지침을 사용하여 OSD(운영 체제 배포) 기능이 올바르게 구성되었는지 확인합니다.

### <a name="validate-and-upgrade-configuration-manager"></a>구성 관리자 유효성 검사 및 업그레이드

1.  구성 관리자 콘솔에서 관리 **업데이트** \> **및 서비스로 이동**

2.  아직 설치되지 않은 설치된 빌드 및 적용 가능한 업데이트를 확인합니다.

3.  구성 [관리자에서 Windows 10에 대한 지원을 검토합니다.](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) 배포를 업그레이드해야 하는 경우 설치하려는 업데이트를 선택한 다음 다운로드를 **선택합니다.**

4.  다운로드가 완료되면 업데이트를 선택한 다음 업데이트 팩 **설치를 선택합니다.**

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>PXE 및 멀티캐스트를 지원하도록 배포 지점 구성

1.  구성 관리자 콘솔에서 관리  배포 \> **지점으로 이동**

2.  Microsoft Teams 회의실 배포를 서비스할 배포 지점 서버를 선택한 다음 속성을 **선택합니다.**

3.  **PXE** 탭을 선택하고 다음 설정을 사용하도록 설정해야 합니다.
    -   클라이언트에 대한 PXE 지원 사용
    -   이 배포 지점이 들어오는 PXE 요청에 응답하도록 허용
    -   알 수 없는 컴퓨터 지원 사용

4.  *선택 사항:* 멀티캐스트 지원을 사용하도록 설정하려면 멀티캐스트 탭을 **선택하고** 다음 설정을 사용하도록 설정해야 합니다.
    -   멀티캐스트를 사용하여 여러 클라이언트에 동시에 데이터 보내기
    -   네트워크 팀의 권장에 따라 UDP 포트 범위 구성

### <a name="configure-the-network-access-account"></a>네트워크 액세스 계정 구성

1.  구성 관리자 콘솔에서 관리  사이트 구성 \> **사이트로 이동한** 다음 \> 사이트를 선택합니다.

2.  설정 **그룹에서** 사이트 구성 요소 **소프트웨어 배포** \> **구성을 선택합니다.**

3.  네트워크 **액세스 계정 탭을** 선택합니다. 하나 이상의 계정을 설정한 다음 확인을 **선택합니다.**

> [!NOTE]
> 계정에는 배포 지점 서버의 네트워크에서 **이** 컴퓨터에 액세스하는 것을 제외하고 특별한 권한이 필요하지 않습니다. 일반 도메인 사용자 계정이 적절합니다. 자세한 내용은 [Configuration Manager에서 사용되는 계정을 참조하세요.](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)

### <a name="configure-a-boot-image"></a>부팅 이미지 구성

1.  구성 관리자 콘솔에서 **소프트웨어 라이브러리** 운영 체제 \> **부팅** \> **이미지로 이동하세요.**

2.  부팅 **이미지(x64)를** 선택한 다음 속성을 **선택합니다.**

3.  데이터 원본 **탭을 선택하고** PXE 사용 배포 지점에서 이 부팅 **이미지 배포를 사용하도록 설정합니다.**

4.  필수 구성 **요소를 설치하려면** 선택적 구성 요소 탭을 선택합니다.

    1.  별 아이콘을 선택하고 **HTML(WinPE-HTA)을 검색합니다.**

    2.  부팅 **이미지에** HTML 애플리케이션 지원을 추가하려면 확인을 선택합니다.

5.  *선택 사항:* 배포 환경을 사용자 지정하려면 사용자 지정 **탭을** 선택합니다.
    -   배포하는 **동안** 명령 프롬프트에 액세스할 수 있도록 하려는 경우 명령 지원(테스트 전용)을 사용하도록 설정합니다. 이 기능을 사용하도록 설정하면 배포 중에 **F8을** 선택하여 명령 프롬프트를 시작할 수 있습니다.
    -   배포 중에 표시할 사용자 지정 배경 이미지를 지정할 수도 있습니다. 이미지를 설정하려면 사용자 지정 배경 이미지 **파일(UNC** 경로)을 지정하고 배경을 선택합니다.

6.  요청이 있는 경우 **예를** 선택하고 업데이트된 부팅 이미지를 배포 지점에 배포합니다.

자세한 내용은 [Configuration Manager를 사용하여 부팅 이미지 관리를 참조하세요.](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images)

> [!NOTE]
> 부팅 가능한 USB 미디어를 만들어 PXE 지원이 없는 환경에 대한 Configuration Manager 작업 시퀀스 기반 배포를 시작할 수 있습니다. 부팅 가능한 미디어에는 부팅 이미지, 선택적 사전 시작 명령 및 필요한 파일 및 Windows PE로 부팅하고 나머지 배포 프로세스에 대한 Configuration Manager에 연결하는 구성 관리자 이진만 포함되어 있습니다. 자세한 내용은 부팅 가능한 미디어 [만들기를 참조하세요.](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)

## <a name="create-configuration-manager-packages"></a>구성 관리자 패키지 만들기

> [!IMPORTANT]
> 각 SRS 설치 관리자 버전에 필요한 운영 체제 버전은 모든 MSI 릴리스에 따라 변경됩니다. 특정 MSI에 대한 최상의 운영 체제 버전을 확인하려면 콘솔 설치 스크립트를 한 번 실행합니다. 자세한 내용은 [Microsoft Endpoint Configuration Manager를 사용하여 Microsoft Teams 회의실 배포를 참조합니다.](rooms-scale.md)

구성 관리자에는 Microsoft Teams 회의실 단위를 배포하고 구성하기 위해 여러 패키지가 필요합니다.

다음 패키지를 만들고 구성한 다음 배포 지점 서버 역할이 할당된 Configuration Manager 사이트 시스템에 배포해야 합니다.

| **패키지 이름**                     | **유형**               | **설명**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2 - SRS 애플리케이션 패키지     | 소프트웨어 패키지       | Microsoft Teams Rooms 배포 키트용 패키지                                      |
| SRS v2 - Sysprep 패키지             | 소프트웨어 패키지       | Microsoft Teams 회의실 단위를 Unattended.xml 사용자 지정 패키지            |
| SRS v2 - Set-SRSComputerName 패키지 | 소프트웨어 패키지       | 배포 중에 컴퓨터 이름을 할당하기 위한 HTA(HTML 애플리케이션) 패키지    |
| SRS v2 - SRS 설정 구성         | 소프트웨어 패키지       | Microsoft Teams Rooms 앱 배포를 구성하는 패키지                          |
| SRS v2 - OS 업데이트 패키지          | 소프트웨어 패키지       | 필수 운영 체제 업데이트를 배포하는 패키지                                      |
| SRS v2 - 루트 인증서 패키지    | 소프트웨어 패키지       | 선택 사항 - 루트 인증서를 배포하는 패키지(도메인에 가입된 단위에는 필요 없음)  |
| SRS v2 - Microsoft Monitoring Agent 패키지 | 소프트웨어 패키지       | 선택 사항 - Microsoft Operations Management Suite 에이전트를 배포하고 구성하는 패키지|
| SRS v2 - WinPE 백그라운드 패키지    | 소프트웨어 패키지       | 부팅 이미지와 함께 사용할 사용자 지정 배경 이미지용 패키지                           |
| Windows 10 Enterprise                | 운영 체제 이미지 | 운영 체제 설치 파일용 패키지(install.wim)                          |
| Surface Pro                          | 드라이버 패키지         | Microsoft Surface Pro용 디바이스 드라이버 및 펌웨어 패키지                     |
| Surface Pro 4                        | 드라이버 패키지         | Microsoft Surface Pro 4용 디바이스 드라이버 및 펌웨어 패키지                   |

자세한 내용은 Configuration Manager의 패키지 [및 프로그램을 참조하세요.](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)

### <a name="create-folders-for-the-package-source-files"></a>패키지 원본 파일에 대한 폴더 만들기

구성 관리자를 사용하려면 패키지 원본 파일이 처음 만들어지며 업데이트될 때 특정 폴더 구조로 구성해야 합니다.

Microsoft Endpoint Configuration Manager 중앙 관리 사이트 또는 기본 사이트 또는 패키지 원본 파일을 호스트하는 데 사용하는 서버 공유에서 다음 폴더 구조를 만들 수 있습니다.

-   SRS v2 - Microsoft Monitoring Agent 패키지
-   SRS v2 - OS 업데이트 패키지
-   SRS v2 - 루트 인증서 패키지
-   SRS v2 - Set-SRSComputerName 패키지
-   SRS v2 - SRS 애플리케이션 패키지
-   SRS v2 - SRS 설정 구성
-   SRS v2 - Sysprep 패키지
-   드라이버
    -   Surface Pro
    -   Surface Pro 4
-   운영 체제
    -   Windows 10 Enterprise

> [!TIP]
> 패키지의 [](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) 폴더 구조, 사용해야 하는 스크립트 및 가져오는 데 필요한 작업 시퀀스 템플릿을 포함하는 zip 파일을 다운로드하여 사용할 수도 있습니다.

### <a name="create-the-monitoring-agent-package"></a>모니터링 에이전트 패키지 만들기

1. 에서 모니터링 에이전트를 <https://go.microsoft.com/fwlink/?LinkId=828603> 다운로드합니다.

2. 명령 프롬프트 창을 열고 명령 프롬프트에서MMASetup-AMD64.exe **/C:를** 입력하여 **SRS v2 - Microsoft Monitoring Agent 패키지** 폴더에 패키지를 추출합니다.

3. 구성 관리자 콘솔에서 **소프트웨어** 라이브러리 애플리케이션 관리 패키지로 이동한 다음 \>  \> 패키지 **만들기를 선택합니다.**

4. 다음 정보를 입력하여 패키지를 만들 수 있습니다.

   - 이름:<strong>SRS v2 - Microsoft Monitoring Agent 패키지</strong>

   - 제조업체:<strong>Microsoft Corporation</strong>

   - 버전:<strong>8.1.11081.0(다운로드한</strong> 설치 파일의 버전 입력)

   - 원본 파일 **확인란이** 포함된 이 패키지를 선택하고 **SRS v2 - Microsoft Monitoring Agent Package** 폴더의 경로를 입력한 다음 다음을 **선택합니다.**

5. 프로그램 **만들기 안 을 선택하고** 다음을 **선택합니다.**

6. 설정 **확인 페이지를 검토하고** 다음을 **선택합니다.**

7. 닫기 **선택**

### <a name="create-the-operating-system-updates-package"></a>운영 체제 업데이트 패키지 만들기

1. **SRS v2 - OS 업데이트** 패키지 폴더에서 새 PowerShell 스크립트를 **Install-SRSv2-OS-Updates.ps1.**

2. 아래 스크립트를Install-SRSv2-OS-Updates.ps1 **복사합니다.** 또는 여기에서 Install-SRSv2-OS-Updates.ps1 스크립트를 다운로드할 수 [있습니다.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. 필수 Windows 업데이트 패키지를 동일한 폴더에 다운로드합니다.
   > [!NOTE]
   > 이 문서가 게시된 [당시에는 KB4056892만](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) 필요했습니다. Microsoft Teams 회의실 콘솔 [구성을](console.md)확인하여 다른 업데이트가 필요한지 확인합니다.

4. 구성 관리자 콘솔에서 **소프트웨어** 라이브러리 애플리케이션 관리 패키지로 이동한 다음 \>  \> 패키지 **만들기를 선택합니다.**

5. 다음 정보를 입력하여 패키지를 만들 수 있습니다.
   -   이름: **SRS v2 – OS 업데이트 패키지**
   -   제조업체: **Microsoft Corporation**
   -   버전: **1.0.0**
   -   이 **패키지에** 원본 파일 확인란을 선택하고 **SRS v2 - OS** 업데이트 패키지 폴더의 경로를 입력한 다음 다음을 **선택합니다.**

6. 프로그램 **만들기 안 을 선택하고** 다음을 **선택합니다.**

7. 설정 **확인 페이지를 검토하고** 다음을 **선택합니다.**

8. 닫기 **선택**

### <a name="create-the-root-certificate-package-optional"></a>루트 인증서 패키지 만들기(선택 사항)

이 패키지를 만들어 Active Directory 도메인에 가입되지 않은 디바이스에 대한 루트 인증서를 배포합니다. 다음 조건이 모두 적용되는 경우 이 패키지를 만드기
-   배포에는 온-프레미스 Lync 또는 비즈니스용 Skype 서버가 포함됩니다.
-   Microsoft Teams 회의실 단위는 도메인 구성원 대신 작업에서 작동하도록 구성됩니다.

1.  루트 인증서를 **SRS v2 – 루트** 인증서 패키지 폴더에 복사합니다.

2.  구성 관리자 콘솔에서 **소프트웨어** 라이브러리 애플리케이션 관리 패키지로 이동한 다음 \>  \> 패키지 **만들기를 선택합니다.**

3.  다음 정보를 입력하여 패키지를 만들 수 있습니다.
    -   이름: **SRS v2 – 루트 인증서 패키지**
    -   제조업체: *조직의 이름*
    -   버전: **1.0.0**
    -   원본 파일 **확인란을** 포함하는 이 패키지를 선택하고 **SRS v2 –** 루트 인증서 패키지 폴더의 경로를 입력한 다음 다음을 **선택합니다.**

4.  프로그램 **만들기 안 을 선택하고** 다음을 **선택합니다.**

5.  설정 **확인 페이지를 검토하고** 다음을 **선택합니다.**

6.  닫기 **선택**

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Microsoft Teams Rooms 배포 키트 패키지 만들기

1.  최신 버전의 Microsoft **Teams Rooms** 배포 키트를 다운로드하고, 이를 <https://go.microsoft.com/fwlink/?linkid=851168> Workstation에 설치합니다.

2.  **C: \\ 프로그램 파일(x86) \\ Skype 채팅방** 시스템 배포 키트에서 **SRS v2 - SRS 애플리케이션 패키지** 폴더로 콘텐츠를 복사합니다.

3.  구성 관리자 콘솔에서 **소프트웨어** 라이브러리 애플리케이션 관리 패키지로 이동한 다음 \>  \> 패키지 **만들기를 선택합니다.**

4.  다음 정보를 입력하여 패키지를 만들 수 있습니다.
    -   이름: **SRS v2 – SRS 애플리케이션 패키지**
    -   제조업체: **Microsoft Corporation**
    -   버전: **3.1.104.0(다운로드한** 설치 파일의 버전 입력)
    -   원본 파일 **확인란을** 포함하는 이 패키지를 선택하고 **SRS v2 – SRS 애플리케이션** 패키지 폴더의 경로를 입력한 다음 다음을 **선택합니다.**
5.  프로그램 **만들기 안 을 선택하고** 다음을 **선택합니다.**

6.  설정 **확인 페이지를 검토하고** 다음을 **선택합니다.**

7.  닫기 **선택**

### <a name="create-the-computer-name-assignment-package"></a>컴퓨터 이름 할당 패키지 만들기

1.  **SRS v2 - Set-SRSComputerName 패키지** 폴더에서 **Set-SRSComputerName.hta라는** 새 HTML 애플리케이션을 생성합니다.

2.  **Set-SRSComputerName.hta** 파일에 다음 스크립트를 복사합니다. 또는 여기에서 Set-SRSComputerName.hta 파일을 다운로드할 수 [있습니다.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
    ```HTML
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  구성 관리자 콘솔에서 **소프트웨어** 라이브러리 애플리케이션 관리 패키지로 이동한 다음 \>  \> 패키지 **만들기를 선택합니다.**

4.  다음 정보를 입력하여 패키지를 만들 수 있습니다.

    -   이름: **SRS v2 - Set-SRSComputerName 패키지**

    -   제조업체: **Microsoft Corporation**

    -   버전: **1.0.0**

    -   원본 파일 **확인란을** 포함하는 이 패키지를 선택하고 **SRS v2 -** Set-SRSComputerName 패키지 폴더에 대한 경로를 입력한 다음 다음을 **선택합니다.**

5.  프로그램 **만들기 안 을 선택하고** 다음을 **선택합니다.**

6.  설정 **확인 페이지를 검토하고** 다음을 **선택합니다.**

7.  닫기 **선택**

### <a name="create-the-sysprep-package"></a>Sysprep 패키지 만들기

1. **SRS v2 – Sysprep 패키지** 폴더에서 새 XML **파일을Unattend.xml.**

2. 다음 텍스트를Unattend.xml **복사합니다.** 또는 여기에서 Unattend.xml 파일을 다운로드할 수 [있습니다.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
   ```XML
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. 구성 관리자 콘솔에서 **소프트웨어** 라이브러리 애플리케이션 관리 패키지로 이동한 다음 \>  \> 패키지 **만들기를 선택합니다.**

4. 다음 정보를 입력하여 패키지를 만들 수 있습니다.
   -   이름: **SRS v2 - Sysprep 패키지**
   -   제조업체: **Microsoft Corporation**
   -   버전: **1.0.0**
   -   원본 파일 **확인란을** 포함하는 이 패키지를 선택하고 **SRS v2 – Sysprep 패키지** 폴더의 경로를 입력한 다음 다음을 **선택합니다.**
5. 프로그램 **만들기 안 을 선택하고** 다음을 **선택합니다.**

6. 설정 **확인 페이지를 검토하고** 다음을 **선택합니다.**

7. 닫기 **선택**

### <a name="create-the-windows-10-enterprise-package"></a>Windows 10 Enterprise 패키지 만들기

1.  Windows 10 Enterprise x64 미디어를 확보하고 **install.wim** 파일을 운영 체제 **\\ Windows 10 Enterprise 폴더에 복사합니다.**

2.  구성 관리자 콘솔에서 **소프트웨어 라이브러리** 운영 체제 운영 체제 이미지로 이동한 다음 운영 체제 이미지 \>  \>  **추가를 선택합니다.**

3.  방금 복사한 **install.wim 파일의** 경로를 지정하고 다음을 **선택합니다.**

4.  Windows  10 Enterprise 이미지의 빌드 번호와 일치하게 버전 필드를 업데이트하고 다음을 **선택합니다.**

5.  세부 **정보 페이지를 검토하고** 다음을 **선택합니다.**

6.  닫기 **선택**

자세한 내용은 Configuration Manager를 사용하여 [OS 이미지 관리를 참조하세요.](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images)

### <a name="create-surface-pro-device-driver-packages"></a>Surface Pro 장치 드라이버 패키지 만들기

Microsoft Teams 회의실은 Surface Pro 및 Surface Pro 4 모두에서 지원됩니다. 환경에 있는 각 Surface Pro 모델에 대한 드라이버 패키지를 만들어야 합니다.

> [!IMPORTANT]
> 드라이버는 Windows 10 Enterprise 빌드 및 Microsoft Teams Rooms 배포 키트 버전과 호환되어야 합니다. 자세한 내용은 Surface 디바이스에 대한 최신 펌웨어 및 드라이버 [다운로드](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) 및 콘솔 [구성을 참조하세요.](console.md)

1.  최신 드라이버 및 펌웨어를 다운로드합니다.
    -   Surface Pro의 경우: <https://www.microsoft.com/download/details.aspx?id=55484>
    -   Surface Pro 4의 경우: <https://www.microsoft.com/download/details.aspx?id=49498>

2.  다운로드한 드라이버 및 펌웨어를 추출합니다. 명령 프롬프트 창을 열고 명령 프롬프트에서 다음 명령 중 하나를 입력합니다.
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  구성 관리자 콘솔에서 **소프트웨어** 라이브러리 운영 체제 드라이버로 이동한 다음 \>  \> 드라이버 **가져오기를 선택합니다.**

4.  **다음 UNC(네트워크** 경로)에서 모든 드라이버 가져오기를 선택하고 원본 폴더(예: C: _Sources Drivers Surface Pro)를 선택한 다음, \\ \\ \\ 다음을 **선택합니다.**

5.  가져온 **드라이버에** 대한 세부 정보 지정 페이지에서 나열된 모든 드라이버를 선택한 다음, 이러한 드라이버를 사용하도록 설정하고 컴퓨터에서 드라이버를 설치할 수 **있도록 합니다.**

6.  범주를 **선택하고** Surface 모델과 일치하는 새 범주를 만들고 확인을 선택한 다음 **다음을** **선택합니다.**

7.  새 **패키지를 선택합니다.**

8.  Surface Pro 모델과 일치하는 패키지 이름을 지정하고, 드라이버 패키지 파일을 저장할 폴더 경로를 입력하고, **확인을** 선택한 다음, 다음을 **선택합니다.**

9.  부팅 이미지 **페이지에서** 부팅 이미지가 선택되어 없는지 확인한 후 다음을 **선택합니다.**

10. 닫기 **선택**

11. 소프트웨어 **라이브러리** \> **운영 체제** \> **드라이버로** **\>** 이동하여 폴더 만들기를 선택한 다음, 방금 드라이버를 가져온 Surface Pro 모델과 일치하는 폴더 이름을 입력합니다.

12. 가져온 모든 드라이버를 새로 만든 폴더로 이동하여 쉽게 탐색하고 작업을 할 수 있습니다.

> [!NOTE]
> 사용 중일 수 있는 다른 Surface Pro 모델에 대해 동일한 단계를 반복합니다. 자세한 내용은 [Configuration Manager에서 드라이버 관리를 참조하세요.](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers)

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Microsoft Teams 회의실 구성 패키지 만들기

1.  구성 관리자 콘솔에서 **소프트웨어** 라이브러리 애플리케이션 관리 패키지로 이동한 다음 \>  \> 패키지 **만들기를 선택합니다.**

2.  다음 정보를 입력하여 패키지를 만들 수 있습니다.

    -   이름: **SRS v2 - SRS 설치 패키지 구성**

    -   제조업체: **Microsoft Corporation**

    -   버전: **1.0.0**

    -   원본 파일 **확인란을** 포함하는 이 패키지를 선택하고 **SRS v2 - SRS** 설정 폴더 구성에 대한 경로를 입력한 다음 다음을 **선택합니다.**

3.  프로그램 **만들기 안 을 선택하고** 다음을 **선택합니다.**

4.  설정 **확인 페이지를 검토하고** 다음을 **선택합니다.**

5.  닫기 **선택**



## <a name="distribute-configuration-manager-packages"></a>구성 관리자 패키지 배포

모든 패키지는 구성 관리자 계층 구조에서 배포 지점 역할이 할당된 서버에 배포되어야 합니다. 아래 지침에 따라 패키지 배포를 시작하세요.

1.  소프트웨어 패키지를 배포합니다.

    1.  구성 관리자 콘솔에서 **소프트웨어** 라이브러리 애플리케이션 \> **관리 패키지로** \> **이동** 배포하려는 모든 소프트웨어 패키지를 선택한 다음 콘텐츠 **배포를 선택합니다.**

    2.  패키지 목록을 검토하고 다음을 **선택합니다.**

    3.  모든 배포 지점 서버(또는 구성 관리자 계층 구조에 따라 메일 지점 그룹)를 목록에 추가하고 다음을 **선택합니다.**

    4.  다음을 **선택하고** **닫기 를 선택합니다.**

2.  드라이버 패키지를 배포합니다.

    1.  구성 관리자 콘솔에서 **소프트웨어 라이브러리** 운영 체제 \> **드라이버** \> **패키지로 이동** 배포하려는 모든 드라이버 패키지를 선택한 다음 콘텐츠 **배포를 선택합니다.**

    2.  패키지 목록을 검토하고 다음을 **선택합니다.**

    3.  모든 배포 지점 서버(또는 구성 관리자 계층 구조에 따라 메일 지점 그룹)를 목록에 추가하고 다음을 **선택합니다.**

    4.  다음을 **선택하고** **닫기 를 선택합니다.**

3.  운영 체제 패키지를 배포합니다.

    1.  구성 관리자 콘솔에서 **소프트웨어 라이브러리** 운영 체제 \> **운영 체제** \> **이미지로 이동하세요.** 배포하려는 모든 운영 체제 이미지를 선택한 다음 콘텐츠 **배포를 선택합니다.**

    2.  패키지 목록을 검토하고 다음을 **선택합니다.**

    3.  모든 배포 지점 서버(또는 구성 관리자 계층 구조에 따라 메일 지점 그룹)를 목록에 추가하고 다음을 **선택합니다.**

    4.  다음을 **선택하고** **닫기 를 선택합니다.**

> [!NOTE]
> 패키지 배포는 패키지 크기, Configuration Manager 계층 구조, 배포 지점 서버 수 및 네트워크에서 사용할 수 있는 대역폭에 따라 다소 시간이 걸릴 수 있습니다.
> 
> Microsoft Teams 회의실 단위 배포를 시작하기 전에 모든 패키지를 배포해야 합니다.
> 
> 배포 상태 콘텐츠 상태 모니터링으로 진행하여 구성 관리자  콘솔에서 패키지 배포의 상태를 \>  \> **검토할 수 있습니다.**

## <a name="configuration-manager-task-sequences"></a>구성 관리자 작업 시퀀스

구성 관리자에서 작업 시퀀스를 사용하여 운영 체제 이미지를 대상 컴퓨터에 배포하는 단계를 자동화합니다. 자동으로 Microsoft Teams 회의실 단위를 배포하려면 대상 Microsoft Teams Rooms 컴퓨터, 설치하려는 Windows 10 Enterprise 운영 체제 이미지 및 기타 추가 콘텐츠(예: 다른 응용 프로그램 또는 소프트웨어 업데이트)를 시작하는 데 사용되는 부팅 이미지를 참조하는 작업 시퀀스를 만듭니다.

### <a name="import-the-sample-task-sequence"></a>샘플 작업 시퀀스 가져오기

샘플 작업 시퀀스를 다운로드하고 쉽게 가져오고 요구에 맞게 사용자 지정할 수 있습니다.

1.  [**샘플**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) 작업 시퀀스를 다운로드하고 다운로드한 zip 파일을 공유 위치에 복사합니다.
2.  구성 관리자 콘솔에서 **소프트웨어** 라이브러리 운영 체제 작업 시퀀스로 이동한 다음 작업 시퀀스 \>  \>  **가져오기를 선택합니다.**

3.  **찾아보기를** 선택하고, 1단계에서 사용한 공유 폴더 위치로 이동하고, **Microsoft Teams 회의실 배포(EN-US).zip** 파일을 선택한 다음, 다음을 **선택합니다.**

4.  작업을 **새로** **만들기로 설정하고** 다음을 **선택합니다.**

5.  설정을 확인하고 다음을 **선택합니다.**

6.  닫기 **선택**

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>참조 패키지가 각 작업 시퀀스 단계에 올바르게 연결되어 있는지 확인합니다.

1. 가져온 작업 시퀀스를 선택한 다음 편집을 **선택합니다.**

    작업 시퀀스 편집기가 열리면 Microsoft Teams 회의실 단위를 배포하고 구성하는 데 필요한 각 순차적 단계가 표시됩니다.

2. 각 단계를 단계별로 진행하고 권장 업데이트를 완료합니다.

   1. **Windows PE에서 다시 시작:** 이 단계가 다시 시작된 다음 컴퓨터를 Windows PXE로 부팅합니다. 이 단계에서는 변경이 필요하지 않습니다.

   2. **파티션 디스크 0 – UEFI:** 이 단계는 디스크 구성을 지우고 구성된 설정에 따라 파티션을 만듭니다. 이 단계를 변경하지 않는 것이 좋습니다.

   3. **SRS 컴퓨터** 이름 설정: 이 단계에서는 배포 중에 Microsoft Teams 회의실 단위의 컴퓨터 이름을 설정하는 UI를 제공하는 HTML 애플리케이션을 포함합니다.
      -  선택적 단계이지만 대체 프로세스를 통해 컴퓨터 이름을 관리하려는 경우 비활성화할 수 있습니다.
      -  **SRS v2 - Set-SRSComputerName 패키지가** 선택되어 있는지 확인 그렇지 않은 경우 패키지를 찾아 선택합니다.

   4. **운영 체제** 적용: 이 단계에서는 배포할 운영 체제 이미지와 사용할 무인 Sysprep 응답 파일을 지정합니다.
      -  올바른 Windows 10 Enterprise 운영 체제 이미지 파일이 선택되어 있는지 확인합니다.
      -  사용자 지정 설치에 무인 또는 **Sysprep 응답** 파일을 사용할 수 있는지 확인하고 **SRS v2 - Sysprep 패키지가** 선택되어 있는지 확인합니다. 또한 파일 **이름이** 다음으로 **설정되어unattend.xml.**

   5. **Windows 설정 적용:** 이 단계에서는 Windows 설치에 대한 정보를 수집합니다.
      -  제품 키, 로컬 관리자 계정 암호 및 표준 시간대를 포함한 라이선스 및 등록 정보를 제공합니다(요구에 따라 다를 수 있습니다).

   6. **네트워크 설정 적용:** 이 단계를 통해 작업 영역 또는 Active Directory 도메인 이름 및 조직 구성 단위를 지정할 수 있습니다.
      > [!NOTE]
      > Actve Directory 도메인의 구성원으로 Microsoft Teams 회의실 단위를 배포하는 데 필요한 권장 작업에 대한 [Skype](domain-joining-considerations.md) 채팅방 시스템 도메인 가입 고려 사항을 참조하세요.
   7. **드라이버 적용:** 이 단계 및 하위 단계는 사용 중 Surface Pro 모델을 기반으로 해당 디바이스 드라이버 및 펌웨어를 배포하는 데 사용됩니다. 이 배포와 연결된 관련 드라이버 패키지를 지정하도록 각 단계를 업데이트합니다.
      -   각 드라이버 패키지는 WMI(Windows Management Instrumentation) 필터를 활용하여 Surface Pro make 및 model에 따라 관련 드라이버 및 펌웨어를 배포하도록 구성됩니다.
      -   이러한 드라이버의 구성을 변경하지 않는 것이 좋습니다. 그렇지 않으면 배포가 실패할 수 있습니다.

   8. **Windows 및 구성 관리자 설정:** 이 단계에서는 Configuration Manager 클라이언트를 배포하고 구성합니다. 기본 제공 Configuration Manager 클라이언트 패키지를 지정하려면 이 단계를 업데이트합니다.

   9. **루트 인증서** 설치: 이 단계는 도메인에 가입되지 않은 디바이스에 대한 루트 인증서를 배포하므로 선택 사항이며 기본적으로 사용하지 않도록 설정됩니다.
      -   Microsoft Teams 회의실 단위에 루트 인증서를 배포해야 하는 경우 이 단계를 사용하도록 설정합니다.
      -   이 단계를 수행해야 하는 경우 **SRS v2 –** 루트 인증서 패키지 및 **64비트** 파일 시스템 리디렉션 사용 안 을 선택해야 합니다.

   10. **모니터링 에이전트** 설치 및 구성: 이 단계에서는 64비트 버전의 Microsoft Azure Monitor 에이전트를 설치하고 Log Analytics 작업 영역으로 연결하도록 에이전트를 구성합니다.
       -   이 단계는 기본적으로 사용하지 않도록 설정되어 있습니다. 모니터링 에이전트를 사용하여 Microsoft Teams 회의실 단위의 상태 모니터링을 사용하려면 이 단계를 사용하도록 설정해야 합니다.
       -   이 단계를 편집하고 명령줄 매개 변수를 업데이트하여 작업 영역 **ID** 및 작업 영역 키를 **지정합니다.**
       -   Operations Management Suite 작업 영역 ID 및 기본 키를 얻는 데 대한 자세한 내용은 [Azure 모니터링에](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) 대한 테스트 디바이스 구성을 참조하세요.
       -   **SRS v2 – Microsoft Monitoring Agent 패키지** 및 사용 안 **64비트** 파일 시스템 리디렉션이 선택되어 있는지 확인
       -   Microsoft Teams Rooms 배포의 상태 모니터링에 대한 자세한 내용은 [Azure Monitor를](azure-monitor-plan.md)사용하여 Microsoft Teams 회의실 관리 계획, Azure [Monitor를](azure-monitor-deploy.md) 사용하여 Microsoft Teams Rooms 관리 배포 및 [Azure Monitor를](azure-monitor-manage.md)사용하여 Microsoft Teams Rooms 디바이스 관리를 참조하세요.

   11. **SRS v2 구성** 파일 복사: 이 단계에서는 필요한 설정 및 구성 파일을 Microsoft Teams 회의실 배포 키트에서 로컬 하드 드라이브로 복사합니다. 이 단계에서는 사용자 지정이 필요하지 않습니다.
       -   **SRS v2 – SRS 애플리케이션** 패키지 및 사용 안 **64비트 파일 시스템 리디렉션이 선택되어** 있는지 확인

   12. **Install-SRSv2-OS-Updates:** 이 단계에서는 Microsoft Teams Rooms 배포에 필요한 모든 필수 운영 체제 업데이트를 배포합니다. 다음을 수행합니다.
       -   필요한 [업데이트를 확인하려면 Microsoft Teams 회의실](console.md) 콘솔 구성을 확인합니다.
       -   **SRS v2 – OS 업데이트 패키지에** 필요한 모든 업데이트가 포함되어 있는지 확인합니다.
       -   **SRS v2 – OS 업데이트 패키지가** 선택되어 있는지 확인합니다.
       -   PowerShell 실행 정책이 우회로 **설정되어 있는지 확인**

   13. **컴퓨터 다시 시작:** 이 단계는 필수 운영 체제 업데이트가 설치된 후 컴퓨터를 다시 시작합니다. 이 단계에서는 사용자 지정이 필요하지 않습니다.

   14. **Windows 구성 요소 구성:** 이 단계에서는 필요한 Windows 기능을 구성합니다. 이 단계에서는 사용자 지정이 필요하지 않습니다.

   15. **컴퓨터 다시 시작:** 이 단계는 Windows 기능이 구성된 후 컴퓨터를 다시 시작합니다. 이 단계에서는 사용자 지정이 필요하지 않습니다.

   16. **로컬 Skype 사용자** 추가: 이 단계에서는 Windows에 자동으로 로그인하고 Microsoft Teams 회의실 응용 프로그램을 시작하는 데 사용되는 로컬 Skype 계정을 만듭니다. 이 단계에는 연결된 소프트웨어 패키지가 없습니다. 이에 대한 사용자 지정은 필요하지 않습니다.

   17. **SRS 애플리케이션** 설정 및 구성: 이 단계에서는 운영 체제의 다음 부팅에 대해 Microsoft Teams Rooms 애플리케이션 설치를 구성합니다.
       -   **SRS v2 – SRS 설정** 패키지 구성 및 **64비트** 파일 시스템 리디렉션 사용 안 하도록 설정이 선택되어 있는지 확인

> [!IMPORTANT]
> 작업 시퀀스 단계가 제공된 순서에 있어야 합니다. 단계의 순서를 수정하거나 추가 단계를 구성하면 배포가 중단될 수 있습니다.
>
> **SRS 애플리케이션** 단계 설정 및 구성은 작업 시퀀스의 마지막 단계가 되어야 합니다. 그렇지 않으면 배포가 실패할 수 있습니다.

### <a name="create-deployment-for-the-task-sequence"></a>작업 시퀀스에 대한 배포 만들기

1. 작업 시퀀스를 선택한 다음 배포를 **선택합니다.**

2. **찾아보기를** 선택하여 배포할 대상 컬렉션을 선택합니다.

3. 알 **수 없는 모든 컴퓨터를 선택한** 다음 확인을 **선택합니다.**

4. 다음을 **선택합니다.**

5. 목적 **드롭다운** **목록에서 사용 가능을** 선택합니다.

6. 다음 목록에서 미디어 및  **PXE만** 선택하고 다음을 **선택합니다.**
   > [!WARNING]
   > 목적이 **사용** 가능으로 설정되어 있는 것이 **매우 중요합니다.** 목적이 **필수로** **설정되어 있지** **않은지 확인** 또한 다음에서 사용할 수 있도록 만들기에서 미디어 및 **PXE만** **선택해야 합니다.**
   >
   > 이러한 값을 다른 값으로 설정하면 부팅 시 모든 컴퓨터에서 Microsoft Teams 회의실 배포 이미지를 얻을 수 있습니다.
7. 일정을 지정하지 말고 다음을 **선택합니다.**

8. 사용자 환경 섹션 내에서 아무 것도 **변경하지** 말고 다음을 **선택합니다.**

9. 경고 섹션 내에서 아무 것도 변경하지 **말고** 다음을 **선택합니다.**

10. 배포 지점 섹션 내에서 아무 것도 변경하지 **말고** 다음을 **선택합니다.**

11. 설정을 확인하고 다음을 **선택합니다.**

12. 닫기 **선택**

<a name="validate-and-troubleshoot-the-solution"></a>솔루션의 유효성 검사 및 문제 해결
--------------------------------------

Microsoft Endpoint Configuration Manager 작업 시퀀스를 완료한 후 테스트 실행을 수행하여 작업 시퀀스가 Microsoft Teams 회의실 단위를 배포하고 구성할 수 있는지 유효성을 검사해야 합니다.

1.  지원되는 이더넷 어댑터 중 하나를 사용하거나 Surface Dock을 사용하여 유선 네트워크에 테스트 디바이스를 연결합니다. 사용자 환경에 대해 PXE 부팅 기능이 구성되지 않은 경우 앞에서 만든 USB 플래시 [](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media) 드라이브의 부팅 이미지를 사용하여 USB에서 부팅하고 Configuration Manager에 연결할 수 있습니다.

2.  펌웨어에 액세스하고 PXE 부팅을 시작합니다.

    1.  Surface 디바이스의 전원이 꺼진지 확인합니다.

    2.  볼륨 증가 **단추를 누를 수** 있습니다.

    3.  전원 단추를 **누르고 니다.**

    4.  디바이스가 부팅을 시작한 후 볼륨 증가 **단추를 해제합니다.**

    5.  부팅 **구성을 선택합니다.**

    6.  다음 중 하나를 수행합니다.

        -   **PXE 부팅을 선택하고** 목록 맨 위로 끌어다 놓습니다. 또는 네트워크 어댑터에서 왼쪽으로 스와이프하여 디바이스에 즉시 부팅할 수 있습니다. 부팅 순서에는 영향을 주지 않습니다.
        -   부팅 미디어가 있는 USB 플래시 드라이브를 선택합니다.

3.  **종료를** 선택하고 지금 다시 **시작을 선택합니다.**

4.  메시지가 표시될 때 네트워크 부팅 **서비스에 대해 Enter를** 선택합니다.

5.  Windows PE가 메모리에 로드하고 작업 시퀀스 마법사가 시작됩니다. 다음을 **선택하여** 계속합니다.

6.  앞에서 가져온 작업 시퀀스를 선택하고 다음을 **선택합니다.**

7.  디스크 구성이 적용된 후 디바이스의 컴퓨터 이름을 지정하라는 메시지가 표시됩니다. 사용자 인터페이스는 Surface Pro 디바이스의 일련 번호를 기반으로 권장되는 컴퓨터 이름을 표시합니다. 제안된 이름을 수락하거나 새 이름을 지정할 수 있습니다. 컴퓨터 이름 할당 화면의 지침을 따릅니다. **수락을 선택하면** 배포가 시작됩니다.

8.  배포 프로세스의 나머지는 자동이기 때문에 더 이상 사용자 입력을 요청하지 않습니다.

9.  배포 작업 시퀀스가 디바이스 구성을 완료하면 Microsoft Teams Rooms 애플리케이션 설정을 구성하도록 요청하는 다음 구성 화면이 표시됩니다.

    ![Microsoft Teams Rooms 응용 프로그램의 초기 설정 화면](../media/room-systems-scale-image2.png)

10.  Surface Pro를 Microsoft Teams 회의실 콘솔에 연결하고 애플리케이션 설정을 구성합니다.

11.  [Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) 회의실에 나열된 기능이 배포된 장치에서 작동하고 있는지 확인합니다.


실패한 설치 문제를 해결하려면 CONFIGURATION Manager 작업 시퀀스에서 실행된 모든 단계를 기록하는 **SMSTS.log** 파일을 검사합니다.

SMSTS.log 파일은 빌드 프로세스의 단계에 따라 여러 경로 중 하나에 저장됩니다. SMSTS.log 파일의 경로를 식별하려면 다음 표를 참조합니다.


| **배포 단계**                                                            | **작업 시퀀스 로그 경로**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE, HDD 형식 이전                                                        | X: \\ Windows \\ Temp \\ smstslog \\ smsts.log             |
| WinPE, HDD 형식 이후                                                         | C: \\ _SMSTaskSequence \\ Logs \\ Smstslog \\ smsts.log    |
| Configuration Manager 에이전트가 설치되기 전에 배포된 운영 체제 | c: \\ _SMSTaskSequence \\ Logs \\ Smstslog \\ smsts.log    |
| 운영 체제 및 배포된 구성 관리자 에이전트                   | %windir% \\ System32 \\ ccm \\ logs \\ Smstslog \\ smsts.log |
| 작업 시퀀스 실행 완료                                                | %windir% \\ System32 \\ ccm \\ logs \\ smsts.log           |

> [!TIP]
> 작업 시퀀스 중에 **F8을** 선택하여 명령 콘솔을 연 다음 SMSTS.log 파일에 액세스할 수 있습니다.

PXE 부팅 문제를 해결하려면 PXE 작업과 관련이 있는 Configuration Manager 서버에서 다음 두 로그 파일을 검사합니다.

-   구성 관리자 설치 로그 디렉터리에 있는 **Pxecontrol.log**

-   MP(Configuration Manager 관리 지점) 로그 디렉터리에 있는 **Smspxe.log**

구성 관리자 설치 문제를 해결하는 데 사용할 수 있는 로그 파일의 전체 목록은 Microsoft Endpoint Configuration Manager 로그 파일 참조를 [참조하세요.](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files)
