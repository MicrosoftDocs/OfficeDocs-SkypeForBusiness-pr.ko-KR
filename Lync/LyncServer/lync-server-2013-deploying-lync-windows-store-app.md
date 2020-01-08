---
title: 'Lync Server 2013: Lync Windows 스토어 앱 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eef2e96b1e58bb9a92b2dc9748624d38f605965f
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40983032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a>Lync Server 2013에서 Lync Windows 스토어 앱 배포

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-12-03_

사용자가 Lync Windows 스토어 앱을 사용할 수 있도록 설정 하기 전에, 배포가 [Lync Server 2013의 Lync Windows 스토어 앱 요구 사항](lync-server-2013-lync-windows-store-app-requirements.md)에 부합 하는지 확인 합니다. Lync Windows 스토어 앱을 지원 하도록 Lync Server 2013를 구성 하는 방법에 대 한 자세한 내용은 NextHop 블로그 문서, "Lync Server 자동 검색 및 Lync Windows 스토어 [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)앱"을 참조 하세요. 서버 환경을 올바르게 구성한 후에는 "Lync"를 검색 하 여 사용자에 게 Windows 스토어에서 Lync 앱을 다운로드 하도록 지시할 수 있습니다.

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a>Lync Windows 스토어 앱에 대해 다단계 인증을 사용 하도록 설정

Lync Server의 누적 업데이트 2013:6 월 2013에서는 Lync Windows 스토어 앱 클라이언트에 대 한 다단계 인증 지원을 추가 합니다. 사용자 이름 및 암호 외에도 스마트 카드나 Pin 등의 추가 인증 방법을 요구 하 여 Lync 모임에 로그인 할 때 외부 사용자를 인증할 수 있습니다. 다단계 인증을 사용 하도록 설정 하려면 Lync Server 2013에서 AD FS (Active Directory Federation Service) 페더레이션 서버를 배포 하 고 수동 인증을 사용 하도록 설정 합니다. AD FS가 구성 된 후 Lync 모임에 참가 하려고 하는 외부 사용자는 사용자 이름 및 암호 챌린지를 포함 하는 AD FS 다단계 인증 웹 페이지와 함께 구성 된 추가 인증 방법과 함께 제공 됩니다. .

<div class=" ">


> [!IMPORTANT]  
> Lync Windows 스토어 앱에 대 한 다단계 인증을 위해 ADFS를 구성 하려는 경우 다음과 같은 중요 한 사항을 고려해 야 합니다. 
> <UL>
> <LI>
> <P>Lync 서버 2013에 대 한 누적 업데이트가 포함 된 lync Server 2013:6 월 2013이 최소값에 필요 합니다. Lync 2013 데스크톱 클라이언트는 lync Server 2013 2013에 대 한 누적 업데이트가 필요 하지 않으므로 Lync 2013 클라이언트가 인증할 수 있으므로 수동 인증이 작동 하는 것 처럼 보일 수 있습니다. 그러나 Lync Windows 스토어 앱 클라이언트에 대 한 인증 프로세스가 완료 되지 않으며 알림 또는 오류 메시지가 표시 되지 않습니다.</P>
> <LI>
> <P>수동 인증이 유일한 인증 유형으로 제공 되도록 서버를 구성 해야 합니다.</P>
> <LI>
> <P>하드웨어 부하 분산 장치를 사용 하는 경우 Lync Windows 스토어 앱 클라이언트의 모든 요청이 동일한 프런트 엔드 서버에서 처리 되도록 부하 분산 장치에서 쿠키 지 속성을 사용 하도록 설정 합니다.</P>
> <LI>
> <P>Lync Server와 AD FS 서버 간에 신뢰 당사자 신뢰를 설정 하는 경우 Lync 모임의 최대 길이를 수용할 수 있는 긴 토큰 수명을 할당 합니다. 일반적으로 240 분의 토큰 수명은 충분 합니다.</P></LI></UL>



</div>

**다단계 인증을 구성 하려면**

1.  AD FS 페더레이션 서버 역할을 설치 합니다. 자세한 내용은의 Active Directory Federation Services 2.0 배포 가이드를 참조 하세요 <http://go.microsoft.com/fwlink/p/?linkid=267511>.

2.  Adfs에 대 한 인증서를 만듭니다. 자세한 내용은의 single sign-on 항목을 사용 하 여 AD FS 계획 및 배포의 "페더레이션 서버 인증서" 섹션을 참조 하세요 [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).

3.  Windows PowerShell 명령줄 인터페이스에서 다음 명령을 실행 합니다.
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  다음 명령을 실행 하 여 파트너 관계를 설정 합니다.
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  다음 신뢰 당사자 규칙을 설정 합니다.
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a>로그인을 방해할 수 있는 알려진 문제

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a>Lync Windows 스토어 앱을 실행 하는 디바이스에서 시간 및 날짜가 정확 하 게 설정 되지 않음

