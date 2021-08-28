---
title: 2단계 인증을 구성합니다비즈니스용 Skype 서버
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
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: '요약: 2단계 인증을 구성하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: f4c8532d08a3ed6c06a702039eea224f231cbd06
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612397"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>2단계 인증을 구성합니다비즈니스용 Skype 서버

**요약:** 2단계 인증을 구성하여 비즈니스용 Skype 서버.

다음 섹션에서는 배포에 대해 2단계 인증을 구성하는 데 필요한 단계에 대해 설명합니다. 2단계 인증에 대한 자세한 내용은 온라인 관리자에 대해 Office 365 다단계 인증 사용 [- 그리드 사용자 게시물 을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=313332)

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>스마트 카드 Enterprise 지원하도록 루트 인증 기관 구성

다음 단계에서는 스마트 카드 인증을 지원하도록 Enterprise 루트 CA를 구성하는 방법을 설명합니다.

루트 CA를 설치하는 Enterprise 자세한 내용은 [Install an Enterprise Root Certification Authority를 참조하십시오.](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10))

1. 도메인 관리자 계정을 Enterprise CA 컴퓨터에 로그인합니다.

2. 시스템 관리자를 시작하고 인증 기관 웹 등록 역할이 설치되어 있는지 확인합니다.

3. 관리 도구 **메뉴에서** 인증 기관 관리 **콘솔을** 여세요.

4. 탐색 창에서 인증 **기관 을 확장합니다.**

5. 인증서 **템플릿을 마우스 오른쪽 단추로 클릭하고** 새로 **고치기** 를 선택한 다음 **발급할 인증서 템플릿 을 선택합니다.**

6. 등록 **에이전트,** **스마트 카드 사용자** 및 스마트 카드 **로그온을 선택합니다.**

7. **확인** 을 클릭합니다.

8. 인증서 **템플릿을 마우스 오른쪽 단추로 클릭합니다.**

9. 관리를 **선택합니다.**

10. Smartcard 사용자 템플릿의 속성을 엽니 다.

11. 보안 **탭을** 클릭합니다.

12. 사용 권한을 다음과 같이 변경합니다.

    - 읽기/등록(허용) 권한이 있는 개별 사용자 AD 계정 추가 또는

    - 읽기/등록(허용) 권한이 있는 스마트 카드 사용자가 포함된 보안 그룹 추가 또는

    - 읽기/등록(허용) 권한이 있는 도메인 사용자 그룹 추가

## <a name="configure-windows-8-for-virtual-smart-cards"></a>가상 Windows 8 카드에 대한 구성

2단계 인증 및 스마트 카드 기술을 배포할 때 고려해야 할 한 가지 요소는 구현 비용입니다. Windows 8 여러 가지 새로운 보안 기능을 제공하며, 가장 흥미로운 새 기능 중 하나는 가상 스마트 카드에 대한 지원입니다.

