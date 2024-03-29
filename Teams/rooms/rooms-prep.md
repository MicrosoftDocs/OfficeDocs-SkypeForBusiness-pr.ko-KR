---
title: 환경 준비
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: 모든 기능을 활용할 수 있도록 Microsoft Teams 룸 배포하기 위한 인프라를 준비하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7006f560c5d0991b74c14fc5eb0b13e829b642d9
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532228"
---
# <a name="prepare-your-environment"></a>작업 환경 준비

이 섹션에는 Microsoft Teams 룸 모든 기능을 사용할 수 있도록 환경을 준비하는 데 필요한 단계에 대한 개요가 포함되어 있습니다.
  
1. 각 Microsoft Teams 룸 콘솔에 대한 리소스 계정을 준비합니다. 자세한 내용은 [Microsoft Teams 룸 배포](rooms-deploy.md)를 참조하세요.
    
2. 디바이스에서 사용할 네트워크/인터넷 연결이 작동하는지 확인합니다.
  
3. 환경을 개선하기 위해 Microsoft는 데이터를 수집합니다. Microsoft에서 데이터를 수집할 수 있도록 허용하려면 다음 사이트를 허용합니다.

   - 원격 분석 클라이언트 엔드포인트: `https://vortex.data.microsoft.com/`
   - 원격 분석 설정 엔드포인트:` https://settings.data.microsoft.com/`
    
### <a name="create-and-test-a-resource-account"></a>리소스 계정 만들기 및 테스트

*리소스 계정은* Microsoft Teams 룸 클라이언트가 일정과 같은 Exchange의 기능에 액세스하고 Microsoft Teams에 연결하는 데 사용하는 계정입니다. 자세한 내용은 [Microsoft Teams 룸 배포](rooms-deploy.md)를 참조하세요.
  
### <a name="check-network-availability"></a>네트워크 가용성 확인

제대로 작동하려면 Microsoft Teams 룸 다음 요구 사항을 충족하는 유선 네트워크에 액세스할 수 있어야 합니다.
  
- Microsoft Exchange 및 Microsoft Teams뿐만 아니라 Active Directory 또는 Azure AD(Azure Active Directory) 인스턴스에 액세스합니다.

- DHCP를 사용하여 IP 주소를 제공할 수 있는 서버에 액세스합니다. Microsoft Teams 룸 첫 번째 단위 시작 시 고정 IP 주소로 구성할 수 없습니다.

- HTTP 포트 80 및 443에 액세스합니다.

- 온-프레미스 비즈니스용 Skype 서버 구현을 [위한 서버에 대한 포트 및 프로토콜 요구 사항](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) 또는 Microsoft Teams의 [Microsoft 365 및 Office 365 URL 및 IP 주소 범위에](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) 설명된 대로 구성된 TCP 및 UDP 포트입니다.

네트워크가 프록시를 통해 실행되는 경우 프록시 주소 또는 스크립트 정보도 필요합니다.
    
> [!IMPORTANT]
> Microsoft Teams 룸 회의실의 정기적인 작업을 방해할 수 있으므로 프록시 인증을 지원하지 않습니다. 프로덕션으로 전환하기 전에 Microsoft Teams 룸 프록시 인증에서 제외되었는지 확인합니다.

> [!IMPORTANT]
> 필요한 대역폭을 보장하려면 유선 1Gbps 네트워크 연결을 사용해야 합니다.

> [!NOTE]
> Microsoft Teams 룸 대한 소프트웨어 업데이트는 비즈니스용 Microsoft Store 자동으로 다운로드됩니다. [비즈니스용 Microsoft Store 및 교육의 필수 구성 요소를](/microsoft-store/prerequisites-microsoft-store-for-business) 참조하여 회의실 콘솔이 스토어에 액세스하고 자체 업데이트할 수 있는지 확인합니다.
  
### <a name="certificates"></a>인증서

Microsoft Teams 룸 디바이스는 Exchange Web Services, Microsoft Teams 또는 비즈니스용 Skype, 네트워크 사용량 및 인증에 인증서를 사용합니다. 관련 서버가 공용 인증서(온라인 및 일부 온-프레미스 배포의 경우)를 사용하는 경우 관리자가 인증서를 설치하는 데 추가 작업이 필요하지 않습니다. 반면에 인증 기관이 프라이빗 CA인 경우 디바이스는 해당 CA를 신뢰해야 합니다. 즉, 디바이스에 CA + CA 체인 인증서가 설치되어 있습니다. 도메인에 디바이스를 추가하면 이 작업이 자동으로 수행됩니다.
  
다른 Windows 클라이언트와 동일한 방식으로 인증서를 설치합니다.

> [!IMPORTANT]
> 프록시 서버가 내부적으로 서명된 인증서를 사용하는 경우 루트 CA를 포함한 내부 인증서 체인을 Microsoft Teams 룸 디바이스에 설치해야 합니다.
  
> [!NOTE]
> Microsoft Teams 룸 비즈니스용 Skype 서버 사용하려면 인증서가 필요할 수 있습니다.
  
### <a name="proxy"></a>프록시

Microsoft Teams 룸 Windows OS에서 프록시 설정을 상속하도록 설계되었습니다. 다음과 같은 방식으로 Windows OS에 액세스합니다.
  
