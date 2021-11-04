---
title: 웹에서 다운로드 가능한 웹 클라이언트 비즈니스용 Skype 서버
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: '요약: 모임 비즈니스용 Skype Web App Skype 및 모임 앱을 비즈니스용 Skype.'
ms.openlocfilehash: c262ab4e9180ae9e02bc899793437a86ffe12ead
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761596"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>웹에서 다운로드 가능한 웹 클라이언트 비즈니스용 Skype 서버

**요약:** 비즈니스용 Skype 함께 사용되는 Skype 2015 Web App 및 Skype 모임 앱을 비즈니스용 Skype 서버.

비즈니스용 Skype Web App 실행 서버에 설치되는 IIS(인터넷 정보 서비스) 웹 클라이언트로, 비즈니스용 Skype 서버 클라이언트가 아직 없는 사용자를 충족하는 비즈니스용 Skype 배포됩니다. 이러한 모임 사용자는 네트워크 외부에서 연결하지 않는 것보다 더 자주 있습니다. 사용자가 모임 URL을 클릭하지만 비즈니스용 Skype 클라이언트가 설치되어 있지 않을 때마다 최신 버전의 비즈니스용 Skype Web App, Skype 모임 앱 또는 비즈니스용 Skype for Mac.

사용자 브라우저의 음성, 비디오 비즈니스용 Skype Web App, 공유 기능을 사용하려면 ActiveX 플러그 인으로 사용되는 Microsoft ActiveX 컨트롤이 필요할 수 있습니다. ActiveX 컨트롤을 미리 설치하거나 메시지가 표시될 때 설치하도록 허용할 수 있습니다. 이 문제는 사용자가 비즈니스용 Skype Web App 처음 사용할 때 또는 ActiveX 컨트롤이 필요한 기능에 처음 액세스할 때 발생합니다.

> [!NOTE]
> 비즈니스용 Skype 서버 에지 서버 배포에서는 경계 네트워크의 HTTPS 역방향 프록시가 비즈니스용 Skype Web App 필요합니다. 단순 URL도 게시해야 합니다. 자세한 내용은 [Setting Up Reverse Proxy Servers](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers) and DNS requirements for simple [URLs in 비즈니스용 Skype 서버.](../../plan-your-deployment/network-requirements/simple-urls.md)

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>사용자에 대해 다단계 인증을 비즈니스용 Skype Web App
<a name="MFA"> </a>

비즈니스용 Skype Web App Skype 및 비즈니스용 Skype for Mac 인증을 지원하지 않습니다. 사용자 이름 및 암호 외에도 스마트 카드 또는 PINS와 같은 추가 인증 방법을 요구하여 사용자가 모임에 로그인할 때 외부 네트워크에서 참가하는 사용자를 비즈니스용 Skype 있습니다. AD FS(Active Directory Federation Service) 페더링 서버를 배포하고 AD FS(Active Directory Federation Service)에서 수동 인증을 사용하도록 설정하여 다단계 인증을 비즈니스용 Skype 서버. AD FS를 구성한 후 비즈니스용 Skype 모임에 참가하려는 외부 사용자에게는 구성한 추가 인증 방법과 함께 사용자 이름 및 암호 챌린지가 포함된 AD FS 다단계 인증 웹 페이지가 표시됩니다.

> [!IMPORTANT]
> 다단계 인증을 위해 AD FS를 구성할 계획인 경우 중요한 고려 사항은 다음과 같습니다.

- 다단계 ADFS 인증은 모임 참가자와 이끌이가 둘 다 같은 조직에 있는 경우 또는 AD FS 페더러조직의 사용자인 경우 작동합니다. Lync 서버 웹 인프라에서 현재 다단계 ADFS 인증을 지원하지 않는 경우 Lync 페더전된 사용자에 대해 다단계 ADFS 인증이 작동하지 않습니다.

- 하드웨어 부하 균형 조정 프로그램을 사용하는 경우 부하 비즈니스용 Skype Web App 또는 모임 앱 클라이언트의 모든 요청이 동일한 프런트 엔드 서버에서 처리될 수 있도록 부하 비즈니스용 Skype Web App 지속성 기능을 사용하도록 설정하십시오.

- 비즈니스용 Skype 서버 및 AD FS 서버 간에 신뢰 관계 트러스트가 설정되는 경우 비즈니스용 Skype 모임의 최대 길이에 걸쳐 충분한 토큰 수명을 할당합니다. 일반적으로 토큰 수명은 240분으로 충분합니다.

- 이 구성은 Lync 모바일 클라이언트에는 적용되지 않습니다.

### <a name="configure-multi-factor-authentication"></a>다단계 인증 구성

1. AD FS 페더ation 서버 역할을 설치합니다. 자세한 내용은 Active [Directory Federation Services 2.0 배포 가이드를 참조하십시오.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd807092(v=ws.10))

2. AD FS용 인증서를 생성합니다. 자세한 내용은 Plan for and deploy AD FS for use with single sign-on 항목의 "페더전 서버 [인증서"](/previous-versions/azure/azure-services/jj205462(v=azure.100)) 섹션을 참조하세요.

3. 명령줄 Windows PowerShell 명령줄 인터페이스에서 다음 명령을 실행합니다.

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. 다음 명령을 실행하여 파트너 관계를 구축합니다.

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. 다음의 기본 규칙 설정

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>BranchCache를 사용하지 않도록 설정
<a name="MFA"> </a>

