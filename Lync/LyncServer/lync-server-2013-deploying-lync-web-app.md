---
title: 'Lync Server 2013: Lync Web App 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2156466e0238a061f2358127c75408fa37e3b823
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507535"
---
# <a name="deploying-lync-web-app-in-lync-server-2013"></a>Lync Server 2013에서 Lync Web App 배포

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-07-18_

Lync Web App은 Lync Server 2013와 함께 설치 되며 기본적으로 사용 하도록 설정 되는 IIS (인터넷 정보 서비스) 웹 클라이언트입니다. 서버에서 Lync Web App을 사용 하도록 설정 하거나 사용자에 게 웹 클라이언트를 배포 하는 데 추가 단계를 수행할 필요가 없습니다. 사용자가 모임 URL을 클릭 했지만 Lync 2013 클라이언트가 설치 되어 있지 않은 경우에는 사용자에 게 최신 버전의 Lync Web App을 사용 하 여 모임에 참가할 수 있는 옵션이 제공 됩니다.

Lync Web App의 음성, 비디오 및 공유 기능을 통해 Microsoft ActiveX 컨트롤이 필요 합니다. ActiveX 컨트롤을 미리 설치 하거나 사용자가 Lync 웹 앱을 처음 사용할 때 또는 ActiveX 컨트롤이 필요한 기능에 처음으로 액세스할 때 수행 되는 메시지가 표시 되 면 설치를 허용 하도록 설정할 수 있습니다.

<div class=" ">


> [!NOTE]  
> Lync Server 2013에 지 서버 배포에서는 Lync Web App 클라이언트 액세스에 경계 네트워크의 HTTPS 역방향 프록시가 필요 합니다. 단순 Url도 게시 해야 합니다. 자세한 내용은 lync server <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">2013에 대 한 역방향 프록시 서버 설정</A> 및 <A href="lync-server-2013-planning-for-simple-urls.md">lync server 2013에서 단순 url에 대 한 계획</A>을 참조 하십시오.



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a>Lync Web App에 대해 Multi-factor Authentication 사용

Lync Server 2013 버전의 Lync Web App에서는 다단계 인증을 지원 합니다. 사용자 이름 및 암호 외에도 추가 인증 방법 (예: 스마트 카드나 Pin)을 요구 하 여 Lync 모임에 로그인 할 때 외부 네트워크에서 참가 하는 사용자를 인증 합니다. Lync Server 2013에서 AD FS (Active Directory Federation Service) 페더레이션 서버를 배포 하 고 수동 인증을 사용 하도록 설정 하 여 다단계 인증을 사용 하도록 설정할 수 있습니다. AD FS가 구성 되 면 Lync 모임을 연결 하려고 시도 하는 외부 사용자에 게 구성한 추가 인증 방법과 함께 사용자 이름 및 암호 챌린지를 포함 하는 AD FS 다단계 인증 웹 페이지가 제공 됩니다.

<div class=" ">


> [!IMPORTANT]  
> 다단계 인증을 사용 하도록 AD FS를 구성 하려는 경우에는 다음과 같은 중요 한 사항을 고려해 야 합니다. 
> <UL>
> <LI>
> <P>다단계 ADFS 인증 모임 참가자와 이끌이 모두가 동일한 조직에 있거나 AD FS 페더레이션 조직에 있는 경우에만 작동 합니다. 다단계 ADFS 인증은 Lync server 웹 인프라가 현재 지원 하지 않으므로 Lync 페더레이션 사용자에 대해서는 작동 하지 않습니다.</P>
> <LI>
> <P>하드웨어 부하 분산 장치를 사용 하는 경우에는 Lync Web App 클라이언트의 모든 요청이 동일한 프런트 엔드 서버에서 처리 되도록 부하 분산 장치에서 쿠키 지 속성을 사용 하도록 설정 합니다.</P>
> <LI>
> <P>Lync Server와 AD FS 서버 간에 신뢰 당사자 트러스트를 설정 하는 경우 Lync 모임의 최대 길이를 확장 하는 데 충분 한 길이의 토큰 수명을 할당 합니다. 일반적으로 240 분의 토큰 수명은 충분 합니다.</P>
> <LI>
> <P>이 구성은 Lync 모바일 클라이언트에는 적용 되지 않습니다.</P></LI></UL>