사양 버전 1.2를 충족하는 TPM(신뢰할 수 있는 플랫폼 모듈) 칩이 장착된 컴퓨터의 경우 이제 조직은 하드웨어에 추가 투자를 하지 않고도 스마트 카드 로그온의 이점을 얻을 수 있습니다. 자세한 내용은 에서 가상 스마트 카드 사용을 [Windows 8.](https://go.microsoft.com/fwlink/p/?LinkId=313365)

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>가상 Windows 8 대해 구성

1. Windows 8 사용할 수 있는 사용자의 자격 증명을 사용하여 비즈니스용 Skype 컴퓨터에 로그인합니다.

2. 시작 Windows 8 화면에서 커서를 화면의 오른쪽 아래 모서리로 움직입니다.

3. 검색 **옵션을** 선택한 다음Command 프롬프트를 검색합니다.

4. 명령 프롬프트를 **마우스 오른쪽 단추로** 클릭한 다음 **관리자 권한으로 실행을 선택합니다.**

5. 다음 명령을 실행하여 TPM(신뢰할 수 있는 플랫폼 모듈) 관리 콘솔을 니다.

   ```console
   Tpm.msc
   ```

6. TPM 관리 콘솔에서 TPM 사양 버전이 1.2 이상인지 확인합니다.

    > [!NOTE]
    > TPM(호환 가능한 트러스트 플랫폼 모듈)을 찾을 수 없다는 대화 상자가 수신되면 컴퓨터에 호환되는 TPM 모듈이 있으며 시스템 BIOS에서 사용하도록 설정되어 있는지 확인합니다.

7. TPM 관리 콘솔 닫기

8. 명령 프롬프트에서 다음 명령을 사용하여 새 가상 스마트 카드를 생성합니다.

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

   > [!NOTE]
   > 가상 스마트 카드를 만들 때 사용자 지정 PIN 값을 제공하기 위해 대신 /pin prompt를 사용합니다.

9. 명령 프롬프트에서 다음 명령을 실행하여 컴퓨터 관리 콘솔을 니다.

  ```console
  CompMgmt.msc
  ```

10. 컴퓨터 관리 콘솔에서 장치 **관리를 선택합니다.**

11. 스마트 **카드 판독기를 확장합니다.**

12. 새 가상 스마트 카드 판독기가 성공적으로 만들어졌습니다.

## <a name="enroll-users-for-smart-card-authentication"></a>스마트 카드 인증을 위해 사용자 등록

일반적으로 스마트 카드 인증을 위해 사용자를 등록하는 방법에는 두 가지가 있습니다. 보다 쉬운 방법은 사용자가 웹 등록을 사용하여 스마트 카드 인증을 직접 등록하도록 하는 반면, 보다 복잡한 방법은 등록 에이전트를 사용하는 것입니다. 이 항목에서는 스마트 카드 인증서에 대한 자체 등록에 대해 중점적으로 다를 수 있습니다.

사용자를 등록 에이전트로 대신하여 등록하는 자세한 내용은 [Enroll for Certificates on Behalf of Other Users을 참조하십시오.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11))

### <a name="to-enroll-users-for-smart-card-authentication"></a>스마트 카드 인증을 위해 사용자를 등록

1. Windows 8 사용할 수 있는 사용자의 자격 증명을 사용하여 비즈니스용 Skype 로그온합니다.

2. 시작 Internet Explorer.

3. 인증 기관 웹 **등록** 페이지(예: 로 https://MyCA.contoso.com/certsrv) 이동합니다.

    > [!NOTE]
    > 웹 사이트를 사용하는 Internet Explorer 10 호환 모드에서 이 웹 사이트를 보아야 할 수 있습니다.

4. 시작 **페이지에서** 인증서 **요청을 선택합니다.**

5. 그런 다음 고급 **요청을 선택합니다.**

6. 이 CA에 요청 만들기 및 **제출을 선택합니다.**

7. 인증서 **템플릿 섹션에서 Smartcard** **사용자를** 선택하고 다음 값을 사용하여 고급 인증서 요청을 완료합니다.

  - **주요 옵션은** 다음 설정을 확인합니다.

    - 새 키 **집합 만들기 라디오** 단추 선택

    - **CSP의 경우** **Microsoft 기본 스마트 카드 암호화 공급자를 선택합니다.**

    - 키 **사용에** 대해 를 **Exchange** 선택합니다(이 옵션은 사용 가능한 유일한 옵션).

    - 키 **크기로** 2048을 입력합니다.

    - 자동 키 **컨테이너 이름이 선택되어 있는지** 확인

    - 다른 상자는 선택하지 않은 것으로 떠 .

  - 추가 **옵션에서** 다음 값을 확인 합니다.

    - 요청 **형식의 경우** **CMC 를 선택합니다.**

    - 해시 **알고리즘의 경우** **sha1 을 선택합니다.**

    - **이름에** 대해Mardcard 인증서를 입력합니다.

8. 실제 스마트 카드 판독기를 사용하는 경우 장치에 스마트 카드를 삽입합니다.

9. **제출을** 클릭하여 인증서 요청을 제출합니다.

10. 메시지가 표시될 때 가상 스마트 카드를 만드는 데 사용된 PIN을 입력합니다.

    > [!NOTE]
    > 기본 가상 스마트 카드 PIN 값은 '12345678'입니다.

11. 인증서가 발급된 후 이  인증서 설치를 클릭하여 등록 프로세스를 완료합니다.

    > [!NOTE]
    >  "이 웹 브라우저에서 인증서 요청 생성을 지원하지 않습니다."라는 오류와 함께 인증서 요청이 실패하면 다음 세 가지 방법으로 문제를 해결할 수 있습니다.
    >- 호환성 보기를 사용하도록 Internet Explorer.
    >- 2016에서 인트라넷 설정 켜기 옵션을 Internet Explorer.
    >- 사용자 지정 옵션 메뉴의 보안 탭에서 모든 영역 기본 수준으로 Internet Explorer 선택합니다.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>AD FS 2.0(Active Directory Federation Services) 구성

다음 섹션에서는 다단계 인증을 지원하도록 AD FS 2.0(Active Directory Federation Services)을 구성하는 방법을 설명합니다. AD FS 2.0을 설치하는 방법에 대한 자세한 내용은 [AD FS 2.0 단계별](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))및 방법 가이드를 참조하세요.

