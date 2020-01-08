---
title: 'Lync Server 2013: 자동 검색을 위한 인증서 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d0270aa76adb7cef2a6da8f6a4f9cb6db090e78
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a>Lync Server 2013에서 자동 검색을 위한 인증서 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-12-12_

디렉터 풀, 프런트 엔드 풀 및 역방향 프록시에 대 한 인증서는 Lync 클라이언트와의 보안 연결을 지원 하기 위해 추가 주제 대체 이름 항목이 필요 합니다.

<div>


> [!NOTE]  
> <STRONG>Get-CsCertificate</STRONG> cmdlet을 사용 하 여 현재 할당 된 인증서에 대 한 정보를 볼 수 있습니다. 그러나 기본 보기에서는 인증서의 속성을 자르고 SubjectAlternativeNames 속성에 모든 값이 표시 되지 않습니다. <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate 및 <STRONG>Set CsCertificate</STRONG> cmdlet을 사용 하 여 일부 정보를 보고 인증서를 요청 하 고 할당할 수 있습니다. 그러나 현재 인증서의 SAN (주체 대체 이름) 속성에 대해 잘 모르는 경우에는 사용할 수 없습니다. 인증서 및 모든 속성 구성원을 보려면 <EM>MMC (Microsoft Management Console)</EM> 에서 인증서 스냅인을 사용 하거나 Lync Server 배포 마법사를 사용 하는 것이 좋습니다. Lync Server 배포 마법사에서 인증서 마법사를 사용 하 여 인증서 속성을 볼 수 있습니다. Lync Server 관리 셸과 <EM>MMC (Microsoft Management Console)</EM> 를 사용 하 여 인증서를 보거나 지정 하는 절차는 다음 절차에 자세히 설명 되어 있습니다. Lync Server 배포 마법사를 사용 하려면 옵션 디렉터 또는 디렉터 풀을 배포한 경우 여기에서 세부 정보를 참조 하세요. <A href="lync-server-2013-configure-certificates-for-the-director.md">Lync server 2013에서 디렉터에 대 한 인증서를 구성</A>합니다. 프런트 엔드 서버 또는 프런트 엔드 풀에 대 한 자세한 내용은 다음을 참조 하세요. <A href="lync-server-2013-configure-certificates-for-servers.md">Lync Server 2013에서 서버의 인증서를 구성</A>합니다.<BR>이 절차의 초기 단계는 현재 인증서가 재생 되는 역할을 표시 하는 준비 단계입니다. 기본적으로 인증서에는 lyncdiscover이 없습니다. &lt;sipdomain&gt; 또는 lyncdiscoverinternal. &lt;이전에 모바일&gt; 서비스를 설치 하지 않았거나 인증서를 미리 준비한 경우가 아니면 내부 도메인 이름 항목이 표시 됩니다. 이 절차에서는 예제 SIP 도메인 이름 ' contoso.com ' 및 내부 도메인 이름 ' contoso.net '의 예를 사용 합니다.<BR>Lync Server 2013 및 Lync Server 2010의 기본 인증서 구성은 기본 (웹 서비스를 제외한 모든 용도), Webservice외부 Nal 및 Web서비스 내부에 대 한 단일 인증서 (' Default ')를 사용 하는 것입니다. 선택적 구성은 각 용도에 대해 별도의 인증서를 사용 하는 것입니다. 인증서는 Lync Server 관리 셸 및 Windows PowerShell cmdlet을 사용 하거나 Lync Server 배포 마법사의 인증서 마법사를 사용 하 여 관리할 수 있습니다.



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Lync Server Management Shell을 사용 하 여 새 주체의 대체 이름을 사용 하 여 인증서를 업데이트 하려면

1.  로컬 관리자 권한 및 사용 권한이 있는 계정을 사용 하 여 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  서버에 지정 된 인증서 및 사용 유형에 대 한 자세한 정보를 확인 합니다. 업데이트 된 인증서를 할당 하려면 다음 단계에서이 정보가 필요 합니다. 명령줄에 다음을 입력 합니다.
    
        Get-CsCertificate

4.  이전 단계의 출력을 확인 하 여 단일 인증서가 여러 용도로 지정 되었는지 또는 각 용도에 대해 다른 인증서가 지정 되었는지 확인 합니다. 사용 매개 변수를 확인 하 여 인증서 사용 방법을 확인 합니다. 표시 된 인증서의 손도장 매개 변수를 비교 하 여 동일한 인증서가 여러 용도로 사용 되 고 있는지 확인 합니다.

5.  인증서를 업데이트 합니다. 명령줄에 다음을 입력 합니다.
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    예를 들어 CsCertificate cmdlet이 기본적으로 사용 하는 인증서를 표시 하는 경우, 그 밖의 Web서비스 사용, 그리고 Webservice외부를 사용 하는 다른 경우와 모두 동일한 손도장 (Thumbprint **)** 값이 동일한 경우 명령줄에 다음을 입력 합니다.
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **중요:**
    
    각 사용에 대해 별도의 인증서가 할당 되는 경우 (손도장 값은 각 인증서에 대해 다르므로) **CsCertificate** cmdlet을 여러 형식으로 실행 하지 않는 것이 중요 합니다. 이 경우 각 사용에 대해 **Set-CsCertificate** cmdlet을 개별적으로 실행 합니다. 예를 들면 다음과 같습니다.
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  인증서를 보려면 **시작**을 클릭 하 고 **실행 ...** 을 클릭 합니다. MMC를 입력 하 여 Microsoft Management Console을 엽니다.

