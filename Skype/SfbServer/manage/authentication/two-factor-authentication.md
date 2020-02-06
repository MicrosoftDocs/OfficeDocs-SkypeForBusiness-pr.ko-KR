---
title: 비즈니스용 Skype 서버에서 2 단계 인증 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: '요약: 비즈니스용 Skype 서버에서 2 단계 인증을 관리 합니다.'
ms.openlocfilehash: 90dc286e247c0c6eeb75bb884071b85e57663278
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818720"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 2 단계 인증 관리
 
**요약:** 비즈니스용 Skype 서버에서 2 단계 인증을 관리 합니다.
  
2 단계 인증은 사용자에 게 두 가지 형태의 인증 또는 자격 증명을 제공 하도록 요구 하는 보안 강화 기능을 제공 합니다. 이것을 "보유 하 고 있는 물건" 이라고 하는 것이 라고도 합니다. 
  
인증서를 사용 하는 2 단계 인증의 일반적인 예는 스마트 카드를 사용 하는 것입니다. 스마트 카드에는 사용자 계정과 연결 된 인증서가 포함 되며, 서버에 저장 된 사용자 및 인증서 정보에 대해 유효성을 검사할 수 있습니다. 제공 된 인증서와 사용자 정보 (사용자 이름 및 암호)를 비교 하 여 서버는 자격 증명의 유효성을 검사 하 고 사용자를 인증 합니다.
  
2 단계 인증을 지원 하도록 비즈니스용 Skype 서버 환경을 구성할 때 다음 주제를 고려 하세요.
  
## <a name="client-support"></a>클라이언트 지원

Lync Server 2013의 누적 업데이트: 7 월 2013 데스크톱 클라이언트와 비즈니스용 Skype 클라이언트는 현재 2 단계 인증을 지 원하는 클라이언트입니다.
  
## <a name="topology-requirements"></a>토폴로지 요구 사항

고객은 Edge, 디렉터 및 사용자 풀이 있는 비즈니스용 Skype 서버를 사용 하 여 2 단계 인증을 배포 하는 것이 좋습니다. 사용자에 게 수동 인증을 사용 하도록 설정 하려면 다음을 포함 하 여 다른 역할 및 서비스에 대해 다른 인증 방법을 사용 하지 않도록 설정 해야 합니다.
  
|**구성 형식**|**서비스 종류**|**서버 역할**|**사용할 수 없도록 설정 하는 인증 유형**|
|:-----|:-----|:-----|:-----|
|웹 서비스  <br/> |되었는지  <br/> |Director  <br/> |Kerberos, NTLM, 인증서  <br/> |
|웹 서비스  <br/> |되었는지  <br/> |프론트 엔드  <br/> |Kerberos, NTLM, 인증서  <br/> |
|가상본  <br/> |EdgeServer  <br/> |쪽  <br/> |Kerberos 및 NTLM  <br/> |
|가상본  <br/> |레지스터  <br/> |프론트 엔드  <br/> |Kerberos 및 NTLM  <br/> |
   
이러한 인증 유형을 서비스 수준에서 사용 하지 않도록 설정 하지 않는 한, 다른 모든 버전의 클라이언트는 배포 내에서 2 단계 인증을 사용 하도록 설정한 후에도 성공적으로 로그인 할 수 없습니다.
  
## <a name="skype-for-business-service-discovery"></a>비즈니스용 Skype 서비스 검색

내부 및/또는 외부 클라이언트가 비즈니스용 Skype 서비스를 검색 하는 데 사용 하는 DNS 레코드는 2 단계 인증을 사용 하도록 설정 되지 않은 비즈니스용 Skype 서버를 확인 하도록 구성 되어야 합니다. 이 구성을 사용 하는 경우, 2 단계 인증을 사용 하도록 설정 되지 않은 비즈니스용 Skype 풀의 사용자는 인증에 PIN을 입력 하는 데 필요 하지 않으며, 2 단계 인증을 사용 하도록 설정 된 비즈니스용 Skype 풀의 사용자는 인증을 위해 PIN을 입력 해야 합니다.
  
## <a name="exchange-authentication"></a>Exchange 인증

Microsoft Exchange에 대해 2 단계 인증을 배포한 고객은 클라이언트의 특정 기능을 사용할 수 없는 경우가 있습니다. 이는 비즈니스용 Skype 클라이언트가 Exchange 통합에 의존 하는 기능에 대 한 2 단계 인증을 지원 하지 않기 때문에 현재 의도적으로 설계 된 것입니다.
  
## <a name="contacts"></a>연락처

통합 된 대화 상대 저장소 기능을 활용 하도록 구성 된 비즈니스용 Skype 사용자는 2 단계 인증을 사용 하 여 로그인 한 후 해당 대화 상대를 더 이상 사용할 수 없다는 것을 알게 됩니다.
  
