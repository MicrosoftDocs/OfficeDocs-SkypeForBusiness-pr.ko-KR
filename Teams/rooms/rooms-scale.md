---
title: Microsoft Endpoint Configuration Manager를 사용 하 여 Microsoft 팀 대화방 배포
author: lanachin
ms.author: v-lanac
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
- seo-marvel-mar2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: 대규모 배포에서 Microsoft 팀 회의실을 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
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
ms.openlocfilehash: 04d5945e042293ad0cb1597307fd4a2b596bee39
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141021"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager를 사용 하 여 Microsoft 팀 대화방 배포

이 문서에서는 Microsoft 끝점 구성 관리자를 사용 하 여 Microsoft 팀 회의실 배포를 만드는 데 필요한 모든 정보를 제공 합니다.

구성 관리자가 제공 하는 사용 하기 쉬운 메서드를 사용 하 여 운영 체제 및 기타 응용 프로그램을 여러 대상 장치에 배포할 수 있습니다.

아래 설명 된 방법을 사용 하 여 Configuration Manager 구성을 안내 하 고 조직에 필요한 경우이 가이드에서 제공 하는 샘플 패키지 및 스크립트를 사용자 지정 합니다.

![Microsoft 팀 대화방 배포 프로세스 구성 관리자 사용](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> 이 솔루션은 Surface Pro 기반 배포 에서만 테스트를 거쳤습니다. Surface Pro를 기반으로 하지 않는 구성에 대 한 제조업체의 지침을 따릅니다.

## <a name="validate-prerequisites"></a>필수 조건 유효성 검사

Configuration Manager를 사용 하 여 Microsoft 팀 회의실을 배포 하려면 다음 필수 구성 요소 및 요구 사항을 충족 해야 합니다.

### <a name="microsoft-endpoint-configuration-manager-requirements"></a>Microsoft Endpoint Configuration Manager 요구 사항

-   Microsoft Endpoint Configuration Manager 버전은 1706 이상 이어야 합니다. 1710 이상을 사용 하는 것이 좋습니다. Configuration manager [에서 windows 10](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) 을 지 원하는 windows 10 버전에 대 한 자세한 내용은 configuration manager에서 확인 하세요.

-   Windows 10 용 지원 되는 버전의 Windows ADK (평가 및 배포 키트)가 설치 되어 있어야 합니다. 여러 버전의 Configuration Manager에서 사용할 수 있는 [Windows 10 ADK](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) 버전을 참조 하 고 배포에 올바른 버전이 포함 되어 있는지 확인 합니다.

-   사이트 시스템 서버에 배포 지점의 역할이 할당 되어 있어야 하며 네트워크에서 시작 된 배포를 사용 하려면 [PXE (부팅 전 실행 환경) 지원](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) 에 부팅 이미지를 사용 해야 합니다. PXE 지원이 사용 되지 않는 경우에는 배포에 [부팅 가능한 미디어](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) 를 사용할 수 있습니다.

-   네트워크 액세스 계정은 새 컴퓨터 (완전 한 금속) 배포 시나리오를 지원 하도록 구성 되어 있어야 합니다. 네트워크 액세스 계정의 구성에 대 한 자세한 내용은 [구성 관리자에 사용 되는 계정을](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)참조 하세요.

-   동일한 Microsoft 팀 대화방 이미지를 동시에 여러 장치에 배포 하는 경우 [멀티 캐스트 지원을](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)사용 하도록 설정 하는 것이 좋습니다.

### <a name="networking-requirements"></a>네트워킹 요구 사항

-   네트워크에는 Microsoft 팀 대화방 유닛이 배포 되는 서브넷에 대 한 자동 IP 주소 배포용으로 구성 된 DHCP (동적 호스트 구성 프로토콜) 서버가 있어야 합니다.

    > [!NOTE]
    > DHCP 임대 기간은 이미지 배포 기간 보다 긴 값으로 설정 해야 합니다. 그렇지 않으면 배포가 실패할 가능성이 있습니다.

-   스위치 및 Vlan을 비롯 한 네트워크는 PXE를 지원 하도록 구성 해야 합니다. IP 도우미 및 PXE 구성에 대 한 자세한 내용은 네트워크 공급 업체에 문의 하세요. 또는 PXE 지원이 사용 되지 않는 경우 배포에 대해 [부팅 가능한 미디어](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) 를 사용할 수 있습니다.

    > [!NOTE]
    > Surface Pro 장치의 경우 네트워크 (PXE 부팅)의 부팅은 이더넷 어댑터 또는 Microsoft의 도킹 스테이션을 사용 하는 경우에만 지원 됩니다. 타사 이더넷 어댑터는 Surface Pro를 사용 하 여 PXE 부팅을 지원 하지 않습니다. 자세한 내용은 [이더넷 어댑터 및 Surface 배포](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) 를 참조 하세요.

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a>운영 체제 배포용 Microsoft Endpoint Configuration Manager 구성

이 문서에서는 이미 올바른 구성 관리자 배포를 보유 하 고 있는 것으로 가정 하 고 구성 관리자를 처음부터 배포 하 고 구성 하는 데 필요한 모든 단계를 자세히 설명 하지 않습니다. Microsoft 끝점 구성 관리자의 [설명서와 구성 지침은](https://docs.microsoft.com/configmgr/) 훌륭한 리소스입니다. 아직 구성 관리자를 배포 하지 않은 경우 이러한 리소스부터 시작 하는 것이 좋습니다.

다음 지침을 사용 하 여 OSD (운영 체제 배포) 기능이 올바르게 구성 되어 있는지 확인 합니다.

### <a name="validate-and-upgrade-configuration-manager"></a>구성 관리자 유효성 검사 및 업그레이드

1.  Configuration Manager 콘솔에서 **관리** \> **업데이트 및 서비스**를 참조 하세요.

2.  설치 된 빌드 및 아직 설치 되지 않은 적용 가능한 업데이트를 확인 합니다.

3.  [구성 관리자에서 Windows 10에 대 한 지원을 검토 합니다](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client). 배포를 업그레이드 해야 하는 경우 설치할 업데이트를 선택한 다음 **다운로드**를 선택 합니다.

4.  다운로드가 완료 되 면 업데이트를 선택 하 고 **업데이트 팩 설치**를 선택 합니다.

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>PXE 및 멀티 캐스트를 지원 하도록 배포 지점 구성

1.  Configuration Manager 콘솔에서 **관리** \> **배포 지점**으로 이동 합니다.

2.  Microsoft 팀 대화방 배포를 서비스할 배포 지점의 서버를 선택한 다음 **속성**을 선택 합니다.

3.  **PXE** 탭을 선택 하 고 다음 설정을 사용할 수 있는지 확인 합니다.
    -   클라이언트에 대해 PXE 지원 사용
    -   이 배포 지점이 들어오는 PXE 요청에 응답할 수 있도록 허용
    -   알 수 없는 컴퓨터 지원 사용

4.  *선택 사항:* 멀티 캐스트 지원을 사용 하도록 설정 하려면 **멀티 캐스트** 탭을 선택 하 고 다음 설정을 사용할 수 있는지 확인 합니다.
    -   멀티 캐스트를 사용 하 여 여러 클라이언트에 동시에 데이터 전송
    -   네트워크 팀의 권장 사항에 따라 UDP 포트 범위 구성

### <a name="configure-the-network-access-account"></a>네트워크 액세스 계정 구성

1.  Configuration Manager 콘솔에서 **관리** \> **사이트 구성** \> **사이트로**이동한 다음 사이트를 선택 합니다.

2.  **설정** 그룹에서 **사이트 구성 요소** \> **소프트웨어 배포**구성을 선택 합니다.

3.  **네트워크 액세스 계정** 탭을 선택 합니다. 하나 이상의 계정을 설정한 다음 **확인**을 선택 합니다.

> [!NOTE]
> 계정에는 배포 지점의 서버에서 해당 **네트워크에서이 컴퓨터 액세스** 권한을 제외한 특별 한 권한이 필요 하지 않습니다. 일반 도메인 사용자 계정이 적합 합니다. 자세한 내용은 [구성 관리자에 사용 되는 계정을](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)참조 하세요.

### <a name="configure-a-boot-image"></a>부팅 이미지 구성

1.  Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> 의 **운영 체제** \> **부팅 이미지로**이동 합니다.

2.  **부팅 이미지 (x64)** 를 선택한 다음 **속성**을 선택 합니다.

3.  **데이터 원본** 탭을 선택 하 고 **PXE 사용 배포 지점의이 부팅 이미지 배포**를 사용 하도록 설정 합니다.

4.  **선택적 구성 요소** 탭을 선택 하 여 필수 구성 요소를 설치 합니다.

    1.  별모양 아이콘을 선택 하 고 **HTML (WinPE-HTA)** 을 검색 합니다.

    2.  **확인** 을 선택 하 여 HTML 응용 프로그램 지원 기능을 부팅 이미지에 추가 합니다.

5.  *선택 사항:* 배포 환경을 사용자 지정 하려면 **사용자 지정** 탭을 선택 합니다.
    -   배포 중에 명령 프롬프트에 대 한 액세스 권한을 부여 하려면 **명령 지원 (테스트만 해당)** 을 사용 하도록 설정 합니다. 이 기능을 사용 하도록 설정 하면 배포 중에 언제 든 지 **F8** 키를 선택 하 여 명령 프롬프트를 시작할 수 있습니다.
    -   배포 중에 표시할 사용자 지정 배경 이미지를 지정할 수도 있습니다. 이미지를 설정 하려면 **사용자 지정 배경 이미지 파일 (UNC 경로) 지정** 을 사용 하도록 설정한 다음 배경을 선택 합니다.

6.  메시지가 표시 되 면 **예** 를 선택 하 고 업데이트 된 부팅 이미지를 배포 지점에 배포 합니다.

자세한 내용은 [Configuration Manager를 사용 하 여 부팅 이미지 관리](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images)를 참조 하세요.

> [!NOTE]
> PXE 지원이 없는 환경에 대 한 Configuration Manager 작업 순서 기반 배포를 시작 하기 위해 부팅 가능 USB 미디어를 만들 수 있습니다. 부팅 가능 미디어에는 Windows PE로 부팅 하 고 나머지 배포 프로세스에 대해 구성 관리자에 연결 하는 데 사용할 부트 이미지, 선택적으로 제공 되는 명령 및 필요한 파일 및 구성 관리자 바이너리가 포함 됩니다. 자세한 내용은 [부팅 가능 미디어 만들기](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)를 참조 하세요.

## <a name="create-configuration-manager-packages"></a>Configuration Manager 패키지 만들기

> [!IMPORTANT]
> 모든 MSI 릴리스의 각 SRS installer 버전에 대해 필요한 운영 체제 버전이 변경 되었습니다. 지정 된 MSI에 가장 적합 한 운영 체제 버전을 확인 하려면 콘솔 설치 스크립트를 한 번 실행 합니다. 자세한 내용은 [Microsoft 끝점 구성 관리자를 사용 하 여 Microsoft 팀 대화방 배포](rooms-scale.md)를 참조 하세요.

Configuration Manager에서 Microsoft 팀 대화방 단위를 배포 하 고 구성 하려면 여러 패키지가 필요 합니다.

다음 패키지를 만들고 구성한 다음 배포 지점의 서버 역할이 지정 된 Configuration Manager 사이트 시스템에 배포 해야 합니다.

| **패키지 이름**                     | **유형**               | **설명**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2-SRS 응용 프로그램 패키지     | 소프트웨어 패키지       | Microsoft 팀 대화방 배포 키트 패키지                                      |
| SRS v2-Sysprep 패키지             | 소프트웨어 패키지       | Microsoft 팀 대화방 단위를 구성 하는 사용자 지정 무인 .xml 패키지            |
| SRS v2-집합-SRSComputerName 패키지 | 소프트웨어 패키지       | 배포 중 컴퓨터 이름을 할당 하는 HTA (HTML application) 패키지    |
| SRS v2-SRS 설정 구성         | 소프트웨어 패키지       | Microsoft 팀 대화방 앱 배포를 구성 하기 위한 패키지                          |
| SRS v2-OS 업데이트 패키지          | 소프트웨어 패키지       | 필수 운영 체제 업데이트를 배포 하기 위한 패키지                                      |
| SRS v2-루트 인증서 패키지    | 소프트웨어 패키지       | 선택-루트 인증서를 배포 하기 위한 패키지 (도메인 가입 된 장치에 필요 하지 않음)  |
| SRS v2-Microsoft Monitoring Agent 패키지 | 소프트웨어 패키지       | 선택-Microsoft Operations Management Suite 에이전트를 배포 하 고 구성 하는 패키지|
| SRS v2-WinPE 백그라운드 패키지    | 소프트웨어 패키지       | 부팅 이미지와 함께 사용할 사용자 지정 배경 이미지를 위한 패키지                           |
| Windows 10 Enterprise                | 운영 체제 이미지 | 운영 체제 설치 파일 (.wim)에 대 한 패키지                          |
| Surface Pro                          | 드라이버 패키지         | Microsoft Surface Pro 용 장치 드라이버 및 펌웨어의 패키지                     |
| Surface Pro 4                        | 드라이버 패키지         | Microsoft Surface Pro 4 용 장치 드라이버 및 펌웨어의 패키지                   |

자세한 내용은 [Configuration Manager에서 패키지 및 프로그램](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)을 참조 하세요.

### <a name="create-folders-for-the-package-source-files"></a>패키지 원본 파일에 대 한 폴더 만들기

구성 관리자를 사용 하려면 패키지 원본 파일이 처음 만들어지고 업데이트 될 때 특정 폴더 구조에 구성 되어야 합니다.

Microsoft Endpoint Configuration Manager 중앙 관리 사이트 또는 기본 사이트 또는 패키지 원본 파일을 호스트 하는 데 사용 중인 서버 공유에 다음 폴더 구조를 만듭니다.

-   SRS v2-Microsoft Monitoring Agent 패키지
-   SRS v2-OS 업데이트 패키지
-   SRS v2-루트 인증서 패키지
-   SRS v2-집합-SRSComputerName 패키지
-   SRS v2-SRS 응용 프로그램 패키지
-   SRS v2-SRS 설정 구성
-   SRS v2-Sysprep 패키지
-   드라이버
    -   Surface Pro
    -   Surface Pro 4
-   운영 체제
    -   Windows 10 Enterprise

> [!TIP]
> 패키지의 폴더 구조, 사용 해야 하는 스크립트, 가져오는 데 필요한 작업 순서 템플릿을 포함 하는 zip 파일을 [다운로드](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) 하 여 사용할 수도 있습니다.

### <a name="create-the-monitoring-agent-package"></a>모니터링 에이전트 패키지 만들기

1. 에서 <https://go.microsoft.com/fwlink/?LinkId=828603>모니터링 에이전트를 다운로드 합니다.

2. 명령 프롬프트 창을 열고 **MMASetup-AMD64/c:** 명령 프롬프트에서 다음을 입력 하 여 **SRS V2-Microsoft Monitoring Agent 패키지** 폴더로 패키지를 추출 합니다.

3. Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **응용 프로그램 관리** \> **패키지로**이동한 다음 **패키지 만들기**를 선택 합니다.

4. 패키지를 만들려면 다음 정보를 입력 합니다.

   - 이름<strong>: SRS v2-Microsoft Monitoring Agent 패키지</strong>

   - 제조 업체<strong>: Microsoft Corporation</strong>

   - 버전<strong>: 8.1.11081.0</strong> (다운로드 한 설치 파일의 버전을 입력 하십시오.)

   - **이 패키지에 원본 파일 포함** 확인란을 선택 하 고 **SRS V2-Microsoft Monitoring Agent 패키지** 폴더 경로를 입력 한 후 **다음**을 선택 합니다.

5. **프로그램 만들지 않음을**선택 하 고 **다음**을 선택 합니다.

6. **설정 확인** 페이지를 검토 하 고 **다음**을 선택 합니다.

7. **닫기를**선택 합니다.

### <a name="create-the-operating-system-updates-package"></a>운영 체제 업데이트 패키지 만들기

1. **SRS v2-OS 업데이트 패키지** 폴더에서 **Install-SRSv2-OS-Updates**이라는 새 PowerShell 스크립트를 만듭니다.

2. 아래 스크립트를 **Install-SRSv2-OS-Updates** 스크립트에 복사 합니다. 또는 [여기](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)에서 Install-SRSv2-OS-Updates 스크립트를 다운로드할 수 있습니다.
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
3. 동일한 폴더에 필수 Windows 업데이트 패키지를 다운로드 합니다.
   > [!NOTE]
   > 이 문서를 게시 한 시점에는 [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) 만 필요 합니다. [Microsoft 팀 대화방 콘솔 구성을](console.md)확인 하 여 다른 업데이트가 필요한 지 여부를 확인 합니다.

4. Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **응용 프로그램 관리** \> **패키지로**이동한 다음 **패키지 만들기**를 선택 합니다.

5. 패키지를 만들려면 다음 정보를 입력 합니다.
   -   이름: **SRS v2-OS 업데이트 패키지**
   -   제조 업체: **Microsoft Corporation**
   -   버전: **1.0.0**
   -   **이 패키지에 원본 파일 포함** 확인란을 선택 하 고 **SRS V2-OS 업데이트 패키지** 폴더 경로를 입력 한 후 **다음**을 선택 합니다.

6. **프로그램 만들지 않음을**선택 하 고 **다음**을 선택 합니다.

7. **설정 확인** 페이지를 검토 하 고 **다음**을 선택 합니다.

8. **닫기를**선택 합니다.

### <a name="create-the-root-certificate-package-optional"></a>루트 인증서 패키지 만들기 (선택 사항)

Active Directory 도메인에 가입 되지 않은 디바이스에 대 한 루트 인증서를 배포 하기 위해이 패키지를 만듭니다. 다음 두 조건이 모두 적용 되는 경우에만이 패키지를 만듭니다.
-   배포에 온-프레미스 Lync 또는 비즈니스용 Skype Server가 포함 되어 있습니다.
-   Microsoft 팀 대화방 단위는 도메인 구성원이 아닌 작업 그룹에서 작동 하도록 구성 됩니다.

1.  루트 인증서를 **SRS v2-루트 인증서 패키지** 폴더에 복사 합니다.

2.  Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **응용 프로그램 관리** \> **패키지로**이동한 다음 **패키지 만들기**를 선택 합니다.

3.  패키지를 만들려면 다음 정보를 입력 합니다.
    -   이름: **SRS v2 – 루트 인증서 패키지**
    -   제조업체: *조직의 이름*
    -   버전: **1.0.0**
    -   **이 패키지에 원본 파일 포함** 확인란을 선택 하 고 **SRS V2-루트 인증서 패키지** 폴더의 경로를 입력 한 후 **다음**을 선택 합니다.

4.  **프로그램 만들지 않음을**선택 하 고 **다음**을 선택 합니다.

5.  **설정 확인** 페이지를 검토 하 고 **다음**을 선택 합니다.

6.  **닫기를**선택 합니다.

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Microsoft 팀 대화방 배포 키트 패키지 만들기

1.  의 **Microsoft 팀 공간 배포 키트** 최신 버전 <https://go.microsoft.com/fwlink/?linkid=851168>을 다운로드 하 여 워크스테이션에 설치 합니다.

2.  **C:\\Program Files (x86)\\Skype 회의실 시스템 배포 키트** 의 콘텐츠를 **SRS v2-srs 응용 프로그램 패키지** 폴더로 복사 합니다.

3.  Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **응용 프로그램 관리** \> **패키지로**이동한 다음 **패키지 만들기**를 선택 합니다.

4.  패키지를 만들려면 다음 정보를 입력 합니다.
    -   이름: **srs v2-Srs 응용 프로그램 패키지**
    -   제조 업체: **Microsoft Corporation**
    -   버전: **3.1.104.0** (다운로드 한 설치 파일의 버전을 입력 하십시오.)
    -   **이 패키지에 원본 파일 포함** 확인란을 선택 하 고 **SRS V2-Srs 응용 프로그램 패키지** 폴더 경로를 입력 한 후 **다음**을 선택 합니다.
5.  **프로그램 만들지 않음을**선택 하 고 **다음**을 선택 합니다.

6.  **설정 확인** 페이지를 검토 하 고 **다음**을 선택 합니다.

7.  **닫기를**선택 합니다.

### <a name="create-the-computer-name-assignment-package"></a>컴퓨터 이름 할당 패키지 만들기

1.  **SRS V2 Set-SRSComputerName 패키지** 폴더에서 **SET-SRSCOMPUTERNAME** 이라는 새 HTML 응용 프로그램을 만듭니다.

2.  **Set-SRSComputerName** 파일에 다음 스크립트를 복사 합니다. 또는 [여기](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)에서 Set-SRSComputerName 파일을 다운로드할 수 있습니다.
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
3.  Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **응용 프로그램 관리** \> **패키지로**이동한 다음 **패키지 만들기**를 선택 합니다.

4.  패키지를 만들려면 다음 정보를 입력 합니다.

    -   Name: **SRS V2 Set-SRSComputerName 패키지**

    -   제조 업체: **Microsoft Corporation**

    -   버전: **1.0.0**

    -   **이 패키지에 원본 파일 포함** 확인란을 선택 하 고 **SRS V2 집합-Srscomputername 패키지** 폴더 경로를 입력 한 후 **다음**을 선택 합니다.

5.  **프로그램 만들지 않음을**선택 하 고 **다음**을 선택 합니다.

6.  **설정 확인** 페이지를 검토 하 고 **다음**을 선택 합니다.

7.  **닫기를**선택 합니다.

### <a name="create-the-sysprep-package"></a>Sysprep 패키지 만들기

1. **SRS v2-Sysprep 패키지** 폴더에서 **UNATTEND.XML** 이라는 새 XML 파일을 만듭니다.

2. 다음 텍스트를 **Unattend .xml** 파일에 복사 합니다. 또는 [여기](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)에서 unattend.xml 파일을 다운로드할 수 있습니다.
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
3. Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **응용 프로그램 관리** \> **패키지로**이동한 다음 **패키지 만들기**를 선택 합니다.

4. 패키지를 만들려면 다음 정보를 입력 합니다.
   -   이름: **SRS v2-Sysprep 패키지**
   -   제조 업체: **Microsoft Corporation**
   -   버전: **1.0.0**
   -   **이 패키지에 원본 파일 포함** 확인란을 선택 하 고 **SRS V2-Sysprep 패키지** 폴더 경로를 입력 한 후 **다음**을 선택 합니다.
5. **프로그램 만들지 않음을**선택 하 고 **다음**을 선택 합니다.

6. **설정 확인** 페이지를 검토 하 고 **다음**을 선택 합니다.

7. **닫기를**선택 합니다.

### <a name="create-the-windows-10-enterprise-package"></a>Windows 10 Enterprise 패키지 만들기

1.  Windows 10 Enterprise x64 미디어를 구하여 **설치 .wim** 파일을 **운영 체제\\Windows 10 enterprise** 폴더에 복사 합니다.

2.  Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **운영** \> **체제로 이동한**다음 운영 체제 이미지 **추가**를 선택 합니다.

3.  방금 복사한 **설치 .wim** 파일의 경로를 지정 하 고 **다음**을 선택 합니다.

4.  Windows 10 Enterprise 이미지의 빌드 번호와 일치 하도록 **Version** 필드를 업데이트 하 고 **다음**을 선택 합니다.

5.  **세부 정보** 페이지를 검토 하 고 **다음**을 선택 합니다.

6.  **닫기를**선택 합니다.

자세한 내용은 [Configuration Manager를 사용 하 여 OS 이미지 관리](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images)를 참조 하세요.

### <a name="create-surface-pro-device-driver-packages"></a>Surface Pro 장치 드라이버 패키지 만들기

Microsoft 팀 대화방은 Surface Pro 및 Surface Pro 4에서 모두 지원 됩니다. 환경에 있는 각 Surface Pro 모델에 대 한 드라이버 패키지를 만들어야 합니다.

> [!IMPORTANT]
> 드라이버는 Windows 10 Enterprise 빌드 및 Microsoft 팀 대화방 배포 키트 버전과 호환 되어야 합니다. 자세한 내용은 [Surface 장치에 대 한 최신 펌웨어 및 드라이버 다운로드](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) 및 [콘솔 구성을](console.md)참조 하세요.

1.  최신 드라이버 및 펌웨어를 다운로드 합니다.
    -   Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484>
    -   Surface Pro 4의 경우:<https://www.microsoft.com/download/details.aspx?id=49498>

2.  다운로드 한 드라이버와 펌웨어를 추출 합니다. 명령 프롬프트 창을 열고 명령 프롬프트에서 다음 명령 중 하나를 입력 합니다.
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **운영 체제** \> **드라이버로**이동한 다음 **드라이버 가져오기를**선택 합니다.

4.  **다음 네트워크 경로 (UNC)에서 모든 드라이버 가져오기를**선택 하 고 원본 폴더 (예: C\\: _Sources\\drivers\\Surface Pro)를 선택한 후 **다음**을 선택 합니다.

5.  **가져온 드라이버에 대 한 세부 정보 지정** 페이지에서 나열 된 모든 드라이버를 선택 하 고 **다음 드라이버 사용 및 컴퓨터에서 설치 하도록 허용**을 선택 합니다.

6.  **범주**를 선택 하 고, 표면 모델과 일치 하는 새 범주를 만들고, **확인**을 선택한 후 **다음**을 선택 합니다.

7.  **새 패키지**를 선택 합니다.

8.  Surface Pro 모델과 일치 하는 패키지 이름을 지정 하 고, 드라이버 패키지 파일을 저장할 폴더 경로를 입력 하 고, **확인**을 선택 하 고 **다음**을 선택 합니다.

9.  **부팅 이미지** 페이지에서 부팅 이미지가 선택 되어 있지 않은지 확인 하 고 **다음**을 선택 합니다.

10. **닫기를**선택 합니다.

11. **소프트웨어 라이브러리** \> **운영 체제** \> **드라이버로**이동 하 고 **폴더 \> 만들기**를 선택한 다음 방금 드라이버를 가져온 Surface Pro 모델과 일치 하는 폴더 이름을 입력 합니다.

12. 가져온 모든 드라이버를 새로 만든 폴더로 이동 하 여 탐색 및 작업을 더 쉽게 수행할 수 있습니다.

> [!NOTE]
> 사용할 수 있는 다른 Surface Pro 모델에 대해 같은 단계를 반복 합니다. 자세한 내용은 [구성 관리자에서 드라이버 관리](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers)를 참조 하세요.

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Microsoft 팀 대화방 구성 패키지 만들기

1.  Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **응용 프로그램 관리** \> **패키지로**이동한 다음 **패키지 만들기**를 선택 합니다.

2.  패키지를 만들려면 다음 정보를 입력 합니다.

    -   이름: **srs v2-Srs 설치 패키지 구성**

    -   제조 업체: **Microsoft Corporation**

    -   버전: **1.0.0**

    -   **이 패키지에 원본 파일 포함** 확인란을 선택 하 고 **SRS V2-srs 구성 설정** 폴더 경로를 입력 한 후 **다음**을 선택 합니다.

3.  **프로그램 만들지 않음을**선택 하 고 **다음**을 선택 합니다.

4.  **설정 확인** 페이지를 검토 하 고 **다음**을 선택 합니다.

5.  **닫기를**선택 합니다.



## <a name="distribute-configuration-manager-packages"></a>Configuration Manager 패키지 배포

모든 패키지는 Configuration Manager 계층 구조에서 배포 지점이 역할을 할당 한 서버에 배포 되어야 합니다. 패키지 배포를 시작 하려면 아래 지침을 따르세요.

1.  소프트웨어 패키지를 배포 합니다.

    1.  Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **응용 프로그램 관리** \> **패키지로**이동 합니다. 배포 하려는 소프트웨어 패키지를 모두 선택 하 고 **콘텐츠 배포**를 선택 합니다.

    2.  패키지 목록을 검토 하 고 **다음**을 선택 합니다.

    3.  모든 배포 지점의 서버 (또는 Configuration Manager 계층 구조에 따라 배포 지점의 그룹)를 목록에 추가 하 고 **다음**을 선택 합니다.

    4.  **다음**을 선택 하 고 **닫기를**선택 합니다.

2.  드라이버 패키지를 배포 합니다.

    1.  Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> 의 **운영 체제** \> **드라이버 패키지로**이동 합니다. 배포 하려는 모든 드라이버 패키지를 선택 하 고 **콘텐츠 배포**를 선택 합니다.

    2.  패키지 목록을 검토 하 고 **다음**을 선택 합니다.

    3.  모든 배포 지점의 서버 (또는 Configuration Manager 계층 구조에 따라 배포 지점의 그룹)를 목록에 추가 하 고 **다음**을 선택 합니다.

    4.  **다음**을 선택 하 고 **닫기를**선택 합니다.

3.  운영 체제 패키지를 배포 합니다.

    1.  Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **운영** \> 체제 ( **운영 시스템 이미지**)로 이동 합니다. 배포 하려는 모든 운영 체제 이미지를 선택한 다음 **콘텐츠 배포**를 선택 합니다.

    2.  패키지 목록을 검토 하 고 **다음**을 선택 합니다.

    3.  모든 배포 지점의 서버 (또는 Configuration Manager 계층 구조에 따라 배포 지점의 그룹)를 목록에 추가 하 고 **다음**을 선택 합니다.

    4.  **다음**을 선택 하 고 **닫기를**선택 합니다.

> [!NOTE]
> 패키지 배포에는 패키지 크기, 구성 관리자 계층 구조, 배포 지점의 서버 수, 네트워크에서 사용할 수 있는 대역폭에 따라 약간의 시간이 걸릴 수 있습니다.
> 
> Microsoft 팀 회의실 단위 배포를 시작 하려면 먼저 모든 패키지를 배포 해야 합니다.
> 
> **Monitoring** \> **배포** 상태 \> **콘텐츠 상태**모니터링으로 진행 하 여 Configuration Manager 콘솔에서 패키지 배포의 상태를 검토할 수 있습니다.

## <a name="configuration-manager-task-sequences"></a>Configuration Manager 작업 순서

작업 순서를 구성 관리자와 함께 사용 하 여 운영 체제 이미지를 대상 컴퓨터에 배포 하는 단계를 자동화 합니다. Microsoft 팀 회의실 단위를 자동화 된 방식으로 배포 하려면 대상 Microsoft 팀 공간 컴퓨터를 시작 하는 데 사용 되는 부팅 이미지, 설치 하려는 Windows 10 Enterprise 운영 체제 이미지, 기타 응용 프로그램 또는 소프트웨어 업데이트 등의 다른 추가 콘텐츠를 참조 하는 작업 순서를 만듭니다.

### <a name="import-the-sample-task-sequence"></a>샘플 작업 순서 가져오기

샘플 작업 순서를 다운로드 하 여 쉽게 가져와 필요에 맞게 사용자 지정할 수 있습니다.

1.  예제 작업 순서를 [**다운로드**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) 하 고 다운로드 한 zip 파일을 공유 위치에 복사 합니다.
2.  Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **운영 체제** \> **작업 시퀀스로**이동한 다음 **작업 순서 가져오기를**선택 합니다.

3.  **찾아보기를**선택 하 고 1 단계에서 사용한 공유 폴더 위치로 이동한 다음 **Microsoft 팀 대화방 배포 (en-us) .zip** 파일을 선택 하 고 **다음**을 선택 합니다.

4.  **새로 만들기** **작업** 을 설정 하 고 **다음**을 선택 합니다.

5.  설정을 확인 하 고 **다음**을 선택 합니다.

6.  **닫기를**선택 합니다.

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>참조 패키지가 각 작업 순서 단계에 제대로 연결 되어 있는지 확인 합니다.

1. 가져온 작업 순서를 선택 하 고 **편집**을 선택 합니다.

    작업 순서 편집기가 열리고 Microsoft 팀 대화방 단위를 배포 하 고 구성 하는 데 필요한 각 순차적 단계가 표시 됩니다.

2. 각 단계를 살펴보고 권장 업데이트를 완료 합니다.

   1. **WINDOWS PE에서 다시 시작**:이 단계는 컴퓨터를 다시 시작 하 고 Windows PXE로 부팅 합니다. 이 단계에서는 변경할 필요가 없습니다.

   2. **파티션 디스크 0 – UEFI**:이 단계에서는 디스크 구성을 닦아내기 하 고 구성 된 설정을 기반으로 파티션을 만듭니다. 이 단계는 변경 하지 않는 것이 좋습니다.

   3. **SRS 컴퓨터 이름 설정**:이 단계에는 배포 중 Microsoft 팀 공간 단위에 대 한 컴퓨터 이름을 설정 하는 UI를 제공 하는 HTML 응용 프로그램이 포함 됩니다.
      -  이 단계는 선택 사항 이지만 대체 프로세스를 통해 컴퓨터 명명을 관리 하려는 경우에만 사용 하지 않도록 설정할 수 있습니다.
      -  **SRS V2 Set-SRSComputerName** 패키지를 선택 했는지 확인 합니다. 그렇지 않으면 패키지를 찾아 선택 합니다.

   4. **운영 체제 적용**:이 단계에서는 배포할 운영 체제 이미지와 무인 Sysprep 응답 파일을 지정 합니다.
      -  올바른 Windows 10 Enterprise 운영 체제 이미지 파일이 선택 되어 있는지 확인 합니다.
      -  **사용자 지정 설치에 무인 또는 sysprep 응답 파일을 사용** 하도록 설정 되어 있는지 확인 하 고 **SRS V2-Sysprep 패키지** 를 선택 합니다. 또한 **파일 이름이** **unattend.xml**으로 설정 되어 있는지 확인 합니다.

   5. **Windows 설정 적용**:이 단계에서는 windows 설치에 대 한 정보를 수집 합니다.
      -  제품 키, 로컬 관리자 계정 암호, 표준 시간대 (필요에 따라 다름)를 포함 하 여 라이선스 및 등록 정보를 제공 합니다.

   6. **네트워크 설정 적용**:이 단계에서는 작업 그룹 또는 Active Directory 도메인 이름 및 조직 구성 단위를 지정할 수 있습니다.
      > [!NOTE]
      > Microsoft 팀 대화방 단위를 Actve 디렉터리 도메인의 구성원으로 배포 하는 데 필요한 권장 작업에 대 한 [Skype 대화방 시스템 도메인 참가 고려 사항을](domain-joining-considerations.md) 참조 하세요.
   7. **드라이버 적용:** 이 단계 및 해당 하위 단계는 보유 하 고 있는 Surface Pro 모델을 기반으로 적용 가능한 디바이스 드라이버와 펌웨어를 배포 하는 데 사용 됩니다. 각 단계를 업데이트 하 여이 배포와 연결 된 관련 드라이버 패키지를 지정 합니다.
      -   각 드라이버 패키지는 Surface Pro 만들기 및 모델을 기반으로 관련 드라이버와 펌웨어를 배포 하기 위해 WMI (Windows Management Instrumentation) 필터를 활용 하도록 구성 됩니다.
      -   이러한 드라이버의 구성은 변경 하지 않는 것이 좋으며, 그렇지 않은 경우에는 배포가 실패할 것을 적극 권장 합니다.

   8. **Windows 및 구성 관리자 설정**:이 단계에서는 Configuration manager 클라이언트를 배포 하 고 구성 합니다. 이 단계를 업데이트 하 여 기본 제공 Configuration Manager 클라이언트 패키지를 지정 합니다.

   9. **루트 인증서 설치**:이 단계는 도메인에 연결 되지 않은 디바이스에 대 한 루트 인증서를 배포 하므로 기본적으로 선택 및 비활성화 되어 있습니다.
      -   Microsoft 팀 회의실 단위에 루트 인증서를 배포 해야 하는 경우이 단계를 사용 합니다.
      -   이 단계를 수행 해야 하는 경우 **SRS v2-루트 인증서 패키지** 및 **사용 안 함 64 비트 파일 시스템 리디렉션이** 선택 되어 있는지 확인 합니다.

   10. **모니터링 에이전트 설치 및 구성**:이 단계에서는 64 비트 버전의 Microsoft Azure 모니터 에이전트를 설치 하 고 에이전트를 로그 분석 작업 영역에 연결 하도록 구성 합니다.
       -   이 단계는 기본적으로 비활성화 되어 있습니다. 모니터링 에이전트를 사용 하 여 Microsoft 팀 회의실의 상태를 모니터링 하는 경우에만이 단계를 사용 하도록 설정 하세요.
       -   이 단계를 편집 하 고 명령줄 매개 변수를 업데이트 하 여 **작업 영역 ID** 와 **작업 영역 키**를 지정 합니다.
       -   Operations Management Suite 작업 영역 ID 및 기본 키를 가져오는 방법에 대 한 자세한 내용은 [Azure 모니터링에 대 한 테스트 장치 구성을](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) 참조 하세요.
       -   **SRS v2-Microsoft Monitoring Agent 패키지** 및 **사용 안 함 64 비트 파일 시스템 리디렉션이** 선택 되어 있는지 확인 합니다.
       -   Microsoft 팀 대화방 배포의 상태를 모니터링 하는 방법에 대 한 자세한 내용은 azure [모니터로 Microsoft 팀 대화방 관리 계획](azure-monitor-plan.md), Azure 모니터로 [microsoft 팀 대화방 관리 배포](azure-monitor-deploy.md) 및 [azure Monitor를 사용 하 여 microsoft 팀 공간 장치 관리](azure-monitor-manage.md)를 참조 하세요.

   11. **SRS V2 구성 파일 복사**:이 단계에서는 Microsoft 팀 대화방 배포 키트의 필수 설정 파일과 구성 파일을 로컬 하드 드라이브에 복사 합니다. 이 단계에서는 사용자 지정이 필요 하지 않습니다.
       -   **Srs v2-Srs 응용 프로그램 패키지** 및 **사용 안 함 64 비트 파일 시스템 리디렉션이** 선택 되어 있는지 확인 합니다.

   12. **설치-SRSv2-OS-업데이트**:이 단계는 Microsoft 팀 대화방 배포에 필요한 필수 운영 체제 업데이트를 배포 합니다. 다음을 수행합니다.
       -   [Microsoft 팀 대화방 콘솔 구성을](console.md) 선택 하 여 필요한 업데이트를 확인 합니다.
       -   **SRS v2-OS 업데이트 패키지** 에 필수 업데이트가 모두 포함 되어 있는지 확인 합니다.
       -   **SRS v2-OS 업데이트 패키지가** 선택 되어 있는지 확인 합니다.
       -   PowerShell 실행 정책이 **Bypass**으로 설정 되어 있는지 확인 합니다.

   13. **컴퓨터 다시 시작**:이 단계에서는 필수 운영 체제 업데이트가 설치 된 후 컴퓨터를 재부팅 합니다. 이 단계에서는 사용자 지정이 필요 하지 않습니다.

   14. **Windows 구성 요소 구성**:이 단계에서는 필요한 Windows 기능을 구성 합니다. 이 단계에서는 사용자 지정이 필요 하지 않습니다.

   15. **컴퓨터 다시 시작**:이 단계는 Windows 기능을 구성한 후 컴퓨터를 재부팅 합니다. 이 단계에서는 사용자 지정이 필요 하지 않습니다.

   16. **로컬 Skype 사용자 추가**:이 단계는 Windows에 자동으로 로그인 하 여 Microsoft 팀 회의실 응용 프로그램을 시작 하는 데 사용 되는 로컬 Skype 계정을 만듭니다. 이 단계에는 연결 된 소프트웨어 패키지가 없으며 사용자 지정이 필요 하지 않습니다.

   17. **SRS 응용 프로그램 설정 및 구성**:이 단계에서는 다음 운영 체제 부팅을 위해 Microsoft 팀 대화방 응용 프로그램 설치를 구성 합니다.
       -   **Srs v2-Srs 설치 패키지 구성** 및 **64 비트 파일 시스템 리디렉션 사용 안 함** 이 선택 되어 있는지 확인 합니다.

> [!IMPORTANT]
> 작업 순서 단계는 제공 되는 순서 대로 진행 되어야 한다는 것이 중요 합니다. 단계의 순서를 수정 하거나 추가 단계를 구성 하면 배포가 중단 될 수가 있습니다.
>
> **SRS 응용 프로그램 설정 및 구성** 단계는 작업 순서의 마지막 단계 여야 하며 그렇지 않으면 배포가 실패할 수 있습니다.

### <a name="create-deployment-for-the-task-sequence"></a>작업 순서에 대 한 배포 만들기

1. 작업 순서를 선택 하 고 **배포**를 선택 합니다.

2. **찾아보기를** 선택 하 여 배포용 대상 모음을 선택 합니다.

3. **알 수 없는 모든 컴퓨터** 를 선택 하 고 **확인**을 선택 합니다.

4. **다음**을 선택 합니다.

5. **용도** 드롭다운 목록에서 **사용 가능** 을 선택 합니다.

6. **다음을 사용 하 여 설정** 목록에서 **미디어 및 PXE만** 을 선택 하 고 **다음**을 선택 합니다.
   > [!WARNING]
   > **용도가** **사용 가능**으로 설정 되어 있어야 합니다. **용도가** **필수**로 설정 **되지** 않았는지 확인 합니다. 또한 **다음에 사용할 수 있도록 설정**에서 **미디어 및 PXE만** 선택 하도록 합니다.
   >
   > 이러한 값을 다른 항목으로 설정 하면 모든 컴퓨터에서 부팅할 때 Microsoft 팀 공간 배포 이미지가 표시 될 수 있습니다.
7. 일정을 지정 하지 않고 **다음**을 선택 합니다.

8. **사용자 환경** 섹션 내에서 아무것도 변경 하지 말고 **다음**을 선택 합니다.

9. **알림** 섹션 내에서 아무것도 변경 하지 말고 **다음**을 선택 합니다.

10. **배포 지점** 섹션 내에서 아무것도 변경 하지 말고 **다음**을 선택 합니다.

11. 설정을 확인 하 고 **다음**을 선택 합니다.

12. **닫기를**선택 합니다.

<a name="validate-and-troubleshoot-the-solution"></a>해결 방법 유효성 검사 및 문제 해결
--------------------------------------

Microsoft 끝점 구성 관리자 작업 시퀀스를 완료 한 후에는 작업 순서가 Microsoft 팀 대화방 단위를 배포 하 고 구성할 수 있는지 확인 하기 위해 테스트 실행을 수행 해야 합니다.

1.  지원 되는 이더넷 어댑터 중 하나를 사용 하거나 Surface dock를 사용 하 여 테스트 장치를 유선 네트워크에 연결 합니다. PXE 부팅 기능이 환경에 맞게 구성 되지 [않은 경우 이전에 만든](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media) usb 플래시 드라이브의 부팅 이미지를 사용 하 여 usb에서 부팅 하 고 구성 관리자에 연결할 수 있습니다.

2.  펌웨어에 액세스 하 고 PXE 부팅 시작:

    1.  Surface 디바이스의 전원이 꺼져 있는지 확인 합니다.

    2.  **볼륨 크게** 단추를 길게 누릅니다.

    3.  **전원** 단추를 눌렀다가 놓습니다.

    4.  장치가 부팅 되기 시작한 후 **볼륨을 위로** 단추를 놓습니다.

    5.  **부팅 구성을**선택 합니다.

    6.  다음 중 하나를 수행 합니다.

        -   **PXE 부팅**을 선택 하 고 목록 맨 위로 끕니다. 또는 네트워크 어댑터에서 왼쪽으로 살짝 밀어 장치에 바로 부팅할 수 있습니다. 이는 부팅 순서에 영향을 주지 않습니다.
        -   부팅 미디어를 보유 하는 USB 플래시 드라이브를 선택 합니다.

3.  **끝내기**를 선택 하 고 **지금 다시 시작**을 선택 합니다.

4.  메시지가 표시 되 면 네트워크 부팅 서비스에 대해 **Enter** 를 선택 합니다.

5.  Windows PE가 메모리에 로드 되 고 작업 순서 마법사가 시작 됩니다. **Next (다음** )를 선택 하 여 계속 합니다.

6.  이전에 가져온 작업 순서를 선택 하 고 **다음**을 선택 합니다.

7.  디스크 구성이 적용 된 후 장치에 대 한 컴퓨터 이름을 지정 하 라는 메시지가 표시 됩니다. 사용자 인터페이스에는 Surface Pro 디바이스의 일련 번호를 기준으로 권장 컴퓨터 이름이 표시 됩니다. 제안 된 이름을 그대로 사용 하거나 새로 지정할 수 있습니다. 컴퓨터 이름 할당 화면의 지침을 따릅니다. **수락**을 선택 하면 배포가 시작 됩니다.

8.  나머지 배포 프로세스는 자동으로 진행 되며 사용자 입력을 더 이상 요구 하지 않습니다.

9.  배포 작업 순서에 따라 디바이스 구성이 완료 되 면 Microsoft 팀 대화방 응용 프로그램 설정을 구성 하 라는 다음 구성 화면이 표시 됩니다.

    ![Microsoft 팀 대화방 응용 프로그램의 초기 설정 화면](../media/room-systems-scale-image2.png)

10.  Surface Pro를 Microsoft 팀 공간 콘솔에 연결 하 고 응용 프로그램 설정을 구성 합니다.

11.  [Microsoft 팀 대화방](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) 에 나열 된 기능이 배포 된 장치에서 작동 하는지 확인 합니다.


실패 한 설치 문제를 해결 하려면 Configuration Manager 작업 순서에서 실행 되는 모든 단계를 기록 하는 **Smsts .log** 파일을 확인 합니다.

SMSTS .log 파일은 빌드 프로세스의 단계에 따라 여러 경로 중 하나에 저장 됩니다. 다음 표를 참조 하 여 SMSTS .log 파일의 경로를 확인 합니다.


| **배포 단계**                                                            | **작업 순서 로그 경로**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE, HDD 형식 앞                                                        | X:\\Windows\\\temp\\smstslog\\smsts. 로그             |
| HDD 형식 이후 WinPE                                                         | C:\\_SMSTaskSequence\\로그\\Smstslog\\smsts .log    |
| 구성 관리자 에이전트를 설치 하기 전에 배포 되는 운영 체제 | c:\\_SMSTaskSequence\\로그\\Smstslog\\smsts .log    |
| 운영 체제 및 구성 관리자 에이전트 배포 됨                   | % windir%\\System32\\ccm\\\\Smstslog\\smsts. i i 로그 |
| 작업 순서 실행 완료                                                | % windir%\\System32\\ccm\\은\\smsts .log를 기록 합니다.           |

> [!TIP]
> 작업 순서 중 언제 든 지 **F8** 키를 선택 하 여 명령 콘솔을 연 다음 smsts. i f f f f f f f f f f f f f f f f f f f f

PXE 부팅 문제를 해결 하려면 Configuration Manager 서버의 PXE 동작과 관련 된 두 로그 파일을 확인 합니다.

-   Configuration Manager 설치 로그 디렉터리에 있는 **Pxecontrol .log**

-   **Smspxe .log**(Configuration Manager 관리 위치 (MP) 로그 디렉터리에 있음)

Configuration Manager 설치 문제를 해결 하는 데 사용할 수 있는 전체 로그 파일 목록은 Microsoft Endpoint Configuration Manager [로그 파일 참조](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files)를 참조 하세요.