7.  MMC 메뉴에서 **파일**을 선택 하 고, **스냅인 추가/제거**를 선택 하 고, 인증서를 선택 합니다. **추가**를 클릭 합니다. 메시지가 표시 되 면 **컴퓨터 계정을**선택 하 고 **다음**을 클릭 합니다.

8.  인증서가이 컴퓨터에 있는 경우 **로컬 컴퓨터**를 선택 합니다. 인증서가 다른 컴퓨터에 있는 경우 **다른 컴퓨터**를 선택 하 고 컴퓨터의 정규화 된 도메인 이름을 입력 하거나 **찾아보기를** 클릭 **하 여 선택할 개체 이름을 입력 하**고 컴퓨터의 이름을 입력 합니다. **이름 확인**을 클릭 합니다. 컴퓨터의 이름이 확인 되 면 밑줄로 표시 됩니다. **확인**을 클릭 한 다음 **마침을**클릭 합니다. **확인** 을 클릭 하 여 선택 항목을 커밋하고 **스냅인 추가/제거** 대화 상자를 닫습니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 콘솔에 인증서가 표시 되지 않으면 사용자 또는 서비스를 선택 하지 않았는지 확인 합니다. 컴퓨터를 선택 해야 하며, probper 인증서를 찾을 수 없게 됩니다.

    
    </div>

9.  인증서의 속성을 보려면 **인증서**를 확장 하 고, **개인**을 확장 하 고, **인증서**를 선택 합니다. 보려는 인증서를 선택 하 고, 인증서를 마우스 오른쪽 단추로 클릭 하 고 **열기**를 선택 합니다.

10. **인증서** 보기에서 **세부 정보**를 선택 합니다. 여기에서 **주체** 를 선택 하 고 지정 된 제목 이름과 연결 된 속성이 표시 되도록 하 여 인증서 주체 이름을 선택할 수 있습니다.

11. 지정 된 제목 대체 이름을 보려면 **제목 대체 이름을**선택 합니다. 지정 된 모든 제목 대체 이름이 표시 됩니다. 속성에 있는 주체 대체 이름은 기본적으로 **DNS 이름** 유형입니다. DNS 호스트 (A 또는 IPv6 AAAA) 레코드에 표시 되는 것으로 정규화 된 도메인 이름이 되어야 하는 다음 구성원이 표시 되어야 합니다.
    
      - 이 풀의 풀 이름 또는 풀이 아닌 경우 단일 서버 이름
    
      - 인증서가 할당 된 서버 이름
    
      - 간단한 URL 레코드, 일반적으로 모임 및 전화 접속
    
      - 웹 서비스 내부 및 웹 서비스 외부 이름 (예: webpool01.contoso.net, webpool01.contoso.com)-토폴로지 작성기 및 재정의 된 웹 서비스 선택 항목을 기준으로 합니다.
    
      - 이미 할당 된 경우 lyncdiscover. \<sipdomain\> 및 lyncdiscoverinternal. \<레코드\> 를 sipdomain.
    
    마지막 항목은 사용자가 가장 관심을 가지 며, lyncdiscover 및 lyncdiscoverinternal SAN 항목이 있는 경우에 해당 합니다.
    
    이 정보가 있으면 인증서 보기와 MMC를 닫을 수 있습니다.

12. 자동 검색 서비스 인 경우 lyncdiscover를 의미 합니다. \>도메인 이름\> 및 lyncdiscoverinternal. \<도메인 이름\> (외부 또는 내부 인증서 인지 여부) 제목 대체 이름이 없고 기본 인 Web서비스 내부 및 webserviceexternal 형식에 대해 단일 기본 인증서를 사용 하 고 있는 경우 다음을 수행 합니다.
    
      - Lync Server 관리 셸 명령줄 프롬프트에 다음을 입력 합니다.
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        SIP 도메인이 많은 경우 새 AllSipDomain 매개 변수를 사용할 수 없습니다. 대신 DomainName 매개 변수를 사용 해야 합니다. DomainName 매개 변수를 사용 하는 경우 lyncdiscoverinternal 및 lyncdiscover 레코드에 대 한 FQDN을 정의 해야 합니다. 예를 들면 다음과 같습니다.
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 인증서를 할당 하려면 다음을 입력 합니다.
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        여기서 "지문"은 새로 발급 된 인증서에 대해 표시 되는 지문입니다.

13. 기본, Web서비스 내부 및 Webservice외부 이름에 별도의 인증서를 사용 하는 경우 내부 자동 검색 주체의 대체 이름이 없는 경우 다음을 수행 합니다.
    
      - Lync Server 관리 셸 명령줄 프롬프트에 다음을 입력 합니다.
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        SIP 도메인이 많은 경우 새 AllSipDomain 매개 변수를 사용할 수 없습니다. 대신 DomainName 매개 변수를 사용 해야 합니다. DomainName 매개 변수를 사용 하는 경우 SIP 도메인 FQDN에 적절 한 접두사를 사용 해야 합니다. 예를 들면 다음과 같습니다.
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 외부 자동 검색 주체의 대체 이름이 없는 경우 명령줄에 다음을 입력 합니다.
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        SIP 도메인이 많은 경우 새 AllSipDomain 매개 변수를 사용할 수 없습니다. 대신 DomainName 매개 변수를 사용 해야 합니다. DomainName 매개 변수를 사용 하는 경우 SIP 도메인 FQDN에 적절 한 접두사를 사용 해야 합니다. 예를 들면 다음과 같습니다.
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - 개별 인증서 종류를 할당 하려면 다음을 입력 합니다.
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        여기서 "지문"은 새로 발급 된 개별 인증서에 대해 표시 되는 지문입니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

