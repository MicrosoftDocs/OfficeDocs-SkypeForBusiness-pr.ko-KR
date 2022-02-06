---
title: 2단계 인증을 비즈니스용 Skype 서버
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: '요약: 2단계 인증을 관리하기 비즈니스용 Skype 서버.'
---

# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>2단계 인증을 비즈니스용 Skype 서버
 
**요약:** 2단계 인증을 관리하여 비즈니스용 Skype 서버.
  
2단계 인증은 사용자가 사용자 이름/암호 조합과 토큰 또는 인증서의 두 가지 인증 또는 ID 형식을 제공하도록 요구하여 보안을 향상합니다. 이를 "있는 것, 알고 있는 것"이라고도 합니다. 
  
인증서를 사용하는 2단계 인증의 일반적인 예로는 스마트 카드를 사용하는 것이 있습니다. 스마트 카드는 사용자 계정과 연결된 인증서를 포함하며 서버에 저장된 사용자 및 인증서 정보에 대해 유효성을 검사할 수 있습니다. 서버는 사용자 정보(사용자 이름 및 암호)를 제공된 인증서와 비교하여 자격 증명의 유효성을 검사하고 사용자를 인증합니다.
  
2단계 인증을 지원하도록 비즈니스용 Skype 서버 구성할 때 다음 주제를 고려합니다.
  
## <a name="client-support"></a>클라이언트 지원

Lync Server 2013: 2013년 7월 데스크톱 클라이언트 및 비즈니스용 Skype 클라이언트용 누적 업데이트는 현재 2단계 인증을 지원하는 유일한 클라이언트입니다.
  
## <a name="topology-requirements"></a>토폴로지 요구 사항

고객은 에지, Director 및 사용자 풀과 함께 전용 비즈니스용 Skype 서버 2단계 인증을 배포하는 것이 좋습니다. 사용자에 대해 수동 인증을 사용하도록 설정하려면 다음을 비롯한 다른 역할 및 서비스에 대해 다른 인증 방법을 사용하지 않도록 설정해야 합니다.
  
|**구성 유형**|**서비스 종류**|**서버 역할**|**사용하지 않도록 설정할 인증 유형**|
|:-----|:-----|:-----|:-----|
|웹 서비스  <br/> |WebServer  <br/> |이사  <br/> |Kerberos, NTLM 및 인증서  <br/> |
|웹 서비스  <br/> |WebServer  <br/> |프런트 엔드  <br/> |Kerberos, NTLM 및 인증서  <br/> |
|프록시  <br/> |EdgeServer  <br/> |Edge  <br/> |Kerberos 및 NTLM  <br/> |
|프록시  <br/> |등록자  <br/> |프런트 엔드  <br/> |Kerberos 및 NTLM  <br/> |
   
서비스 수준에서 이러한 인증 유형을 사용하지 않도록 설정하지 않은 경우 배포 내에서 2단계 인증을 사용하도록 설정한 경우 다른 모든 버전의 클라이언트는 성공적으로 로그인할 수 없습니다.
  
## <a name="skype-for-business-service-discovery"></a>비즈니스용 Skype 서비스 검색

내부 및/또는 외부 클라이언트가 비즈니스용 Skype 서비스를 검색하는 데 사용하는 DNS 레코드는 2단계 인증을 사용할 수 없는 비즈니스용 Skype 서버로 확인하도록 구성해야 합니다. 이 구성을 사용하면 비즈니스용 Skype 인증을 사용하도록 설정되지 않은 비즈니스용 Skype 풀의 사용자는 인증을 위해 PIN을 입력할 필요는 없습니다. 그러나 2단계 인증을 사용하도록 설정된 비즈니스용 Skype 풀의 사용자는 인증을 위해 PIN을 입력해야 합니다.
  
## <a name="exchange-authentication"></a>Exchange 인증

Microsoft 2단계 인증을 배포한 Exchange 클라이언트의 특정 기능을 사용할 수 없는 경우도 있습니다. 이 동작은 비즈니스용 Skype 클라이언트가 통합에 종속된 기능에 대해 2단계 인증을 Exchange 않습니다.
  
## <a name="contacts"></a>Contacts

비즈니스용 Skype 저장소 기능을 활용하도록 구성된 사용자는 2단계 인증을 사용하여 로그인한 후 해당 연락처를 더 이상 사용할 수 없습니다.
  
**Invoke-CsUcsRollback** cmdlet을 사용하여 통합 연락처 저장소에서 기존 사용자 연락처를 제거하고 비즈니스용 Skype 서버 2단계 인증을 사용하도록 설정해야 합니다.
  