</div>

**다단계 인증을 구성 하려면**

1.  AD FS 페더레이션 서버 역할을 설치 합니다. 자세한 내용은 다음 위치에 있는 Active Directory Federation Services 2.0 배포 가이드를 참조 하세요. <https://go.microsoft.com/fwlink/p/?linkid=267511>

2.  AD FS에 대 한 인증서를 만듭니다. 자세한 내용은의 ' 페더레이션 서버 인증서 ' 섹션에서 single sign-on 사용에 대 한 use AD FS를 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376) .

3.  Windows PowerShell 명령줄 인터페이스에서 다음 명령을 실행 합니다.
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  다음 명령을 실행 하 여 파트너 관계를 설정 합니다.
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  다음과 같은 신뢰 당사자 규칙을 설정 합니다.
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a>BranchCache 구성

Windows 7 및 Windows Server 2008 R2의 BranchCache 기능은 Lync Web App 웹 구성 요소를 방해할 수 있습니다. Lync Web App 사용자에 대 한 문제를 방지 하려면 BranchCache를 사용 하도록 설정 하지 않았는지 확인 합니다.

BranchCache를 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) Windows Server 2008 R2 기술 라이브러리의 Microsoft 다운로드 센터 및 HTML 형식으로 제공 되는 Branchcache 배포 가이드를 참조 [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789) 하세요.

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a>Lync Web App 배포 확인

Test-CsUcwaConference cmdlet을 사용 하 여 테스트 사용자 쌍이 통합 커뮤니케이션 웹 API (c)를 사용 하 여 회의에 참가할 수 있는지 확인할 수 있습니다. 이 cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서의 [test-csucwaconference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) 를 참조 하십시오.

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a>Windows Server 2008 R2에서 플러그 인 설치 문제 해결

Windows Server 2008 R2를 실행 하는 컴퓨터에서 플러그 인 설치가 실패 하는 경우 Internet Explorer 보안 설정 또는 DisableMSI 레지스트리 키 설정을 수정 해야 할 수 있습니다.

**Internet Explorer에서 보안 설정을 수정 하려면**

1.  Internet Explorer를 엽니다.

2.  **도구**, **인터넷 옵션**을 차례로 클릭 한 다음 **고급**을 클릭 합니다.

3.  아래로 스크롤하여 **보안** 섹션으로 이동 합니다.

4.  **암호화 된 페이지를 디스크에 저장 안 함**을 선택 취소 한 다음 **확인**을 클릭 합니다.
    
    <div class=" ">
    

    > [!NOTE]  
    > 이 설정을 선택 하면 Lync Web App에서 첨부 파일을 다운로드 하려고 할 때 오류가 발생 합니다.

    
    </div>

5.  모임에 다시 참가합니다. 플러그 인을 오류 없이 다운로드 해야 합니다.

**DisableMSI 레지스트리 설정을 수정 하려면**

1.  **시작**을 클릭한 다음 **실행**을 클릭합니다.

2.  레지스트리 편집기에 액세스 하려면 **regedit**를 입력 합니다.

3.  HKEY \_ 로컬 \_ 컴퓨터 \\ 소프트웨어 \\ 정책 \\ Microsoft \\ Windows Installer로 이동 \\ 합니다.

4.  REG DWORD 형식의 DisableMSI 레지스트리 키를 편집 하거나 추가 \_ 하 고이를 0으로 설정 합니다.

5.  모임에 다시 참가합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 모임 참가 페이지 구성](lync-server-2013-configuring-the-meeting-join-page.md)  
[Lync Server 2013의 lync Web App 지원 되는 플랫폼](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

