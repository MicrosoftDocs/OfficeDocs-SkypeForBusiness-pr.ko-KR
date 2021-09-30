---
title: 등록자 구성 설정 관리 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: '요약: 사용자에 대한 등록자 구성 설정을 비즈니스용 Skype 서버.'
ms.openlocfilehash: 8413d7d1604a598b8c46cebe753d408d9300d823
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60015012"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>등록자 구성 설정 관리 비즈니스용 Skype 서버
 
**요약:** 사용자에 대한 등록자 구성 설정을 비즈니스용 Skype 서버.
  
등록자에서 프록시 서버 인증 방법을 구성할 수 있습니다. 지정하는 인증 프로토콜에 따라 풀의 서버가 클라이언트에 대해 문제를 던지게 됩니다. 사용 가능한 프로토콜은 다음입니다.
  
- **Kerberos** 클라이언트에서 사용할 수 있는 가장 강력한 암호 기반 인증 체계이지만 일반적으로는 키 배포 센터(Kerberos 도메인 컨트롤러)에 대한 클라이언트 연결이 필요하기 때문에 엔터프라이즈 클라이언트에서만 사용할 수 있습니다. 이 설정은 서버에서 엔터프라이즈 클라이언트만 인증하는 경우 적절합니다.
    
- **NTLM** 암호에 대해 챌린지 응답 해시 체계를 사용하는 클라이언트가 사용할 수 있는 암호 기반 인증입니다. 원격 사용자와 같은 키 배포 센터(Kerberos 도메인 컨트롤러)에 연결하지 않고 클라이언트에서 사용할 수 있는 유일한 인증 형식입니다. 서버에서 원격 사용자만 인증하는 경우 NTLM을 선택해야 합니다.
    
- **인증서 인증** 이 방법은 서버에서 Lync 전화 Edition 클라이언트, 공통 영역 전화, 비즈니스용 Skype 및 Lync Windows 스토어 앱에서 인증서를 얻어야 하는 새로운 인증 방법입니다. Lync 전화 Edition 클라이언트에서 사용자가 로그인하고 PIN(개인 식별 번호)을 제공하여 인증된 후 비즈니스용 Skype 서버 휴대폰에 SIP URI를 프로비전하고 joe(예: SN=joe@contoso.com)를 휴대폰에 식별하는 비즈니스용 Skype 서버 서명된 인증서 또는 사용자 인증서를 프로비전합니다. 이 인증서는 등록자 및 웹 서비스에 대한 인증에 사용됩니다.
    
> [!NOTE]
> 서버에서 원격 클라이언트 및 엔터프라이즈 클라이언트 둘 다에 대한 인증을 지원할 경우 Kerberos 및 NTLM을 모두 사용하도록 설정하는 것이 좋습니다. 이렇게 하면 원격 클라이언트에는 NTLM 인증만 제공되도록 에지 서버와 내부 서버가 통신합니다. 이 서버에서 Kerberos만 사용하도록 설정한 경우에는 원격 사용자를 인증할 수 없습니다. 서버에 대해 엔터프라이즈 사용자를 인증할 경우에도 Kerberos가 사용됩니다. 
  
Lync Windows 스토어 앱 클라이언트를 사용하려면 인증서 인증을 사용하도록 설정해야 합니다.
  
### <a name="to-create-new-registrar-configuration-settings"></a>새 등록자 구성 설정을 만들하려면

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.  
    
3. 왼쪽 탐색 표시줄에서 **보안**, **등록자** 를 차례로 클릭합니다.
    
4. 등록자 **페이지에서** 새로 **추가를 클릭합니다.**
    
5. 서비스 **선택에서** 등록 기관을 적용할 서비스를 클릭한 다음 확인 을 **클릭합니다.**
    
