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
description: 모든 기능을 활용할 수 있도록 Microsoft Teams 룸 인프라를 준비하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5003bbb3554436ca388990aeebfec4ce6dfb9f57
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58577962"
---
# <a name="prepare-your-environment"></a>작업 환경 준비

이 섹션에는 환경을 준비하는 데 필요한 단계에 대한 개요가 포함되어 있으므로 모든 기능을 사용할 수 Microsoft Teams 룸.
  
1. 각 콘솔에 대한 디바이스 Microsoft Teams 룸 준비합니다. 자세한 [내용은 Microsoft Teams 룸](rooms-deploy.md) 배포를 참조합니다.
    
2. 디바이스에서 사용할 네트워크/인터넷 연결이 작동하고 있는지 확인합니다. 
    
   DHCP를 사용하여 IP 주소를 받을 수 있어야 합니다. (Microsoft Teams 룸 시작 시 정적 IP 주소로 구성할 수는 없지만, 이후 디바이스 또는 업스트림 스위치 또는 라우터에서 디바이스에 대한 정적 IP 주소를 구성할 수 있습니다.

   미디어에 대한 일반 포트를 여는 것 외에도 이러한 포트가 열려 있어야 합니다.
   - HTTPS: 443
   - HTTP: 80

   네트워크가 프록시를 통해 실행되는 경우 프록시 주소 또는 스크립트 정보도 필요합니다.
    
   > [!IMPORTANT]
   > Microsoft Teams 룸 작업을 방해할 수 있는 프록시 인증을 지원하지 않습니다. 프로덕션에 Microsoft Teams 룸 프록시 인증에서 제외된지 확인
  
3. 환경을 개선하기 위해 Microsoft는 데이터를 수집합니다. Microsoft에서 데이터를 수집하도록 허용하기 위해 다음 사이트를 허용합니다.

   - 원격 분석 클라이언트 엔드포인트: https://vortex.data.microsoft.com/
   - 원격 분석 설정 엔드포인트: https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>디바이스 계정 만들기 및 테스트

디바이스 *계정은* Microsoft Teams 룸 클라이언트가 일정과 같은 Exchange 기능에 액세스하고, 비즈니스용 Skype. 자세한 [내용은 Microsoft Teams 룸](rooms-deploy.md) 배포를 참조합니다.
  
### <a name="check-network-availability"></a>네트워크 가용성 확인

제대로 작동하려면 Microsoft Teams 룸 요구 사항을 충족하는 유선 네트워크에 대한 액세스 권한이 있어야 합니다.
  
- Active Directory 또는 Azure AD(Azure Active Directory) 인스턴스 및 Microsoft Exchange 및 비즈니스용 Skype 액세스합니다.

- DHCP를 사용하여 IP 주소를 제공할 수 있는 서버에 대한 액세스입니다. Microsoft Teams 룸 시작 시 정적 IP 주소로 구성할 수 없습니다.

- HTTP 포트 80 및 443에 대한 액세스입니다.

- TCP 및 UDP 포트는 프레미스 비즈니스용 Skype 서버 구현을 위한 서버의 포트 및 프로토콜 요구 사항 또는 Microsoft 365 및 Office 365 URL 및 [IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) 주소 범위에 Microsoft Teams 또는 비즈니스용 Skype 구성합니다. [](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)

> [!IMPORTANT]
> 필요한 대역폭을 보장하기 위해 유선 1Gbps 네트워크 연결을 사용해야 합니다.

> [!NOTE]
> 소프트웨어 업데이트는 Microsoft Teams 룸 자동으로 다운로드 비즈니스용 Microsoft Store됩니다. 룸 [콘솔이](/microsoft-store/prerequisites-microsoft-store-for-business) 저장소 및 자체 업데이트에 액세스할 수 비즈니스용 Microsoft Store 확인을 위해 교육 및 교육에 대한 전제 를 참조합니다.
  
### <a name="certificates"></a>인증서

사용자 Microsoft Teams 룸 디바이스는 웹 서비스, Exchange, Microsoft Teams 또는 비즈니스용 Skype, 네트워크 사용 및 인증에 대해 인증서를 사용합니다. 관련 서버가 공용 인증서를 사용하는 경우( Online 및 일부 On-Premises 배포의 경우) 인증서를 설치하는 데 관리자의 일부에서 추가 작업이 필요하지 않습니다. 반면에 인증서 기관이 사설 CA(On-Premises 배포에 일반적)인 경우 디바이스는 CA + CA 체인 인증서가 디바이스에 설치되어 있는 CA를 신뢰해야 합니다. 도메인에 디바이스를 추가하면 이 작업이 자동으로 수행될 수 있습니다.
  
다른 클라이언트의 경우와 동일한 방식으로 인증서를 Windows 있습니다. 
  
> [!NOTE]
> 인증서를 사용하려면 인증서가 Microsoft Teams 룸 비즈니스용 Skype 서버.
  
### <a name="proxy"></a>프록시

Microsoft Teams 룸 OS에서 프록시 설정을 상속하도록 Windows 있습니다. 다음과 Windows OS에 액세스합니다.
  
1. Microsoft Teams 룸 UI에서 디바이스의 로컬 관리자 암호에 대한 메시지가 설정 기어 아이콘을 클릭합니다(기본 암호는 **sfb입니다).**
2. 다음에  설정 탭한 다음 이동 단추를 Windows 탭한 다음 관리자 로그인 단추로 이동 단추를 탭한  다음 관리자 단추를 클릭합니다(컴퓨터가  도메인에 가입된 경우 다른 사용자를 선택한 다음 .\admin을 사용자 이름으로 사용).  
3. 검색 **Windows** 왼쪽 아래 형식의 regedit(화면을 길게 누르거나 마우스 오른쪽 단추로 클릭하고 관리자 권한으로 실행을 **선택합니다).**
4. HKEY_USERS 폴더(컴퓨터 사용자 SID 목록이 표시됩니다)를 클릭하여 루트 폴더가 선택되어 HKEY_USERS 확인합니다.
       
5. 파일을 클릭한 다음 **Hive 로드를 선택하세요.**
6. **C:\Users\Skype** 폴더로 찾아 파일 이름 상자 NTUSER.dat를 입력하고 열기 단추를 누릅니다.

7. 새로 로드된 Hive에 대한 키 이름을 묻는 메시지가 표시됩니다. Skype 입력합니다(이제 사용자에 대한 레지스트리 Skype 표시됩니다).
 
8. Skype 키를 열고 HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings 다음 설정을 입력해야 합니다. 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    ProxyServer가 존재하지 않는 경우 이 키를 문자열로 추가해야 할 수 있습니다. xx.xx.xx.xx:8080을 프록시 서버의 ip/host 및 포트에 변경합니다.
 
    고객이 PAC 파일을 사용하는 경우 구성은 아래 예제와 같습니다.

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. 변경이 완료되면 Skype 사용자 키(Skype 루트 폴더)를 강조 표시하고 레지스트리 파일 메뉴에서 Hive 언로드를 선택합니다(확인하라는 메시지가 표시됩니다. **예를 선택합니다).**
    
10. 이제 레지스트리 편집기를 닫고 로고프를 검색 상자에 Windows 수 있습니다.
    
11. 로그인 화면으로 돌아가서 사용자를 Skype **합니다.** 이전 모든 단계가 성공한 경우 Microsoft Teams 룸 디바이스가 성공적으로 로그인됩니다.
    
FQDNs, 포트 및 IP 주소 범위에 대한 자세한 내용은 네트워크 보안 문서를 참조하여 Microsoft Teams 룸. [](./security.md#network-security)
  
  
### <a name="create-provisioning-packages"></a>프로비전 패키지 만들기

프로비전 패키지를 사용하여 Exchange Server, Microsoft 365 또는 Office 365.
  
### <a name="admin-group-management"></a>관리 그룹 관리

도메인에 가입한 후 그룹 정책 또는 로컬 컴퓨터 관리를 사용하여 도메인의 PC를 사용하는 경우와 마찬가지로 보안 그룹을 로컬 관리자로 Windows 수 있습니다. 보안 그룹의 구성원인 모든 사람은 자격 증명을 입력하고 자격 증명을 잠금 해제할 설정.
  
> [!NOTE]
> Microsoft Teams 룸 디바이스가 도메인에 대한 신뢰를 잃는 경우(예: 도메인에 가입된 Microsoft Teams 룸 도메인에서 해당 도메인을 제거한 경우) 디바이스에 인증하고 도메인을 열 수 설정. 해결은 로컬 관리자 계정으로 로그인하는 것입니다. 
  
## <a name="local-accounts"></a>로컬 계정

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft Teams 룸 로컬 사용자 계정

디바이스 계정은 일반적으로 암호를 사용하지 않습니다. 암호를 입력할 수 있지만 해당 암호가 만료되면 사용자가 콘솔 애플리케이션에서 잠겨 있을 수 있는 가능성을 포함하여 결과가 발생할 수 있습니다. 따라서 관리자는 암호를 만료할 수 없는지 확인해야 합니다.
  
### <a name="admin---local-administrator-account"></a>"관리자" - 로컬 관리자 계정

Microsoft Teams 룸 암호는 "sfb"로 설정됩니다. 암호는 Windows 설정 파일로 이동하거나 Windows 또는 AutoUnattend.xml 파일로 이동하여 로컬로 변경할 수 있습니다(ADK의 Windows 시스템 이미지 관리자를 사용하여 xml 파일을 \> 변경합니다.
  
> [!CAUTION]
> 가능한 한 빨리 Microsoft Teams 룸 암호를 변경해야 합니다. 
  
도메인 관리자가 로컬 관리자로 설정되는 그룹 정책을 설정하여 로컬 관리자 암호를 관리할 수도 있습니다.
  
로컬 관리자 암호는 설정 중에 선택으로 포함되지 않습니다.
  
### <a name="machine-account"></a>컴퓨터 계정

다른 디바이스와 Windows 마찬가지로 PC 이름 변경에 대해 마우스 **오른쪽 단추로 클릭하여** 컴퓨터 이름을 설정 \>  \> **수 있습니다.**
  
도메인에 가입한 후 컴퓨터의 이름을 변경하려면 컴퓨터의 새 이름 다음에 PowerShell 명령인 **Rename-Computer를** 사용하여 이름을 변경합니다.
  
## <a name="related-topics"></a>관련 항목

[계획 Microsoft Teams 룸](rooms-plan.md)

[Microsoft Teams 룸 요구사항](requirements.md)
  
[Microsoft Teams 룸 배포](rooms-deploy.md)
  
[Microsoft Teams 룸 콘솔 구성](console.md)
  
[Microsoft Teams 룸 관리](rooms-manage.md)

[교육 및 교육을 위한 비즈니스용 Microsoft Store 전제](/microsoft-store/prerequisites-microsoft-store-for-business)