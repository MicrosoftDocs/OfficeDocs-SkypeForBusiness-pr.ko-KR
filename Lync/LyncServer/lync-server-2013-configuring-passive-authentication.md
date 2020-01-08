---
title: 'Lync Server 2013: 수동 인증 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 590a196ca0e34c0c063b10703c7edd131eb82c50
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40985784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a>Lync Server 2013 수동 인증 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-07-11_

다음 섹션에서는 수동 인증을 지원 하도록 Lync Server 2013을 누적 업데이트로 구성 하는 방법을 설명 합니다: 7 월 2013. 2 단계 인증을 사용 하도록 설정 된 Lync 사용자는 실제 또는 가상 스마트 카드와 누적 업데이트를 사용 하 여 Lync 2013 (2013 클라이언트: 7 월)로 로그인 하는 데 유효한 PIN이 필요 합니다.

<div class="">


> [!NOTE]  
> 고객은 서비스 수준에서 등록자 및 웹 서비스에 대 한 수동 인증을 사용 하도록 설정 하는 것이 좋습니다. 전역 수준에서 등록자 및 웹 서비스에 대 한 수동 인증이 사용 하도록 설정 되어 있는 경우, Lync 2013를 사용 하 여 로그인 하지 않은 사용자에 대해 7 월 2013 클라이언트 데스크톱 클라이언트의 누적 업데이트로 인해 조직 전체 인증 오류가 발생할 수 있습니다.



</div>

<div>

## <a name="web-service-configuration"></a>웹 서비스 구성

다음 단계에서는 수동 인증을 사용 하도록 설정 되는 디렉터, 엔터프라이즈 풀 및 Standard Edition 서버에 대 한 사용자 지정 웹 서비스 구성을 만드는 방법에 대해 설명 합니다.

**사용자 지정 웹 서비스 구성을 만들려면**

1.  Lync 관리자 계정을 사용 하는 7 월 2013 프런트 엔드 서버에 누적 업데이트를 사용 하 여 Lync Server 2013에 로그인 합니다.

2.  Lync Server 2013 관리 셸을 시작 합니다.

3.  Lync Server Management Shell 명령줄에서 다음 명령을 실행 하 여 수동 인증에 사용할 각 디렉터, 엔터프라이즈 풀 및 Standard Edition Server에 대 한 새 웹 서비스 구성을 만듭니다.
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > WsFedPassiveMetadataUri FQDN에 대 한 값은 AD FS 2.0 서버의 페더레이션 서비스 이름입니다. 페더레이션 서비스 이름 값은 탐색 창에서 <STRONG>서비스</STRONG> 를 마우스 오른쪽 단추로 클릭 한 다음 <STRONG>페더레이션 서비스 속성 편집</STRONG>을 선택 하 여 AD FS 2.0 관리 콘솔에서 찾을 수 있습니다.

    
    </div>

4.  다음 명령을 실행 하 여 UseWsFedPassiveAuth 및 WsFedPassiveMetadataUri 값이 올바르게 설정 되었는지 확인 합니다.
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  클라이언트의 경우 Passive 인증은 webticket 인증에 가장 선호 하는 인증 방법입니다. 수동 인증을 사용 하도록 설정 되는 모든 디렉터, Enterprise 풀 및 Standard Edition 서버에 대해 다음 명령을 실행 하 여 Lync 웹 서비스에서 다른 모든 인증 유형을 사용 하지 않도록 설정 해야 합니다.
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  다음 명령을 실행 하 여 다른 모든 인증 유형이 비활성화 되었는지 확인 합니다.
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a>프록시 구성

Lync 웹 서비스에 대해 인증서 인증을 사용할 수 없는 경우 Lync 클라이언트는 Kerberos 또는 NTLM 등의 덜 기본 인증 형식을 사용 하 여 등록자 서비스에 인증 합니다. Lync 클라이언트가 webticket을 검색할 수 있도록 인증서 인증이 여전히 필요 하지만, 등록 기관 서비스에 대해 Kerberos 및 NTLM을 사용 하지 않도록 설정 해야 합니다.

다음 단계에서는 수동 인증을 사용 하도록 설정 되는 Edge 풀, 엔터프라이즈 풀 및 Standard Edition 서버에 대 한 사용자 지정 프록시 구성을 만드는 방법을 설명 합니다.

**사용자 지정 프록시 구성을 만들려면**

1.  Lync Server Management Shell 명령줄에서 다음을 실행 하 여 수동 인증에 사용할 수 있는 누적 업데이트 인 각 Lync Server 2013에 대 한 새 프록시 구성 만들기: 7 월 2013 Edge 풀, 엔터프라이즈 풀, Standard Edition server 다음 명령을 실행 합니다.
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  다음 명령을 실행 하 여 다른 모든 프록시 인증 유형이 비활성화 되었는지 확인 합니다.
    ```powershell
    Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
     ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

