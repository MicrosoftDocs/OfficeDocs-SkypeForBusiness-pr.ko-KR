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
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 이 문서에서는 Microsoft Teams 회의실 콘솔 및 주변 장치를 설정하고 구성하는 방법을 알아봅니다.
ms.openlocfilehash: 7a36ed93f370c0aeb302da246b223732383719fb
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662063"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Microsoft Teams 룸 콘솔 구성

이 문서에서는 Microsoft Teams 회의실 콘솔 및 주변 장치를 설정하는 방법을 알아봅니다.
  
필요한 Microsoft Teams 또는 비즈니스용 Skype 및 Exchange 계정이 Microsoft Teams 채팅방 배포에 설명된 바와 같이 이미 생성 및 테스트된 경우 이러한 [단계를 수행해야 합니다.](rooms-deploy.md) Microsoft Teams 회의실 요구 사항에 설명된 하드웨어 및 [소프트웨어가 필요합니다.](requirements.md) 이 항목에는 다음 섹션이 포함되어 있습니다.
  
- [설치 미디어 준비](console.md#Prep_Media)
- [콘솔에 개인 CA 인증서 설치](console.md#Certs)
- [Windows 10 및 Microsoft Teams 회의실 콘솔 앱 설치](console.md#Reimage)
- [본체의 초기 설정](console.md#Initial)
- [Microsoft Teams Rooms 배포 검사 목록](console.md#Checklist)

> [!NOTE]
> Microsoft Teams 회의실은 Microsoft Teams 채팅방 배포에 설명된 장치 계정이 올바르게 설정된 올바르게 구성된 Microsoft Teams 또는 비즈니스용 Skype 환경에서만 [작동합니다.](rooms-deploy.md)
  
## <a name="prepare-the-installation-media"></a>설치 미디어 준비
<a name="Prep_Media"> </a>

Microsoft Teams Rooms 콘솔 앱을 설치하려면 용량이 32GB 이상인 USB 저장 장치가 필요합니다. 디바이스에 다른 파일이 없습니다. USB 저장소의 기존 파일은 손실됩니다.
  
> [!NOTE]
> 이러한 지침에 따라 Microsoft Teams 회의실 설치 미디어를 만들지 못하면 예기치 않은 동작이 발생할 수 있습니다.

> [!NOTE]
> 아래 프로세스는 새 Microsoft Teams Rooms 장치를 이미지로 만드는 설치 미디어를 만드는 것입니다. 기존 디바이스는 기본적으로 Windows 업데이트 및 Windows 스토어에서 자동으로 업데이트됩니다.

> [!IMPORTANT]
> Microsoft Teams 회의실 설치 미디어를 만드는 데 사용되는 Windows 10 컴퓨터는 대상 설치 미디어와 동일하거나 이후 버전의 Windows에 있어야 합니다.
  
1. 다음 [CreateSrsMedia.ps1 다운로드합니다.](https://go.microsoft.com/fwlink/?linkid=867842)
2. Windows 10 CreateSrsMedia.ps1 상승된 프롬프트에서 스크립트를 실행합니다.
3. 스크립트의 지침에 따라 Microsoft Teams 회의실 USB 설정 디스크를 만드세요.


> [!TIP]
> 스크립트가 CreateSrsMedia.ps1 시작될 때마다 화면 출력에는 세션에 대한 로그 파일 또는 기록이 포함됩니다. 스크립트 실행에 문제가 있는 경우 지원을 요청할 때 해당 대본의 복사본을 사용할 수 있도록 합니다. 

CreateSrsMedia.ps1 스크립트는 다음 작업을 자동화합니다.

1. Microsoft Teams 회의실용 최신 MSI 설치 관리자를 다운로드합니다.
2. 사용자가 제공해야 하는 Windows 빌드를 판단합니다. 가장 최근에 릴리스된 버전은 Microsoft Teams 회의실 장치에서 사용하기 위해 테스트되거나 지원되지 않을 수 있습니다.
3. 필요한 지원 구성 요소를 다운로드합니다.
4. 설치 미디어에서 필요한 구성 요소를 어셈블합니다.

특정 버전의 Windows 10이 필요하며 이 버전은 볼륨 라이선스 고객에게만 제공됩니다.  볼륨 라이선스 서비스 센터에서 [복사본을 얻을 수 있습니다.](https://www.microsoft.com/Licensing/servicecenter/)

완료되면 컴퓨터에서 USB 디스크를 제거하고 Windows 10 및 Microsoft Teams 회의실 콘솔 앱 [설치를 진행합니다.](console.md#Reimage)

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Windows 10 및 Microsoft Teams 회의실 콘솔 앱 설치
<a name="Reimage"> </a>

이제 만든 설치 미디어를 적용해야 합니다. 대상 디바이스는 어플라이언스로 실행됩니다. 기본 사용자는 Microsoft Teams 회의실 콘솔 앱만 실행하도록 설정됩니다.

1. 대상 디바이스가 도크(예: Surface Pro)에 설치된 경우 도크에서 연결을 끊습니다.

2. 대상 디바이스가 네트워크에 연결되어 있지 않은지 확인합니다.

3. 대상 디바이스가 AC 전원에 연결되어 있는지 확인합니다.

4. USB 설치 디스크를 대상 디바이스에 연결합니다.

5. USB 설치 디스크로 부팅합니다. 제조업체 지침을 참조하세요. 대상 디바이스가 Surface Pro인 경우 다음 단계를 사용하여 USB 설치 디스크로 부팅합니다.

    a. 볼륨을 계속 누르고(-) 단추를 누릅니다.

    b. 전원 단추를 누르고 니다.

    c. Windows 설치가 부팅된 후 볼륨 다운(-) 단추를 해제합니다.

8. 설치가 완료되면 시스템이 종료됩니다.
    
시스템이 종료된 후 USB 설정 디스크를 제거하는 것이 안전합니다. 이 시점에서 대상 장치를 도크에 두고(도크 기반 제품을 사용하는 경우), 회의실에 필요한 주변 장치를 연결하고, 네트워크에 연결할 수 있습니다. 제조업체 지침을 참조하세요.

> [!NOTE]
> Microsoft Teams 회의실에 대한 소프트웨어 업데이트는 비즈니스용 Microsoft Store에서 자동으로 다운로드됩니다. 비즈니스 및 교육용 [Microsoft Store의](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 전제적 준비를 참조하여 방 콘솔이 스토어에 액세스하고 셀프 업데이트할 수 있는지 확인합니다.  

### <a name="selecting-a-language"></a>언어 선택 

크리에이터 업데이트에서는 암시적 언어 선택이 사용자에게 원하는 실제 응용 프로그램 언어를 제공하지 않는 시나리오에서 ApplyCurrentRegionAndLanguage.ps1 스크립트를 사용해야 합니다(예: 콘솔 앱이 프랑스어로 제공되지만 영어로 제공될 예정).
  
> [!NOTE]
> 다음 지침은 Windows 크리에이터의 업데이트를 사용하여 만든 본체에만 사용할 수 있습니다. 새 프로비전 시스템과 함께 미디어를 사용하여 설정되지 않은 레거시/시장 내 시스템은 이러한 지침을 사용할 수 없지만 이 수동 개입이 필요한 초기 문제도 겪지 말아야 합니다(Anniversary Edition을 사용하면 설정의 일부로 앱 언어를 명시적으로 선택할 수 있습니다).
  
### <a name="to-apply-your-desired-language"></a>원하는 언어를 적용합니다.

1. 관리 모드로 전환합니다.
    
2. 시작 메뉴를 선택합니다.
    
3. 기어 아이콘을 선택하여 설정 **앱을** 실행합니다.
    
4. 시간 **언어를 &amp; 선택합니다.**
    
5. 지역 **언어를 &amp; 선택합니다.**
    
6. 언어 **추가를 선택합니다.**
    
7. 추가할 언어를 선택합니다.
    
8. 방금 "언어" 목록에 추가한 언어를 선택합니다.
    
9. 기본값으로 **설정 선택**
    
10. 제거하고자 하는 언어:
    
    a. 제거할 언어를 선택합니다.
    
    b. **[제거]를 선택합니다.**
    
11. 상승된 명령 프롬프트를 시작 합니다.
    
12. 다음 명령을 실행합니다. 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. 시스템을 다시 시작합니다.
    
이제 원하는 언어가 Microsoft Teams 회의실 콘솔에 적용됩니다.
## <a name="initial-set-up-of-the-console"></a>본체의 초기 설정
<a name="Initial"> </a>

Windows가 설치되면 Microsoft Teams 회의실 콘솔 앱이 다음에 시작되거나 /reboot 옵션이 선택된 경우 초기 설치 프로세스로 이동됩니다.
  
1. 사용자 계정 화면이 나타납니다. 본체에 사용할 채팅방 계정의 Skype 로그인 주소(user@domain 형식)를 입력합니다.
    
2. 방 계정의 암호를 입력하고 다시 입력하여 확인할 수 있습니다.
    
3. "도메인 구성"에서 비즈니스용 Skype 서버용 FQDN을 설정하세요. 비즈니스용 Skype SIP 도메인이 사용자의 Exchange 도메인과 다른 경우 이 필드에 Exchange 도메인을 입력합니다.
    
4. 다음을 **클릭합니다.**
    
5. 기능 화면에서 표시된 디바이스를 선택하고 다음을 **클릭합니다.** 기본값은 자동 화면 공유를 설정하고 모임 이름을 끄기로 숨기는 것입니다. 선택할 디바이스는 다음입니다.
    
   - 회의용 마이크: 이 회의실의 기본 마이크입니다.
    
   - 회의용 발표자: 회의의 기본 발표자입니다. 
    
   - 기본 스피커: HDMI에서 오디오에 사용되는 스피커입니다.
    
     각 항목에는 선택할 수 있는 옵션의 드롭다운 메뉴가 있습니다. 각 디바이스에 대해 선택해야 합니다.
    
6. **마침** 을 클릭합니다.
    
Microsoft Teams 회의실 콘솔 앱은 위에서 입력한 자격 증명으로 비즈니스용 Skype Server에 즉시 로그인하기 시작해야 합니다. 또한 동일한 자격 증명을 사용하여 Exchange와 일정 동기화를 시작해야 합니다. 콘솔 앱 사용에 대한 자세한 내용은 [Microsoft Teams 회의실 도움말을 참조하세요.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)
  
> [!IMPORTANT]
> Microsoft Teams 회의실은 인증된 콘솔 하드웨어의 존재에 의존합니다. Microsoft Teams 회의실 콘솔 앱을 포함하는 올바르게 생성된 이미지도 본체 하드웨어가 감지되지 않는 한 초기 설치 절차를 따라 부팅되지 않습니다. Surface Pro 기반 솔루션의 경우 이 검사를 통과하려면 Surface Pro를 함께 제공되는 Dock 하드웨어에 연결해야 합니다.
  
> [!NOTE]
> 터치 키보드에서 기호가 지원되지 않는 경우 초기 설정 중에 일부 비영어 사용자는 본체에 연결된 물리적 키보드가 필요할 수 있습니다.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>콘솔에 개인 CA 인증서 설치
<a name="Certs"> </a>

Microsoft Teams 회의실 콘솔은 연결하는 서버에서 사용하는 인증서를 신뢰해야 합니다. O365의 경우 이러한 서버는 공용 인증 기관을 사용하며 Windows 10에서 자동으로 신뢰하기 때문에 자동으로 수행됩니다. 인증 기관이 비공개인 경우(예: Active Directory 및 Windows 인증 기관을 사용하여 프레미스 배포) 몇 가지 방법으로 Microsoft Teams 회의실 콘솔에 인증서를 추가할 수 있습니다.
  
- 콘솔을 Active Directory에 조인할 수 있으며 인증 기관이 Active Directory에 게시된 경우 필요한 인증서가 자동으로 추가됩니다(일반 배포 옵션).
    
- 이미징 프로세스 후에 인증서를 수동으로 설치할 수 있습니다. 이렇게 하기 전에 콘솔의 초기 설정이 [완료되어야 합니다.](console.md#Initial)
    
### <a name="to-manually-install-the-certificate"></a>인증서를 수동으로 설치하려면

1. 컴퓨터에 CA 인증서를 다운로드하고 "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"에 저장합니다.
    
2. 콘솔을 관리 모드로 전환합니다(관리 모드 및 [장치 관리 참조).](rooms-operations.md#AdminMode)
    
3. 다음 명령을 실행합니다.
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Active Directory 도메인 가입(선택 사항)
<a name="Certs"> </a>

Microsoft Teams 회의실 콘솔을 도메인에 가입할 수 있습니다. 많은 Workstation 정책이 Microsoft Teams 회의실과 호환되지 않는 경우 Microsoft Teams 회의실 콘솔은 PC Workstations와 별도의 OU에 배치해야 합니다. 일반적인 예로는 Microsoft Teams 회의실이 자동으로 시작되지 않도록 하는 암호 적용 정책이 있습니다. GPO 설정 관리에 대한 자세한 내용은 [Microsoft Teams 회의실 관리를 참조하세요.](rooms-operations.md)
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Microsoft Teams 회의실을 도메인에 가입하려면

1. 관리자 계정에서 콘솔에 로그인합니다(관리자 모드 및 [디바이스 관리 참조).](rooms-operations.md#AdminMode)
    
2. 상승된 Powershell 명령 프롬프트를 실행합니다.
    
3. Powershell에서 다음 명령을 입력합니다.
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

예를 들어 자격이 있는 도메인이 redmond.corp.microsoft.com Microsoft Teams 회의실 콘솔이 "리소스" OU의 자식인 "Microsoft Teams 회의실" OU에 있도록 하려는 경우 명령은 다음과 같습니다.
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 도메인에 가입할 때 컴퓨터 이름을 변경하려면 컴퓨터의 새 이름 다음에 -NewName 플래그를 사용 합니다.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Microsoft Teams Rooms 배포 검사 목록
<a name="Checklist"> </a>

본체와 모든 주변 장치를 완전히 구성하는지 최종 확인하는 동안 다음 검사 목록을 사용 합니다.
  
**애플리케이션 설정**

|||
|:-----|:-----|
|☐  <br/> |콘솔 화면 오른쪽 위에 방 계정 이름 및 전화 번호(PSTN을 사용하는 경우)가 올바르게 표시됩니다.  <br/> |
|☐  <br/> |Windows 컴퓨터 이름이 올바르게 설정되었습니다(원격 관리에 유용).  <br/> |
|☐  <br/> |관리자 계정 암호 설정 및 확인  <br/> |
|☐  <br/> |모든 펌웨어 업데이트가 적용되었습니다.  <br/> |
   
**오디오/비디오 주변 장치**

|||
|:-----|:-----|
|☐  <br/> |카메라 주변 펌웨어 버전이 올바른 경우(해당하는 경우)  <br/> |
|☐  <br/> |카메라 기능 및 최적 위치  <br/> |
|☐  <br/> |재생 기본 장치 및 재생 기본 통신 디바이스에 대한 설정이 의도한 오디오 주변 장치로 설정됩니다.  <br/> |
|☐  <br/> |기본 통신 장치를 의도한 오디오 주변 장치로 설정하기 위한 설정  <br/> |
|☐  <br/> |오디오 주변 펌웨어 버전이 올바른 경우(해당하는 경우)  <br/> |
|☐  <br/> |오디오 입력 장치 기능 및 최적 위치  <br/> |
|☐  <br/> |오디오 출력 디바이스 기능 및 최적 위치  <br/> |
   
**Dock**

|||
|:-----|:-----|
|☐  <br/> |케이블이 안전하고 고정되지 않습니다.  <br/> |
|☐  <br/> |HDMI를 통해 오디오가 기능합니다.  <br/> |
|☐  <br/> |HDMI를 통해 비디오가 기능합니다.  <br/> |
|☐  <br/> |Dock은 자유롭게 스위브할 수 있습니다.  <br/> |
|☐  <br/> |환경에 허용되는 디스플레이 밝기  <br/> |
   
## <a name="see-also"></a>참고 항목
<a name="Checklist"> </a>

[Microsoft Teams 룸 계획](rooms-plan.md)
  
[Microsoft Teams 룸 배포](rooms-deploy.md)
  
[Microsoft Teams 룸 콘솔 구성](console.md)
  
[Microsoft Teams 룸 관리](rooms-manage.md)
