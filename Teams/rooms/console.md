---
title: Microsoft Teams 룸 이미지 빌드
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 이 문서에서는 Microsoft Teams 룸 콘솔 및 해당 주변 장치를 설정하고 구성하는 방법을 설명합니다.
ms.openlocfilehash: 2a38154ebca1dfae282722fdb64e76389627ca15
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270113"
---
# <a name="build-a-microsoft-teams-rooms-image"></a>Microsoft Teams 룸 이미지 빌드

이 문서에서는 Teams 룸 대량 배포를 위해 Microsoft Teams 룸 이미지를 빌드하는 방법을 설명합니다.

> [!NOTE]
> 다음 단계는 대량 배포를 위해 [WIM 기반 이미지를](/windows-hardware/manufacture/desktop/capture-and-apply-an-image) 만들 때만 사용해야 합니다. 개별 디바이스를 복구하는 경우 OEM(Original Equipment Manufacturer)에 문의하여 지원을 요청하세요.

[배포](rooms-deploy.md) Microsoft Teams 룸 설명한 대로 필요한 Microsoft Teams 또는 비즈니스용 Skype 및 Exchange 계정이 이미 만들어지고 테스트된 경우에만 이러한 단계를 수행해야 합니다. [Microsoft Teams 룸 요구 사항에](requirements.md) 설명된 하드웨어 및 소프트웨어가 필요합니다. 이 항목에는 다음 섹션이 포함되어 있습니다.
  
