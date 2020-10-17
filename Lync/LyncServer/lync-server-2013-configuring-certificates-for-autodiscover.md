---
title: 'Lync Server 2013: 자동 검색을 위한 인증서 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e97bb7d77bbd468fff18084ecc7d4da8c5feb7f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502115"
---
# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a>Lync Server 2013에서 자동 검색에 대 한 인증서 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-12-12_

디렉터 풀, 프런트 엔드 풀 및 역방향 프록시에 대 한 인증서에는 Lync 클라이언트와의 보안 연결을 지원 하기 위한 추가 주체 대체 이름 항목이 필요 합니다.

<div>


> [!NOTE]  
> <STRONG>Get-CsCertificate</STRONG> cmdlet을 사용하여 현재 지정된 인증서에 대한 정보를 볼 수 있습니다. 하지만 기본 보기에서는 인증서의 속성이 잘려서 표시되므로 SubjectAlternativeNames 속성의 모든 값이 표시되지 않습니다. <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate 및 <STRONG>Set-CsCertificate</STRONG> cmdlet을 사용하면 일부 정보를 보고 인증서를 요청 및 지정할 수 있습니다. 하지만 현재 인증서에 있는 SAN(주체 대체 이름)의 속성이 확실하지 않을 때는 최선의 방법이 아닙니다. 인증서 및 모든 속성 구성원을 보려면 <EM>MMC (Microsoft Management Console)</EM> 에서 인증서 스냅인을 사용 하거나 Lync Server 배포 마법사를 사용 하는 것이 좋습니다. Lync Server 배포 마법사에서 인증서 마법사를 사용 하 여 인증서 속성을 볼 수 있습니다. Lync Server 관리 셸 및 <EM>MMC (Microsoft Management Console)</EM> 를 사용 하 여 인증서를 보거나 요청 하 고 할당 하는 절차는 다음 절차에 자세히 설명 되어 있습니다. Lync Server 배포 마법사를 사용 하려면 자세한 내용은 여기에서 추가 디렉터 또는 디렉터 풀을 배포한 경우 ( <A href="lync-server-2013-configure-certificates-for-the-director.md">Lync server 2013에서 디렉터에 대 한 인증서 구성</A>)을 참조 하십시오. 프런트 엔드 서버 또는 프런트 엔드 풀에 대 한 자세한 내용은 <A href="lync-server-2013-configure-certificates-for-servers.md">Lync Server 2013에서 서버에 대 한 인증서 구성</A>를 참조 하십시오.<BR>이 절차의 시작 단계는 현재 인증서가 수행하는 역할을 확인하는 준비 단계입니다. 기본적으로 인증서에는 lyncdiscover가 포함 되지 않습니다. &lt; microsoft.rtc.management.xds.sipdomain object &gt; 또는 lyncdiscoverinternal &lt; &gt; 이전에 모바일 서비스를 설치 하지 않았거나 인증서를 미리 준비 하지 않은 경우 내부 도메인 이름 항목 이 절차에서는 예제 SIP 도메인 이름 'contoso.com' 및 예제 내부 도메인 이름 'contoso.net'을 사용합니다.<BR>Lync Server 2013 및 Lync Server 2010에 대 한 기본 인증서 구성은 용도 기본값 (웹 서비스를 제외한 모든 용도), WebServicesExternal 및 Web서비스 내부를 사용 하 여 단일 인증서 (이름이 ' Default ' 인 ' 기본값 ')를 사용할 수 있습니다. 선택적인 구성은 각 용도에 대해 별도의 인증서를 사용하는 것입니다. Lync Server 관리 셸 및 Windows PowerShell cmdlet을 사용 하거나 Lync Server 배포 마법사에서 인증서 마법사를 사용 하 여 인증서를 관리할 수 있습니다.



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Lync Server 관리 셸을 사용 하 여 새 주체 대체 이름을 사용 하 여 인증서를 업데이트 하려면

1.  로컬 관리자 권한이 있는 계정을 사용하여 컴퓨터에 로그온합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  서버에 지정된 인증서 및 인증서를 사용할 유형을 확인합니다. 다음 단계에서 업데이트된 인증서를 지정하려면 이 정보가 필요합니다. 정보를 확인하려면 명령줄에 다음을 입력합니다.
    
        Get-CsCertificate

4.  이전 단계의 출력에서 단일 인증서가 여러 용도로 지정되어 있는지 또는 각 용도에 따라 서로 다른 인증서가 지정되어 있는지를 확인합니다. 또한 Use 매개 변수에서 인증서 사용 방법을 확인하고, 표시된 인증서의 Thumbprint 매개 변수를 비교해 같은 인증서가 여러 용도로 사용되는지 확인합니다.

5.  명령줄에 다음을 입력하여 인증서를 업데이트합니다.
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    예를 들어 **Get-CsCertificate** cmdlet을 실행한 결과 용도가 각각 Default, WebServicesInternal, WebServicesExternal인 인증서가 표시되었는데 이들 인증서의 Thumbprint 값은 모두 같은 경우에는 명령줄에 다음을 입력합니다.
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **중요:**
    
    각 사용에 대해 별도의 인증서가 할당 된 경우 (각 인증서에 대해 손도장 값이 다른 경우) **set-cscertificate** cmdlet을 여러 형식으로 실행 하지 않는 것이 중요 합니다. 이 경우 각 사용에 대해 **set-cscertificate** cmdlet을 개별적으로 실행 합니다. 예제:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  인증서를 보려면 **시작**, **실행…** 을 차례로 클릭하고 MMC를 입력해서 Microsoft Management Console을 엽니다.

