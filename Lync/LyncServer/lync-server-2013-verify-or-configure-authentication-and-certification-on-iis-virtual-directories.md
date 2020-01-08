---
title: 'Lync Server 2013: IIS 가상 디렉터리에 대한 인증 확인 또는 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ae692f788d906d01852990490ace01f67eebe63
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a>Lync Server 2013에서 IIS 가상 디렉터리에 대한 인증 확인 또는 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-05-25_

IIS (인터넷 정보 서비스) 가상 디렉터리에서 인증서를 구성 하거나 인증서가 올바르게 구성 되었는지 확인 하려면 다음 절차를 사용 합니다. 내부 Lync Server 풀과 선택적 디렉터 또는 디렉터 풀 서버에서 IIS를 실행 하는 각 서버에 대해 다음 절차를 수행 합니다.

<div>


> [!NOTE]  
> 다음 절차에서는 IIS의 모든 용도 Lync Server, 내부 웹 사이트 및 외부 웹 사이트에 사용 되는 조합 된 인증서를 요청 하는 절차를 정의 합니다. Lync Server 2010에서 인증서 요청, 가져오기, 할당을&nbsp;관리 하는 express 목적을 위한 Lync Server 관리 셸 Windows PowerShell cmdlet 집합을 도입 했습니다. 이 절차에서는 요청을 처리할 수 있는 내부적으로 배포 된 CA (인증 기관)가 있다고 가정 합니다. Lync Server 목적으로 공용 인증서를 사용 하거나 CA에 오프 라인 요청이 필요한 경우 – Output 매개 변수에 대 한 자세한 내용은이 항목의 자세한 구문을 참조 하세요. <A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">요청-CsCertificate</A>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a>IIS 가상 디렉터리에 대 한 인증 및 인증서를 구성 하려면

1.  다음을 성공적으로 완료 하려면 웹 서비스가 설치 된 컴퓨터 (프런트 엔드 서버 또는 디렉터)에 로그온 하 여 로컬 관리자 여야 합니다. 인증 기관이 조직의 인증 기관에 해당 하는 경우 인증서를 요청할 인증 기관에 대 한 **읽기** 및 **등록** 권한이 있어야 합니다. 오프 라인 인증서 요청을 구성 하 고 보내는 경우에는 인증 기관에 대 한 사용 권한이 필요 하지 않습니다.

2.  **시작**을 클릭 하 고 **모든 프로그램**을 선택한 다음 **관리 도구**를 선택 하 고 **IIS (인터넷 정보 서비스) 관리자**를 클릭 합니다.

3.  **IIS (인터넷 정보 서비스) 관리자**에서 **ServerName**을 선택 합니다. **기능 보기**에서 **서버 인증서**를 선택 하 고 마우스 오른쪽 단추를 클릭 한 다음 **기능 열기**를 선택 합니다.
    
    <div>
    

    > [!TIP]  
    > 서버 인증서 기능 보기에서 서버에 할당 된 인증서가 있는 경우 여기에 표시 됩니다. IIS에서 외부 웹 사이트의 요구 사항과 일치 하는 인증서가 있는 경우 해당 인증서를 다시 사용할 수 있습니다. 인증서를 보려면 인증서를 마우스 오른쪽 단추로 클릭 하 고 <STRONG>보기 ...</STRONG> 를 선택 합니다.

    
    </div>

4.  인증서를 요청 하는 프런트 엔드 서버 또는 디렉터에서 **시작**을 클릭 하 고 **모든 프로그램**, **Microsoft lync server 2013**을 차례로 선택한 다음 **Lync server Management Shell**을 클릭 합니다.

5.  Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Get-CsCertificate
    
    출력은 컴퓨터 개인 인증서 저장소에서 현재 서버에 있는 인증서의 목록입니다. 조합 된 인증서 (즉, 기본 웹 서비스 내부 및 웹 서비스 외부에 동일한 인증서를 사용 하는 경우)에는 Use 속성이 기본 인 Web서비스 내부 및 Webservice외부 Nal으로 채워집니다. 또한 손도장 속성은 각 사용 유형에 대해 동일 하 게 됩니다. 이 예제에는 Get-CsCertificate의 예제 출력이 나와 있습니다.
    
    현재 ![scert 상태에 대 한 CsCertificate 정보]가져오기-(images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "CsCertificate 정보 (현재 scert 상태)")

6.  Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    예를 들어 다음 예제와 같이 전체 명령이 표시 됩니다.
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > 기본적으로 CsCertificate에서는 주체 이름을 서버 또는 풀 이름으로 채우고, 주체 대체 이름의 항목을 서버 FQDN, 풀 FQDN, 간단한 URL Fqdn, 내부 및 외부 웹 서비스 Fqdn으로 채웁니다. 이는 배포의 토폴로지 문서를 참조 하 여 수행 됩니다. 누락 된 값이 있고 – Verbose 매개 변수를 지정한 경우 대체 이름에 대 한 계산 된 값과 실제 값이 서로 다르지만 사용자에 게 어떤 값이 누락 되지 않았음을 알리는 메시지가 표시 됩니다. Cmdlet이 참조 하는 계산 된 전체 값을 제공 합니다. 출력에 계산 된 대체 이름 문자열을 사용 하 여 모든 값을 포함할 새 인증서를 다시 요청 합니다.

    
    </div>
    
    (images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "요청-CsCertifica를 사용 하 여 인증서 요청의 CsCertifica 출력을") ![사용 하 여 인증서 요청의 출력]

7.  Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    예를 들어 다음 예제와 같이 전체 명령이 표시 됩니다.
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    CsCertificate cmdlet의 출력은 기본, Webservice외부의 Nal 및 Web서비스 내부 사용에 대해 동일한 인증서 (인증서의 손도장으로 식별 됨)를 할당 하는 것을 보여 줍니다.
    
    (images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Iis WebExt에서 CsCertificate") 의 ![iis webext 출력에 대 한 Set CsCertificate의 출력]

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a>IIS 가상 디렉터리에서 인증 및 인증서를 확인 하거나 구성 하려면

1.  **시작**을 클릭 하 고 **모든 프로그램**을 선택한 다음 **관리 도구**를 선택 하 고 **IIS (인터넷 정보 서비스) 관리자**를 클릭 합니다.

2.  **IIS (인터넷 정보 서비스) 관리자**에서 **ServerName**을 확장 한 다음 **사이트**를 확장 합니다.

3.  **Lync Server 외부 웹 사이트**를 마우스 오른쪽 단추로 클릭 한 다음 **바인딩 편집** 을 클릭 합니다.

4.  Https가 포트 4443와 연결 되어 있는지 확인 한 다음 **https**를 클릭 합니다.

5.  HTTPS 항목을 선택 하 고 **편집**을 클릭 한 다음 Lync Server WebServicesExternalCertificate이이 프로토콜에 바인딩되어 있는지 확인 합니다. CsCertificate cmdlet의 지문을 비교 하 여 필요한 인증서가 HTTPS 바인딩과 올바르게 연결 되어 있는지 확인 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Get-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