## <a name="skill-search"></a>기술 검색

비즈니스용 Skype 환경에서 기술 검색 기능을 구성한 고객은 2단계 인증을 사용하도록 설정한 비즈니스용 Skype 기능이 작동하지 않는다는 것을 발견할 수 있습니다. 이는 기본적으로 Microsoft SharePoint 2단계 인증을 지원하지 않습니다.
  
## <a name="credentials"></a>자격 증명

2단계 인증을 사용하도록 구성된 사용자에게 영향을 줄 수 있는 저장된 비즈니스용 Skype 자격 증명과 관련된 배포 고려 사항이 여러 가지 있습니다.
  
### <a name="deleting-saved-credentials"></a>저장된 자격 증명 삭제

2단계 인증을  사용하여 처음으로 로그인을 시도하기 전에 비즈니스용 Skype 클라이언트에서 내 로그인 정보 삭제 옵션을 사용하고 %localappdata%\Microsoft\Office\15.0\비즈니스용 Skype %localappdata%\Microsoft\Office\15.0\비즈니스용 Skype에서 SIP 프로필 폴더를 삭제해야 합니다.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Kerberos 또는 NTLM 인증 방법을 사용하는 경우 사용자의 Windows 자격 증명이 인증에 자동으로 사용됩니다. 인증에 비즈니스용 Skype 서버 Kerberos 및/또는 NTLM을 사용하도록 설정하는 일반적인 사용자 배포에서는 사용자가 로그인할 때마다 자격 증명을 입력할 필요가 없습니다.
  
사용자에게 PIN을 입력하라는 메시지가 표시되기 전에 사용자에게 자격 증명을 입력하라는 메시지가 표시되면 그룹 정책을 통해 클라이언트 컴퓨터에서 **DisableNTCredentials** 레지스트리 키가 의도하지 않은 것으로 구성될 수 있습니다.
  
자격 증명에 대한 추가 메시지가 표시되지 않도록 설정하기 위해 로컬 workstation에서 다음 레지스트리 항목을 만들거나 비즈니스용 Skype 관리 템플릿을 사용하여 그룹 정책을 사용하여 특정 풀의 모든 사용자에게 적용할 수 있습니다.
  
HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
REG_DWORD: DisableNTCredentials

값: 0x0
  
### <a name="savepassword"></a>SavePassword

사용자가 처음으로 비즈니스용 Skype 로그인하면 암호를 저장하라는 메시지가 사용자에게 표시됩니다. 이 옵션을 선택하면 사용자의 클라이언트 인증서를 개인 인증서 저장소에 저장하고 사용자의 Windows 자격 증명을 로컬 컴퓨터의 자격 증명 관리자에 저장할 수 있습니다.
  
2단계 인증을 지원하도록 구성된 비즈니스용 Skype **SavePassword** 레지스트리 설정을 사용하지 않도록 설정해야 합니다. 사용자가 암호를 저장하지 못하게 만들 수 있도록 로컬 workstation에서 다음 레지스트리 항목을 변경하거나 비즈니스용 Skype 관리 템플릿을 사용하여 그룹 정책을 사용하여 특정 풀의 모든 사용자에게 적용할 수 있습니다.
  
HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
REG_DWORD: SavePassword
  
값: 0x0
  
## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 토큰 재생

AD FS 2.0은 토큰 재생 검색이라고 하는 기능을 제공합니다. 이 기능을 통해 동일한 토큰을 사용하는 여러 토큰 요청을 검색한 다음 삭제합니다. 이 기능을 사용하도록 설정하면 토큰 재생 검색은 동일한 토큰이 두 번 이상 사용되지 않는지 확인하여 WS-Federation 수동 프로필과 SAML WebSSO 프로필 모두에서 인증 요청의 무결성을 보호합니다.
  
키오스크를 사용하는 경우와 같이 보안이 매우 중요한 상황에서 이 기능을 사용하도록 설정해야 합니다. 토큰 재생 검색에 대한 자세한 내용은 [Best Practices for Secure Planning and Deployment of AD FS 2.0를 참조하십시오](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff630160(v=ws.10)).
  
## <a name="guest-user-access"></a>게스트 사용자 액세스

외부 네트워크에서 2단계 인증을 비즈니스용 Skype 지원하도록 ADFS 프록시 또는 역방향 프록시를 구성하는 방법은 이 항목에서 다루지 않습니다.
  
## <a name="see-also"></a>참고 항목

[2단계 인증을 구성합니다비즈니스용 Skype 서버](configure-two-factor.md)
