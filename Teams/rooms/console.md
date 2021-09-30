---
title: Microsoft Teams 룸 콘솔 구성
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
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 이 문서에서는 콘솔 및 주변 장치를 설정하고 Microsoft Teams 룸 방법을 설명합니다.
ms.openlocfilehash: 0acd5449c97f1a42f1a1c015b74df8f7cdaf3e4c
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011562"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Microsoft Teams 룸 콘솔 구성

이 문서에서는 콘솔 및 주변 장치를 Microsoft Teams 룸 방법을 설명합니다.
  
필요한 계정 또는 Microsoft Teams 비즈니스용 Skype Exchange 배포 에서 설명한 [Microsoft Teams 룸.](rooms-deploy.md) 요구 사항에 설명된 하드웨어 [및 Microsoft Teams 룸 필요합니다.](requirements.md) 이 항목에는 다음 섹션이 포함되어 있습니다.
  
- [설치 미디어 준비](console.md#Prep_Media)
- [본체에 개인 CA 인증서 설치](console.md#Certs)
- [Windows 10 및 Microsoft Teams 룸 앱 설치](console.md#Reimage)
- [콘솔의 초기 설정](console.md#Initial)
- [Microsoft Teams 룸 배포 검사 목록](console.md#Checklist)

> [!NOTE]
> Microsoft Teams 룸 디바이스 계정이 배포 에서 설명한 Microsoft Teams 비즈니스용 Skype 올바르게 설정되는 환경에서만 제대로 구성된 [Microsoft Teams 룸.](rooms-deploy.md)
  
## <a name="prepare-the-installation-media"></a>설치 미디어 준비
<a name="Prep_Media"> </a>

콘솔 Microsoft Teams 룸 설치하려면 용량이 32GB 이상인 USB 저장소 디바이스가 필요합니다. 디바이스에 다른 파일이 없습니다. USB 저장소의 기존 파일이 손실됩니다.
  
> [!NOTE]
> 이러한 지침에 Microsoft Teams 룸 설치 미디어를 만들지 못하면 예기치 않은 동작이 발생할 수 있습니다.

> [!NOTE]
> 아래 프로세스는 새 디바이스를 이미지하는 설치 미디어를 Microsoft Teams 룸 위한 것입니다. 기존 디바이스는 기본적으로 업데이트 및 Windows 저장소에서 Windows 업데이트합니다.

> [!IMPORTANT]
> Windows 10 설치 미디어를 만드는 데 Microsoft Teams 룸 컴퓨터는 대상 설치 미디어와 동일한 Windows 버전에 있어야 합니다.
  
1. 스크립트를 [CreateSrsMedia.ps1 다운로드합니다.](https://go.microsoft.com/fwlink/?linkid=867842)
2. CreateSrsMedia.ps1 컴퓨터의 상승된 프롬프트에서 Windows 10 실행합니다.
3. 스크립트의 지침에 따라 USB Microsoft Teams 룸 디스크를 만들 수 있습니다.


> [!TIP]
> 스크립트가 CreateSrsMedia.ps1 시작할 때마다 화면 출력에는 세션에 대한 로그 파일 또는 전사 이름이 포함됩니다. 스크립트를 실행하는 데 문제가 있는 경우 지원을 요청할 때 해당 녹취록의 복사본을 사용할 수 있는지 확인 합니다. 

CreateSrsMedia.ps1 스크립트는 다음 작업을 자동화합니다.

1. 최신 MSI 설치 관리자를 다운로드하여 Microsoft Teams 룸.
2. 사용자가 제공해야 하는 Windows 빌드를 결정합니다. 가장 최근에 릴리스된 버전은 디바이스와 함께 사용하기 위해 테스트되거나 지원되지 않을 Microsoft Teams 룸 있습니다.
3. 필요한 지원 구성 요소를 다운로드합니다.
4. 설치 미디어에서 필요한 구성 요소를 조립합니다.

특정 버전의 Windows 10 필요하며, 이 버전은 볼륨 라이선스 고객에게만 사용할 수 있습니다.  볼륨 라이선스 서비스 센터에서 [복사본을 얻을 수 있습니다.](https://www.microsoft.com/Licensing/servicecenter/)

완료되면 컴퓨터에서 USB 디스크를 제거하고 Windows 10 콘솔 앱 Microsoft Teams 룸 [진행합니다.](console.md#Reimage)

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Windows 10 및 Microsoft Teams 룸 앱 설치
<a name="Reimage"> </a>

이제 만든 설정 미디어를 적용해야 합니다. 대상 디바이스는 어플라이언스로 실행됩니다. 기본 사용자는 콘솔 앱만 Microsoft Teams 룸 설정됩니다.

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
> 다음 지침은 크리에이터의 업데이트를 사용하여 만든 콘솔에만 Windows 합니다. 새 프로비전 시스템과 함께 미디어를 사용하여 설정되지 않은 레거시/인-마켓 시스템은 이러한 지침을 사용할 수 없지만 이 수동 개입이 필요한 초기 문제로 고통을 겪지 않습니다(주년 버전에서는 설정의 일부로 앱 언어를 명시적으로 선택할 수 있습니다).
  
### <a name="to-apply-your-desired-language"></a>원하는 언어를 적용하기 위해

1. 관리자 모드로 전환합니다.
    
2. 시작 메뉴.
    
3. 기어 아이콘을 선택하여  설정 실행합니다.
    
4. 시간 **언어를 &amp; 선택합니다.**
    
5. 지역 **언어를 &amp; 선택합니다.**
    
6. 언어 **추가를 선택합니다.**
    
7. 추가할 언어를 선택합니다.
    
8. 방금 "언어" 목록에 추가한 언어를 선택합니다.
    
9. 기본값으로 **설정을 선택합니다.**
    
10. 제거하고자 하는 언어의 경우:
    
    a. 제거할 언어를 선택합니다.
    
    b. 제거를 **선택합니다.**
    
11. 상승된 명령 프롬프트를 시작합니다.
    
12. 다음 명령을 실행합니다. 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. 시스템을 다시 시작합니다.
    
이제 원하는 언어가 콘솔에 Microsoft Teams 룸 적용됩니다.
## <a name="initial-set-up-of-the-console"></a>콘솔의 초기 설정
<a name="Initial"> </a>

Windows 설치한 후 Microsoft Teams 룸 콘솔 앱이 다음에 시작되거나 /reboot 옵션을 선택한 경우 초기 설치 프로세스로 이동됩니다.
  
1. 사용자 계정 화면이 나타납니다. 본체와 Skype 사용할 user@domain 로그인 주소(user@domain 형식)를 입력합니다.
    
2. 룸 계정에 대한 암호를 입력하고 다시 입력하여 확인합니다.
    
3. "도메인 구성"에서 도메인에 대한 FQDN을 비즈니스용 Skype 서버. SIP 비즈니스용 Skype 사용자의 Exchange 도메인과 다른 경우 이 Exchange 도메인을 입력합니다.
    
4. 다음 **을 클릭합니다.**
    
5. 기능 화면에서 표시된 디바이스를 선택하고 다음 을 **클릭합니다.** 기본값은 자동 화면 공유를 설정하고 모임 이름을 끄기 및 숨기기로 설정하는 것입니다. 선택할 디바이스는 다음을 선택합니다.
    
   - 회의용 마이크: 이 회의실의 기본 마이크입니다.
    
   - 회의용 발표자: 회의의 기본 스피커입니다. 
    
   - 기본 스피커: HDMI 인제스트의 오디오에 사용되는 스피커입니다.
    
     각 항목에는 선택할 옵션의 드롭다운 메뉴가 있습니다. 각 디바이스에 대해 선택해야 합니다.
    
6. **마침** 을 클릭합니다.
    
Microsoft Teams 룸 콘솔 앱은 위에서 입력한 자격 증명으로 비즈니스용 Skype 서버 즉시 로그인을 시작해야 합니다. 또한 동일한 자격 증명을 사용하여 일정을 Exchange 시작해야 합니다. 콘솔 앱 사용에 대한 자세한 내용은 Microsoft Teams 룸 [참조하세요.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)
  
> [!IMPORTANT]
> Microsoft Teams 룸 콘솔 하드웨어의 존재에 의존합니다. 콘솔 앱이 Microsoft Teams 룸 올바르게 만든 이미지라도 콘솔 하드웨어가 검색되지 않는 한 초기 설정 절차를 따라 부팅되지 않습니다. Surface Pro 솔루션의 경우 이 Surface Pro 확인을 전달하려면 해당 Surface Pro Dock 하드웨어에 연결해야 합니다.
  
> [!NOTE]
> 영어가 아닌 일부 사용자는 터치 키보드에서 기호가 지원되지 않는 경우 초기 설정 중에 본체에 연결된 물리적 키보드가 필요할 수 있습니다.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>본체에 개인 CA 인증서 설치
<a name="Certs"> </a>

Microsoft Teams 룸 콘솔은 연결되는 서버에서 사용하는 인증서를 신뢰해야 합니다. O365의 경우 이러한 서버가 공용 인증서 기관을 사용하고 있으며 이러한 서버는 자동으로 신뢰할 수 Windows 10. 인증서 기관이 비공개인 경우(예: Active Directory 및 Windows 인증 기관을 사용하여 프레미스 배포) 몇 가지 방법으로 인증서를 Microsoft Teams 룸 수 있습니다.
  
- 콘솔을 Active Directory에 조인할 수 있으며 인증서 기관이 Active Directory에 게시된 경우 필요한 인증서를 자동으로 추가합니다(일반 배포 옵션).
    
- 이미징 프로세스 후에 인증서를 수동으로 설치할 수 있습니다. 이렇게 하기 전에 콘솔의 초기 설정 [을 완료해야 합니다.](console.md#Initial)
    
### <a name="to-manually-install-the-certificate"></a>인증서를 수동으로 설치하려면

1. 컴퓨터에 CA 인증서를 다운로드하고 "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"에 저장합니다.
    
2. 콘솔을 관리 모드로 [전환합니다(관리자 모드 및 디바이스 관리 참조).](rooms-operations.md#AdminMode)
    
3. 다음 명령을 실행합니다.
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Active Directory 도메인 가입(선택 사항)
<a name="Certs"> </a>

도메인에 Microsoft Teams 룸 콘솔에 참가할 수 있습니다. Microsoft Teams 룸 많은 workstation 정책이 사용자와 호환되지 않는 경우 PC 작업대와 별도의 OU에 Microsoft Teams 룸. 일반적인 예로 암호 적용 정책이 Microsoft Teams 룸 시작할 수 없습니다. GPO 설정 관리에 대한 자세한 내용은 관리 를 [Microsoft Teams 룸.](rooms-operations.md)
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>도메인에 Microsoft Teams 룸 참가하려면

1. 관리자 계정에서 본체에 로그인합니다(관리자 [모드 및 디바이스 관리 참조).](rooms-operations.md#AdminMode)
    
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
|☐   |룸 계정 이름 및 휴대폰 #(PSTN을 사용하도록 설정한 경우) 콘솔 화면 오른쪽 위에 올바르게 표시됩니다.   |
|☐   |Windows 이름이 올바르게 설정되어 있습니다(원격 관리에 유용)   |
|☐   |관리자 계정 암호 설정 및 확인   |
|☐   |모든 펌웨어 업데이트가 적용되었습니다.   |
   
**오디오/비디오 주변 장치**

|완료되었습니다. |확인 |
|:-----:|:-----|
|☐   |카메라 주변 펌웨어 버전이 올바른 경우(해당하는 경우)   |
|☐   |카메라 기능 및 최적 위치   |
|☐   |설정 기본 디바이스 및 재생 기본 통신 디바이스에 대해 의도된 오디오 주변 장치로 설정   |
|☐   |설정 기본 통신 디바이스를 의도된 오디오 주변 장치로 설정하기 위한 기본 설정   |
|☐   |오디오 주변 펌웨어 버전이 올바른 경우(해당하는 경우)   |
|☐   |오디오 입력 디바이스 기능 및 최적 위치   |
|☐   |오디오 출력 디바이스 기능 및 최적 위치   |

**Dock**

|완료되었습니다. |확인 |
|:-----:|:-----|
|☐   |케이블이 안전하며 고정되지 않습니다.   |
|☐   |HDMI를 통해 오디오 인제스트가 작동   |
|☐   |HDMI를 통해 비디오 인제스트가 작동   |
|☐   |Dock은 자유롭게 스위브할 수 있습니다.   |
|☐   |디스플레이 밝기는 환경에 허용됩니다.   |


   
## <a name="see-also"></a>참고 항목
<a name="Checklist"> </a>

[Microsoft Teams 룸 계획](rooms-plan.md)
  
[Microsoft Teams 룸 배포](rooms-deploy.md)
  
[Microsoft Teams 룸 콘솔 구성](console.md)
  
[Microsoft Teams 룸 관리](rooms-manage.md)