7.  MMC 메뉴에서 **파일**, **프로그램 스냅인 추가/제거…**, 인증서를 차례로 선택하고 **추가**를 클릭합니다. 프롬프트가 표시되면 **컴퓨터 계정**을 선택한 후 **다음**을 클릭합니다.

8.  인증서가이 컴퓨터에 있는 경우 **로컬 컴퓨터**를 선택 합니다. 인증서가 다른 컴퓨터에 있는 경우 **다른 컴퓨터**를 선택 하 고 컴퓨터의 정규화 된 도메인 이름을 입력 하거나 **찾아보기를** 클릭 **하 여 선택할 개체 이름을 입력**합니다 .에서 컴퓨터의 이름을 입력 합니다. **이름 확인**을 클릭합니다. 컴퓨터 이름이 확인 되 면 밑줄이 표시 됩니다. **확인**을 클릭 한 다음 **마침을**클릭 합니다. **확인** 을 클릭 하 여 선택 항목을 커밋하고 **스냅인 추가/제거** 대화 상자를 닫습니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 인증서가 콘솔에 표시 되지 않으면 사용자 또는 서비스를 선택 하지 않았는지 확인 합니다. 컴퓨터를 선택 해야 하며, 그렇지 않으면 probper 인증서를 찾을 수 없게 됩니다.

    
    </div>

9.  인증서의 속성을 보려면 **인증서**, **개인**을 차례로 확장하고 **인증서**를 선택합니다. 보려는 인증서를 선택하고 인증서를 마우스 오른쪽 단추로 클릭한 후 **열기**를 선택합니다.

10. **인증서** 보기에서 **자세히**를 선택합니다. 여기에서는 **주체**를 선택하여 인증서 주체 이름을 선택할 수 있고 지정된 주체 이름 및 연결된 속성이 표시됩니다.

11. 지정된 주체 대체 이름을 보려면 **주체 대체 이름**을 선택합니다. 지정된 모든 주체 대체 이름이 표시됩니다. 속성에서 발견되는 주체 대체 이름은 기본적으로 **DNS 이름** 유형입니다. 다음과 같은 멤버가 표시됩니다(모든 멤버가 DNS 호스트(A 또는 IPv6인 경우 AAAA) 레코드에 표시된 대로 정규화된 도메인 이름으로 표시됨).
    
      - 이 풀의 풀 이름 또는 단일 서버 이름(풀이 아닌 경우)
    
      - 인증서가 지정된 서버 이름
    
      - 단순 URL 레코드(일반적으로 meet 및 dialin)
    
      - 웹 서비스 내부 및 웹 서비스 외부 이름 (예: webpool01.contoso.net, webpool01.contoso.com)-토폴로지 작성기 및 재정의를 사용한 웹 서비스 선택에 대 한 선택 사항에 따라 달라 집니다.
    
      - 이미 지정 된 경우 lyncdiscover입니다.\<sipdomain\> 및 lyncdiscoverinternal입니다.\<sipdomain\> 레코드.
    
    lyncdiscover 및 lyncdiscoverinternal SAN 항목이 있는 경우 마지막 항목이 가장 중요한 항목입니다.
    
    이러한 정보를 준비했으면 인증서 보기 및 MMC를 닫을 수 있습니다.

12. 자동 검색 서비스인 경우 lyncdiscover를 의미 합니다. \> 도메인 이름 \> 및 lyncdiscoverinternal.\<domain name\> (외부 또는 내부 인증서 인지에 따름) 주체 대체 이름이 누락 되었고 기본, Web서비스 내부 및 WebServiceExternal 형식에 대해 단일 기본 인증서를 사용 하는 경우 다음을 수행 합니다.
    
      - Lync Server 관리 셸 명령줄 프롬프트에 다음을 입력 합니다.
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        SIP 도메인이 많은 경우에는 새 AllSipDomain 매개 변수를 사용할 수 없습니다. 대신, DomainName 매개 변수를 사용 해야 합니다. DomainName 매개 변수를 사용 하는 경우 lyncdiscoverinternal 및 lyncdiscover record에 대해 FQDN을 정의 해야 합니다. 예제:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 인증서를 지정하려면 다음을 입력합니다.
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        "Thumbprint"는 새로 발급된 인증서에 표시되는 지문입니다.

13. 기본, WebServicesInternal 및 WebServicesExternal에 대해 개별 인증서를 사용할 때 내부 자동 검색 주체 대체 이름이 누락된 경우 다음을 수행합니다.
    
      - Lync Server 관리 셸 명령줄 프롬프트에 다음을 입력 합니다.
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        SIP 도메인이 여러 개인 경우 새 AllSipDomain 매개 변수는 사용할 수 없으며 대신 DomainName 매개 변수를 사용해야 합니다. DomainName 매개 변수를 사용할 때는 SIP 도메인 FQDN에 대해 적절한 접두사를 사용해야 합니다. 예를 들면 다음과 같습니다.
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 누락된 외부 자동 검색 주체 대체 이름에 대해 명령줄에 다음을 입력합니다.
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        SIP 도메인이 여러 개인 경우 새 AllSipDomain 매개 변수는 사용할 수 없으며 대신 DomainName 매개 변수를 사용해야 합니다. DomainName 매개 변수를 사용할 때는 SIP 도메인 FQDN에 대해 적절한 접두사를 사용해야 합니다. 예를 들면 다음과 같습니다.
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - 개별 인증서 유형을 지정하려면 다음을 입력합니다.
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        "Thumbprint"는 새로 발급된 인증서에 표시되는 지문입니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

