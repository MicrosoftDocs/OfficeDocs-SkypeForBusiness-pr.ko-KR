---
title: 'Lync Server 2013: IIS 가상 디렉터리에 대 한 인증 및 인증 확인 또는 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28011a5eb436096d0d8486a6f05ac9024ac388d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a>Lync Server 2013의 IIS 가상 디렉터리에 대 한 인증 및 인증 확인 또는 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-05-25_

다음 절차에 따라 IIS (인터넷 정보 서비스) 가상 디렉터리에서 인증서를 구성 하거나 인증서가 올바르게 구성 되었는지 확인 합니다. 내부 Lync Server 풀 및 선택 사항인 디렉터 또는 디렉터 풀 서버에서 IIS를 실행 하는 각 서버에 대해 다음 절차를 수행 합니다.

<div>


> [!NOTE]  
> 다음 절차에서는 IIS에서 모든 용도의 Lync Server, 내부 웹 사이트 및 외부 웹 사이트에 사용 되는 결합 된 인증서를 요청 하는 절차를 정의 합니다. Lync Server 2010에서는 인증서 요청, 가져오기 및 할당을&nbsp;관리 하는 Express 용도의 Lync Server 관리 셸 Windows PowerShell cmdlet 집합이 도입 되었습니다. 이 절차에서는 내부적으로 배포된 CA(인증 기관)가 요청을 처리할 수 있다고 가정합니다. Lync Server 목적으로 공용 인증서를 사용 하거나 CA에 오프 라인 요청이 필요한 경우 – Output 매개 변수에 대 한 자세한 내용은이 항목의 자세한 구문을 참조 하십시오. <A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">요청-Set-cscertificate</A>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a>IIS 가상 디렉터리에서 인증 및 인증서를 구성하려면

1.  다음을 성공적으로 완료 하려면 웹 서비스가 설치 되어 있고 로컬 관리자 인 컴퓨터에 로그온 되어 있어야 합니다. 인증 기관이 조직의 인증 기관인 경우 인증서를 요청할 인증 기관에 대해서 **읽기** 및 **등록** 권한이 있어야 합니다. 오프라인 인증서 요청을 구성하고 보낼 경우에는 인증 기관에 대한 권한이 필요하지 않습니다.

2.  **시작**을 클릭하고 **모든 프로그램**, **관리 도구**를 차례로 선택한 후 **IIS(인터넷 정보 서비스) 관리자**를 클릭합니다.

3.  **IIS(인터넷 정보 서비스) 관리자**에서 **ServerName**을 선택합니다. **기능 보기**에서 **서버 인증서**를 선택하고 마우스 오른쪽 단추로 클릭한 후 **기능 열기**를 선택합니다.
    
    <div>
    

    > [!TIP]  
    > 서버 인증서 기능 보기에서 서버에 지정된 인증서가 있으면 여기에 표시됩니다. IIS에서 외부 웹 사이트에 대한 요구 사항과 일치하는 인증서가 있으면 해당 인증서를 다시 사용할 수 있습니다. 인증서를 보려면 인증서를 마우스 오른쪽 단추로 클릭하고 <STRONG>보기…</STRONG>를 선택합니다.

    
    </div>

4.  인증서를 요청 하는 프런트 엔드 서버 또는 디렉터에서 **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 선택한 다음 **Lync server 관리 셸을**클릭 합니다.

5.  Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Get-CsCertificate
    
    컴퓨터 개인 인증서 저장소의 현재 서버에 있는 인증서 목록이 출력됩니다. 조합된 인증서(즉, 기본값, 내부 웹 서비스 및 외부 웹 서비스가 동일한 인증서 사용)에서는 Use 속성에 기본값, WebServicesInternal 및 WebServicesExternal이 채워집니다. 또한 Thumbprint 속성은 각 Use 유형에 대해 동일합니다. 이 예에서는 Get-CsCertificate의 출력 예를 보여줍니다.
    
    ![Set-cscertificate 현재 scert 상태에 대 한 정보](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Set-cscertificate 현재 scert 상태에 대 한 정보")

6.  Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    전체 명령은 다음 예와 같이 표시됩니다.
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > 기본적으로 Request-CsCertificate는 제목 이름을 서버 또는 풀 이름으로 채우고 제목 대체 이름의 항목에 서버 FQDN, 풀 FQDN, 단순 URL FQDN, 내부 및 외부 웹 서비스 FQDN을 채웁니다. 이러한 작업은 배포에서 토폴로지 문서를 참조하여 수행됩니다. 값이 누락되었고 –Verbose 매개 변수를 지정한 경우 대체 이름에 대해 계산된 값 및 실제 값이 다르다는 알림이 표시되지만 어느 값이 누락되었는지는 표시되지 않습니다. cmdlet이 참조하는 전체 계산된 값을 제공합니다. 모든 값을 포함하는 새 인증서를 다시 요청하려면 출력에 있는 계산된 대체 이름 문자열을 사용합니다.

    
    </div>
    
    ![요청을 사용 하 여 인증서 요청의 출력 CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "요청을 사용 하 여 인증서 요청의 출력 CsCertifica")

7.  Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    전체 명령은 다음 예와 같이 표시됩니다.
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    Set-CsCertificate cmdlet의 출력에는 기본값, WebServicesExternal 및 WebServicesInternal 사용을 위해 동일 인증서(인증서 지문으로 식별)가 지정된 것으로 표시됩니다.
    
    ![IIS WebExt에서 Set-cscertificate의 출력](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "IIS WebExt에서 Set-cscertificate의 출력")

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a>IIS 가상 디렉터리에서 인증 및 인증서를 확인하거나 구성하려면

1.  **시작**을 클릭하고 **모든 프로그램**, **관리 도구**를 차례로 선택한 후 **IIS(인터넷 정보 서비스) 관리자**를 클릭합니다.

2.  **IIS (인터넷 정보 서비스) 관리자**에서 **ServerName**을 확장 하 고 **사이트**를 확장 합니다.

3.  **Lync Server External Web Site**를 마우스 오른쪽 단추로 클릭하고 **바인딩 편집**을 클릭합니다.

4.  https가 포트 4443과 연결되어 있는지 확인하고 **https**를 클릭합니다.

5.  HTTPS 항목을 선택 하 고 **편집**을 클릭 한 후 Lync Server WebServicesExternalCertificate가이 프로토콜에 바인딩되어 있는지 확인 합니다. Set-CsCertificate cmdlet의 지문을 비교하여 예상 인증서가 HTTPS 바인딩과 올바르게 연결되어 있는지 확인합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Set-cscertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[Set-cscertificate](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

