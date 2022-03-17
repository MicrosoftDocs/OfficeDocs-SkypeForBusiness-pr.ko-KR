---
title: 이미지 Microsoft Teams 룸 빌드
ms.author: czawideh
author: cazawideh
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 이 문서에서는 콘솔 및 주변 장치를 설정하고 Microsoft Teams 룸 방법을 설명합니다.
ms.openlocfilehash: c13a247f2ce9d7fee7571f7f3a202310b2ce8b41
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514723"
---
# <a name="build-a-microsoft-teams-rooms-image"></a>이미지 Microsoft Teams 룸 빌드

이 문서에서는 대량 배포를 위한 Microsoft Teams 룸 이미지를 빌드하는 방법을 Teams 룸.

> [!NOTE]
> 다음 단계는 대량 배포를 위해 [WIM 기반 이미지를](/windows-hardware/manufacture/desktop/capture-and-apply-an-image) 만들 때만 사용해야 합니다. 개별 디바이스를 복구하는 경우 지원이 필요한 경우 OEM(원래 장비 제조업체)에 문의합니다.

배포에서 설명한 Microsoft Teams 또는 비즈니스용 Skype Exchange 계정이 이미 만들어진 경우만 이러한 단계를 [Microsoft Teams 룸](rooms-deploy.md). 요구 사항에 설명된 하드웨어 [및 Microsoft Teams 룸 필요합니다](requirements.md). 이 항목에는 다음 섹션이 포함되어 있습니다.
  
