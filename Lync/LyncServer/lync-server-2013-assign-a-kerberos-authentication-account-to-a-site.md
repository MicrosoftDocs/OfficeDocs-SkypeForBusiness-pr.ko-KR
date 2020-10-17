---
title: 'Lync Server 2013: 사이트에 Kerberos 인증 계정 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6137224f313238dae33462298931167ba7bb810
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529525"
---
# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a>Lync Server 2013에서 사이트에 Kerberos 인증 계정 할당

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2017-04-18_

이 절차를 성공적으로 완료하려면 RTCUniversalServerAdmins 그룹의 구성원인 사용자로 로그온해야 합니다.

Kerberos 계정을 만든 후 이를 사이트에 지정해야 합니다. Active Directory 사이트가 아니라 Lync Server 2013 사이트입니다. 배포별로 여러 개의 Kerberos 인증 계정을 만들 수 있지만 사이트에는 계정을 하나만 지정할 수 있습니다. 다음 절차에 따라 이전에 만든 Kerberos 인증 계정을 사이트에 지정하십시오. Kerberos 계정을 만드는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 kerberos 인증 계정 만들기](lync-server-2013-create-a-kerberos-authentication-account.md)를 참조 하십시오.

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a>Kerberos 인증 계정을 사이트에 지정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 Lync Server 2013 또는 관리 도구가 설치 된 컴퓨터에 있는 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령줄에서 다음의 두 명령을 실행합니다.
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    예:
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > 도메인\사용자 형식을 사용하여 UserAccount 매개 변수를 지정해야 합니다. User@Domain.extension 형식은 Kerberos 인증 용도로 만든 컴퓨터 개체를 나타내는 데 사용할 수 없습니다.

    
    </div>

4.  **선택**: [Lync Server 2013에서 웹 서비스 URL을 변경 하는](lync-server-2013-change-the-web-services-url.md)경우 WebServices에 대 한 재정의 FQDN (정규화 된 도메인 이름)을 구성 했을 수 있습니다. 이러한 경우에는이 FQDN에 대 한 SPN도 추가 해야 합니다. 예를 들어 FQDN이 webservices 인 경우 다음을 실행 합니다.
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > 계정 추가 또는 계정 제거와 같은 Kerberos 인증을 변경한 후에는 Lync Server 관리 셸 명령 프롬프트에서 <STRONG>Enable-enable-cstopology</STRONG> 을 실행 해야 합니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

