---
title: 비즈니스용 Skype 서버에서 2단계 인증 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: '요약: 비즈니스용 Skype 서버에서 2단계 인증을 관리합니다.'
ms.openlocfilehash: 415eb23779450bc09cdaa25ea2e60b6cf3526e40
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806546"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 2단계 인증 관리
 
**요약:** 비즈니스용 Skype 서버에서 2단계 인증을 관리합니다.
  
2단계 인증을 사용하면 사용자가 두 가지 형태의 인증 또는 ID, 즉 사용자 이름/암호 조합과 토큰 또는 인증서를 제공하도록 요구하여 보안을 향상할 수 있습니다. 이를 "있는 것, 알고 있는 것"이라고도 합니다. 
  
인증서를 사용하는 2단계 인증의 일반적인 예는 스마트 카드를 사용하는 것입니다. 스마트 카드에는 사용자 계정과 연결된 인증서가 포함되어 있으며 서버에 저장된 사용자 및 인증서 정보에 대해 유효성을 검사할 수 있습니다. 서버는 사용자 정보(사용자 이름 및 암호)를 제공된 인증서와 비교하여 자격 증명의 유효성을 검사하고 사용자를 인증합니다.
  
2단계 인증을 지원하도록 비즈니스용 Skype 서버 환경을 구성할 때 다음 주제를 고려하세요.
  
## <a name="client-support"></a>클라이언트 지원

Lync Server 2013용 누적 업데이트: 2013년 7월 데스크톱 클라이언트 및 비즈니스용 Skype 클라이언트는 현재 2단계 인증을 지원하는 유일한 클라이언트입니다.
  
## <a name="topology-requirements"></a>토폴로지 요구 사항

고객은 에지, Director 및 사용자 풀이 있는 전용 비즈니스용 Skype 서버를 사용하여 2단계 인증을 배포하는 것이 좋습니다. 사용자에 대해 수동 인증을 사용하도록 설정하려면 다음을 비롯한 다른 역할 및 서비스에 대해 다른 인증 방법을 사용하지 않도록 설정해야 합니다.
  
|**구성 유형**|**서비스 종류**|**서버 역할**|**사용하지 않도록 설정할 인증 유형**|
|:-----|:-----|:-----|:-----|
|웹 서비스  <br/> |WebServer  <br/> |이사  <br/> |Kerberos, NTLM 및 인증서  <br/> |
|웹 서비스  <br/> |WebServer  <br/> |프런트 엔드  <br/> |Kerberos, NTLM 및 인증서  <br/> |
|프록시  <br/> |EdgeServer  <br/> |Edge  <br/> |Kerberos 및 NTLM  <br/> |
|프록시  <br/> |등록자  <br/> |프런트 엔드  <br/> |Kerberos 및 NTLM  <br/> |
   
서비스 수준에서 이러한 인증 유형을 사용하지 않도록 설정하지 않으면 배포 내에서 2단계 인증을 사용하도록 설정하면 다른 모든 버전의 클라이언트가 성공적으로 로그인할 수 없습니다.
  
## <a name="skype-for-business-service-discovery"></a>비즈니스용 Skype 서비스 검색

내부 및/또는 외부 클라이언트가 비즈니스용 Skype 서비스를 검색하는 데 사용하는 DNS 레코드는 2단계 인증을 사용할 수 없는 비즈니스용 Skype 서버로 확인하도록 구성해야 합니다. 이 구성에서는 2단계 인증을 사용하도록 설정되지 않은 비즈니스용 Skype 풀의 사용자가 인증을 위해 PIN을 입력할 필요는 없는 반면, 2단계 인증을 사용하도록 설정된 비즈니스용 Skype 풀의 사용자는 인증을 위해 PIN을 입력해야 합니다.
  
## <a name="exchange-authentication"></a>Exchange 인증

Microsoft Exchange에 대해 2단계 인증을 배포한 고객은 클라이언트의 특정 기능을 사용할 수 없음을 찾을 수 있습니다. 이는 현재 비즈니스용 Skype 클라이언트가 Exchange 통합에 종속된 기능에 대해 2단계 인증을 지원하지 않습니다.
  
## <a name="contacts"></a>연락처

통합 연락처 저장소 기능을 활용하도록 구성된 비즈니스용 Skype 사용자는 2단계 인증을 사용하여 로그인한 후 해당 연락처를 더 이상 사용할 수 없습니다.
  
