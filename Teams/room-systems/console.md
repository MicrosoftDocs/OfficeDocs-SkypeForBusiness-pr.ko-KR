---
title: Microsoft 팀 대화방 콘솔 구성
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: 이 문서에서는 Microsoft 팀 회의실 콘솔과 주변 장치를 설정 하는 방법을 설명 합니다.
ms.openlocfilehash: f42f89d25a58ce96308318cc732e85f7080b86e5
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569910"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Microsoft 팀 대화방 콘솔 구성

이 문서에서는 Microsoft 팀 회의실 콘솔과 주변 장치를 설정 하는 방법을 설명 합니다.
  
[Microsoft 팀 대화방 배포](room-systems-v2.md)에 설명 된 대로 필요한 microsoft 팀 또는 비즈니스용 Skype 및 Exchange 계정이 이미 만들어지고 테스트 된 경우에만이 단계를 수행 해야 합니다. [Microsoft 팀 회의실 요구 사항](requirements.md)에 설명 된 하드웨어 및 소프트웨어가 필요 합니다. 이 항목에서는 다음 섹션을 다룹니다.
  
- [설치 미디어 준비](console.md#Prep_Media)
- [콘솔에 개인 CA 인증서 설치](console.md#Certs)
- [Windows 10 및 Microsoft 팀 대화방 콘솔 앱 설치](console.md#Reimage)
- [콘솔의 초기 설정](console.md#Initial)
- [Microsoft 팀 대화방 배포 검사 목록](console.md#Checklist)

> [!NOTE]
> Microsoft 팀 대화방은 [microsoft 팀 대화방 배포](room-systems-v2.md)에 설명 된 대로 디바이스 계정이 올바르게 설정 된 microsoft 팀 또는 비즈니스용 Skype 환경 에서만 제대로 작동 합니다.
  
## <a name="prepare-the-installation-media"></a>설치 미디어 준비
<a name="Prep_Media"> </a>

Microsoft 팀 공간 콘솔 앱을 설치 하려면 최소한 32GB의 용량을 갖춘 USB 저장 장치가 필요 합니다. 장치에 다른 파일이 없어야 합니다. USB 저장소의 기존 파일이 모두 손실 됩니다.
  
> [!NOTE]
> 이러한 지침에 따라 Microsoft 팀 회의실 설치 미디어를 만들지 못하면 예기치 않은 동작이 발생할 수 있습니다.

> [!NOTE]
> 아래 프로세스는 새 Microsoft 팀 공간 장치를 이미지 하기 위해 설치 미디어를 만드는 것입니다. 기존 장치는 기본적으로 Windows Update 및 Windows 스토어에서 자동으로 업데이트 됩니다.
  
1. [CreateSrsMedia 스크립트](https://go.microsoft.com/fwlink/?linkid=867842)를 다운로드 합니다.
2. Windows 10 컴퓨터의 관리자 권한 프롬프트에서 CreateSrsMedia 스크립트를 실행 합니다.
3. 스크립트의 지침에 따라 Microsoft 팀 대화방 USB 설치 디스크를 만듭니다.


> [!TIP]
> CreateSrsMedia 스크립트가 시작 될 때마다 화면 출력에는 세션에 대 한 로그 파일의 이름 또는 기록이 포함 됩니다. 스크립트를 실행 하는 데 문제가 있는 경우 지원을 요청할 때 해당 기록의 복사본을 사용할 수 있는지 확인 합니다. 

CreateSrsMedia 스크립트는 다음 작업을 자동화 합니다.

1. Microsoft 팀 대화방의 최신 MSI 설치 관리자를 다운로드 합니다.
2. 사용자가 제공 해야 하는 Windows의 빌드를 확인 합니다. 가장 최근에 릴리스된 버전이 Microsoft 팀 회의실 장치에서 사용 하도록 테스트 및 지원 되지 않을 수 있습니다.
3. 필요한 지원 구성 요소를 다운로드 합니다.
4. 필요한 구성 요소를 설치 미디어에 어셈블합니다.

특정 버전의 Windows 10이 필요 하며,이 버전은 볼륨 라이선스 고객만 사용할 수 있습니다.  [볼륨 라이선싱 서비스 센터](https://www.microsoft.com/Licensing/servicecenter/)에서 복사본을 가져올 수 있습니다.

완료 되 면 컴퓨터에서 USB 디스크를 제거 하 고 [Windows 10 및 Microsoft 팀 대화방 콘솔 앱](console.md#Reimage)을 계속 설치 합니다.

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Windows 10 및 Microsoft 팀 대화방 콘솔 앱 설치
<a name="Reimage"> </a>

지금 만든 설치 미디어를 적용 해야 합니다. 대상 장치가 기기로 실행 되 고 기본 사용자는 Microsoft 팀 대화방 콘솔 앱만 실행 하도록 설정 됩니다.

1. 대상 장치가 dock에 설치 되는 경우 (예: Surface Pro) dock에서 연결을 끊습니다.

2. 대상 장치가 네트워크에 연결 되어 있지 않은지 확인 합니다.

3. 대상 장치가 AC 전원에 연결 되어 있는지 확인 합니다.

4. USB 설치 디스크를 대상 장치에 연결 합니다.

5. USB 설치 디스크로 부팅 합니다. 제조업체 지침을 참조 하세요. 대상 장치가 Surface Pro 인 경우 다음 단계를 사용 하 여 USB 설정 디스크로 부팅 합니다.

    에서. 볼륨 작게 (-) 단추를 길게 눌러 계속 합니다.

    b. 전원 단추를 눌렀다가 놓습니다.

    c. Windows 설치 프로그램이 부팅 되 면 볼륨 작게 (-) 단추를 놓습니다.

8. 설치가 완료 되 면 시스템이 종료 됩니다.
    
시스템이 종료 된 후에는 USB 설치 디스크를 제거 하는 것이 안전 합니다. 이 시점에서 대상 디바이스를 dock에 배치 (dock 기반 제품을 사용 하는 경우) 하 고 회의실에 필요한 주변 장치를 연결한 다음 네트워크에 연결할 수 있습니다. 제조업체 지침을 참조 하세요.

> [!NOTE]
> Microsoft 팀 대화방의 소프트웨어 업데이트는 비즈니스용 Microsoft Store에서 자동으로 다운로드 됩니다. [Microsoft Store 비즈니스 에디션 및 학력에 대 한 필수 구성 요소](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 를 참조 하 여 채팅방 콘솔에서 스토어 및 자동 업데이트에 액세스할 수 있는지 확인 합니다.  

### <a name="selecting-a-language"></a>언어 선택 

만든이의 업데이트에서 암시적 언어 선택이 사용자에 게 원하는 실제 응용 프로그램 언어를 제공 하지 않는 시나리오의 ps1 스크립트 (예: 콘솔 앱을 프랑스어로 표시 하려는 경우)를 사용 해야 합니다. 영어를 사용할 수 있습니다.
  
> [!NOTE]
> 다음 지침은 Windows Creator의 업데이트를 사용 하 여 만든 콘솔에만 적용 됩니다. 새 프로비저닝 시스템으로 미디어를 사용 하 여 설정 하지 않은 레거시/시장 시스템에서는 이러한 지침을 사용할 수 없지만,이 수동 작업을 수행 하는 초기 문제 (기념 Edition 설치 과정의 일부로 명시적으로 앱 언어를 설정 합니다.
  
### <a name="to-apply-your-desired-language"></a>원하는 언어를 적용 하려면

1. 관리 모드로 전환 합니다.
    
2. 시작 메뉴를 선택 합니다.
    
3. 기어 아이콘을 선택 하 여 **설정** 앱을 시작 합니다.
    
4. **시간 &amp; 언어**를 선택 합니다.
    
5. **지역 &amp; 언어**를 선택 합니다.
    
6. **언어 추가를**선택 합니다.
    
7. 추가 하고자 하는 언어를 선택 합니다.
    
8. "언어" 목록에 방금 추가한 언어를 선택 합니다.
    
9. **기본값으로 설정을**선택 합니다.
    
10. 제거할 언어에 대해 다음을 수행 합니다.
    
    에서. 제거 하고자 하는 언어를 선택 합니다.
    
    b. **제거**를 선택 합니다.
    
11. 관리자 권한 명령 프롬프트를 시작 합니다.
    
12. 다음 명령을 실행 합니다. 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. 시스템을 다시 시작 합니다.
    
이제 Microsoft 팀 대화방 콘솔에 해당 언어가 적용 됩니다.
## <a name="initial-set-up-of-the-console"></a>콘솔의 초기 설정
<a name="Initial"> </a>

Windows가 설치 된 후에는 Microsoft 팀 대화방 콘솔 앱이 다음에 시작 될 때 또는/reboot 옵션이 선택 된 경우 초기 설정 프로세스로 이동 됩니다.
  
1. 사용자 계정 화면이 나타납니다. 콘솔과 함께 사용할 룸 계정의 Skype 로그인 주소 (사용자 @ 도메인 형식으로)를 입력 합니다.
    
2. 채팅방 계정에 대 한 암호를 입력 하 고 다시 입력 하 여 확인 합니다.
    
3. "도메인 구성"에서 비즈니스용 Skype 서버용 FQDN을 설정 합니다. 비즈니스용 Skype SIP 도메인이 사용자의 Exchange 도메인과 다른 경우이 필드에 Exchange 도메인을 입력 합니다.
    
4. **다음**을 클릭 합니다.
    
5. 기능 화면에서 표시 된 장치를 선택 하 고 **다음**을 클릭 합니다. 기본적으로 자동 화면 공유를 On으로 설정 하 고 모임 이름 숨기기를 해제로 설정 합니다. 선택할 장치는 다음과 같습니다.
    
   - 회의 마이크:이 회의실에 대 한 기본 마이크입니다.
    
   - 회의 스피커: 컨퍼런스 기본 스피커 
    
   - 기본 스피커: HDMI 수집에서 오디오에 사용 되는 스피커입니다.
    
     각 항목에는 선택할 수 있는 옵션의 드롭다운 메뉴가 있습니다. 각 장치에 대 한 항목을 선택 해야 합니다.
    
6. **마침을**클릭 합니다.
    
Microsoft 팀 대화방 콘솔 앱은 바로 위의 자격 증명으로 비즈니스용 Skype Server에 로그인을 시작 하 고 동일한 자격 증명을 사용 하 여 Exchange와 일정을 동기화 하기 시작 해야 합니다. 콘솔 앱을 사용 하는 방법에 대 한 자세한 내용은 [Microsoft 팀 대화방 도움말](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)을 참조 하세요.
  
> [!IMPORTANT]
> Microsoft 팀 대화방은 인증 된 콘솔 하드웨어의 존재 여부에 따라 달라 집니다. Microsoft 팀 공간 콘솔 앱을 포함 하는 올바르게 만든 이미지도 콘솔 하드웨어가 검색 되지 않는 한 초기 설정 절차를 지 나 부팅 되지 않습니다. Surface Pro 기반 솔루션의 경우 Surface Pro는 함께 제공 된 dock 하드웨어에 연결 해야만이 검사를 통과할 수 있습니다.
  
> [!NOTE]
> 일부 영어가 아닌 사용자는 터치 키보드에서 기호가 지원 되지 않는 경우 초기 설정 시 콘솔에 연결 된 실제 키보드가 필요할 수 있습니다.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>콘솔에 개인 CA 인증서 설치
<a name="Certs"> </a>

Microsoft 팀 대화방 콘솔은 연결 하는 서버에서 사용 하는 인증서를 신뢰 해야 합니다. O365의 경우이는 해당 서버가 공개 인증 기관을 사용 하 고 있으며 Windows 10에서 자동으로 신뢰 되기 때문에 자동으로 수행 됩니다. Active Directory와 Windows 인증 기관과의 온-프레미스 배포와 같은 인증 기관이 비공개 인 경우 다음과 같은 두 가지 방법으로 인증서를 Microsoft 팀 공간 콘솔에 추가할 수 있습니다.
  
- Active Directory에 콘솔을 가입 하 고 인증 기관이 Active Directory에 게시 되 면 (일반 배포 옵션) 필요한 인증서가 자동으로 추가 되도록 할 수 있습니다.
    
- 이미징 프로세스가 완료 되 면 수동으로 인증서를 설치할 수 있습니다. 이 작업을 수행 하기 전에 먼저 [콘솔 설정을](console.md#Initial)완료 해야 합니다.
    
### <a name="to-manually-install-the-certificate"></a>수동으로 인증서를 설치 하려면

1. CA 인증서를 컴퓨터에 다운로드 하 고 "C:\Skype 채팅방 Systems\x64\Scripts\Provisioning\CAcertificate.cer"에 저장 합니다.
    
2. 콘솔을 관리 모드 ( [관리자 모드 및 장치 관리](room-systems-v2-operations.md#AdminMode)참조)로 배치 합니다.
    
3. 다음 명령을 실행 합니다.
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Active Directory 도메인에 가입 (선택 사항)
<a name="Certs"> </a>

Microsoft 팀 대화방 콘솔을 도메인에 연결할 수 있습니다. 많은 워크스테이션 정책이 Microsoft 팀 대화방과 호환 되지 않으므로 microsoft 팀 공간 콘솔을 PC 워크스테이션과 별도의 OU에 배치 해야 합니다. 일반적인 예는 Microsoft 팀 대화방을 자동으로 시작 하는 것을 방지 하는 암호 적용 정책입니다. GPO 설정 관리에 대 한 자세한 내용은 [Microsoft 팀 대화방 관리](room-systems-v2-operations.md)를 참조 하세요.
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>도메인에 Microsoft 팀 대화방에 참가 하려면

1. 관리자 계정으로 콘솔에 로그인 합니다 ( [관리자 모드 및 장치 관리](room-systems-v2-operations.md#AdminMode)참조).
    
2. 관리자 권한 Powershell 명령 프롬프트를 실행 합니다.
    
3. Powershell에 다음 명령을 입력 합니다.
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

예를 들어 정규화 된 도메인이 redmond.corp.microsoft.com Microsoft 팀 대화방 콘솔이 "Resources" OU의 자식인 "Microsoft 팀 대화방" OU에 있어야 하는 경우 명령은 다음과 같이 표시 됩니다.
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 도메인에 참가할 때 컴퓨터의 이름을 바꾸려면-NewName 플래그를 사용 하 고 컴퓨터의 새 이름을 입력 합니다.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Microsoft 팀 대화방 배포 검사 목록
<a name="Checklist"> </a>

콘솔 및 모든 주변 기기가 완전히 구성 되었음을 최종 확인 하는 동안 다음 검사 목록을 사용 합니다.
  
**응용 프로그램 설정**

|||
|:-----|:-----|
|☐  <br/> |콘솔 화면의 오른쪽 위에 대화방 계정 이름 및 전화 번호 (PSTN 사용)가 올바르게 표시 됨  <br/> |
|☐  <br/> |Windows 컴퓨터 이름이 올바르게 설정 되어 있습니다 (원격 관리에 유용).  <br/> |
|☐  <br/> |Administrator 계정 비밀 번호 설정 및 확인 됨  <br/> |
|☐  <br/> |모든 펌웨어 업데이트가 적용 되었습니다.  <br/> |
   
**오디오/비디오 주변 장치**

|||
|:-----|:-----|
|☐  <br/> |카메라 주변 기기 펌웨어 버전이 올바릅니다 (해당 하는 경우).  <br/> |
|☐  <br/> |카메라 작동 및 위치 최적화  <br/> |
|☐  <br/> |기본 장치 및 재생에 대 한 설정을 원하는 오디오 주변 장치에 설정 하는 기본 통신 디바이스  <br/> |
|☐  <br/> |원하는 오디오 주변 기기에 설정 된 기본 통신 디바이스의 기록 설정  <br/> |
|☐  <br/> |오디오 주변 기기 펌웨어 버전이 올바릅니다 (해당 하는 경우).  <br/> |
|☐  <br/> |오디오 입력 디바이스 작동 및 최적 위치  <br/> |
|☐  <br/> |오디오 출력 디바이스 작동 및 최적 위치  <br/> |
   
**입력판**

|||
|:-----|:-----|
|☐  <br/> |케이블이 안전 하 고 pinched 않습니다.  <br/> |
|☐  <br/> |HDMI를 통한 오디오 수집 기능이 작동 합니다.  <br/> |
|☐  <br/> |HDMI를 통해 비디오 수집 기능이 작동 합니다.  <br/> |
|☐  <br/> |자유롭게 항구 회전 가능  <br/> |
|☐  <br/> |환경에 대해 디스플레이 밝기가 허용 됨  <br/> |
   
## <a name="see-also"></a>참고 항목
<a name="Checklist"> </a>

[Microsoft 팀 회의실 계획](skype-room-systems-v2-0.md)
  
[Microsoft 팀 대화방 배포](room-systems-v2.md)
  
[Microsoft 팀 대화방 콘솔 구성](console.md)
  
[Microsoft 팀 대화방 관리](skype-room-systems-v2.md)