6. 새 **등록자 설정에서** 클라이언트의 기능 및 환경의 지원에 따라 다음 중 하나 이상을 선택합니다.
    
   - **Kerberos 인증 사용** - 이 풀의 서버가 Kerberos 인증을 사용하여 시도합니다.
    
   - **NTLM 인증 사용** - 이 풀의 서버가 NTLM을 사용하여 시도합니다.
    
   - **인증서 인증 사용** - 이 풀의 서버가 클라이언트에 대한 인증서를 발급합니다.
    
7. **커밋** 을 클릭합니다.
    
## <a name="modify-existing-registrar-configuration-settings"></a>기존 등록자 구성 설정 수정

등록자를 사용하여 프록시 서버 인증 프토토콜을 구성할 수 있습니다. 
  
> [!NOTE]
> 서버에서 원격 클라이언트 및 엔터프라이즈 클라이언트 둘 다에 대한 인증을 지원할 경우 Kerberos 및 NTLM을 모두 사용하도록 설정하는 것이 좋습니다. 이렇게 하면 원격 클라이언트에는 NTLM 인증만 제공되도록 에지 서버와 내부 서버가 통신합니다. 이 서버에서 Kerberos만 사용하도록 설정한 경우에는 원격 사용자를 인증할 수 없습니다. 서버에 대해 엔터프라이즈 사용자를 인증할 경우에도 Kerberos가 사용됩니다. 
  
다음 단계에 따라 기존의 등록자를 수정할 수 있습니다. 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a>기존 등록자 구성 설정을 수정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.  
    
3. 왼쪽 탐색 표시줄에서 **보안**, **등록자** 를 차례로 클릭합니다.
    
4. **등록자** 페이지에서 서비스를 클릭하고 **편집**, **자세한 정보 표시** 를 차례로 클릭합니다.
    
5. 환경의 지원 및 클라이언트 기능에 따라 **등록자 설정 편집** 에서 다음 중 하나 이상을 선택합니다.
    
   - **Kerberos 인증 사용** - 이 풀의 서버가 Kerberos 인증을 사용하여 시도합니다.
    
   - **NTLM 인증 사용** - 이 풀의 서버가 NTLM을 사용하여 시도합니다.
    
   - **인증서 인증 사용** - 이 풀의 서버가 클라이언트에 대한 인증서를 발급합니다.
    
6. **커밋** 을 클릭합니다.
    
### <a name="to-delete-registrar-configuration-settings"></a>등록자 구성 설정을 삭제하려면

1. RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 
    
3. 왼쪽 탐색 표시줄에서 **보안**, **등록자** 를 차례로 클릭합니다.
    
4. 등록자 **페이지와** 검색 필드에 삭제할 등록자 이름을 모두 또는 일부분 입력합니다.
    
5. 목록에서 원하는 등록자, 편집, 삭제를 **클릭합니다.** 
    
6. **확인** 을 클릭합니다.
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>cmdlet을 설정 등록자 구성 Windows PowerShell 제거

등록자 구성 설정은 **Remove-CsProxyConfiguration** cmdlet과 Windows PowerShell 삭제할 수 있습니다. 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 응용 Windows PowerShell 연결에 대한 자세한 비즈니스용 Skype 서버 [Microsoft Lync Remote PowerShell Administration 을 참조합니다.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>특정 등록자 보안 설정 집합을 제거하려면

- 다음 명령은 에지 서버 서버에 적용된 등록자 보안 설정을 atl-edge-011.litwareinc.com.
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>사이트 범위에 적용된 모든 등록자 보안 설정을 제거하려면

- 다음 명령은 등록자 서비스에 적용된 모든 등록자 보안 설정을 제거합니다.
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>NTLM 인증을 허용하는 모든 등록자 보안 설정을 제거하려면

- 다음 명령은 클라이언트 인증에 NTLM을 사용할 수 있는 모든 등록자 보안 설정을 삭제합니다.
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

자세한 내용은 [Remove-CsProxyConfiguration을 참조합니다.](/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps)
