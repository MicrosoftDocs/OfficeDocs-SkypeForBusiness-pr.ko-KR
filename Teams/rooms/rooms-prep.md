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
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: 모든 기능을 활용할 수 있도록 Microsoft Teams 회의실을 배포하기 위한 인프라를 준비하는 방법에 대해 자세히 배워야 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d0c5d5a1b0333a30b7730d6c8b91d06e67e291b4
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662433"
---
# <a name="prepare-your-environment"></a>작업 환경 준비

이 섹션에는 Microsoft Teams 회의실의 모든 기능을 사용할 수 있도록 환경을 준비하는 데 필요한 단계의 개요가 포함되어 있습니다.
  
1. 각 Microsoft Teams 회의실 콘솔에 대한 장치 계정을 준비합니다. 자세한 [내용은 Microsoft Teams 회의실 배포를](rooms-deploy.md) 참조합니다.
    
2. 사용할 디바이스에 대한 네트워크/인터넷 연결이 작동하고 있는지 확인합니다. 
    
   - DHCP를 사용하여 IP 주소를 받을 수 있어야 합니다. (Microsoft Teams 회의실은 첫 번째 단위 시작 시 고정 IP 주소로 구성할 수 없지만, 이후 디바이스의 고정 IP는 디바이스 또는 업스트림 스위치 또는 라우터에서 구성할 수 있습니다.)
   - 미디어에 대한 일반 포트를 여는 것 외에도 이러한 포트가 열려 있어야 합니다.
   - HTTPS: 443
   - HTTP: 80
   - 네트워크가 프록시를 통해 실행되는 경우 프록시 주소 또는 스크립트 정보도 필요합니다.
    
     > [!IMPORTANT]
     > Microsoft Teams 회의실은 프록시 인증을 지원하지 않습니다. 이 경우 회의실의 정기적인 운영에 방해가 될 수 있습니다. 프로덕션에 들어가기 전에 Microsoft Teams 회의실이 프록시 인증에서 제외되어야 합니다.
  
3. 환경을 개선하기 위해 Microsoft는 데이터를 수집합니다. Microsoft에서 데이터를 수집할 수 있도록 허용하기 위해 다음 사이트를 허용합니다.

   - 원격 분석 클라이언트 엔드포인트: https://vortex.data.microsoft.com/
   - 원격 분석 설정 엔드포인트: https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>디바이스 계정 만들기 및 테스트

장치  *계정은*  Microsoft Teams 회의실 클라이언트가 일정과 같은 Exchange의 기능에 액세스하고 비즈니스용 Skype를 사용하도록 설정하는 데 사용하는 계정입니다. 자세한 [내용은 Microsoft Teams 회의실 배포를](rooms-deploy.md) 참조합니다.
  
### <a name="check-network-availability"></a>네트워크 가용성 확인

제대로 작동하려면 Microsoft Teams 회의실 디바이스에서 다음 요구 사항을 충족하는 유선 네트워크에 액세스할 수 있어야 합니다.
  
- Active Directory 또는 Azure AD(Azure Active Directory) 인스턴스뿐만 아니라 Microsoft Exchange 및 비즈니스용 Skype 서버에 액세스할 수 있습니다.
- DHCP를 사용하여 IP 주소를 제공할 수 있는 서버에 액세스합니다. Microsoft Teams 회의실은 첫 번째 단위 시작 시 고정 IP 주소로 구성할 수 없습니다.
- HTTP 포트 80 및 443에 액세스합니다.
- TCP 및 UDP 포트는 Microsoft [](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) Teams 또는 비즈니스용 Skype 온라인 구현을 위한 Microsoft [365 및 Office 365 URL](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) 및 IP 주소 범위를 위한 포트 및 프로토콜 요구 사항에 설명되어 있습니다.

> [!IMPORTANT]
> 필요한 대역폭을 보장하려면 유선 1Gbps 네트워크 연결을 사용합니다.

