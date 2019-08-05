---
title: 비즈니스용 Skype 서버에서 2 단계 인증 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: '요약: 비즈니스용 Skype 서버에서 2 단계 인증을 구성 합니다.'
ms.openlocfilehash: 91a8929b89a584b116f1c7ec9313daa2fe679fd0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189690"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 2 단계 인증 구성

**요약:** 비즈니스용 Skype 서버에서 2 단계 인증을 구성 합니다.

다음 섹션에서는 배포에 대해 2 단계 인증을 구성 하는 데 필요한 단계에 대해 설명 합니다. 2 단계 인증에 대 한 자세한 내용은 [온라인 관리자-그리드 사용자 게시에 대해 Office 365 다단계 인증 사용](https://go.microsoft.com/fwlink/p/?LinkId=313332)을 참조 하세요.

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>스마트 카드 인증을 지원 하도록 엔터프라이즈 루트 인증 기관 구성

다음 단계에서는 스마트 카드 인증을 지원 하도록 엔터프라이즈 루트 CA를 구성 하는 방법을 설명 합니다.

엔터프라이즈 루트 CA를 설치 하는 방법에 대 한 자세한 내용은 [엔터프라이즈 루트 인증 기관 설치](https://go.microsoft.com/fwlink/p/?LinkID=313364)를 참조 하세요.

1. 도메인 관리자 계정을 사용 하 여 엔터프라이즈 CA 컴퓨터에 로그인 합니다.

2. 시스템 관리자를 시작 하 고 인증 기관 웹 등록 역할이 설치 되어 있는지 확인 합니다.

3. **관리 도구** 메뉴에서 **인증 기관** 관리 콘솔을 엽니다.

4. 탐색 창에서 **인증 기관을**확장 합니다.

5. **인증서 템플릿을**마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 선택한 다음 **발급할 인증서 템플릿을**선택 합니다.

6. **등록 에이전트**, **스마트 카드 사용자**, **스마트 카드 로그온**을 선택 합니다.

7. **확인**을 클릭합니다.

8. **인증서 템플릿을**마우스 오른쪽 단추로 클릭 합니다.

9. **관리**를 선택 합니다.

10. 스마트 카드 사용자 서식 파일의 속성을 엽니다.

11. **보안** 탭을 클릭 합니다.

12. 아래와 같이 사용 권한을 변경 합니다.

    - 읽기/등록 (허용) 권한을 사용 하 여 개별 사용자 광고 계정을 추가 하거나

    - 읽기/등록 (허용) 권한이 있는 스마트 카드 사용자를 포함 하는 보안 그룹을 추가 하거나

    - 읽기/등록 (허용) 권한을 사용 하 여 도메인 사용자 그룹 추가

## <a name="configure-windows-8-for-virtual-smart-cards"></a>가상 스마트 카드에 맞게 Windows 8 구성

2 단계 인증 및 스마트 카드 기술을 구축할 때 고려해 야 하는 한 가지 요인은 구현 비용입니다. Windows 8은 다양 한 새로운 보안 기능을 제공 하 고 가장 흥미로운 새 기능 중 하나는 가상 스마트 카드를 지원 합니다.

규정 버전 1.2을 충족 하는 TPM (신뢰할 수 있는 플랫폼 모듈) 칩이 장착 된 컴퓨터의 경우, 이제 조직에서는 하드웨어에 대 한 추가 투자 없이 스마트 카드 로그온의 이점을 얻을 수 있습니다. 자세한 내용은 [Windows 8과 함께 가상 스마트 카드 사용](https://go.microsoft.com/fwlink/p/?LinkId=313365)을 참조 하세요.

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>가상 스마트 카드에 대해 Windows 8을 구성 하려면

1. 비즈니스용 Skype 사용이 가능한 사용자의 자격 증명을 사용 하 여 Windows 8 컴퓨터에 로그인 합니다.

2. Windows 8 시작 화면에서 화면 오른쪽 아래 모서리로 커서를 이동 합니다.

3. **검색** 옵션을 선택한 다음 Forcommand 프롬프트를 검색 합니다.

4. **명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 선택 합니다.

5. 다음 명령을 실행 하 여 TPM (신뢰할 수 있는 플랫폼 모듈) 관리 콘솔을 엽니다.

  ```
  Tpm.msc
  ```

6. TPM 관리 콘솔에서 TPM 사양 버전이 최소 1.2 인지 확인

    > [!NOTE]
    > 호환 되는 TPM (신뢰할 수 있는 플랫폼 모듈)을 찾을 수 없다는 대화 상자가 표시 되는 경우 컴퓨터에 호환 되는 TPM 모듈이 있고 시스템 BIOS에서 사용 하도록 설정 되어 있는지 확인 합니다.

7. TPM 관리 콘솔을 닫습니다.

8. 명령 프롬프트에서 다음 명령을 사용 하 여 새 가상 스마트 카드를 만듭니다.

  ```
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > 가상 스마트 카드를 만들 때 사용자 지정 PIN 값을 제공 하려면/cpin prompt를 대신 사용 합니다.

9. 명령 프롬프트에서 다음 명령을 실행 하 여 컴퓨터 관리 콘솔을 엽니다.

  ```
  CompMgmt.msc
  ```

10. 컴퓨터 관리 콘솔에서 **장치 관리**를 선택 합니다.

11. **스마트 카드 판독기**를 확장 합니다.

12. 새 가상 스마트 카드 판독기가 성공적으로 생성 되었는지 확인 합니다.

## <a name="enroll-users-for-smart-card-authentication"></a>스마트 카드 인증을 위해 사용자 등록

스마트 카드 인증을 위해 사용자를 등록 하는 방법에는 일반적으로 두 가지가 있습니다. 더 간단한 방법은 사용자가 웹 등록을 사용 하 여 스마트 카드 인증을 직접 등록 하도록 하는 반면 복잡 한 방법은 등록 에이전트를 사용 하는 것입니다. 이 항목에서는 스마트 카드 인증서의 자체 등록에 대해 중점적으로 설명 합니다.

등록 에이전트로 사용자를 등록 하는 방법에 대 한 자세한 내용은 [다른 사용자를 대신 하 여 인증서 등록](https://go.microsoft.com/fwlink/p/?LinkID=313367)을 참조 하세요.

### <a name="to-enroll-users-for-smart-card-authentication"></a>스마트 카드 인증을 위해 사용자를 등록 하려면

1. 비즈니스용 Skype 사용이 가능한 사용자의 자격 증명을 사용 하 여 Windows 8 workstation에 로그인 합니다.

2. Internet Explorer를 실행 합니다.

3. **인증 기관 웹 등록** 페이지 (예:)로 이동 https://MyCA.contoso.com/certsrv)합니다.

    > [!NOTE]
    > Internet Explorer 10을 사용 하는 경우 호환 모드에서이 웹 사이트를 확인 해야 할 수 있습니다.

4. **시작** 페이지에서 **인증서 요청**을 선택 합니다.

5. 그런 다음 **고급 요청**을 선택 합니다.

6. **이 CA에 대 한 요청 만들기 및 제출을**선택 합니다.

7. **인증서 템플릿** 섹션에서 **스마트 카드 사용자** 를 선택 하 고 다음 값을 사용 하 여 고급 인증서 요청을 완료 합니다.

  - **키 옵션** 다음 설정을 확인 합니다.

    - **새 키 집합 만들기** 라디오 단추를 선택 합니다.

    - **CSP**의 경우 **Microsoft 기본 스마트 카드 암호화 공급자** 선택

    - **키 사용**에 대해 **Exchange** 를 선택 합니다 (사용 가능한 유일한 옵션).

    - **키 크기**에는 2048을 입력 합니다.

    - **자동 키 컨테이너 이름이** 선택 되었는지 확인

    - 다른 확인란은 선택 하지 않은 상태로 둡니다.

  - **추가 옵션** 에서 다음 값을 확인 합니다.

    - **요청 형식의** 경우 **CMC**를 선택 합니다.

    - **해시 알고리즘** 의 경우 **sha1**을 선택 합니다.

    - **친근 한 이름** enterSmardcard 인증서.

8. 실제 스마트 카드 판독기를 사용 하는 경우 장치에 스마트 카드를 삽입 합니다.

9. **제출을** 클릭 하 여 인증서 요청을 제출 합니다.

10. 메시지가 표시 되 면 가상 스마트 카드를 만드는 데 사용 된 PIN을 입력 합니다.

    > [!NOTE]
    > 기본 가상 스마트 카드 PIN 값은 ' 12345678 '입니다.

11. 인증서가 발급 되 면 **이 인증서 설치** 를 클릭 하 여 등록 프로세스를 완료 합니다.

    > [!NOTE]
    >  "이 웹 브라우저가 인증서 요청 생성을 지원 하지 않습니다" 오류가 발생 하 여 인증서 요청이 실패 하면 문제를 해결할 수 있는 세 가지 방법이 있습니다.

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>AD FS 2.0 (Active Directory Federation Services) 구성

다음 섹션에서는 multi-factor authentication을 지원 하도록 AD FS 2.0 (Active Directory Federation Services)를 구성 하는 방법을 설명 합니다. AD FS 2.0을 설치 하는 방법에 대 한 자세한 내용은 [AD fs 2.0 단계별 및 가이드 사용법](https://go.microsoft.com/fwlink/p/?LinkId=313374)을 참조 하세요.

> [!NOTE]
> AD FS 2.0을 설치할 때 Windows Server Manager를 사용 하 여 Active Directory Federation Services 역할을 추가 하지 마세요. 대신 [Active Directory Federation Services 2.0 RTW 패키지](https://go.microsoft.com/fwlink/p/?LinkId=313375)를 다운로드 하 여 설치 합니다.

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>2 단계 인증을 위해 AD FS를 구성 하려면

1. 도메인 관리자 계정을 사용 하 여 AD FS 2.0 컴퓨터에 로그인 합니다.

2. Windows PowerShell을 시작 합니다.

3. Windows PowerShell 명령줄에서 다음 명령을 실행 합니다.

  ```
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. 다음 명령을 실행 하 여 배포와 관련 된 서버 이름을 대체 하 여 수동 인증을 사용할 각 서버와 파트너 관계를 설정 합니다.

  ```
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. 관리 도구 메뉴에서 AD FS 2.0 관리 콘솔을 실행 합니다.

6. **신뢰 관계** > **신뢰 당사자 신뢰**를 확장 합니다.

7. 비즈니스용 Skype 서버용으로 새 트러스트가 생성 되었는지 확인 합니다.

8. 다음 명령을 실행 하 여 Windows PowerShell을 사용 하 여 신뢰 당사자 신뢰에 대 한 발급 권한 부여 규칙을 만들고 할당 합니다.

  ```
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. 다음 명령을 실행 하 여 Windows PowerShell을 사용 하 여 신뢰 당사자 신뢰에 대 한 발급 변환 규칙을 만들고 할당 합니다.

  ```
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. AD FS 2.0 관리 콘솔에서 신뢰 당사자 신뢰를 마우스 오른쪽 단추로 클릭 하 고 **클레임 규칙 편집**을 선택 합니다.

11. **발급 권한 부여 규칙** 탭을 선택 하 고 새 권한 부여 규칙이 성공적으로 만들어졌는지 확인 합니다.

12. **발급 변형 규칙** 탭을 선택 하 고 새 변형 규칙이 성공적으로 만들어졌는지 확인 합니다.

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>클라이언트 인증을 지원 하도록 AD FS 2.0 구성

AD FS 2.0에서 스마트 카드를 사용 하 여 인증을 지원 하도록 구성할 수 있는 인증 유형에는 두 가지 가능 합니다.

- FBA (양식 기반 인증)

- 전송 계층 보안 클라이언트 인증

폼 기반 인증을 사용 하 여 사용자 이름/암호를 사용 하거나 스마트 카드 및 PIN을 사용 하 여 인증할 수 있는 웹 페이지를 개발할 수 있습니다. 이 항목에서는 AD FS 2.0를 사용 하 여 전송 계층 보안 클라이언트 인증을 구현 하는 방법에 대해 중점적으로 설명 합니다. AD FS 2.0 인증 형식에 대 한 자세한 내용은 [AD fs 2.0: 로컬 인증 유형을 변경 하는 방법을](https://go.microsoft.com/fwlink/p/?LinkId=313384)참조 하세요.

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>클라이언트 인증을 지원 하도록 AD FS 2.0를 구성 하려면

1. 도메인 관리자 계정을 사용 하 여 AD FS 2.0 컴퓨터에 로그인 합니다.

2. Windows 탐색기를 실행 합니다.

3. C:\inetpub\adfs\ls로 이동

4. 기존 web.config 파일의 백업 복사본을 만듭니다.

5. 메모장을 사용 하 여 기존 web.config 파일을 엽니다.

6. 메뉴 모음에서 **편집** 을 선택 하 고 **찾기를**선택 합니다.

7. Localauthenticationtypes \<\>를 검색 합니다.

    4 개의 인증 유형이 한 줄당 하나씩 나열 됩니다.

8. TLSClient 인증 형식이 포함 된 줄을 섹션의 목록 맨 위로 이동 합니다.

9. Web.config 파일을 저장 하 고 닫습니다.

10. 관리자 권한으로 명령 프롬프트를 실행 합니다.

11. 다음 명령을 실행 하 여 IIS를 다시 시작 합니다.

  ```
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>비즈니스용 Skype 서버 수동 인증 구성

다음 섹션에서는 수동 인증을 지원 하도록 비즈니스용 Skype 서버를 구성 하는 방법을 설명 합니다. 이 기능을 사용 하도록 설정 하면, 2 단계 인증을 사용 하도록 설정 된 사용자는 비즈니스용 Skype 클라이언트를 사용 하 여 로그인 하기 위해 실제 또는 가상 스마트 카드와 유효한 PIN을 사용 해야 합니다.

> [!NOTE]
> 고객은 서비스 수준에서 등록자 및 웹 서비스에 대 한 수동 인증을 사용 하도록 설정 하는 것이 좋습니다. 전역 수준에서 등록자와 웹 서비스에 대해 수동 인증이 사용 하도록 설정 되어 있는 경우 지원 되는 데스크톱 클라이언트를 사용 하 여 로그인 하지 않은 사용자에 대 한 조직 전체 인증 실패가 발생할 수 있습니다.

### <a name="web-service-configuration"></a>웹 서비스 구성

다음 단계에서는 수동 인증을 사용 하도록 설정 되는 디렉터, 엔터프라이즈 풀 및 Standard Edition 서버에 대 한 사용자 지정 웹 서비스 구성을 만드는 방법에 대해 설명 합니다.

### <a name="to-create-a-custom-web-service-configuration"></a>사용자 지정 웹 서비스 구성을 만들려면

1. 비즈니스용 skype 관리자 계정을 사용 하 여 비즈니스용 Skype 서버 프런트 엔드 서버에 로그인 합니다.

2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다.

3. 비즈니스용 Skype Server Management Shell 명령줄에서 다음 명령을 실행 하 여 수동 인증에 사용할 각 디렉터, 엔터프라이즈 풀 및 Standard Edition Server에 대 한 새 웹 서비스 구성을 만듭니다.

  ```
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > WsFedPassiveMetadataUri FQDN에 대 한 값은 AD FS 2.0 서버의 페더레이션 서비스 이름입니다. 페더레이션 서비스 이름 값은 탐색 창에서 **서비스** 를 마우스 오른쪽 단추로 클릭 한 다음 **페더레이션 서비스 속성 편집**을 선택 하 여 AD FS 2.0 관리 콘솔에서 찾을 수 있습니다.

4. 다음 명령을 실행 하 여 UseWsFedPassiveAuth 및 WsFedPassiveMetadataUri 값이 올바르게 설정 되었는지 확인 합니다.

  ```
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. 클라이언트의 경우 Passive 인증은 webticket 인증에 가장 선호 하는 인증 방법입니다. 수동 인증을 사용 하도록 설정 되는 모든 디렉터, Enterprise 풀 및 Standard Edition 서버에 대해 다음 cmdlet을 실행 하 여 비즈니스용 Skype Web Services에서 다른 모든 인증 유형을 사용 하지 않도록 설정 해야 합니다.

  ```
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. 다음 cmdlet을 실행 하 여 다른 모든 인증 유형을 사용 하지 않도록 설정 했는지 확인 합니다.

  ```
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>프록시 구성

비즈니스용 skype Web Services에 대해 인증서 인증을 사용 하지 않도록 설정 하면 비즈니스용 Skype 클라이언트에서 등록 기관 서비스에 인증 하는 데 Kerberos 또는 NTLM 등의 덜 선호 하는 인증 유형을 사용 하 게 됩니다. 클라이언트가 webticket을 검색할 수 있도록 인증서 인증이 여전히 필요 하지만, 등록 기관 서비스에 대해 Kerberos 및 NTLM을 사용 하지 않도록 설정 해야 합니다.

다음 단계에서는 수동 인증을 사용 하도록 설정 되는 Edge 풀, 엔터프라이즈 풀 및 Standard Edition 서버에 대 한 사용자 지정 프록시 구성을 만드는 방법을 설명 합니다.

### <a name="to-create-a-custom-proxy-configuration"></a>사용자 지정 프록시 구성을 만들려면

1. 비즈니스용 Skype Server Management Shell 명령줄에서 다음을 실행 하 여 수동 인증에 사용할 각 비즈니스용 Skype Server Edge 풀, 엔터프라이즈 풀 및 Standard Edition Server에 대 한 새 프록시 구성을 만듭니다. 명령과

  ```
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. 다음 명령을 실행 하 여 다른 모든 프록시 인증 유형이 비활성화 되었는지 확인 합니다.

  ```
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 2 단계 인증 관리](two-factor-authentication.md)

[비즈니스용 Skype 클라이언트 및 비즈니스용 Skype 서버에서 2 단계 인증 사용](use-two-factor.md)
