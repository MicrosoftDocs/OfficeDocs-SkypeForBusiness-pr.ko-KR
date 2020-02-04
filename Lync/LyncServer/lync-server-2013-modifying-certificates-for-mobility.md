---
title: 'Lync Server 2013: 모바일 기능용으로 인증서 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 150dc8c7b4021e1e2c7ccab6ccc71823c01c388e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a>Lync Server 2013에서 모바일 기능용으로 인증서 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-06-20_

Lync 환경과 모바일 클라이언트 간의 보안 연결을 지원 하기 위해 디렉터 풀, 프런트 엔드 풀 및 리버스 프록시의 SSL (Secure Socket Layer) 인증서를 일부 추가 주체 대체 이름으로 업데이트 해야 합니다 ( SAN) 항목이 있습니다. 이동성의 인증서 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 모바일 기능에 대 한 기술 요구](lync-server-2013-technical-requirements-for-mobility.md)사항 섹션을 참조 하 고, 기본적으로 인증 기관에서 추가 SAN 항목이 포함 된 새 인증서를 가져온 다음이 문서의 단계를 사용 하 여 해당 인증서를 추가 해야 합니다.

시작 하기 전에, 일반적으로 인증서에 이미 존재 하는 주체의 대체 이름을 알고 있는 것이 좋습니다. 이미 구성 되어 있는 항목이 확실 하지 않은 경우에는 다양 한 방법으로 확인할 수 있습니다. 이 옵션은 **CsCertificate** 및 기타 PowerShell 명령을 실행 하 여이 정보를 확인 하는 반면 (아래에서 살펴보겠습니다) 기본적으로 데이터는 잘릴 수 있으므로 필요한 속성을 모두 볼 수 없게 됩니다. 인증서와 모든 해당 속성이 제대로 표시 되도록 하려면 MMC (Microsoft Management Console)로 이동 하 여 인증서 스냅인을 로드 하거나 (아래에서 설명) Lync Server 배포 마법사를 확인 하기만 하면 됩니다.

위에서 설명한 대로 다음 단계는 Lync Server 관리 셸과 MMC를 사용 하 여 인증서를 업데이트 하는 과정을 안내 합니다. 이를 대신 하 여 Lync Server 배포 마법사에서 인증서 마법사를 사용 하는 경우에는 (없는 경우) 디렉터 또는 디렉터 풀에 대해 [Lync Server 2013에서 디렉터에 대 한 인증서 구성을](lync-server-2013-configure-certificates-for-the-director.md) 확인할 수 있습니다 (없을 수도 있음). 프런트 엔드 서버 또는 프런트 엔드 풀의 경우 [Lync Server 2013에서 서버에 대 한 인증서 구성을](lync-server-2013-configure-certificates-for-servers.md)확인 해야 합니다.

마지막으로 고려해 야 할 한 가지 사항은 Lync Server 2013 환경에 기본 인증서가 하나 있거나 기본 (웹 서비스를 제외한 모든 항목), Webservice외부 Nal 및 Web서비스 내부에 대 한 별도의 인증서가 있을 수 있다는 것입니다. 모든 구성과 관련 하 여이 단계를 수행 하는 데 도움이 될 것입니다.

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Lync Server Management Shell을 사용 하 여 새 주체의 대체 이름을 사용 하 여 인증서를 업데이트 하려면

1.  로컬 관리자 권한이 있는 계정을 사용 하 여 Lync Server 2013 서버에 로그온 해야 합니다. 또한 12 단계 이상에서 PowerShell **요청-CsCertificate** 를 실행 하는 경우에는 지정 된 CA (인증 기관)에 대 한 권한이 계정에 있어야 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  업데이트 된 인증서를 할당할 수 있으려면 먼저 서버에 할당 된 인증서와 사용 유형을 확인 해야 합니다. 명령줄에 다음을 입력 합니다.
    
        Get-CsCertificate

4.  이전 단계의 출력을 검토 하 여 단일 인증서가 여러 용도로 지정 되었는지 또는 각 용도에 대해 다른 인증서가 지정 되었는지 확인 합니다. 사용 하는 매개 변수를 확인 하 여 인증서를 사용 하는 방법을 확인 합니다. 표시 된 인증서의 손도장 매개 변수를 비교 하 여 동일한 인증서가 여러 용도로 사용 되 고 있는지 확인 합니다. 지문 매개 변수에 대 한 시각을 유지 합니다.

5.  인증서를 업데이트 합니다. 명령줄에 다음을 입력 합니다.
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    예를 들어 **CsCertificate** Cmdlet이 기본적으로 사용 하는 인증서를 표시 하는 경우, 다른 사용자와 함께 web서비스를 사용 하 고 다른 작업을 수행 하 고 있으며,이 둘이 모두 동일한 손도장 (Thumbprint) 값을가지고 있으며, 명령줄에서 다음과 같이 입력 해야 합니다.
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **중요:**
    
    각 사용에 대해 별도의 인증서가 할당 되는 경우 (위에서 선택한 손도장 값은 각 인증서에 따라 다름) 위의 예와 같이 여러 형식으로 **CsCertificate** cmdlet을 실행 **하지** 않는 것이 중요 합니다. 이 경우 각 사용에 대해 **Set-CsCertificate** cmdlet을 개별적으로 실행 합니다. 예를 들면 다음과 같습니다.
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  인증서 (또는 인증서)를 보려면 **시작**을 클릭 하 고 **실행 ...** 을 클릭 합니다. MMC를 입력 하 여 Microsoft Management Console을 엽니다.