> [!NOTE]
> Microsoft Teams 회의실에 대한 소프트웨어 업데이트는 비즈니스용 Microsoft Store에서 자동으로 다운로드됩니다. 비즈니스 및 교육용 [Microsoft Store의](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 전제적 준비를 참조하여 방 콘솔이 스토어에 액세스하고 셀프 업데이트할 수 있는지 확인합니다.
  
### <a name="certificates"></a>인증서

Microsoft Teams 회의실 디바이스는 Exchange Web Services, Microsoft Teams 또는 비즈니스용 Skype, 네트워크 사용 및 인증에 대한 인증서를 사용합니다. 관련 서버가 공용 인증서(온라인 및 일부 On-Premises 배포의 경우)를 사용하는 경우 관리자의 일부에서 인증서를 설치하기 위해 추가 작업이 필요하지 않습니다. 반면에 인증 기관이 개인 CA(일반적으로 On-프레미스 배포)인 경우 디바이스는 CA + CA 체인 인증서가 디바이스에 설치되어 있는 CA를 신뢰해야 합니다. 도메인에 디바이스를 추가하면 이 작업이 자동으로 수행될 수 있습니다.
  
다른 Windows 클라이언트와 동일한 방식으로 인증서를 설치합니다. 
  
> [!NOTE]
> Microsoft Teams 회의실에서 비즈니스용 Skype 서버를 사용하려면 인증서가 필요할 수 있습니다.
  
### <a name="proxy"></a>프록시

Microsoft Teams 회의실은 Windows OS에서 프록시 설정을 상속하도록 디자인되어 있습니다. 다음과 같은 방식으로 Windows OS에 액세스합니다.
  
1. Microsoft Teams 회의실 UI에서 설정 기어 아이콘을 클릭하면 디바이스에서 로컬 관리자 암호를 묻는 메시지가 표시됩니다(기본 암호는 **sfb임).**
2. 설정을 **탭한** 다음 **Windows로** 이동 단추를 탭한 다음 관리자 로그인 단추로 이동 단추를  탭한 다음 관리자 단추를  클릭합니다(컴퓨터가 도메인에 가입되어 있는 경우 다른 사용자를 선택한 다음 .\admin을 사용자 이름으로 사용). 
3. Windows **검색** 상자의 왼쪽 아래에서 regedit를 입력합니다(화면을 길게 누르거나 마우스 오른쪽 단추로 클릭하고 관리자 권한으로 실행 **선택).**
4. HKEY_USERS 폴더(컴퓨터 사용자 SID 목록이 표시)를 클릭하여 루트 폴더가 선택되어 HKEY_USERS 확인합니다.
       
5. 파일을 클릭한 다음 **Hive 로드를 클릭합니다.**
6. **C:\Users\Skype** 폴더를 찾아 파일 이름 상자 NTUSER.dat에 입력하고 열기 단추를 누릅니다.

7. 새로 로드한 Hive에 대한 키 이름을 묻는 메시지가 표시됩니다. Skype를 입력합니다(이제 Skype 사용자의 레지스트리 설정이 표시됩니다).
 
8. Skype 키를 열고 다음 HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings 다음 설정을 입력해야 합니다. 
    
    `[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]`
    
    `"MigrateProxy"=dword:00000001`
    
    `"ProxyEnable"=dword:00000001`
    
    `"ProxyServer"="xx.xx.xx.xx:8080"`
    
    ProxyServer가 없는 경우 이 키를 문자열로 추가해야 할 수 있습니다. xx.xx.xx.xx:8080을 프록시 서버의 ip/호스트 및 포트로 변경합니다.
    
9. 변경이 완료되면 Skype 사용자 키(Skype의 루트 폴더)를 강조 표시하고 레지스트리 파일 메뉴에서 Hive 언로드를 선택합니다(확인 메시지가 표시됩니다. 예 **선택).**
    
10. 이제 레지스트리 편집기를 닫고 Windows 검색 상자에 로고프를 입력할 수 있습니다.
    
11. 로그인 화면으로 **돌아가서 Skype 사용자를** 선택하세요. 이전 단계가 모두 성공하면 Microsoft Teams 회의실 디바이스가 성공적으로 로그인됩니다.
    
이 애플리케이션을 사용하려면 아래에 설명된 엔드포인트에 연결할 수 있어야 합니다. IP 주소를 표시하기 위해 트래픽 흐름을 설명하는 표 아래의 IP 주소 섹션을 확장합니다.
  
**방화벽 프록시 호스트 이름/포트 예제**

|목적|원본 또는 자격 증명|원본 포트|대상|CDN|Office 365용 ExpressRoute|대상 IP|대상 포트|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|인증 및 ID  <br/> |[Microsoft 365 및 Office 365 인증 및 ID 참조](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity) <br/> |||
|포털 및 공유  <br/> |[Microsoft 365 관리 센터 및 공유 보기](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity) <br/> |||
|SIP 신호  <br/> |클라이언트 컴퓨터 또는 로그온한 사용자  <br/> |사용 후 사용 후 사용 후 포트  <br/> |\*.contoso.com  <br/> |아니요  <br/> |예  <br/> |[비즈니스용 Skype IP 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|PSOM(영구 공유 개체 모델) 연결 웹 회의  <br/> |클라이언트 컴퓨터 또는 로그온한 사용자  <br/> |사용 후 사용 후 사용 후 포트  <br/> |\*.contoso.com  <br/> |아니요  <br/> |예  <br/> |[비즈니스용 Skype IP 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|HTTPS 다운로드  <br/> |클라이언트 컴퓨터 또는 로그온한 사용자  <br/> |사용 후 사용 후 사용 후 포트  <br/> |\*.contoso.com  <br/> |아니요  <br/> |예  <br/> |[비즈니스용 Skype IP 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|오디오  <br/> |클라이언트 컴퓨터 또는 로그온한 사용자  <br/> |TCP/UDP 50,000-50019  <br/> |\*.contoso.com  <br/> |아니요  <br/> |예  <br/> |[비즈니스용 Skype IP 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50,000-59,999  <br/> |
|비디오  <br/> |클라이언트 컴퓨터 또는 로그온한 사용자  <br/> |TCP/UDP 50,020-50039  <br/> |\*.contoso.com  <br/> |아니요  <br/> |예  <br/> |[비즈니스용 Skype IP 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50,000-59,999  <br/> |
|데스크톱 공유  <br/> |클라이언트 컴퓨터 또는 로그온한 사용자  <br/> |TCP/UDP 50,040-50059  <br/> |\*.contoso.com  <br/> |아니요  <br/> |예  <br/> |[비즈니스용 Skype IP 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, 50,000-59,999  <br/> |
|iOS 장치에서 Lync Mobile 2010에 대한 Lync Mobile 푸시 알림 Android, Nokia Symbian 또는 Windows Phone 모바일 장치에는 필요하지 않습니다.  <br/> |클라이언트 컴퓨터 또는 로그온한 사용자  <br/> |사용 후 사용 후 사용 후 포트  <br/> |\*.contoso.com  <br/> |아니요  <br/> |예  <br/> |[비즈니스용 Skype IP 범위](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Skype 원격 분석  <br/> |클라이언트 컴퓨터 또는 로그온한 사용자  <br/> |사용 후 사용 후 사용 후 포트  <br/> |skypemaprdsitus.trafficmanager.net  <br/> pipe.skype.com  <br/> |아니요  <br/> |아니요  <br/> |해당 없음  <br/> |TCP 443  <br/> |
|Skype 클라이언트 빠른 팁  <br/> |클라이언트 컴퓨터 또는 로그온한 사용자  <br/> |사용 후 사용 후 사용 후 포트  <br/> |quicktips.skypeforbusiness.com  <br/> |아니요  <br/> |아니요  <br/> |해당 없음  <br/> |TCP 443  <br/> |

> [!NOTE]
> Contoso.com 및 broadcast.skype.com 와일드카드는 Microsoft 365 또는 Office 365에 독점적으로 사용되는 긴 노드 목록을 나타났습니다. 
  
### <a name="create-provisioning-packages"></a>프로비전 패키지 만들기

프로비전 패키지를 사용하여 Exchange Server, Microsoft 365 또는 Office 365에 인증합니다.
  
### <a name="admin-group-management"></a>관리 그룹 관리

도메인에 가입한 후 도메인의 Windows PC와 마찬가지로 그룹 정책 또는 로컬 컴퓨터 관리를 사용하여 보안 그룹을 로컬 관리자로 설정할 수 있습니다. 보안 그룹의 구성원인 모든 사람이 자격 증명을 입력하고 설정을 잠금 해제할 수 있습니다.
  
> [!NOTE]
> Microsoft Teams Rooms 장치가 도메인과 신뢰를 잃는 경우(예: 도메인에 가입된 후 도메인에서 Microsoft Teams 회의실을 제거하는 경우) 디바이스에 인증하고 설정을 열 수 없습니다. 해결 해결은 로컬 관리자 계정으로 로그인하는 것입니다. 
  
## <a name="local-accounts"></a>로컬 계정

### <a name="microsoft-teams-rooms-local-user-account"></a>Microsoft Teams 회의실 로컬 사용자 계정

디바이스 계정은 일반적으로 암호를 사용하지 않습니다. 암호를 입력할 수 있지만 해당 암호가 만료될 때 사용자가 콘솔 애플리케이션에서 잠글 수 있는 가능성을 포함하여 결과가 있습니다. 따라서 관리자는 암호가 만료되지 않도록 해야 합니다.
  
### <a name="admin---local-administrator-account"></a>"관리자" - 로컬 관리자 계정

Microsoft Teams 회의실 기본 암호는 "sfb"로 설정됩니다. 암호는 Windows 설정 Windows로 이동하거나 AutoUnattend.xml 파일에서 로컬로 변경할 수 있습니다(ADK의 Windows 시스템 이미지 관리자를 사용하여 xml 파일을 \> 변경).
  
> [!CAUTION]
> 최대한 빨리 Microsoft Teams 회의실 암호를 변경해야 합니다. 
  
도메인 관리자가 로컬 관리자로 지정되는 그룹 정책을 설정하여 로컬 관리자 암호를 관리할 수도 있습니다.
  
로컬 관리자 암호는 설치 중에 선택으로 포함되지 않습니다.
  
### <a name="machine-account"></a>컴퓨터 계정

Windows 디바이스와 마찬가지로 PC 이름 변경에 대한 설정을 마우스 오른쪽 단추로 클릭하여 컴퓨터 이름을 변경할 \> \> 수 있습니다.
  
 도메인에 가입한 후 컴퓨터의 이름을 변경하려면 Rename-Computer PowerShell 명령 다음에 컴퓨터의 새 이름을 사용 합니다.
  
## <a name="related-topics"></a>관련 항목

[Microsoft Teams 회의실 계획](rooms-plan.md)

[Microsoft Teams 룸 요구사항](requirements.md)
  
[Microsoft Teams 룸 배포](rooms-deploy.md)
  
[Microsoft Teams 룸 콘솔 구성](console.md)
  
[Microsoft Teams 룸 관리](rooms-manage.md)

[비즈니스 및 교육용 Microsoft Store에 대한 전제적 준비](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 