- [설치 미디어 준비](console.md#Prep_Media)
- [본체에 개인 CA 인증서 설치](console.md#Certs)
- [콘솔 Windows 10 및 Microsoft Teams 룸 설치](console.md#Reimage)
- [콘솔의 초기 설정](console.md#Initial)
- [Microsoft Teams 룸 배포 검사 목록](console.md#Checklist)

## <a name="prepare-the-installation-media"></a>설치 미디어 준비
<a name="Prep_Media"> </a>

콘솔 Microsoft Teams 룸 설치하려면 용량이 32GB 이상인 USB 저장소 디바이스가 필요합니다. 디바이스에 다른 파일이 없습니다. USB 저장소의 기존 파일이 손실됩니다.
  
> [!NOTE]
> 이러한 지침에 Microsoft Teams 룸 설치 미디어를 만들지 못하면 예기치 않은 동작이 발생할 수 있습니다.

> [!NOTE]
> 아래 프로세스는 새 디바이스를 이미지하는 설치 미디어를 Microsoft Teams 룸 것입니다. 기존 디바이스는 기본적으로 업데이트 및 Windows 저장소에서 Windows 업데이트합니다.

> [!IMPORTANT]
> Windows 10 설치 미디어를 만드는 데 Microsoft Teams 룸 컴퓨터는 대상 설치 미디어와 동일한 또는 Windows 버전에 있어야 합니다.
  
1. 스크립트를 [CreateSrsMedia.ps1 다운로드합니다](https://go.microsoft.com/fwlink/?linkid=867842).
2. CreateSrsMedia.ps1 컴퓨터의 상승된 프롬프트에서 Windows 10 실행합니다.
3. 스크립트의 지침에 따라 USB Microsoft Teams 룸 만들 수 있습니다.


> [!TIP]
> 스크립트가 CreateSrsMedia.ps1 시작할 때마다 화면 출력에는 세션에 대한 로그 파일 또는 전사 이름이 포함됩니다. 스크립트를 실행하는 데 문제가 있는 경우 지원을 요청할 때 해당 녹취록의 복사본을 사용할 수 있는지 확인 합니다. 

CreateSrsMedia.ps1 스크립트는 다음 작업을 자동화합니다.

1. 최신 MSI 설치 관리자를 다운로드하여 Microsoft Teams 룸.
2. 사용자가 제공해야 하는 Windows 빌드를 결정합니다. 가장 최근에 릴리스된 버전은 디바이스와 함께 사용하기 위해 테스트되거나 지원되지 않을 Microsoft Teams 룸 있습니다.
3. 필요한 지원 구성 요소를 다운로드합니다.
4. 설치 미디어에서 필요한 구성 요소를 조립합니다.

> [!NOTE]
특정 버전의 Windows 10 필요하며, 이 버전은 볼륨 라이선스 고객에게만 사용할 수 있습니다.  볼륨 라이선스 서비스 센터에서 복사본 [을 얻을 수 있습니다](https://www.microsoft.com/Licensing/servicecenter/).

완료되면 컴퓨터에서 USB 디스크를 제거하고 본체 Windows 10 Microsoft Teams 룸 [진행합니다](console.md#Reimage).

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>콘솔 Windows 10 및 Microsoft Teams 룸 설치
<a name="Reimage"> </a>

이제 만든 설정 미디어를 적용해야 합니다. 대상 디바이스는 어플라이언스로 실행됩니다. 기본 사용자는 앱만 Microsoft Teams 룸 설정됩니다.

1. 대상 디바이스가 dock에 설치되는 경우(예: Surface Pro) dock에서 연결을 끊습니다.

2. 대상 디바이스가 네트워크에 연결되어 있지 않은지 확인합니다.

3. 대상 디바이스가 AC 전원에 연결되어 있는지 확인합니다.

4. USB 설정 디스크를 대상 디바이스에 연결합니다.

5. USB 설정 디스크로 부팅합니다. 제조업체 지침을 참조하세요. 대상 디바이스가 Surface Pro 경우 다음 단계를 사용하여 USB 설정 디스크로 부팅합니다.

    a. 누를 때 볼륨을 계속 누르고(-) 단추를 누릅니다.

    b. 전원 단추를 누르고 해제합니다.

    c. 설치 Windows 부팅하면 볼륨 다운(-) 단추를 해제합니다.

8. 설치가 완료되면 시스템이 종료됩니다.
    
시스템이 종료된 후 USB 설정 디스크를 제거하는 것이 안전합니다. 이 시점에서 대상 디바이스를 해당 dock에 두고(dock 기반 제품을 사용하는 경우), 회의실에 필요한 주변 장치를 연결하고 네트워크에 연결할 수 있습니다. 제조업체 지침을 참조하세요.

> [!NOTE]
> 소프트웨어 업데이트는 Microsoft Teams 룸 자동으로 다운로드 비즈니스용 Microsoft Store됩니다. 룸 [콘솔이](/microsoft-store/prerequisites-microsoft-store-for-business) 저장소 및 자체 업데이트에 액세스할 수 비즈니스용 Microsoft Store 확인을 위해 교육 및 교육에 대한 전제 를 참조합니다.  

### <a name="selecting-a-language"></a>언어 선택 

크리에이터의 업데이트에서는 암시적 언어 선택이 사용자에게 원하는 실제 애플리케이션 언어를 제공하지 않는 시나리오에서 ApplyCurrentRegionAndLanguage.ps1 스크립트를 사용해야 합니다(예: 콘솔 앱이 프랑스어로 제공되지만 영어로 제공됩니다).
  
> [!NOTE]
> 다음 지침은 Windows 크리에이터의 업데이트(Windows 10 20H1) 이상을 사용하여 만든 콘솔에만 작동합니다.
  
### <a name="to-apply-your-desired-language"></a>원하는 언어를 적용하기 위해

1. 관리자 모드로 전환합니다.
    
2. 시작 메뉴.
    
3. 기어 아이콘을 선택하여 **설정 실행합니다**.
    
4. 시간 **언어를 &amp; 선택합니다**.
    
5. 언어를 **선택합니다**.
    
6. 언어 **추가를 선택합니다**.
    
7. 추가할 언어를 선택합니다.
    
8. 언어 기능을 설치합니다.
    
9. 내 화면 표시 언어로 Windows 선택하지 않습니다.
    
10. 설치 **를 선택합니다**.
    
11. 방금 "언어" 목록에 추가한 언어를 선택합니다.
    
12. 기본값으로 설정 - 위쪽 화살표를 기본값으로 설정

13. 제거하고자 하는 언어의 경우:
    
    a. 제거할 언어를 선택합니다.
    
    b. 제거를 선택합니다.

14. 상승된 명령 프롬프트를 시작합니다.

15. 다음 명령을 실행합니다. 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
16. 시스템을 다시 시작합니다.
    
이제 원하는 언어가 콘솔에 Microsoft Teams 룸 적용됩니다.
## <a name="initial-set-up-of-the-console"></a>콘솔의 초기 설정
<a name="Initial"> </a>

Windows 설치한 후 Microsoft Teams 룸 앱이 초기 설정 프로세스로 이동됩니다.
  
1. 사용자 계정 화면이 나타납니다. 본체에 사용할 Exchange 룸 계정의 Microsoft user@domain 로그인 주소(user@domain 형식)를 입력합니다.
    
2. 룸 계정에 대한 암호를 입력하고 다시 입력하여 확인합니다.
   
3. 지원되는 모임 모드(Microsoft Teams 전용, 비즈니스용 Skype 전용) 또는 두 가지 혼합 모드 옵션 중 하나를 선택합니다. 필요한 경우 최신 인증을 사용하도록 설정합니다.

4. 다음 **을 선택합니다**.
    
5. 비즈니스용 Skype 및 비즈니스용 Skype SIP 도메인이 사용자의 Exchange 도메인과 다른 경우 고급 섹션에서 비즈니스용 Skype 서버 FQDN을 설정합니다. 도메인을 사용하지 비즈니스용 Skype SIP 도메인이 Exchange 도메인과 일치하는 경우 이 섹션을 비워 두십시오.
6. 다음 **을 선택합니다**.
    
7. 완료를 **선택합니다**.
    
Microsoft Teams 룸 앱은 위에서 입력한 자격 증명을 사용하여 Microsoft Teams 비즈니스용 Skype 서버 로그인해야 합니다. 또한 동일한 자격 증명을 사용하여 일정을 Exchange 시작해야 합니다. 사용에 대한 자세한 내용은 Teams 룸 도움말을 [Microsoft Teams 룸 참조합니다](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Microsoft Teams 룸 콘솔 하드웨어의 존재에 의존합니다. 콘솔 앱이 포함된 올바르게 만든 이미지도 Microsoft Teams 룸 하드웨어가 검색되지 않는 한 초기 설정 절차를 따라 부팅되지 않습니다. Surface Pro 솔루션의 경우 이 Surface Pro 확인을 전달하려면 해당 Surface Pro Dock 하드웨어에 연결해야 합니다.
  
> [!NOTE]
> 영어가 아닌 일부 사용자는 터치 키보드에서 기호가 지원되지 않는 경우 초기 설정 중에 본체에 연결된 물리적 키보드가 필요할 수 있습니다.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>본체에 개인 CA 인증서 설치
<a name="Certs"> </a>
> [!NOTE]
> 다음은 연결에 Teams 룸 비즈니스용 Skype.

Microsoft Teams 룸 서버에 사용되는 인증서를 신뢰해야 합니다. 인증서 기관이 비공개인 경우(예: Active Directory 및 Windows 인증 기관을 사용하여 프레미스 배포) 두 가지 방법으로 인증서를 Microsoft Teams 룸 수 있습니다.
  
- 콘솔을 Active Directory에 조인할 수 있으며 인증서 기관이 Active Directory에 게시된 경우 필요한 인증서를 자동으로 추가합니다(일반 배포 옵션).
    
- 이미징 프로세스 후에 인증서를 수동으로 설치할 수 있습니다. 이렇게 하기 전에 본체의 초기 설정이 [완료되어야 합니다](console.md#Initial).
    
### <a name="to-manually-install-the-certificate"></a>인증서를 수동으로 설치하려면

1. 컴퓨터에 CA 인증서를 다운로드하고 "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"에 저장합니다.
    
2. 콘솔을 관리 모드로 전환합니다( [관리자 모드 및 디바이스 관리 참조](rooms-operations.md#AdminMode)).
    
3. 다음 명령을 실행합니다.
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Active Directory 도메인 가입(선택 사항)
<a name="Certs"> </a>

도메인에 Microsoft Teams 룸 수 있습니다. Microsoft Teams 룸 많은 workstation 정책이 사용자와 호환되지 않는 경우 PC 작업대와 별도 OU에 Microsoft Teams 룸. 일반적인 예로 암호 적용 정책이 Microsoft Teams 룸 시작할 수 없습니다. GPO 설정 관리에 대한 자세한 내용은 GPO 설정 [관리를 Microsoft Teams 룸](rooms-operations.md).
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>도메인에 Microsoft Teams 룸 참가하려면

1. 관리자 계정에서 본체에 로그인합니다(관리자 [모드 및 디바이스 관리 참조](rooms-operations.md#AdminMode)).
    
2. Powershell 명령 프롬프트를 실행합니다.
    
3. Powershell에서 다음 명령을 입력합니다.
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

예를 들어 자격이 redmond.corp.microsoft.com 도메인이 Microsoft Teams 룸 "리소스" OU의 자식인 "Microsoft Teams 룸" OU에 있는 경우 명령은 다음과 같습니다.
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 도메인에 조인할 때 컴퓨터의 이름을 변경하려면 -NewName 플래그와 컴퓨터의 새 이름을 사용 합니다.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Microsoft Teams 룸 배포 검사 목록
<a name="Checklist"> </a>

본체와 모든 주변 장치를 완전히 구성하는지 최종 확인하는 동안 다음 검사 목록을 사용합니다.
  
**애플리케이션 설정**

|완료되었습니다. |확인 |
|:-----:|:-----|
|☐   |룸 계정 이름 및 휴대폰 #(PSTN이 설정된 경우)이 올바르게 표시됩니다.   |
|☐   |Windows 이름이 올바르게 설정되어 있습니다(원격 관리에 유용)   |
|☐   |관리자 계정 암호 설정 및 확인   |
|☐   |모든 펌웨어 업데이트가 적용되었습니다.   |
   
**오디오/비디오 주변 장치**

|완료되었습니다. |확인 |
|:-----:|:-----|
|☐   |카메라 주변 펌웨어 버전이 올바른 경우(해당하는 경우)   |
|☐   |카메라 기능 및 최적 위치   |
|☐   |설정 기본 디바이스 및 재생 기본 통신 디바이스에 대해 의도된 오디오 주변 장치로 설정   |
|☐   |설정 기본 통신 디바이스를 의도된 오디오 주변 장치로 설정하기 위한 설정   |
|☐   |오디오 주변 펌웨어 버전이 올바른 경우(해당하는 경우)   |
|☐   |오디오 입력 디바이스 기능 및 최적 위치   |
|☐   |오디오 출력 디바이스 기능 및 최적 위치   |

**콘솔**

|완료되었습니다. |확인 |
|:-----:|:-----|
|☐   |케이블이 안전하며 고정되지 않습니다.   |
|☐   |HDMI를 통해 오디오 인제스트가 작동   |
|☐   |HDMI를 통해 비디오 인제스트가 작동   |
|☐   |콘솔은 자유롭게 돌 수 있습니다.   |



   
## <a name="see-also"></a>참고 항목
<a name="Checklist"> </a>

[Microsoft Teams 룸 계획](rooms-plan.md)
  
[Microsoft Teams 룸 배포](rooms-deploy.md)
  
[Microsoft Teams 룸 콘솔 구성](console.md)
  
[Microsoft Teams 룸 관리](rooms-manage.md)