7.  MMC 메뉴에서 **파일**을 선택 하 고, **스냅인 추가/제거**를 선택 하 고, 인증서를 선택 합니다. **추가**를 클릭 합니다. 메시지가 표시 되 면 **컴퓨터 계정을**선택 하 고 **다음**을 클릭 합니다.

8.  인증서가 있는 서버인 경우 **로컬 컴퓨터**를 선택 합니다. 다른 컴퓨터에 인증서가 있는 경우 **다른 컴퓨터**를 선택 하 고 컴퓨터의 정규화 된 도메인 이름에 입력 하거나, **찾아보기를** 클릭 **하 여 선택할 개체 이름을 입력**하 고 컴퓨터의 이름을 입력 합니다. **이름 확인**을 클릭 합니다. 컴퓨터의 이름이 확인 되 면 밑줄로 표시 됩니다. **확인**을 클릭 한 다음 **마침을**클릭 합니다. **확인** 을 클릭 하 여 선택 항목을 커밋하고 **스냅인 추가/제거** 대화 상자를 닫습니다.

9.  인증서의 속성을 보려면 **인증서**를 확장 하 고, **개인**을 확장 하 고, **인증서**를 선택 합니다. 보려는 인증서를 선택 하 고, 인증서를 마우스 오른쪽 단추로 클릭 하 고 **열기**를 선택 합니다.

10. **인증서** 보기에서 **세부 정보**를 선택 합니다. 여기에서 **주체** 를 선택 하 고 지정 된 제목 이름과 연결 된 속성이 표시 되도록 하 여 인증서 주체 이름을 선택할 수 있습니다.

11. 지정 된 제목 대체 이름을 보려면 **제목 대체 이름을**선택 합니다. 지정 된 모든 제목 대체 이름이 여기에 표시 됩니다. 여기에 있는 주체 대체 이름은 기본적으로 **DNS 이름** 유형입니다. DNS 호스트 (A 또는 IPv6 AAAA) 레코드에 표시 되는 것으로 정규화 된 도메인 이름이 되어야 하는 다음 구성원이 표시 되어야 합니다.
    
      - 이 풀의 풀 이름 또는 풀이 아닌 경우 단일 서버 이름
    
      - 인증서가 할당 된 서버 이름
    
      - 간단한 URL 레코드, 일반적으로 모임 및 전화 접속
    
      - 웹 서비스 내부 및 웹 서비스 외부 이름 (예: webpool01.contoso.net, webpool01.contoso.com)-토폴로지 작성기 및 재정의 된 웹 서비스 선택 항목을 기준으로 합니다.
    
      - 이미 할당 된 경우 lyncdiscover. \<sipdomain\> 및 lyncdiscoverinternal. \<레코드\> 를 sipdomain.
    
    마지막 항목은 사용자가 가장 관심을 갖는 것을 의미 합니다-lyncdiscover 및 lyncdiscoverinternal SAN 항목이 있는 경우
    
    확인할 인증서가 여러 개 있는 경우이 단계를 반복 합니다. 이 정보가 있으면 인증서 보기와 MMC를 닫을 수 있습니다.

12. 자동 검색 서비스 주체 대체 이름이 없고 기본적으로 단일 기본 인증서를 사용 하는 경우, Web서비스 내부 및 WebServiceExternal 형식에 대해 다음을 수행 합니다.
    
      - Lync Server 관리 셸 명령줄 프롬프트에 다음을 입력 합니다.
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        SIP 도메인이 많은 경우 새 AllSipDomain 매개 변수를 사용할 수 없습니다. 대신 DomainName 매개 변수를 사용 해야 합니다. DomainName 매개 변수를 사용 하는 경우 lyncdiscoverinternal 및 lyncdiscover 레코드에 대 한 FQDN을 정의 해야 합니다. 예를 들면 다음과 같습니다.
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 인증서를 할당 하려면 다음을 입력 합니다.
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        여기서 "지문"은 새로 발급 된 인증서에 대해 표시 되는 지문입니다.

13. 기본, Web서비스 내부, 그리고 Webservice외부에서 별도의 인증서를 사용 하는 경우 내부 자동 검색 SAN이 없는 경우 다음을 수행 합니다.
    
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
    
    <div>
    

    > [!NOTE]  
    > 참고로,이 단계를 실행 하는 계정에 적절 한 권한이 있는 인증 기관에 대 한 액세스 권한이 있는 경우에만 12 ~ 13 단계가 실행 되어야 합니다. 해당 권한이 있는 계정으로 로그인 할 수 없거나 인증서에 대 한 공개 또는 원격 인증 기관을 사용 하는 경우에는 Lync Server 배포 마법사를 통해이를 요청 해야 합니다. 문서.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