- [설치 미디어 준비](console.md#Prep_Media)
- [콘솔에 프라이빗 CA 인증서 설치](console.md#Certs)
- [Windows 10 및 Microsoft Teams 룸 콘솔 앱 설치](console.md#Reimage)
- [콘솔의 초기 설정](console.md#Initial)
- [Microsoft Teams 룸 배포 검사 목록](console.md#Checklist)

## <a name="prepare-the-installation-media"></a>설치 미디어 준비
<a name="Prep_Media"> </a>

Microsoft Teams 룸 콘솔 앱을 설치하려면 최소 32GB 용량의 USB 스토리지 디바이스가 필요합니다. 디바이스에 다른 파일이 없어야 합니다. USB 스토리지의 기존 파일은 손실됩니다.
  
> [!NOTE]
> 이러한 지침에 따라 Microsoft Teams 룸 설치 미디어를 만들지 못하면 예기치 않은 동작이 발생할 수 있습니다.

> [!NOTE]
> 아래 프로세스는 새 Microsoft Teams 룸 디바이스를 이미지로 만드는 설치 미디어를 만드는 것입니다. 기존 디바이스는 기본적으로 Windows 업데이트 Windows 스토어에서 자동으로 업데이트됩니다.

> [!IMPORTANT]
> Microsoft Teams 룸 설치 미디어를 만드는 데 사용되는 Windows 10 컴퓨터는 대상 설치 미디어와 동일하거나 이후 버전의 Windows에 있어야 합니다.
  
1. [CreateSrsMedia.ps1 스크립트](https://go.microsoft.com/fwlink/?linkid=867842)를 다운로드합니다.
2. Windows 10 컴퓨터의 관리자 권한 프롬프트에서 CreateSrsMedia.ps1 스크립트를 실행합니다.
3. 스크립트의 지침에 따라 Microsoft Teams 룸 USB 설치 디스크를 만듭니다.


> [!TIP]
> CreateSrsMedia.ps1 스크립트가 시작될 때마다 화면 출력에는 세션에 대한 로그 파일 또는 대본의 이름이 포함됩니다. 스크립트 실행에 문제가 있는 경우 지원을 요청할 때 해당 대본의 복사본을 사용할 수 있어야 합니다. 

CreateSrsMedia.ps1 스크립트는 다음 작업을 자동화합니다.

1. Microsoft Teams 룸 최신 MSI 설치 관리자를 다운로드합니다.
2. 사용자가 제공해야 하는 Windows 빌드를 결정합니다. 가장 최근에 릴리스된 버전은 Microsoft Teams 룸 디바이스에서 사용하기 위해 테스트 및 지원될 수도 있고 그렇지 않을 수도 있습니다.
3. 필요한 지원 구성 요소를 다운로드합니다.
4. 설치 미디어에서 필요한 구성 요소를 어셈블합니다.

> [!NOTE]
특정 버전의 Windows 10 필요하며 이 버전은 볼륨 라이선스 고객에게만 제공됩니다.  [볼륨 라이선스 서비스 센터에서](https://www.microsoft.com/Licensing/servicecenter/) 복사본을 가져올 수 있습니다.

완료되면 컴퓨터에서 USB 디스크를 제거하고 [Windows 10 및 Microsoft Teams 룸 콘솔 앱 설치를](console.md#Reimage) 진행합니다.

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Windows 10 및 Microsoft Teams 룸 콘솔 앱 설치
<a name="Reimage"> </a>

이제 만든 설치 미디어를 적용해야 합니다. 대상 디바이스는 어플라이언스로 실행되고 기본 사용자는 Microsoft Teams 룸 앱만 실행하도록 설정됩니다.

1. 대상 디바이스가 도크에 설치되는 경우(예: Surface Pro) 도크에서 연결을 끊습니다.

2. 대상 디바이스가 네트워크에 연결되어 있지 않은지 확인합니다.

3. 대상 디바이스가 AC 전원에 연결되어 있는지 확인합니다.

4. USB 설치 디스크를 대상 디바이스에 연결합니다.

5. USB 설치 디스크로 부팅합니다. 제조업체 지침을 참조하세요. 대상 디바이스가 Surface Pro 경우 다음 단계를 사용하여 USB 설치 디스크로 부팅합니다.

    a. 볼륨을 누른 상태로(-) 단추를 계속 누릅니다.

    b. 전원 단추를 누르고 놓습니다.

    C. Windows 설치 프로그램이 부팅되면 볼륨 다운(-) 단추를 해제합니다.

8. 설치가 완료되면 시스템이 종료됩니다.
    
시스템이 종료된 후에는 USB 설치 디스크를 제거해도 안전합니다. 이 시점에서 대상 디바이스를 도크 기반 제품을 사용하는 경우 도크에 배치하고, 회의실에 필요한 주변 장치를 연결하고, 네트워크에 연결할 수 있습니다. 제조업체 지침을 참조하세요.

> [!NOTE]
> Microsoft Teams 룸 대한 소프트웨어 업데이트는 비즈니스용 Microsoft Store 자동으로 다운로드됩니다. [비즈니스용 Microsoft Store 및 교육의 필수 구성 요소를](/microsoft-store/prerequisites-microsoft-store-for-business) 참조하여 회의실 콘솔이 스토어에 액세스하고 자체 업데이트할 수 있는지 확인합니다.  

### <a name="selecting-a-language"></a>언어 선택 

크리에이터스 업데이트에서는 암시적 언어 선택에서 사용자에게 원하는 실제 애플리케이션 언어를 제공하지 않는 시나리오에서 ApplyCurrentRegionAndLanguage.ps1 스크립트를 사용해야 합니다(예: 콘솔 앱이 프랑스어로 표시되기를 원하지만 영어로 제공됨).
  
> [!NOTE]
> 다음 지침은 Windows Creator 업데이트(Windows 10 20H1) 이상을 사용하여 만든 콘솔에서만 작동합니다.
  
### <a name="to-apply-your-desired-language"></a>원하는 언어를 적용하려면

1. 관리 모드로 전환합니다.
    
2. 시작 메뉴를 선택합니다.
    
3. 기어 아이콘을 선택하여 **설정** 앱을 시작합니다.
    
4. **시간 &amp; 언어** 를 선택합니다.
    
5. **언어** 를 선택합니다.
    
6. **언어 추가를** 선택합니다.
    
7. 추가할 언어를 선택합니다.
    
8. 언어 기능을 설치합니다.
    
9. 내 Windows 표시 언어로 설정을 확인하지 마세요.
    
10. **설치** 를 선택합니다.
    
11. 방금 "언어" 목록에 추가한 언어를 선택합니다.
    
12. 기본값으로 설정 - 위쪽 화살표를 이동하여 기본값 설정

13. 제거하려는 모든 언어의 경우:
    
    a. 제거할 언어를 선택합니다.
    
    b. 제거를 선택합니다.

14. 관리자 권한 명령 프롬프트를 시작합니다.

15. 다음 명령을 실행합니다. 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
16. 시스템을 다시 시작합니다.
    
원하는 언어가 이제 Microsoft Teams 룸 콘솔에 적용됩니다.
## <a name="initial-set-up-of-the-console"></a>콘솔의 초기 설정
<a name="Initial"> </a>

Windows가 설치되면 Microsoft Teams 룸 앱이 초기 설치 프로세스로 전환됩니다.
  
1. 사용자 계정 화면이 나타납니다. 콘솔에서 사용할 회의실 계정의 Microsoft Exchange 리소스 계정 로그인 주소(user@domain 형식)를 입력합니다.
    
2. 회의실 계정의 암호를 입력하고 다시 입력하여 확인합니다.
   
3. 지원되는 모임 모드인 Microsoft Teams만, 비즈니스용 Skype 전용 또는 두 가지 혼합 모드 옵션 중 하나를 선택합니다. 필요한 경우 최신 인증을 사용하도록 설정합니다.

4. **다음** 을 선택합니다.
    
5. 비즈니스용 Skype 사용하고 비즈니스용 Skype SIP 도메인이 사용자의 Exchange 도메인과 다른 경우 고급 섹션에서 비즈니스용 Skype 서버 대한 FQDN을 설정합니다. 비즈니스용 Skype 사용하지 않거나 SIP 도메인이 Exchange 도메인과 일치하는 경우 이 섹션을 비워 둡니다.
6. **다음** 을 선택합니다.
    
7. **마침** 을 선택합니다.
    
Microsoft Teams 룸 앱은 위에서 입력한 자격 증명으로 Microsoft Teams에 로그인하거나 비즈니스용 Skype 서버 동일한 자격 증명을 사용하여 Exchange와 일정 동기화를 시작해야 합니다. Teams 룸 사용에 대한 자세한 내용은 [Microsoft Teams 룸 도움말](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)을 참조하세요.
  
> [!IMPORTANT]
> Microsoft Teams 룸 인증된 콘솔 하드웨어의 존재에 의존합니다. 콘솔 하드웨어가 검색되지 않는 한 Microsoft Teams 룸 콘솔 앱을 포함하는 올바르게 생성된 이미지도 초기 설정 절차를 지나서 부팅되지 않습니다. Surface Pro 기반 솔루션의 경우 이 검사를 통과하려면 Surface Pro 함께 제공되는 도크 하드웨어에 연결해야 합니다.
  
> [!NOTE]
> 일부 비영어 언어 사용자는 터치 키보드에서 기호가 지원되지 않는 경우 초기 설정 중에 콘솔에 연결된 물리적 키보드가 필요할 수 있습니다.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>콘솔에 프라이빗 CA 인증서 설치
<a name="Certs"> </a>
> [!NOTE]
> 다음은 Teams 룸 비즈니스용 Skype 연결하는 경우에만 적용됩니다.

Microsoft Teams 룸 연결하는 서버에서 사용하는 인증서를 신뢰해야 합니다. 인증 기관이 프라이빗인 경우(예: Active Directory 및 Windows 인증 기관을 사용하여 온-프레미스 배포) 다음과 같은 몇 가지 방법으로 Microsoft Teams 룸 인증서를 추가할 수 있습니다.
  
- Active Directory에 콘솔을 조인할 수 있으며 인증 기관이 Active Directory(일반 배포 옵션)에 게시된 경우 필요한 인증서를 자동으로 추가합니다.
    
- 이미징 프로세스 후에 인증서를 수동으로 설치할 수 있습니다. 이렇게 하려면 [먼저 콘솔의 초기 설정을](console.md#Initial) 완료해야 합니다.
    
### <a name="to-manually-install-the-certificate"></a>인증서를 수동으로 설치하려면

1. CA 인증서를 컴퓨터에 다운로드하고 "C:\Skype 룸 시스템\x64\Scripts\Provisioning\CAcertificate.cer"에 저장합니다.
    
2. 콘솔을 관리 모드로 전환합니다([관리 모드 및 디바이스 관리](rooms-operations.md#AdminMode) 참조).
    
3. 다음 명령을 실행합니다.
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Active Directory 도메인 가입(선택 사항)
<a name="Certs"> </a>

도메인에 Microsoft Teams 룸 가입할 수 있습니다. Microsoft Teams 룸 많은 워크스테이션 정책이 Microsoft Teams 룸 호환되지 않으므로 PC 워크스테이션과 별도의 OU에 배치해야 합니다. 일반적인 예는 Microsoft Teams 룸 자동으로 시작되지 않도록 하는 암호 적용 정책입니다. GPO 설정 관리에 대한 자세한 내용은 [Microsoft Teams 룸 관리를](rooms-operations.md) 참조하세요.
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>도메인에 Microsoft Teams 룸 가입하려면

1. 관리자 계정에서 콘솔에 로그인합니다([관리 모드 및 디바이스 관리](rooms-operations.md#AdminMode) 참조).
    
2. 관리자 권한 Powershell 명령 프롬프트를 시작합니다.
    
3. Powershell에서 다음 명령을 입력합니다.
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, ... ,OU=<Top level OU>,DC=<child domain>,...,DC=<top level domain>"
   ```

예를 들어 정규화된 도메인이 redmond.corp.microsoft.com Microsoft Teams 룸 콘솔이 "Resources" OU의 자식인 "Microsoft Teams 룸" OU에 있게 하려는 경우 명령은 다음과 같습니다.
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 도메인에 가입할 때 컴퓨터의 이름을 바꾸려면 -NewName 플래그와 컴퓨터의 새 이름을 사용합니다.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Microsoft Teams 룸 배포 검사 목록
<a name="Checklist"> </a>

콘솔 및 모든 주변 디바이스가 완전히 구성되어 있는지 최종 확인을 수행하는 동안 다음 검사 목록을 사용합니다.
  
**애플리케이션 설정**

|완료 |확인 |
|:-----:|:-----|
|☐   |회의실 계정 이름 및 전화 번호(PSTN을 사용하는 경우)가 올바르게 표시됩니다.   |
|☐   |Windows 컴퓨터 이름이 올바르게 설정됨(원격 관리에 유용)   |
|☐   |관리자 계정 암호 설정 및 확인됨   |
|☐   |모든 펌웨어 업데이트가 적용되었습니다.   |
   
**오디오/비디오 주변 장치**

|완료 |확인 |
|:-----:|:-----|
|☐   |카메라 주변 장치 펌웨어 버전이 올바르다(해당하는 경우)   |
|☐   |카메라 기능 및 최적 위치   |
|☐   |기본 디바이스 재생 및 재생 기본 통신 디바이스에 대한 설정이 의도한 오디오 주변 장치로 설정됨   |
|☐   |기본 통신 디바이스를 의도한 오디오 주변 장치로 설정하기 위한 설정   |
|☐   |오디오 주변 장치 펌웨어 버전이 올바르다(해당하는 경우)   |
|☐   |오디오 입력 디바이스가 작동하고 최적으로 배치됨   |
|☐   |오디오 출력 디바이스가 작동하고 최적으로 배치됨   |

**콘솔**

|완료 |확인 |
|:-----:|:-----|
|☐   |케이블은 안전하며 꼬집지 않음   |
|☐   |HDMI를 통해 오디오 수집이 작동합니다.   |
|☐   |HDMI를 통해 비디오 수집이 작동합니다.   |
|☐   |콘솔을 자유롭게 회전할 수 있음   |



   
## <a name="see-also"></a>참고 항목
<a name="Checklist"> </a>

[Microsoft Teams 룸 계획](rooms-plan.md)
  
[Microsoft Teams 룸 배포](rooms-deploy.md)
  
[Microsoft Teams 룸 콘솔 구성](console.md)
  
[Microsoft Teams 룸 관리](rooms-manage.md)