Windows 7 및 Windows Server 2008 R2의 BranchCache 기능은 웹 비즈니스용 Skype Web App 방해할 수 있습니다. 사용자에 대한 문제를 비즈니스용 Skype Web App BranchCache가 사용하도록 설정되어 있지 않은지 확인합니다.

BranchCache를 사용할 수 없습니다.에 대한 자세한 내용은 [BranchCache 배포 가이드 를 참조하십시오.](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)

## <a name="verifying-skype-for-business-web-app-deployment"></a>배포 비즈니스용 Skype Web App 확인
<a name="MFA"> </a>

테스트 Test-CsUcwaConference 사용하여 한 쌍의 테스트 사용자가 UCWA(Unified Communications Web API)를 사용하여 회의에 참가할 수 있는지 확인할 수 있습니다. 이 cmdlet에 대한 자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서에서 [Test-CsUcwaConference를](/powershell/module/skype/test-csucwaconference?view=skype-ps) 참조하십시오.

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Windows Server 2008 R2에서 플러그 인 설치 문제 해결
<a name="MFA"> </a>

Windows Server 2008 R2를 실행하는 컴퓨터에서 플러그 인을 설치하지 못하는 경우 Internet Explorer 보안 설정 또는 DisableMSI 레지스트리 키 설정을 수정해야 할 수 있습니다.

### <a name="modify-the-security-setting-in-internet-explorer"></a>보안 설정의 Internet Explorer

1. Internet Explorer를 엽니다.

2. 도구, **인터넷 옵션,** 고급을  **클릭합니다.**

3. 아래로 스크롤하여 **보안 섹션으로** 스크롤합니다.

4. 암호화된 **페이지를 디스크에** 저장하지 않습니다.를 선택 취소한 다음 확인을 **클릭합니다.**

    > [!NOTE]
    > 이 설정을 선택한 경우 이 설정으로 인해 첨부 파일을 다운로드할 때 오류가 비즈니스용 Skype Web App.

5. 모임에 다시 참가합니다. 플러그 인이 오류 없이 다운로드해야 합니다.

### <a name="modify-the-disablemsi-registry-setting"></a>DisableMSI 레지스트리 설정 수정

1. **시작** 을 클릭한 다음 **실행** 을 클릭합니다.

2. 레지스트리 편집기에 액세스하기 위해 **regedit 를 입력합니다.**

3. 사이트로 HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.

4. 다음 형식의 DisableMSI 레지스트리 REG_DWORD 편집하거나 추가하고 0으로 설정합니다.

5. 모임에 다시 참가합니다.

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>모임 Skype 앱을 사용하여 비즈니스용 Skype Web App 사용(선택 사항, 비즈니스용 Skype 서버 2015만 해당)
<a name="SMA_Enable"> </a>

이 절차는 선택 사항이며 비즈니스용 Skype 서버 2015 CU5 이상에 적용됩니다. 이 기능을 사용하지 않는 경우 외부 사용자는 이 기능을 사용하여 모임에 비즈니스용 Skype Web App.

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>간소화된 모임 참가 및 모임 Skype 앱 사용

1. Content Delivery Network(CDN)에 액세스할 수 있도록 설정하면 사용자는 온라인으로 CDN 연결하고 Skype 모임 앱(Windows) 및 비즈니스용 Skype for Mac(Mac에서)를 다운로드할 수 있으며 간소화된 모임 참가 환경을 사용할 수 있습니다.

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. 모임 참가 웹 페이지 또는 Skype 모임 앱의 클라이언트 쪽 로깅 원격 분석이 Microsoft 서버로 전송될 수 있도록 허용합니다(이 명령은 기본값은 false임).

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Microsoft로 전송되는 정보는 데이터 수집 비즈니스용 Skype [준수합니다.](/skypeforbusiness/legal-and-regulatory/data-collection-practices)

3. 로컬에서 호스팅되는 비즈니스용 Skype Web App 환경으로 이전 시간 제한을 CDN 수 없습니다. 기본값은 6초입니다. 이 값을 0으로 설정하면 시간 제한이 없습니다.

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> 비즈니스용 Skype 서버 2015 누적 업데이트 5에서 MeetingUxUseCdn을 사용할 경우 기본값은 False로 설정됩니다. 이로 인해 비즈니스용 Skype for Mac 관리자가 MeetingUxUseCdn을 True로 설정한 경우에도 비즈니스용 Skype 클라이언트가 페더러가 아닌 파트너 모임에 게스트로 참가할 수 없는 문제가 발생하게 됩니다. 이 작업을 비즈니스용 Skype 서버 2015에는 누적 업데이트 7, 6.0.9319.534 이상이 있어야 합니다. [2015에서 Skype 모임](https://support.microsoft.com/kb/4132312)앱을 사용하여 비즈니스용 Skype Web App 비즈니스용 Skype 서버 참조하세요.


## <a name="see-also"></a>참고 항목
<a name="SMA_Enable"> </a>

[모임 클라이언트 계획(Web App 및 모임 앱)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[모임 참가 페이지에서 비즈니스용 Skype 서버](../../manage/conferencing/meeting-join-page.md)

[Microsoft Online Services 개인 정보 취급 방침](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[라이선싱 사용 약관 및 문서](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)