**Invoke-CsUcsRollback** cmdlet을 사용하여 2단계 인증을 사용하도록 설정하기 전에 통합 연락처 저장소에서 기존 사용자 연락처를 제거하고 비즈니스용 Skype 서버에 저장해야 합니다.
  
## <a name="skill-search"></a>기술 검색

비즈니스용 Skype 환경에서 기술 검색 기능을 구성한 고객은 비즈니스용 Skype가 2단계 인증을 사용하도록 설정되어 있는 경우 이 기능이 작동하지 않는다는 것을 발견할 수 있습니다. 이는 Microsoft SharePoint가 현재 2단계 인증을 지원하지 않습니다.
  
## <a name="credentials"></a>자격 증명

저장된 비즈니스용 Skype 자격 증명과 관련된 배포 고려 사항은 2단계 인증을 사용하도록 구성된 사용자에게 영향을 줄 수 있습니다.
  
### <a name="deleting-saved-credentials"></a>저장된 자격 증명 삭제

사용자는 2단계 인증을 사용하여 처음으로 로그인하기 전에 비즈니스용 Skype 클라이언트에서 내 로그인 정보 삭제 옵션을 사용하고 %localappdata%\Microsoft\Office\15.0\비즈니스용 Skype에서 SIP 프로필 폴더를 삭제해야 합니다. 
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Kerberos 또는 NTLM 인증 방법을 사용하는 경우 사용자의 Windows 자격 증명이 인증에 자동으로 사용됩니다. Kerberos 및/또는 NTLM이 인증을 사용하도록 설정된 일반적인 비즈니스용 Skype 서버 배포에서는 사용자가 로그인할 때마다 자격 증명을 입력할 필요가 없습니다.
  
사용자에게 PIN을 입력하라는 메시지가 표시되기 전에 사용자에게 자격 증명을 입력하라는 메시지가 표시되면 **DisableNTCredentials** 레지스트리 키가 클라이언트 컴퓨터에서 그룹 정책을 통해 의도하지 않은 것으로 구성될 수 있습니다.
  
자격 증명에 대한 추가 메시지가 표시되지 않도록 설정하기 위해 로컬 작업소에서 다음 레지스트리 항목을 만들거나 비즈니스용 Skype 관리 템플릿을 사용하여 그룹 정책을 사용하여 특정 풀의 모든 사용자에게 적용합니다.
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

사용자가 처음으로 비즈니스용 Skype에 로그인하면 암호를 저장하라는 메시지가 사용자에게 표시됩니다. 이 옵션을 선택하면 사용자의 클라이언트 인증서를 개인 인증서 저장소에 저장하고 사용자의 Windows 자격 증명을 로컬 컴퓨터의 자격 증명 관리자에 저장할 수 있습니다.
  
비즈니스용 Skype가 2단계 인증을 지원하도록 구성된 경우 **SavePassword** 레지스트리 설정을 사용하지 않도록 설정해야 합니다. 사용자가 암호를 저장하지 못하게 설정하기 위해 로컬 작업소에서 다음 레지스트리 항목을 변경하거나 비즈니스용 Skype 관리 템플릿을 사용하여 그룹 정책을 사용하여 특정 풀의 모든 사용자에게 적용합니다.
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 토큰 재생

AD FS 2.0은 토큰 재생 검색이라고 하는 기능을 제공합니다. 이 기능을 통해 동일한 토큰을 사용하는 여러 토큰 요청을 검색한 다음 삭제합니다. 이 기능을 사용하는 경우 토큰 재생 검색은 동일한 토큰이 두 번 이상 사용되지 않는지 확인하여 WS-Federation 수동 프로필과 SAML WebSSO 프로필 둘 다에서 인증 요청의 무결성을 보호합니다.
  
키오스크를 사용하는 경우와 같이 보안이 매우 중요한 상황에서 이 기능을 사용하도록 설정해야 합니다. 토큰 재생 검색에 대한 자세한 내용은 [AD FS 2.0의](https://go.microsoft.com/fwlink/p/?LinkId=309215)보안 계획 및 배포 모범 사례를 참조하세요.
  
## <a name="external-user-access"></a>외부 사용자 액세스

외부 네트워크에서 비즈니스용 Skype 2단계 인증을 지원하도록 ADFS 프록시 또는 역방향 프록시를 구성하는 방법은 이 항목에서 다루지 않습니다.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 2단계 인증 구성](configure-two-factor.md)
  
