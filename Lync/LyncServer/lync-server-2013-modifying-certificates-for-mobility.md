---
title: 'Lync Server 2013: 모바일 기능에 대 한 인증서 수정'
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
ms.openlocfilehash: 54b42ba288c89f8735d3f7d13dee9a1944efe82b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a>Lync Server 2013에서 모바일 기능에 대 한 인증서 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-06-20_

Lync 환경과 모바일 클라이언트 간의 보안 연결을 지원 하기 위해 디렉터 풀, 프런트 엔드 풀 및 역방향 프록시에 대 한 SSL (Secure sockets Layer) 인증서를 추가 주체 대체 이름으로 업데이트 해야 합니다 ( SAN) 항목 모바일 기능에 대 한 인증서 요구 사항에 대 한 자세한 내용을 확인 해야 하는 경우에는 [Lync Server 2013의 모바일 기능에 대 한 기술 요구](lync-server-2013-technical-requirements-for-mobility.md)사항에서 인증서 요구 사항 섹션을 참조 하 고, 기본적으로 추가 SAN 항목을 포함 하 여 인증 기관에서 새 인증서를 가져온 다음이 문서의 단계를 사용 하 여 해당 인증서를 추가 해야 합니다.

시작 하기 전에 먼저 인증서에 이미 있는 주체 대체 이름을 아는 것이 좋습니다. 이미 구성 되어 있는 것을 모르는 경우에는 다양 한 방법으로 확인할 수 있습니다. 이 정보를 보기 위해 **set-cscertificate** 및 기타 PowerShell 명령을 실행 하는 옵션 (아래에서 설명)은 기본적으로 데이터를 잘리게 되므로 필요한 모든 속성을 확인 하지 못할 수 있습니다. 인증서와 모든 해당 속성을 확인 하려면 MMC (Microsoft Management Console)로 이동 하 고 인증서 스냅인을 로드 합니다 (아래 참조). 또는 Lync Server 배포 마법사를 확인 하기만 하면 됩니다.

위에서 설명한 것 처럼 다음 단계에서는 Lync Server 관리 셸 및 MMC를 사용 하 여 인증서를 업데이트 하는 과정을 안내 합니다. 이를 대신 하 여 Lync Server 배포 마법사에서 인증서 마법사를 사용 하는 경우에는 디렉터 또는 디렉터 풀에 대해 [Lync Server 2013에서 디렉터에 대 한 인증서 구성](lync-server-2013-configure-certificates-for-the-director.md) (사용자가 없을 수 있음)을 확인할 수 있습니다. 프런트 엔드 서버 또는 프런트 엔드 풀의 경우 [Lync Server 2013에서 서버에 대 한 인증서 구성을](lync-server-2013-configure-certificates-for-servers.md)확인 해야 합니다.

마지막으로 고려할 사항 중 하나는 Lync Server 2013 환경에 기본 인증서가 하나만 있을 수 있다는 것을 의미 하거나, 기본값 (웹 서비스는 물론 모든 기능), WebServicesExternal 및 Web서비스 내부에 대해 별도의 인증서를 사용할 수 있다는 것입니다. 구성에 관계 없이, 이러한 단계를 통해 다음을 수행 하는 것이 좋습니다.

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>Lync Server 관리 셸을 사용 하 여 새 주체 대체 이름을 사용 하 여 인증서를 업데이트 하려면

1.  로컬 관리자 권한 및 사용 권한이 있는 계정을 사용 하 여 Lync Server 2013 서버에 로그온 해야 합니다. 또한 12 단계와 그 이후에 Set-cscertificate PowerShell **요청** 을 실행 하는 경우 계정에 지정 된 CA (인증 기관)에 대 한 권한이 있어야 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  업데이트 된 인증서를 할당 하려면 서버에 할당 된 인증서와 사용 유형에 대 한 정보를 확인 해야 합니다. 명령줄에 다음을 입력합니다.
    
        Get-CsCertificate

4.  이전 단계의 출력을 검토 하 여 여러 용도로 단일 인증서가 할당 되었는지, 아니면 각 사용에 대해 서로 다른 인증서를 할당 했는지 확인 합니다. 사용 매개 변수를 확인 하 여 인증서가 사용 되는 방식을 확인할 수 있습니다. 표시 된 인증서의 지문 매개 변수를 비교 하 여 동일한 인증서에 여러 사용이 있는지 확인 합니다. 지문 매개 변수에 눈을 둡니다.

5.  인증서를 업데이트 합니다. 명령줄에 다음을 입력합니다.
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    예를 들어 **set-cscertificate** Cmdlet에 기본을 사용 하는 인증서, 즉 Web서비스 내부를 사용 하는 경우, 그리고 WebServicesExternal을 사용 하는 경우와 동일한 지문 값이 있는 경우 명령줄에서 다음을 입력 해야 합니다.
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **중요:**
    
    각 사용에 대해 별도의 인증서가 할당 되어 있는 경우 위 예에서와 같이, 위에서 확인 한 지문 값이 서로 다른 경우에는 **set-cscertificate** cmdlet을 실행 **하지** 않는 것이 중요 합니다. 이 경우 각 사용에 대해 **set-cscertificate** cmdlet을 개별적으로 실행 합니다. 예:
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  인증서 (또는 인증서)를 보려면 **시작**, **실행**을 차례로 클릭 합니다. MMC를 입력 하 여 Microsoft Management Console을 엽니다.

7.  MMC 메뉴에서 **파일**을 선택 하 고 **스냅인 추가/제거**를 선택한 다음 인증서를 선택 합니다. **추가**를 클릭합니다. 메시지가 표시 되 면 **컴퓨터 계정을**선택 하 고 **다음**을 클릭 합니다.

