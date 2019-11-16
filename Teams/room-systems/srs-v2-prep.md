---
title: 환경 준비
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: 이 문서에서는 Microsoft 팀 대화방을 배포 하기 위한 인프라 준비에 대해 설명 합니다.
ms.openlocfilehash: b7bc3b7791edf88fd6882b67cdaa7d9b65e87741
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675806"
---
# <a name="prepare-your-environment"></a>작업 환경 준비

이 섹션에서는 Microsoft 팀 대화방의 모든 기능을 사용할 수 있도록 환경을 준비 하는 데 필요한 단계에 대해 간략하게 설명 합니다.
  
1. 각 Microsoft 팀 공간 콘솔에 대 한 디바이스 계정을 준비 합니다. 자세한 내용은 [Microsoft 팀 대화방 배포](room-systems-v2.md) 를 참조 하세요.
    
2. 사용할 디바이스에 대해 작동 하는 네트워크/인터넷 연결이 있는지 확인 합니다. 
    
   - DHCP를 사용 하 여 IP 주소를 받을 수 있어야 합니다. (Microsoft 팀 대화방은 첫 번째 단위 시작 시 고정 IP 주소로 구성할 수 없지만 나중에 장치에 대 한 고정 IP를 장치 또는 업스트림 스위치 또는 라우터에서 구성할 수 있습니다.)
   - 이 포트는 다음과 같이 열려 있어야 합니다 (미디어에 대 한 일반 포트 열기 외에).
   - HTTPS: 443
   - HTTP: 80
   - 네트워크가 프록시를 통해 실행 되는 경우에는 프록시 주소 또는 스크립트 정보도 필요 합니다.
    
     > [!NOTE]
     > Microsoft 팀 대화방은 HDMI 수집 기능 (비디오, 오디오)에 문제가 발생 하는 데 관측 된 HDCP 입력을 지원 하지 않습니다. Microsoft 팀 대화방에 연결 된 스위치에 HDCP 옵션이 설정 되어 있는지 확인 합니다.
  
3. Microsoft는 환경을 개선 하기 위해 데이터를 수집 합니다. Microsoft에서 데이터를 수집 하도록 허용 하려면 다음 사이트를 허용 목록.

   - 원격 분석 클라이언트 끝점:https://vortex.data.microsoft.com/
   - 원격 분석 설정 끝점:https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>디바이스 계정 만들기 및 테스트

*장치 계정은* Microsoft 팀 대화방 클라이언트가 일정과 같은 Exchange의 기능에 액세스 하 고 비즈니스용 Skype를 사용 하도록 설정 하는 데 사용 하는 계정입니다. 자세한 내용은 [Microsoft 팀 대화방 배포](room-systems-v2.md) 를 참조 하세요.
  
### <a name="check-network-availability"></a>네트워크 가용성 확인

제대로 작동 하려면 Microsoft 팀 대화방 장치가 다음 요구 사항을 충족 하는 유선 네트워크에 액세스할 수 있어야 합니다.
  
- Active Directory 또는 Azure AD (Azure Active Directory) 인스턴스에 대 한 액세스 및 Microsoft Exchange 및 비즈니스용 Skype 서버에 대 한 액세스가 가능 합니다.
- DHCP를 사용 하 여 IP 주소를 제공할 수 있는 서버에 액세스 합니다. Microsoft 팀 대화방은 고정 IP 주소로 구성할 수 없습니다.
- HTTP 포트 80 및 443에 액세스 합니다.
- 온-프레미스 비즈니스용 Skype Server 구현에 대 한 [서버의 포트 및 프로토콜 요구 사항](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) 에 설명 된 대로 구성 되는 TCP 및 UDP 포트와 Microsoft 팀 또는 비즈니스용 skype online 구현에 대 한 [Office 365 url 및 IP 주소 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)