> [!NOTE]
> AD FS 2.0을 설치할 때 Windows 서버 관리자를 사용하여 Active Directory Federation Services 역할을 추가하지 않습니다. 대신 [Active Directory Federation Services 2.0 RTW 패키지를 다운로드하여 설치합니다.](https://go.microsoft.com/fwlink/p/?LinkId=313375)

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>2단계 인증에 대해 AD FS를 구성

1. 도메인 관리자 계정을 사용하여 AD FS 2.0 컴퓨터에 로그인합니다.

2. Windows PowerShell을 시작합니다.

3. 명령 Windows PowerShell 명령줄에서 다음 명령을 실행합니다.

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. 다음 명령을 실행하여 배포와 관련한 서버 이름을 바꾸어 수동 인증을 사용하도록 설정할 각 서버와 파트너 관계를 설정합니다.

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. 관리 도구 메뉴에서 AD FS 2.0 관리 콘솔을 실행합니다.

6. **트러스트 관계**  >  **신뢰 파티 트러스트 를 확장합니다.**

7. 사용자 계정의 새 트러스트가 비즈니스용 Skype 서버.

8. 다음 명령을 실행하여 신뢰 파티 트러스트에 대한 Windows PowerShell 규칙을 만들고 할당합니다.

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. 다음 명령을 실행하여 신뢰 파티 트러스트에 대한 Windows PowerShell 변환 규칙을 만들고 할당합니다.

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. AD FS 2.0 관리 콘솔에서 신뢰하는 사용자 트러스트 를 마우스 오른쪽 단추로 클릭하고 클레임 규칙 **편집을 선택합니다.**

11. **Issuance Authorization Rules(발행 권한 부여 규칙)** 탭을 선택하고 새 권한 부여 규칙이 성공적으로 만들어졌습니다.

12. **Issuance Transform Rules(발행 변환 규칙)** 탭을 선택하고 새 변환 규칙이 성공적으로 만들어졌습니다.

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>클라이언트 인증을 지원하도록 AD FS 2.0 구성

AD FS 2.0에서 스마트 카드를 사용한 인증을 지원하도록 구성할 수 있는 두 가지 인증 유형이 있습니다.

- FBA(양식 기반 인증)

- 전송 계층 보안 클라이언트 인증

양식 기반 인증을 사용하면 사용자가 사용자 이름/암호를 사용하여 또는 스마트 카드와 PIN을 사용하여 인증할 수 있는 웹 페이지를 개발할 수 있습니다. 이 항목에서는 AD FS 2.0을 사용하여 전송 계층 보안 클라이언트 인증을 구현하는 방법을 중점적으로 다루고 있습니다. AD FS 2.0 인증 유형에 대한 자세한 내용은 [AD FS 2.0: 로컬](https://go.microsoft.com/fwlink/p/?LinkId=313384)인증 유형을 변경하는 방법을 참조하세요.

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>클라이언트 인증을 지원하도록 AD FS 2.0을 구성합니다.

1. 도메인 관리자 계정을 사용하여 AD FS 2.0 컴퓨터에 로그인합니다.

2. 탐색기를 Windows 실행합니다.

3. C:\inetpub\adfs\ls로 탐색

4. 기존 데이터베이스 파일의 백업 복사본을 web.config.

5. 기존 web.config 파일을 메모장.

6. 메뉴 표시줄에서 편집을 **선택한** 다음 찾기를 **선택합니다.**

7. \<localAuthenticationTypes\>를 검색합니다.

    네 가지 인증 유형이 나열되어 있습니다(한 줄에 하나씩).

8. TLSClient 인증 유형이 포함된 줄을 섹션의 목록 맨 위로 이동하십시오.

9. 파일 파일을 저장하고 web.config 닫습니다.

10. 관리자 권한으로 명령 프롬프트를 실행합니다.

11. 다음 명령을 실행하여 IIS를 다시 시작합니다.

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>수동 비즈니스용 Skype 서버 구성

다음 섹션에서는 수동 인증을 지원하도록 비즈니스용 Skype 서버 방법을 설명합니다. 일단 사용하도록 설정되면 2단계 인증을 사용하도록 설정된 사용자는 실제 또는 가상 스마트 카드와 유효한 PIN을 사용하여 비즈니스용 Skype 합니다.

> [!NOTE]
> 고객은 서비스 수준에서 등록자 및 웹 서비스에 대해 수동 인증을 사용하도록 설정하는 것이 좋습니다. 전역 수준에서 등록자 및 웹 서비스에 대해 수동 인증을 사용하도록 설정하면 지원되는 데스크톱 클라이언트로 로그인하지 않은 사용자의 조직 전체 인증 오류가 발생합니다.

### <a name="web-service-configuration"></a>웹 서비스 구성

다음 단계에서는 수동 인증을 사용할 수 있는 Enterprise 풀 및 Standard Edition 서버에 대한 사용자 지정 웹 서비스 구성을 만드는 방법을 설명합니다.

### <a name="to-create-a-custom-web-service-configuration"></a>사용자 지정 웹 서비스 구성을 만들하려면

1. 비즈니스용 Skype 서버 계정으로 비즈니스용 Skype 프런트 엔드 서버에 로그인합니다.

2. 관리 비즈니스용 Skype 서버 실행합니다.

3. 비즈니스용 Skype 서버 관리 셸 명령줄에서 다음 명령을 실행하여 수동 인증을 사용하도록 설정되는 Enterprise 풀 및 Standard Edition 서버에 대해 새 웹 서비스 구성을 생성합니다.

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

   > [!CAUTION]
   > WsFedPassiveMetadataUri FQDN 값은 AD FS 2.0 서버의 페더ATION 서비스 이름입니다. Federation Service Name 값은 탐색 창에서 서비스를 마우스 오른쪽 단추로 클릭한 다음  **Federation Service** 속성 편집을 선택하여 AD FS 2.0 관리 콘솔에서 찾을 수 있습니다.

4. 다음 명령을 실행하여 UseWsFedPassiveAuth 및 WsFedPassiveMetadataUri 값이 올바르게 설정되어 있는지 확인합니다.

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. 클라이언트의 경우 수동 인증은 webticket 인증에 대한 최소 선호 인증 방법입니다. 수동 인증을 사용하도록 설정할 모든 Enterprise 풀 및 Standard Edition 서버에 대해 다음 cmdlet을 실행하여 비즈니스용 Skype 웹 서비스에서 다른 모든 인증 유형을 사용하지 않도록 설정해야 합니다.

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. 다음 cmdlet을 실행하여 다른 모든 인증 유형이 사용하지 않도록 설정되어 있는지 확인

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>프록시 구성

비즈니스용 Skype 웹 서비스에 대해 인증서 인증을 사용하지 않도록 설정하면 비즈니스용 Skype 클라이언트는 덜 선호되는 인증 유형(예: Kerberos 또는 NTLM)을 사용하여 등록자 서비스에 인증합니다. 클라이언트가 웹틱킷을 검색할 수 있도록 허용하려면 인증서 인증이 계속 필요하며, 등록자 서비스에 대해 Kerberos 및 NTLM을 사용하지 않도록 설정해야 합니다.

다음 단계에서는 수동 인증을 사용하도록 설정되는 에지 풀, Enterprise 풀 및 Standard Edition 서버의 사용자 지정 프록시 구성을 만드는 방법을 설명합니다.

### <a name="to-create-a-custom-proxy-configuration"></a>사용자 지정 프록시 구성을 만들하려면

1. 비즈니스용 Skype 서버 관리 셸 명령줄에서 다음 명령을 실행하여 비즈니스용 Skype 서버 에지 풀, Enterprise 풀 및 Standard Edition 서버에 대해 새 프록시 구성을 생성합니다.

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. 다음 명령을 실행하여 다른 모든 프록시 인증 유형이 사용하지 않도록 설정되어 있는지 확인

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>참고 항목

[2단계 인증을 비즈니스용 Skype 서버](two-factor-authentication.md)

[클라이언트 및 클라이언트에서 비즈니스용 Skype 2단계 인증 비즈니스용 Skype 서버](use-two-factor.md)