8.  인증서가 있는 서버인 경우 **로컬 컴퓨터**를 선택 합니다. 인증서가 다른 컴퓨터에 있는 **경우에는** **다른 컴퓨터**를 선택 하 고 컴퓨터의 정규화 된 도메인 이름을 입력 하거나, 원하는 **개체 이름을 입력 하 여 선택**하 고 컴퓨터의 이름을 입력할 수 있습니다. **이름 확인**을 클릭합니다. 컴퓨터 이름이 확인 되 면 밑줄이 표시 됩니다. **확인**을 클릭 한 다음 **마침을**클릭 합니다. **확인** 을 클릭 하 여 선택 항목을 커밋하고 **스냅인 추가/제거** 대화 상자를 닫습니다.

9.  인증서의 속성을 보려면 **인증서**, **개인**을 차례로 확장하고 **인증서**를 선택합니다. 보려는 인증서를 선택하고 인증서를 마우스 오른쪽 단추로 클릭한 후 **열기**를 선택합니다.

10. **인증서** 보기에서 **자세히**를 선택합니다. 여기에서는 **주체**를 선택하여 인증서 주체 이름을 선택할 수 있고 지정된 주체 이름 및 연결된 속성이 표시됩니다.

11. 지정된 주체 대체 이름을 보려면 **주체 대체 이름**을 선택합니다. 지정 된 모든 주체 대체 이름이 여기에 표시 됩니다. 여기서 찾은 주체 대체 이름은 기본적으로 **DNS 이름** 형식입니다. 다음과 같은 멤버가 표시됩니다(모든 멤버가 DNS 호스트(A 또는 IPv6인 경우 AAAA) 레코드에 표시된 대로 정규화된 도메인 이름으로 표시됨).
    
      - 이 풀의 풀 이름 또는 단일 서버 이름 (풀이 아닌 경우)
    
      - 인증서가 지정된 서버 이름
    
      - 단순 URL 레코드(일반적으로 meet 및 dialin)
    
      - 웹 서비스 내부 및 웹 서비스 외부 이름 (예: webpool01.contoso.net, webpool01.contoso.com)-토폴로지 작성기 및 재정의를 사용한 웹 서비스 선택에 대 한 선택 사항에 따라 달라 집니다.
    
      - 이미 지정 된 경우 lyncdiscover입니다. \<microsoft.rtc.management.xds.sipdomain object\> 및 lyncdiscoverinternal \<microsoft.rtc.management.xds.sipdomain object\> 레코드
    
    사용자가 가장 관심을 가질 수 있는 마지막 항목은 무엇 인가요? lyncdiscover 및 lyncdiscoverinternal SAN 항목이 있는 경우
    
    확인할 인증서가 여러 개인 경우이 단계를 반복 합니다. 이러한 정보를 준비했으면 인증서 보기 및 MMC를 닫을 수 있습니다.

12. 자동 검색 서비스 주체 대체 이름이 누락되었고 기본, WebServicesInternal 및 WebServiceExternal 형식에 대해 단일 기본 인증서를 사용하는 경우 다음을 수행합니다.
    
      - Lync Server 관리 셸 명령줄 프롬프트에 다음을 입력 합니다.
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        SIP 도메인이 많은 경우에는 새 AllSipDomain 매개 변수를 사용할 수 없습니다. 대신 DomainName 매개 변수를 사용 해야 합니다. DomainName 매개 변수를 사용 하는 경우 lyncdiscoverinternal 및 lyncdiscover 레코드의 FQDN을 정의 해야 합니다. 예:
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 인증서를 지정하려면 다음을 입력합니다.
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        "Thumbprint"는 새로 발급된 인증서에 표시되는 지문입니다.

13. 기본, Web서비스 내부 및 WebServicesExternal에 대해 별도의 인증서를 사용할 때 내부 자동 검색 SAN의 누락 된 경우 다음을 수행 합니다.
    
      - Lync Server 관리 셸 명령줄 프롬프트에 다음을 입력 합니다.
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        SIP 도메인이 많은 경우에는 새 AllSipDomain 매개 변수를 사용할 수 없습니다. 대신 DomainName 매개 변수를 사용 해야 합니다. DomainName 매개 변수를 사용 하는 경우 SIP 도메인 FQDN에 대해 적절 한 접두사를 사용 해야 합니다. 예:
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 누락된 외부 자동 검색 주체 대체 이름에 대해 명령줄에 다음을 입력합니다.
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        SIP 도메인이 많은 경우에는 새 AllSipDomain 매개 변수를 사용할 수 없습니다. 대신 DomainName 매개 변수를 사용 해야 합니다. DomainName 매개 변수를 사용 하는 경우 SIP 도메인 FQDN에 대해 적절 한 접두사를 사용 해야 합니다. 예:
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - 개별 인증서 유형을 지정하려면 다음을 입력합니다.
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        "Thumbprint"는 새로 발급된 인증서에 표시되는 지문입니다.
    
    <div>
    

    > [!NOTE]  
    > 여기서는 12 단계와 13 단계가 실행 되는 계정에 적절 한 사용 권한이 있는 인증 기관에 대 한 액세스 권한이 있는 경우에만 실행 해야 합니다. 이러한 권한을 가진 계정으로 로그인 할 수 없거나 인증서에 대해 공용 또는 원격 인증 기관을 사용 하는 경우에는 Lync Server 배포 마법사를 통해이를 요청 해야 하며, 여기서는 아티클에서.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