2 단계 인증을 사용 하도록 설정 하기 전에 **CsUcsRollback** cmdlet을 사용 하 여 통합 된 연락처 저장소에서 기존 사용자 연락처를 제거 하 고 비즈니스용 Skype 서버에 저장 해야 합니다.
  
## <a name="skill-search"></a>기술 검색

비즈니스용 skype 환경에서 기술 검색 기능을 구성한 고객은 비즈니스용 Skype가 2 단계 인증을 사용 하도록 설정 되어 있는 경우에는이 기능이 작동 하지 않는다는 것을 알게 됩니다. 이것은 Microsoft SharePoint가 현재 2 단계 인증을 지원 하지 않기 때문에 의도적으로 설계 된 것입니다.
  
## <a name="credentials"></a>증명과

2 단계 인증을 사용 하도록 구성 된 사용자에 게 영향을 줄 수 있는 비즈니스용 Skype 자격 증명과 관련 된 다양 한 배포 고려 사항이 있습니다.
  
### <a name="deleting-saved-credentials"></a>저장 된 자격 증명 삭제

2 단계 인증을 사용 하 여 처음으로 로그인 하기 전에 비즈니스용 Skype 클라이언트에서 **내 로그인 정보 삭제** 옵션을 사용 하 고 비즈니스용%localappdata%\Microsoft\Office\15.0\Skype에서 해당 SIP 프로필 폴더를 삭제 해야 합니다.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Kerberos 또는 NTLM 인증 방법을 사용 하면 사용자의 Windows 자격 증명이 인증에 자동으로 사용 됩니다. Kerberos 및/또는 NTLM이 인증을 사용 하도록 설정 되어 있는 일반적인 비즈니스용 Skype 서버 배포에서는 사용자가 로그인 할 때마다 자격 증명을 입력할 필요가 없습니다.
  
사용자가 PIN을 입력 하 라는 메시지가 표시 되기 전에 실수로 자격 증명을 묻는 메시지가 표시 되는 경우, 그룹 정책을 통해 클라이언트 컴퓨터에 **DisableNTCredentials** 레지스트리 키가 실수로 구성 될 수 있습니다.
  
자격 증명에 대 한 추가 메시지가 표시 되지 않도록 하려면 로컬 워크스테이션에서 다음 레지스트리 항목을 만들거나 비즈니스용 Skype 관리 템플릿을 사용 하 여 그룹 정책을 사용 하 여 지정 된 풀의 모든 사용자에 게 적용 합니다.
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

사용자가 처음으로 비즈니스용 Skype에 로그인 하면 사용자에 게 암호를 저장 하 라는 메시지가 표시 됩니다. 이 옵션을 선택 하면 사용자의 클라이언트 인증서가 개인 인증서 저장소에 저장 되 고 사용자의 Windows 자격 증명은 로컬 컴퓨터의 자격 증명 관리자에 저장 됩니다.
  
비즈니스용 Skype가 2 단계 인증을 지원 하도록 구성 된 경우 **Savepassword** 레지스트리 설정을 사용 하지 않도록 설정 해야 합니다. 사용자가 암호를 저장 하지 못하도록 하려면 로컬 워크스테이션에서 다음 레지스트리 항목을 변경 하거나 비즈니스용 Skype 관리 템플릿을 사용 하 여 그룹 정책을 사용 하 여 지정 된 풀의 모든 사용자에 게 적용 합니다.
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 토큰 재생

AD FS 2.0는 동일한 토큰을 사용 하는 여러 토큰 요청이 검색 되 고 삭제 될 수 있는 토큰 재생 검색 이라는 기능을 제공 합니다. 이 기능을 사용 하는 경우 토큰 재생 감지는 동일한 토큰이 두 번 이상 사용 되지 않도록 하 여 WS-FEDERATION 수동 프로필 및 SAML WebSSO 프로필 둘 다의 인증 요청에 대 한 무결성을 보호 합니다.
  
이 기능을 사용 하려면 보안이 키오스크를 사용 하는 경우와 같이 매우 높은 관심사에 있는 상황에 따라야 합니다. 토큰 재생 검색에 대 한 자세한 내용은 [AD FS 2.0의 보안 계획 및 배포에 대 한 모범 사례](https://go.microsoft.com/fwlink/p/?LinkId=309215)를 참조 하세요.
  
## <a name="external-user-access"></a>외부 사용자 액세스

외부 네트워크에서 비즈니스용 Skype의 2 단계 인증을 지원 하도록 ADFS 프록시 또는 리버스 프록시를 구성 하는 것은 이러한 항목에서 다루지 않습니다.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 2 단계 인증 구성](configure-two-factor.md)
  
