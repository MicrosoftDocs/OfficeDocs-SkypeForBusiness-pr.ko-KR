---
title: 비즈니스용 Skype 서버에서 웹 다운로드 가능 클라이언트 배포
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: '요약: 비즈니스용 skype에 사용 되는 비즈니스용 skype 웹 앱 및 Skype 모임 앱을 배포 합니다.'
ms.openlocfilehash: 16a2a28bf634524d6f61ba579652a6dddfd06de3
ms.sourcegitcommit: 0ad2fb145496210b728034d291a456b4caabdbf9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429424"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 웹 다운로드 가능 클라이언트 배포

**요약:** 비즈니스용 skype 서버에 사용 되는 비즈니스용 Skype 2015 웹 앱 및 Skype 모임 앱을 배포 합니다.

비즈니스용 skype 웹 앱은 비즈니스용 skype 서버를 실행 하는 서버에 설치 된 IIS (인터넷 정보 서비스) 웹 클라이언트 이며, 기본적으로 비즈니스용 Skype 클라이언트가 없는 사용자에 게 모임 요청에 따라 배포 됩니다. 이러한 모임 사용자는 네트워크 외부에서 연결 하지 않는 것이 좋습니다. 사용자가 모임 URL을 클릭 했지만 비즈니스용 Skype 클라이언트가 설치 되어 있지 않은 경우에는 사용자에 게 최신 버전의 비즈니스용 Skype 웹 앱, Skype 모임 앱 또는 Mac 용 비즈니스용 Skype를 사용 하 여 모임에 참가할 수 있는 옵션이 제공 됩니다.

비즈니스용 Skype Web App의 음성, 비디오 및 공유 기능을 사용 하려면 사용자 브라우저에서 플러그 인을 위한 Microsoft ActiveX 컨트롤이 필요 합니다. ActiveX 컨트롤을 미리 설치 하거나 사용자가 비즈니스용 Skype 웹 앱을 처음 사용할 때 또는 ActiveX 컨트롤이 필요한 기능에 처음으로 액세스할 때 수행 되는 메시지가 표시 되 면 설치를 허용 하도록 설정할 수 있습니다.

> [!NOTE]
> 비즈니스용 skype 서버에 지 서버 배포에서는 비즈니스용 Skype Web App 클라이언트 액세스에 경계 네트워크의 HTTPS 역방향 프록시가 필요 합니다. 단순 Url도 게시 해야 합니다. 자세한 내용은 [비즈니스용 Skype 서버에서 단순 url에 대 한](../../plan-your-deployment/network-requirements/simple-urls.md) [역방향 프록시 서버](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) 및 DNS 요구 사항 설정을 참조 하십시오.

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>비즈니스용 Skype 웹 응용 프로그램에 대해 Multi-factor Authentication 사용
<a name="MFA"> </a>

비즈니스용 skype 웹 앱, Skype 모임 앱 및 Mac 용 비즈니스용 Skype는 다단계 인증을 지원 합니다. 사용자 이름 및 암호 외에도 다른 인증 방법 (예: 스마트 카드나 Pin)을 사용 하 여 비즈니스용 Skype 모임에 로그인 할 때 외부 네트워크에서 참가 하는 사용자를 인증 해야 할 수 있습니다. 비즈니스용 Skype 서버에서 AD FS (Active Directory Federation Service) 페더레이션 서버를 배포 하 고 수동 인증을 사용 하도록 설정 하 여 다단계 인증을 사용 하도록 설정할 수 있습니다. AD FS를 구성한 후에는 비즈니스용 Skype 모임에 참가 하려는 외부 사용자에 게 구성한 추가 인증 방법과 함께 사용자 이름 및 암호 챌린지를 포함 하는 AD FS 다단계 인증 웹 페이지가 제공 됩니다.

> [!IMPORTANT]
> 다단계 인증을 사용 하도록 AD FS를 구성 하려는 경우에는 다음과 같은 중요 한 사항을 고려해 야 합니다.

- 다단계 ADFS 인증 모임 참가자와 이끌이 모두가 동일한 조직에 있거나 AD FS 페더레이션 조직에 있는 경우에만 작동 합니다. 다단계 ADFS 인증은 Lync server 웹 인프라가 현재 지원 하지 않으므로 Lync 페더레이션 사용자에 대해서는 작동 하지 않습니다.

- 하드웨어 부하 분산 장치를 사용 하는 경우 비즈니스용 Skype 웹 앱 또는 모임 앱 클라이언트의 모든 요청이 동일한 프런트 엔드 서버에서 처리 되도록 부하 분산 장치에서 쿠키 지 속성을 사용 하도록 설정 합니다.

- 비즈니스용 Skype 서버와 AD FS 서버 간에 신뢰 당사자 트러스트를 설정 하는 경우 비즈니스용 Skype 모임의 최대 길이에 맞게 충분히 긴 토큰 수명을 할당 합니다. 일반적으로 240 분의 토큰 수명은 충분 합니다.

- 이 구성은 Lync 모바일 클라이언트에는 적용 되지 않습니다.

### <a name="configure-multi-factor-authentication"></a>다단계 인증 구성