장치의 시간 설정은 서버의 시간 설정과 동기화 되어야 합니다. 이는 Microsoft Surface 같은 장치 및 도메인에 가입 되어 있지 않은 Windows RT를 실행 하는 다른 장치에 특히 중요 합니다. 시간 서버에서 이러한 장치에 대 한 시간을 자동으로 설정 하려면 장치의 관리자 권한 명령 프롬프트에서 다음 명령을 실행 합니다.
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a>Lync Windows 스토어 앱에서 Lync server 또는 서비스에 액세스할 수 없음

Lync Windows 스토어 앱은 4G LTE USB 모뎀과 같이 Windows 8을 실제 장치로 등록 하지 않는 네트워크 어댑터를 통해 Lync server 또는 서비스에 액세스 하지 못할 수 있습니다. 데스크톱 앱과 브라우저가 다른 서버 및 웹 사이트에 액세스할 수 있는 경우에도 Lync Windows 스토어 앱이이 문제를 발생 시킬 수 있습니다.

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a>Lync Windows 스토어 앱에서 Lync Server 2010 및 Office Communications Server 2007 R2 Edge 서버를 사용 하 여 로그인 할 수 없음

토폴로지가 Office Communications Server 2007 R2 Edge 서버로 제공 되는 Lync Server 2010으로 구성 된 경우 Lync Server의 누적 업데이트 2010:7 월 2013에 업데이트 된 토폴로지 작성기 버전을 실행 해야 합니다. 이전 버전의 토폴로지 작성기는 Office Communications Server 2007 Edge 서버에 필요한 매핑을 만들지 않으므로 Lync Windows 스토어 앱 클라이언트가 로그인 할 수 없습니다. 다음과 같은 단계가 필요 합니다.

1.  Lync server 2010 풀 및 Lync Server 2010 이사회에 2010 년 7 2013 월에 대 한 누적 업데이트를 설치 합니다.

2.  다음을 수행 하 여 외부 SIP 진입점이 Edge 서버 주소 라는 것을 나타내도록 Lync 자동 검색 구성을 업데이트 합니다.
    
    1.  Lync Server Management Shell을 엽니다.
    
    2.  다음 명령을 실행 합니다.
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a>인증서 이름 유효성 검사 오류로 인해 Lync Windows 스토어 앱에서 로그인 할 수 없음

최신 버전의 Lync Windows 스토어 앱을 실행 하 고 있지 않은 Office 365 사용자에 대 한 로그인 문제가 발생할 수 있습니다. 이 문제는 일반적으로 여러 도메인을 사용 하는 경우에 발생 합니다 (예를 들어 SIP URI가 **userA@domainZ.com** 되지만 Edge 서버는 **sip.domainX.com**). 이 문제를 해결 하려면 사용자가 Windows 8.1이 필요한 최신 버전의 Lync Windows 스토어 앱을 설치 해야 합니다.

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a>Lync Windows 스토어 앱 로그를 사용 하 여 문제 해결

장치에서 생성 된 로그를 사용 하 여 문제를 해결할 수 있습니다. 로그는 다음 폴더에 저장 됩니다.

% LocalAppData%\\패키지\\Microsoft. l8wekyb3d8bbwe nx\_\\localstate\\추적

사용자의 로그를 가져오기 전에 로깅이 설정 되어 있는지 확인 한 다음 사용자에 게 메모리에 저장 된 모든 정보가 하드 드라이브의 파일에도 저장 되도록 로그를 저장 하도록 요청 합니다.

**로깅을 설정 하려면**

1.  장치에서 Lync Windows 스토어 앱을 엽니다.

2.  화면 오른쪽에서 살짝 밉니다. 마우스를 사용 하는 경우 화면의 오른쪽 위 모서리를 가리킨 다음 마우스 포인터를 화면 아래로 이동 합니다.

3.  **설정을**선택 하 고 **옵션**을 선택한 다음 **진단 로그** 를 **On**으로 설정 합니다.

4.  이전에 **진단 로그가** 해제 된 경우 Lync를 다시 시작 해야 합니다. Lync를 다시 시작 하려면 다음 중 하나를 수행 합니다.
    
      - 장치를 다시 시작 합니다.
    
      - Lync 작업을 종료 하 고 앱을 다시 실행 합니다. 작업을 종료 하려면 Windows 작업 관리자를 열고 **Lync**를 선택한 다음 **작업 종료**를 탭 합니다. Lync가 목록에 없는 경우 **추가 세부 정보** 를 탭 하 고 **백그라운드 프로세스**에서 Lync를 찾습니다.

**로그를 저장 하려면**

1.  장치에서 Lync Windows 스토어 앱을 엽니다.

2.  로그인 해 보세요.

3.  화면 오른쪽에서 살짝 밉니다. 마우스를 사용 하는 경우 화면의 오른쪽 위 모서리를 가리킨 다음 마우스 포인터를 화면 아래로 이동 합니다.

4.  **설정을**선택 하 고 **정보**를 선택한 다음 **로그 저장**을 선택 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