> [!IMPORTANT]
> 유선 1 Gbps 네트워크 연결을 사용 하 여 필요한 대역폭을 보유 하 고 있는지 확인 합니다.

> [!NOTE]
> Microsoft 팀 대화방의 소프트웨어 업데이트는 비즈니스용 Microsoft Store에서 자동으로 다운로드 됩니다. [Microsoft Store 비즈니스 에디션 및 학력에 대 한 필수 구성 요소](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 를 참조 하 여 채팅방 콘솔에서 스토어 및 자동 업데이트에 액세스할 수 있는지 확인 합니다.
  
### <a name="certificates"></a>인증

Microsoft 팀 대화방 장치는 Exchange Web Services, Microsoft 팀 또는 비즈니스용 Skype, 네트워크 사용량 및 인증에 대 한 인증서를 사용 합니다. 관련 서버에서 온라인 및 일부 온-프레미스 배포의 경우와 같은 공용 인증서를 사용 하는 경우에는 관리자가 인증서를 설치 하는 데 필요한 추가 작업을 수행 하지 않아야 합니다. 다른 한편 인증 기관이 개인 CA 인 경우 (온-프레미스 배포의 경우)에는 디바이스에서 CA + CA 체인 인증서가 장치에 설치 되어 있는 ca를 신뢰 해야 합니다. 도메인에 디바이스를 추가 하면이 작업이 자동으로 수행 될 수 있습니다.
  
다른 Windows 클라이언트를 사용할 때와 동일한 방식으로 인증서를 설치 합니다. 
  
> [!NOTE]
> Microsoft 팀 대화방에서 비즈니스용 Skype Server를 사용 하 게 하려면 인증서가 필요할 수 있습니다.
  
### <a name="proxy"></a>가상본

Microsoft 팀 대화방은 Windows OS에서 프록시 설정을 상속 하도록 디자인 되었습니다. 다음과 같은 방법으로 Windows OS에 액세스 합니다.
  
1. Microsoft 팀 대화방 UI에서 장치에 대 한 로컬 관리자 암호 (기본 암호는 **sfb**)를 묻는 메시지가 표시 되는 설정 기어 아이콘을 클릭 합니다.
2. 다음으로 **이동** 단추를 탭 하 고, **관리자** 로그인으로 이동 단추를 클릭 한 다음 **관리** 단추 (컴퓨터가 도메인에 가입 되어 있는 경우 **다른 사용자** 선택)를 누른 다음 사용자 이름으로 .\admin를 사용 하 여 **설정** 에 대해 살펴보겠습니다.
3. **Windows 검색** 상자 왼쪽 아래에서 regedit에 입력 합니다 (화면을 길게 누르거나 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행**을 선택 합니다.)
4. HKEY_USERS 폴더 (컴퓨터 사용자 Sid 목록이 표시 됨)를 클릭 하 여 루트 폴더 HKEY_USERS 선택 되어 있는지 확인 합니다.
       
5. 파일을 클릭 한 다음 **하이브 로드를 선택 합니다.**
6. **C:\Users\Skype** 폴더로 이동 하 고 파일 이름 상자 NTUSER를 입력 하 고 열기 단추를 누릅니다.

7. 새로 로드 된 하이브에 대 한 키 이름을 입력 하 라는 메시지가 표시 됩니다. Skype에 입력 하세요 (이제 Skype 사용자를 위한 레지스트리 설정을 볼 수 있습니다).
 
8. Skype 키를 열고 HKEY_USERS \Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet 설정을 찾아본 다음이 설정이 입력 되었는지 확인 합니다. 
    
    `[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]`
    
    `"MigrateProxy"=dword:00000001`
    
    `"ProxyEnable"=dword:00000001`
    
    `"ProxyServer"="xx.xx.xx.xx:8080"`
    
    ProxyServer가 없는 경우이 키를 문자열로 추가 해야 할 수 있습니다. xx: 8080을 프록시 서버의 ip/host 및 포트로 변경 하세요.
    
9. 변경 작업이 완료 되 면 Skype 사용자 키 (Skype의 루트 폴더)를 강조 표시 하 고 레지스트리 파일 메뉴에서 하이브 언로드를 선택 합니다 (확인 하 라는 메시지가 표시 됨- **예** 선택).
    
10. 이제 레지스트리 편집기를 닫고 Windows 검색 상자로 로그를 입력할 수 있습니다.
    
11. 로그인 화면으로 돌아와서 **Skype** 사용자를 선택 합니다. 앞의 모든 단계를 완료 한 경우 Microsoft 팀 대화방 장치에서 성공적으로 로그인 할 수 있습니다.
    
이 응용 프로그램을 사용 하려면 아래 설명 된 끝점에 연결할 수 있어야 합니다. IP 주소를 보려면 트래픽 흐름을 설명 하는 표 아래의 IP 주소 섹션을 확장 합니다.
  
**방화벽 프록시 호스트 이름/포트 예제**

|것|원본 또는 자격 증명|원본 포트|위치로|CDN|Office 365 용 Express 경로|대상 IP|대상 포트|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|인증 및 id  <br/> |[Office 365 인증 및 id를](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity) 참조 하세요. <br/> |||
|포털 및 공유  <br/> |[Office 365 포털 및 공유를](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity) 참조 하세요. <br/> |||
|SIP 신호  <br/> |클라이언트 컴퓨터 또는 로그온 한 사용자  <br/> |임시 포트  <br/> |\*contoso.com  <br/> |아니요  <br/> |예  <br/> |[비즈니스용 Skype IP 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|PSOM (영구 공유 개체 모델) 연결 웹 회의  <br/> |클라이언트 컴퓨터 또는 로그온 한 사용자  <br/> |임시 포트  <br/> |\*contoso.com  <br/> |아니요  <br/> |예  <br/> |[비즈니스용 Skype IP 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|HTTPS 다운로드  <br/> |클라이언트 컴퓨터 또는 로그온 한 사용자  <br/> |임시 포트  <br/> |\*contoso.com  <br/> |아니요  <br/> |예  <br/> |[비즈니스용 Skype IP 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|오디오  <br/> |클라이언트 컴퓨터 또는 로그온 한 사용자  <br/> |TCP/UDP 50000-50019  <br/> |\*contoso.com  <br/> |아니요  <br/> |예  <br/> |[비즈니스용 Skype IP 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50000-59999  <br/> |
|비디오만  <br/> |클라이언트 컴퓨터 또는 로그온 한 사용자  <br/> |TCP/UDP 50020-50039  <br/> |\*contoso.com  <br/> |아니요  <br/> |예  <br/> |[비즈니스용 Skype IP 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50000-59999  <br/> |
|데스크톱 공유  <br/> |클라이언트 컴퓨터 또는 로그온 한 사용자  <br/> |TCP/UDP 50040-50059  <br/> |\*contoso.com  <br/> |아니요  <br/> |예  <br/> |[비즈니스용 Skype IP 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, 50000-59999  <br/> |
|IOS 장치에서 Lync Mobile 2010에 대 한 lync Mobile 푸시 알림 Android, Nokia Symbian 또는 Windows Phone 모바일 장치에는 필요 하지 않습니다.  <br/> |클라이언트 컴퓨터 또는 로그온 한 사용자  <br/> |임시 포트  <br/> |\*contoso.com  <br/> |아니요  <br/> |예  <br/> |[비즈니스용 Skype IP 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Skype 원격 분석  <br/> |클라이언트 컴퓨터 또는 로그온 한 사용자  <br/> |임시 포트  <br/> |skypemaprdsitus.trafficmanager.net  <br/> pipe.skype.com  <br/> |아니요  <br/> |아니요  <br/> |해당 없음  <br/> |TCP 443  <br/> |
|Skype 클라이언트 퀵 팁  <br/> |클라이언트 컴퓨터 또는 로그온 한 사용자  <br/> |임시 포트  <br/> |quicktips.skypeforbusiness.com  <br/> |아니요  <br/> |아니요  <br/> |해당 없음  <br/> |TCP 443  <br/> |

> [!NOTE]
> Contoso.com 및 broadcast.skype.com의 와일드 카드는 Office 365에만 사용 되는 노드의 긴 목록을 나타냅니다. 
  
### <a name="create-provisioning-packages"></a>프로비저닝 패키지 만들기

배포 패키지를 사용 하 여 Exchange Server 또는 Office 365를 인증 합니다.
  
### <a name="admin-group-management"></a>관리 그룹 관리

도메인에 가입한 후 그룹 정책 또는 로컬 컴퓨터 관리를 사용 하 여 도메인의 Windows PC와 마찬가지로 보안 그룹을 로컬 관리자로 설정할 수 있습니다. 해당 보안 그룹의 구성원 인 모든 사용자는 자신의 자격 증명을 입력 하 고 설정을 해제할 수 있습니다.
  
> [!NOTE]
> Microsoft 팀 대화방 장치가 도메인에 대 한 신뢰를 상실 한 경우 (예를 들어 도메인에 가입한 후 도메인에서 Microsoft 팀 대화방을 제거 하는 경우)에는 디바이스에 인증 하 고 설정을 열 수 없게 됩니다. 해결 방법은 로컬 관리자 계정으로 로그인 하는 것입니다. 
  
## <a name="local-accounts"></a>로컬 계정

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft 팀 대화방 로컬 사용자 계정

일반적으로 장치 계정은 암호를 사용 하지 않습니다. 암호를 지정할 수 있지만 암호가 만료 될 때 사용자가 콘솔 응용 프로그램을 잠글 수 있다는 것을 포함 하 여 발생 하는 결과가 있습니다. 따라서 관리자는 암호가 만료 될 수 없도록 하는 것이 좋습니다.
  
### <a name="admin---local-administrator-account"></a>"관리자"-로컬 관리자 계정

Microsoft 팀 대화방 기본 암호는 "sfb"로 설정 됩니다. Windows 설정 \> 으로 이동 하 여 암호를 로컬에서 변경할 수 있습니다 (Windows 또는 AutoUnattend 파일에서 Windows 시스템 이미지 관리자를 사용 하 여 xml 파일을 변경 합니다.).
  
> [!CAUTION]
> Microsoft 팀 대화방 비밀 번호를 최대한 빨리 변경 하세요. 
  
또한 도메인 관리자가 로컬 관리자를 만드는 그룹 정책을 설정 하 여 로컬 관리자 암호를 관리할 수 있습니다.
  
설치 중에는 로컬 관리자 암호가 선택 사항으로 포함 되어 있지 않습니다.
  
### <a name="machine-account"></a>컴퓨터 계정

모든 Windows 디바이스와 마찬가지로 컴퓨터 이름의 이름을 바꾸려면 PC 이름 바꾸기에 대 한 \> \> 설정을 마우스 오른쪽 단추로 클릭 하면 됩니다.
  
 도메인에 가입한 후 컴퓨터 이름을 바꾸려면 컴퓨터 이름 바꾸기 명령 다음에 컴퓨터의 새 이름을 사용 합니다.
  
## <a name="see-also"></a>참고 항목

[Microsoft 팀 회의실 계획](skype-room-systems-v2-0.md)

[Microsoft 팀 방에 대 한 요구 사항](requirements.md)
  
[Microsoft 팀 대화방 배포](room-systems-v2.md)
  
[Microsoft 팀 대화방 콘솔 구성](console.md)
  
[Microsoft 팀 대화방 관리](skype-room-systems-v2.md)

[Microsoft Store 비즈니스 에디션 및 교육을 위한 필수 구성 요소](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 
