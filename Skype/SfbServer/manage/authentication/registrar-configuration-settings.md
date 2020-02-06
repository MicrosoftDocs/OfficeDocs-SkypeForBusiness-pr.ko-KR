---
title: 비즈니스용 Skype 서버에서 등록자 구성 설정 관리
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
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: '요약: 비즈니스용 Skype 서버에 대 한 등록자 구성 설정을 관리 합니다.'
ms.openlocfilehash: 0c4529fb7343cf3db1e516858987a3ba60435513
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818760"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 등록자 구성 설정 관리
 
**요약:** 비즈니스용 Skype 서버에 대 한 등록자 구성 설정을 관리 합니다.
  
레지스트라를 사용 하 여 프록시 서버 인증 방법을 구성할 수 있습니다. 지정 하는 인증 프로토콜은 풀의 서버가 클라이언트에 발급 하는 챌린지 유형을 결정 합니다. 사용할 수 있는 프로토콜은 다음과 같습니다.
  
- **커버로스** 이는 클라이언트가 사용할 수 있는 가장 강력한 암호 기반 인증 구성표 이지만 일반적으로 키 배포 센터 (Kerberos 도메인 컨트롤러)에 대 한 클라이언트 연결이 필요 하기 때문에 엔터프라이즈 클라이언트 에서만 사용할 수 있습니다. 이 설정은 서버에서 엔터프라이즈 클라이언트만 인증 하는 경우에 적합 합니다.
    
- **NTLM** 암호에 챌린지 응답 해싱 스키마를 사용 하는 클라이언트가 사용할 수 있는 암호 기반 인증입니다. 이것은 원격 사용자와 같은 키 배포 센터 (Kerberos 도메인 컨트롤러)에 연결 되지 않고 클라이언트가 사용할 수 있는 유일한 인증 형태입니다. 서버에서 원격 사용자만 인증 하는 경우 NTLM을 선택 해야 합니다.
    
- **인증서 인증** 이는 서버가 Lync Phone Edition 클라이언트, 공통 지역 전화, 비즈니스용 Skype 및 Lync Windows 스토어 앱에서 인증서를 받아야 하는 경우의 새로운 인증 방법입니다. Lync Phone Edition 클라이언트에서 사용자가 로그인 하 고 PIN (개인 식별 번호)을 제공 하 여 인증을 받은 후에는 비즈니스용 Skype 서버에서 휴대폰에 SIP URI를 프로 비전 하 고 비즈니스용 Skype 서버 서명 인증서 또는 Joe (Ex: SN=joe@contoso.com)를 식별 하는 사용자 인증서를 프로 비전 합니다. 이 인증서는 레지스트라 및 웹 서비스를 사용 하 여 인증 하는 데 사용 됩니다.
    
> [!NOTE]
> 서버에서 원격 및 엔터프라이즈 클라이언트에 대 한 인증을 지 원하는 경우 Kerberos와 NTLM을 모두 사용 하도록 설정 하는 것이 좋습니다. Edge 서버와 내부 서버는 원격 클라이언트에만 NTLM 인증만 제공 되도록 통신 합니다. 이러한 서버에서 Kerberos만 사용 하도록 설정 된 경우에는 원격 사용자를 인증할 수 없습니다. 엔터프라이즈 사용자도 서버에 대해 인증 하는 경우 Kerberos가 사용 됩니다. 
  
Lync Windows 스토어 앱 클라이언트를 사용 하는 경우 인증서 인증을 사용 하도록 설정 해야 합니다.
  
### <a name="to-create-new-registrar-configuration-settings"></a>새 등록자 구성 설정을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.  
    
3. 왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **등록자**를 클릭 합니다.
    
4. **등록자** 페이지에서 **새로 만들기** 클릭
    
5. **서비스 선택**에서 등록 기관에 적용할 서비스를 클릭 한 다음 **확인**을 클릭 합니다.
    
6. **새 등록자 설정**에서 해당 환경의 클라이언트 및 지원 기능에 따라 다음 중 하나 이상을 선택 합니다.
    
   - Kerberos **인증을 사용** 하 여 풀의 서버에서 kerberos 인증을 사용 하 여 문제를 해결 하도록 합니다.
    
   - **Ntlm 인증을 사용** 하 여 풀의 서버에서 ntlm을 사용 하는 데 문제가 있는지 확인 합니다.
    
   - **인증서 인증을 사용 하도록 설정** 하 여 풀의 서버가 클라이언트에 인증서를 발급 하도록 합니다.
    
7. **커밋**을 클릭합니다.
    
## <a name="modify-existing-registrar-configuration-settings"></a>기존 등록자 구성 설정 수정

레지스트라를 사용 하 여 프록시 서버 인증 프로토콜을 구성할 수 있습니다. 
  
> [!NOTE]
> 서버에서 원격 및 엔터프라이즈 클라이언트에 대 한 인증을 지 원하는 경우 Kerberos와 NTLM을 모두 사용 하도록 설정 하는 것이 좋습니다. Edge 서버와 내부 서버는 원격 클라이언트에만 NTLM 인증만 제공 되도록 통신 합니다. 이러한 서버에서 Kerberos만 사용 하도록 설정 된 경우에는 원격 사용자를 인증할 수 없습니다. 엔터프라이즈 사용자도 서버에 대해 인증 하는 경우 Kerberos가 사용 됩니다. 
  
기존 등록자를 수정 하려면 다음 단계를 따르세요. 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a>기존 등록자 구성 설정을 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.  
    
3. 왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **등록자**를 클릭 합니다.
    
4. **등록자** 페이지에서 서비스를 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
5. **등록자 편집 설정**에서 해당 환경의 클라이언트 및 지원의 기능에 따라 다음 중 하나 이상을 선택 합니다.
    
   - Kerberos **인증을 사용** 하 여 풀의 서버에서 kerberos 인증을 사용 하 여 문제를 해결 하도록 합니다.
    
   - **Ntlm 인증을 사용** 하 여 풀의 서버에서 ntlm을 사용 하는 데 문제가 있는지 확인 합니다.
    
   - **인증서 인증을 사용 하도록 설정** 하 여 풀의 서버가 클라이언트에 인증서를 발급 하도록 합니다.
    
6. **커밋**을 클릭합니다.
    
### <a name="to-delete-registrar-configuration-settings"></a>등록자 구성 설정을 삭제 하려면

1. RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
    
3. 왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **등록자**를 클릭 합니다.
    
4. **등록자** 페이지에서 검색 필드에 삭제 하려는 등록자의 이름을 전부 또는 일부 입력 합니다.
    
5. 목록에서 원하는 등록 기관을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.
    
6. **확인**을 클릭합니다.
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 등록자 구성 설정 제거

Windows PowerShell 및 **제거-CsProxyConfiguration** cmdlet을 사용 하 여 등록자 구성 설정을 삭제할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>특정 등록자 보안 설정 집합을 제거 하려면

- 다음 명령은 edge Server atl-edge-011.litwareinc.com에 적용 된 등록자 보안 설정을 제거 합니다.
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>사이트 범위에 적용 된 모든 등록자 보안 설정을 제거 하려면

- 다음 명령을 실행 하면 등록자 서비스에 적용 된 모든 등록자 보안 설정이 제거 됩니다.
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>NTLM 인증을 허용 하는 모든 등록자 보안 설정을 제거 하려면

- 다음 명령은 클라이언트 인증에 NTLM을 사용할 수 있는 모든 등록자 보안 설정을 삭제 합니다.
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

자세한 내용은 [-CsProxyConfiguration 제거](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps)를 참조 하세요.
  

