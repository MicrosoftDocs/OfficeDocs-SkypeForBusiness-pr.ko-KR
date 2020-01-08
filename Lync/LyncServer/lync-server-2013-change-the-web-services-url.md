---
title: 'Lync Server 2013: 웹 서비스 URL 변경'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 335c73a56da1d8b9a28e7089a7cc2238724a322b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a>Lync Server 2013에서 웹 서비스 URL 변경

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2015-11-16_

프런트 엔드 풀 및 Standard Edition 서버를 설정 하는 경우 외부 웹 팜 FQDN (정규화 된 도메인 이름) 및 관련 포트를 구성 하는 옵션이 있습니다. Lync Server 배포 마법사를 실행할 때이 URL을 구성 하지 않은 경우 이러한 설정을 수동으로 구성 해야 합니다. 일반적으로 관리자는 권장 및 기본 포트 이므로 이러한 설정을 수정할 필요가 없습니다.

<div>


> [!NOTE]  
> 스탠더드 버전 서버를 구성 하는 동안 다음 스크린샷은 다음을 수행 했기 때문에 FQDN 재정의 옵션을 사용할 수 없습니다. 이 옵션은 프런트 엔드 풀에서 엔터프라이즈 버전 서버를 구성할 때 사용할 수 있습니다.



</div>

![웹 서비스 풀 설정 편집](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "웹 서비스 풀 설정 편집")

<div>

## <a name="to-configure-web-services"></a>웹 서비스를 구성 하려면

1.  도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 토폴로지 작성기가 설치 된 컴퓨터에 로그온 합니다.

2.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

3.  토폴로지 작성기의 콘솔 트리에서 **Standard Edition 프런트 엔드 서버**, **Enterprise Edition 프런트 엔드 풀**및 **디렉터리 풀**에서 풀 이름을 선택 합니다. 이름을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 한 다음 **웹 서비스**를 클릭 합니다.

4.  **외부 웹 서비스 FQDN**을 추가 하거나 편집한 다음 **확인**을 클릭 합니다.
    
    <div>
    

    > [!WARNING]  
    > 프런트 엔드 풀 또는 프런트 엔드 서버를 두 개 이상 사용 하는 경우에는 외부 웹 서비스 FQDN이 고유 해야 합니다. 예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 <STRONG>pool01.contoso.com</STRONG>로 정의 하는 경우 다른 프런트 엔드 풀 또는 프런트 엔드 서버에 대해 <STRONG>pool01.contoso.com</STRONG> 를 사용할 수 없습니다. 디렉터를 배포 하는 경우 모든 디렉터 또는 디렉터 풀에 대해 정의 된 외부 웹 서비스 FQDN은 모든 프론트 엔드 풀 또는 프런트 엔드 서버 뿐만 아니라 다른 모든 디렉터 또는 디렉터 풀에서 고유 해야 합니다.

    
    </div>

5.  수신 및 게시 된 포트가 사용자 환경에 맞게 올바르게 구성 되었는지 확인 합니다.

6.  해당 환경의 모든 Standard Edition server, 프런트 엔드 풀 및 디렉터 풀에 대해이 단계를 반복 합니다.

7.  콘솔 트리에서 **Lync Server 2013**을 클릭 한 다음 **작업** 창에서 **토폴로지 게시**를 클릭 합니다.

수신 및 게시 포트를 구성할 때 알아야 할 몇 가지 요구 사항은 다음과 같습니다.

  - 표시 되는 수신 포트는 각 프런트 엔드 서버에서 IIS (인터넷 정보 서버)에 대해 구성 된 포트입니다.

  - 내부 및 외부 수신 대기 포트는 IIS에 대해 달라 야 합니다. 외부 수신 대기 포트는 내부 웹 트래픽에 대 한 하드웨어 부하 분산 장치를 나타내고 하나는 외부 웹 트래픽에 대 한 역방향 프록시 서버를 나타내므로 일반적으로 같습니다.

  - 프런트 엔드 풀, 디렉터 또는 디렉터 풀의 내부 웹 서비스를 재정의 하 고 고유한 FQDN을 정의할 수 있습니다.
    
    <div>
    

    > [!WARNING]  
    > 내부 웹 서비스를 자체 정의 FQDN으로 재정의 하기로 결정 한 경우 각 FQDN은 다른 프런트 엔드 풀, 디렉터 또는 디렉터 풀에서 고유 해야 합니다.

    
    </div>

  - 게시 된 포트는 역방향 프록시 또는 하드웨어 부하 분산 장치를 수신 대기 포트로 구성 해야 합니다.

  - 프런트 엔드 풀의 경우 (예제에 표시 되지 않음) 웹 트래픽은 하드웨어 부하 분산 장치를 통해 제공 되 고 내부 SIP 풀 트래픽 이동이 DNS 부하 분산 장치를 통해 제공 되므로 내부 SIP 풀 FQDN은 내부 웹 서비스 FQDN과 달라 야 합니다. . 이 요구 사항을 충족 해야 합니다.

  - Lync Server Standard Edition 배포에는이 서버의 부하를 분산할 수 없기 때문에 내부 웹 서비스 FQDN을 재정의 하거나 허용 하지 않아도 됩니다.

  - 내부 SIP와 웹 트래픽 모두에 사용 하는 하드웨어 부하 분산 장치가 환경에 있는 경우 토폴로지 작성기를 통해이를 구분할 수 없습니다.
    
    웹 서비스 Fqdn은 서로 쉽게 구분 되어야 합니다. 이는 URL 리디렉션이 클라이언트를 적절 한 서버에 가리키는지 확인 하는 데 도움이 됩니다. 예를 들어 Fqdn이 두 개인 경우 하나의 meeting.contoso.com 및 다른 conferencing.contoso.com의 이름을 지정할 수 있습니다. Meet1.contoso.com 및 meet2.contoso.com와 같이 더 비슷한 이름을 갖는 Fqdn을 사용 하는 경우 리디렉션 문제가 발생할 수 있습니다.

외부 웹 서비스는 주변 네트워크의 리버스 프록시와 함께 작동 합니다. 이 웹 서비스를 사용 하 여 클라이언트에 대 한 외부 액세스를 제공 합니다. 여기에서 구성 하는 Fqdn은 로그온 할 때 클라이언트로 보내지며, 원격으로 연결할 때 HTTPS 연결을 다시 역방향 프록시로 만드는 데 사용 됩니다. 역방향 프록시 서버는 외부 웹 서비스 FQDN을 내부 하드웨어 부하 분산 장치 또는 풀에 직접 전달 합니다. 역방향 프록시는 외부 웹 서비스 FQDN을 내부 웹 서버의 IP 주소로 확인할 수 있어야 합니다. 공용 인터넷에서 외부 웹 서비스 FDQN를 확인할 수 있어야 합니다.

내부 서버가 Standard Edition 서버인 경우 내부 FQDN은 Standard Edition 서버 FQDN입니다. 내부 서버가 프런트 엔드 풀 인 경우 FQDN은 내부 웹 팜 서버의 부하를 분산 하는 하드웨어 부하 분산 장치 VIP (가상 IP)입니다. 하나 이상의 Enterprise Edition server를 사용 하는 프런트 엔드 풀에는 하드웨어 부하 분산이 필요 합니다. Standard Edition server 또는 단일 Enterprise Edition 프런트 엔드 서버에는 부하 분산이 필요 하지 않습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