1. Microsoft Teams 룸 UI에서 디바이스에서 로컬 관리자 암호를 묻는 메시지가 표시되는 설정 기어 아이콘을 클릭합니다(기본 암호는 **sfb** 임).
2. **설정을** 탭한 다음 **Windows로 이동** 단추를 탭한 다음 **관리 로그인 단추로 이동** 단추를 탭한 다음 **관리자** 단추를 클릭합니다(컴퓨터가 도메인에 가입된 경우 **다른 사용자를** 선택한 다음 .\admin을 사용자 이름으로 사용).
3. **Windows 검색** 상자 왼쪽 아래의 regedit에 입력합니다(화면을 길게 누르거나 마우스 오른쪽 단추를 클릭하고 **관리자 권한으로 실행** 선택).
4. HKEY_USERS 폴더(컴퓨터 사용자 SID 목록이 표시됨)를 클릭하면 루트 폴더 HKEY_USERS 선택되어 있는지 확인합니다.
       
5. 파일을 클릭한 다음 **Hive 로드를 선택합니다.**
6. **C:\Users\Skype** 폴더로 이동하여 파일 이름 상자 NTUSER.dat에 입력하고 열기 단추를 누릅니다.

7. 새로 로드된 Hive의 키 이름을 묻는 메시지가 표시됩니다. Skype를 입력합니다(이제 Skype 사용자에 대한 레지스트리 설정이 표시됨).
 
8. Skype 키를 열고 HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings 찾은 다음, 이러한 설정이 입력되었는지 확인합니다. 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    ProxyServer가 없는 경우 이 키를 문자열로 추가해야 할 수 있습니다. xx.xx.xx.xx:8080을 프록시 서버의 ip/호스트 및 포트로 변경합니다.
 
    고객이 PAC 파일을 사용하는 경우 구성은 아래 예제와 같습니다.

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. 변경이 완료되면 Skype 사용자 키(Skype의 루트 폴더)를 강조 표시하고 레지스트리 파일 메뉴에서 Hive 언로드를 선택합니다(확인 메시지가 표시됩니다. **예** 선택).
    
10. 이제 레지스트리 편집기를 닫고 Windows 검색 상자에 로그오프를 입력할 수 있습니다.
    
11. 로그인 화면으로 돌아가 **서 Skype** 사용자를 선택합니다. 이전 단계가 모두 성공하면 Microsoft Teams 룸 디바이스가 성공적으로 로그인됩니다.
    
Microsoft Teams 룸 필요한 FQDN, 포트 및 IP 주소 범위에 대한 자세한 내용은 [네트워크 보안](./security-windows.md#network-security) 문서를 참조하세요.
  
### <a name="admin-group-management"></a>관리 그룹 관리

도메인(Azure Active Directory 또는 Active Directory)에 가입하도록 선택하는 경우 Microsoft Endpoint Manager, 그룹 정책 또는 로컬 컴퓨터 관리를 사용하여 도메인의 Windows PC와 마찬가지로 보안 그룹을 로컬 관리자로 설정할 수 있습니다. 해당 보안 그룹의 구성원인 모든 사용자는 자격 증명을 입력하고 설정을 잠금 해제할 수 있습니다.
  
> [!NOTE]
> Microsoft Teams 룸 디바이스가 도메인에 대한 신뢰를 잃는 경우(예: 도메인에 가입된 후 도메인에서 Microsoft Teams 룸 제거하는 경우) 디바이스에 인증하고 설정을 열 수 없습니다. 해결 방법은 로컬 관리 계정으로 로그인하는 것입니다. 
  
## <a name="local-accounts"></a>로컬 계정

### <a name="microsoft-teams-rooms-local-user-account"></a>로컬 사용자 계정 Microsoft Teams 룸

Teams 룸 "Skype"라는 암호 없는 로컬 계정을 포함합니다. 이 계정은 Windows에 로그인하여 Teams 룸 앱을 시작하는 데 사용됩니다. 이 계정에 암호를 적용하는 것은 지원되지 않습니다. 자세한 내용은 [Microsoft Teams 룸 보안을](security-windows.md) 참조하세요.
  
### <a name="admin---local-administrator-account"></a>"관리" - 로컬 관리자 계정

Microsoft Teams 룸 기본 암호는 "sfb"로 설정됩니다. 암호는 관리 모드 또는 AutoUnattend.xml 파일을 통해 로컬로 변경할 수 있습니다(ADK의 Windows 시스템 이미지 관리자를 사용하여 xml 파일을 변경).
  
> [!CAUTION]
> 가능한 한 빨리 Microsoft Teams 룸 암호를 변경해야 합니다. 
  
로컬 관리자 암호는 설치 중에 선택 항목으로 포함되지 않습니다.

Microsoft Teams 룸 [보안](security-windows.md) 문서에서 관리 계정에 대한 자세한 내용을 확인할 수 있습니다.
  
### <a name="machine-account"></a>컴퓨터 계정

다른 Windows 장치와 마찬가지로 **PC 이름 바꾸기****에 대한** \> **설정을** \> 마우스 오른쪽 단추로 클릭하여 컴퓨터 이름을 바꿀 수 있습니다.
  
도메인에 가입한 후 컴퓨터 이름을 바꾸려면 PowerShell 명령인 [Rename-Computer](/powershell/module/microsoft.powershell.management/rename-computer)와 컴퓨터의 새 이름을 사용합니다.
  
## <a name="related-topics"></a>관련 주제

[계획 Microsoft Teams 룸](rooms-plan.md)

[Microsoft Teams 룸 요구사항](requirements.md)
  
[Microsoft Teams 룸 배포](rooms-deploy.md)
  
[Microsoft Teams 룸 콘솔 구성](console.md)
  
[Microsoft Teams 룸 관리](rooms-manage.md)

[비즈니스용 Microsoft Store 및 교육의 필수 구성 요소](/microsoft-store/prerequisites-microsoft-store-for-business)