1. AD FS 페더레이션 서버 역할을 설치 합니다. 자세한 내용은 [Active Directory Federation Services 2.0 배포 가이드](https://go.microsoft.com/fwlink/p/?linkid=267511) 를 참조 하세요.

2. AD FS에 대 한 인증서를 만듭니다. 자세한 내용은 single sign-on을 사용 하 여 AD FS 계획 및 배포의 ["페더레이션 서버 인증서"](https://go.microsoft.com/fwlink/p/?LinkId=285376) 섹션을 참조 하세요.

3. Windows PowerShell 명령줄 인터페이스에서 다음 명령을 실행 합니다.

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. 다음 명령을 실행 하 여 파트너 관계를 설정 합니다.

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. 다음과 같은 신뢰 당사자 규칙을 설정 합니다.

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>BranchCache 사용 안 함
<a name="MFA"> </a>

Windows 7 및 Windows Server 2008 R2의 BranchCache 기능은 비즈니스용 Skype Web App 웹 구성 요소를 방해할 수 있습니다. 비즈니스용 Skype 웹 앱 사용자에 대 한 문제를 방지 하려면 BranchCache를 사용 하도록 설정 하지 않았는지 확인 합니다.

BranchCache를 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 [Branchcache 배포 가이드](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)를 참조 하세요.

## <a name="verifying-skype-for-business-web-app-deployment"></a>비즈니스용 Skype 웹 앱 배포 확인
<a name="MFA"> </a>

Test-csucwaconference cmdlet을 사용 하 여 테스트 사용자 쌍이 통합 커뮤니케이션 웹 API (c)를 사용 하 여 회의에 참가할 수 있는지 확인할 수 있습니다. 이 cmdlet에 대 한 자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서의 [test-csucwaconference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 을 참조 하십시오.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Windows Server 2008 R2에서 플러그 인 설치 문제 해결
<a name="MFA"> </a>

Windows Server 2008 R2를 실행 하는 컴퓨터에서 플러그 인 설치가 실패 하는 경우 Internet Explorer 보안 설정 또는 DisableMSI 레지스트리 키 설정을 수정 해야 할 수 있습니다.

### <a name="modify-the-security-setting-in-internet-explorer"></a>Internet Explorer에서 보안 설정 수정

1. Internet Explorer를 엽니다.

2. **도구**, **인터넷 옵션**을 차례로 클릭 한 다음 **고급**을 클릭 합니다.

3. 아래로 스크롤하여 **보안** 섹션으로 이동 합니다.

4. **암호화 된 페이지를 디스크에 저장 안 함**을 선택 취소 한 다음 **확인**을 클릭 합니다.

    > [!NOTE]
    > 이 설정을 선택 하면 비즈니스용 Skype Web App에서 첨부 파일을 다운로드 하려고 할 때 오류가 발생 합니다.

5. 모임에 다시 참가합니다. 플러그 인을 오류 없이 다운로드 해야 합니다.

### <a name="modify-the-disablemsi-registry-setting"></a>DisableMSI 레지스트리 설정 수정

1. **시작**을 클릭한 다음 **실행**을 클릭합니다.

2. 레지스트리 편집기에 액세스 하려면 **regedit**를 입력 합니다.

3. HKEY_LOCAL_MACHINE \Software\Policies\Microsoft\Windows\Installer.로 이동

4. REG_DWORD 형식의 DisableMSI 레지스트리 키를 편집 하거나 추가 하 고이를 0으로 설정 합니다.

5. 모임에 다시 참가합니다.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Skype 모임 앱에서 비즈니스용 Skype 웹 앱을 교체 하도록 설정 (선택 사항, 비즈니스용 Skype 서버 2015만 해당)
<a name="SMA_Enable"> </a>

이 절차는 선택 사항이 며 비즈니스용 Skype 서버 2015 CU5 이상에 적용 됩니다. 사용 하지 않는 경우 외부 사용자는 비즈니스용 Skype Web App을 사용 하 여 모임에 참가 합니다.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>간소화 된 모임 참가 및 Skype 모임 앱 사용

1. CDN (콘텐츠 배달 네트워크)에 대 한 액세스를 사용 하도록 설정 하면 사용자는 CDN online에 연결 하 여 비즈니스용 skype 모임 앱 (Windows) 및 비즈니스용 Skype for Mac (Mac)을 사용 하며,이를 통해 간단한 모임 참가 환경을 사용할 수 있습니다.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. 모임 참가 웹 페이지 또는 Skype 모임 앱에서 클라이언트 쪽 로깅 원격 분석을 Microsoft 서버로 보낼 수 있도록 허용 합니다 (기본값은 false로 설정 됨).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Microsoft로 전송 되는 정보는 [개인 정보 보호 및 Microsoft 팀](../../../../Teams/teams-privacy.md)을 엄격히 준수 하 고 있습니다.

3. CDN을 사용할 수 없는 경우 로컬에서 호스트 한 비즈니스용 Skype Web App 환경으로 변경 되기 전에 제한 시간을 다시 설정 합니다. 기본값은 6 초입니다. 이 값을 0으로 설정 하면 시간 제한이 발생 하지 않습니다.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> 비즈니스용 Skype 서버 2015 누적 업데이트 5에서 MeetingUxUseCdn를 사용 하는 경우 기본값은 False로 설정 됩니다. 비즈니스용 skype 관리자가 MeetingUxUseCdn를 True로 설정한 경우에도 Mac 용 lync for Business 클라이언트에서 페더레이션 파트너가 아닌 모임을 게스트로 참가할 수 없는 문제를 일으킵니다. 이 작업을 제대로 수행 하려면 비즈니스용 Skype 서버 2015에 누적 업데이트 7, 6.0.9319.534 이상 이상이 있어야 합니다. 비즈니스용 skype [웹 2015 앱을 교체 하려면 Skype 모임 앱 사용을](https://support.microsoft.com/kb/4132312)참조 하세요.


## <a name="see-also"></a>참고 항목
<a name="SMA_Enable"> </a>

[모임 클라이언트 계획 (웹 앱 및 모임 앱)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[비즈니스용 Skype 서버에서 모임 참가 페이지 구성](../../manage/conferencing/meeting-join-page.md)

[Microsoft Online Services 개인 정보 취급 방침](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[사용권 조항 및 설명서](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
