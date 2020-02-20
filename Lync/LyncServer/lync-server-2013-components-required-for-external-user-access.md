---
title: 'Lync Server 2013: 외부 사용자 액세스에 필요한 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31381edc58240d990096b47498b5c98845af5b2d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013의 외부 사용자 액세스에 필요한 구성 요소

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-05-29_

대부분의 Edge 구성 요소는 경계 네트워크에 배포 됩니다. 경계 네트워크의 에지 토폴로지를 구성하는 구성 요소는 다음과 같습니다. 명시 된 경우를 제외 하 고, 구성 요소는 [Lync Server 2013의 외부 사용자 액세스에 대 한 시나리오](lync-server-2013-scenarios-for-external-user-access.md) 에 포함 되어 경계 네트워크에 있습니다. 에지 구성 요소는 다음과 같습니다.

  - 에지 서버

  - 역방향 프록시

  - 방화벽

  - 디렉터 (선택 사항 및 논리적으로 내부 네트워크에 위치)

  - 확장된 에지 토폴로지에 대한 부하 분산(DNS 부하 분산 또는 하드웨어 부하 분산 장치)
    
    <div>
    

    > [!IMPORTANT]  
    > DNS 부하 분산과 하드웨어 부하 분산을 서로 다른 인터페이스에서 사용할 수 없습니다. 두 인터페이스에서 모두 하드웨어 부하 분산 또는 DNS 부하 분산을 사용해야 합니다.

    
    </div>

<div>

## <a name="edge-servers"></a>에지 서버

에 지 서버는 외부 사용자가 내부 배포에서 제공 하는 서비스에 대 한 네트워크 트래픽을 주고 받습니다. 에지 서버에서 실행되는 서비스는 다음과 같습니다.

  - **액세스에 지 서비스**   액세스에 지 서비스는 아웃 바운드 및 인바운드 SIP (Session 착수 프로토콜) 트래픽에 대해 신뢰할 수 있는 단일 연결 지점을 제공 합니다.

  - **웹 회의에 지 서비스**   웹 회의에 지 서비스는 외부 사용자가 내부 Lync Server 2013 배포에서 호스팅되는 모임에 참가할 수 있도록 합니다.

  - **A/v에 지 서비스**   a/v에 지 서비스는 외부 사용자가 오디오, 비디오, 응용 프로그램 공유 및 파일 전송을 사용할 수 있도록 합니다. 사용자는 외부 참가자가 포함 된 모임에 오디오 및 비디오를 추가할 수 있으며, 지점간 세션에서 외부 사용자와 직접 오디오 및/또는 비디오를 사용 하 여 통신할 수 있습니다. A/V 에지 서비스는 데스크톱 공유 및 파일 전송도 지원합니다.

  - **Xmpp 프록시 서비스**   xmpp 프록시 서비스는 구성 된 xmpp 페더레이션 파트너와의 xmpp (extensible messaging and 현재 상태 프로토콜) 메시지를 수락 하 고 보냅니다.

권한 있는 외부 사용자가 내부 Lync Server 2013 배포에 연결 하기 위해에 지 서버에 액세스할 수 있지만,에 지 서버는 내부 네트워크에 대 한 다른 액세스 방법을 제공 하지 않습니다.

<div>


> [!NOTE]  
> 에 지 서버는 페더레이션 시나리오와 같이 사용 하도록 설정 된 Lync 클라이언트 및 기타 Microsoft Edge 서버에 대 한 연결을 제공 하기 위해 배포 됩니다. 이러한 에지 서버는 다른 끝점 클라이언트 또는 서버 유형으로부터의 연결을 허용하지 않습니다. 구성된 XMPP 파트너와의 연결을 허용하기 위해 XMPP 게이트웨이 서버를 배포할 수 있습니다. 에지 서버 및 XMPP 게이트웨이는 이러한 클라이언트 및 페더레이션으로부터의 끝점 연결만 지원할 수 있습니다.



</div>

</div>

<div>

## <a name="reverse-proxy"></a>역방향 프록시

역방향 프록시는 다음과 같은 경우에 필요합니다.

  - 사용자가 단순 URL을 사용하여 모임 또는 전화 접속 전화 회의에 연결하도록 허용하려는 경우

  - 외부 사용자가 모임 콘텐츠를 다운로드할 수 있도록 하기 위해

  - 외부 사용자가 메일 그룹을 확장할 수 있도록 하기 위해

  - 사용자가 클라이언트 인증서 기반 인증용 사용자 기반 인증서를 가져오도록 허용하기 위해

  - 원격 사용자가 주소록 서버에서 파일을 다운로드하거나 주소록 웹 쿼리 서비스에 쿼리를 제출할 수 있도록 하기 위해

  - 원격 사용자가 클라이언트 및 장치 소프트웨어에 대한 업데이트를 가져올 수 있도록 하기 위해

  - 모바일 장치에서 Mobility Service를 제공하는 프런트 엔드 서버를 자동으로 검색할 수 있도록 하기 위해

  - Office 365 또는 Apple 푸시 알림 서비스에서 모바일 장치로 푸시 알림을 보낼 수 있도록 하기 위해

역방향 프록시에 대 한 자세한 내용과 역방향 프록시가 충족 해야 하는 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 역방향 프록시에 대 한 구성 요구 사항](lync-server-2013-configuration-requirements-for-reverse-proxy.md)정보를 참조 하세요.

<div>


> [!NOTE]  
> 외부 사용자는 Lync Server 2013을 사용 하 여 통신에 참여 하기 위해 조직에 대 한 VPN (가상 사설망) 연결이 필요 하지 않습니다. 조직에 VPN 기술이 구현 되어 있고 사용자가 Lync 용 VPN을 사용 하는 경우 미디어 트래픽 (예: 비디오 회의)에 악영향을 줄 수 있습니다. 미디어 트래픽이 AV에 지 서비스에 직접 연결 하 고 VPN을 사용 하지 않도록 하는 방법을 제공 하는 것이 좋습니다. 자세한 내용은 다음 홉 블로그 문서, "Lync Media에서 VPN 터널 바이패스를 사용 하도록 설정"을 참조 하세요 <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A>.



</div>

</div>

<div>

## <a name="firewall"></a>방화벽이

외부 방화벽만 사용하거나 외부 방화벽과 내부 방화벽을 둘 다 사용하여 에지 토폴로지를 배포할 수 있습니다. 시나리오 아키텍처에는 두 개의 방화벽이 포함 되어 있습니다. 두 개의 방화벽을 사용하면 한 네트워크 에지에서 다른 네트워크 에지로 엄격한 라우팅이 이루어지며 두 방화벽 수준 뒤에 있는 내부 네트워크가 보호되므로 두 개의 방화벽을 사용하는 것이 좋습니다.

</div>

<div>

## <a name="director"></a>영화

디렉터는 홈 사용자 계정이 아닌 Lync Server 2013의 별도의 선택적 서버 역할 이거나, 현재 상태 또는 회의 서비스를 제공 합니다. 또한에 지 서버가 내부 서버로 향하는 인바운드 SIP 트래픽을 라우팅하는 내부 다음 홉 서버 역할을 합니다. 디렉터는 인바운드 요청을 사전 인증 하 고 사용자의 홈 풀이나 서버로 리디렉션합니다. 디렉터에서 사전 인증을 사용 하 여 배포에 알려지지 않은 사용자 계정에서 요청을 삭제할 수 있습니다.

디렉터는 DoS (서비스 거부) 공격과 같은 악의적인 트래픽 으로부터 Standard Edition 서버 및 프런트 엔드 서버를 엔터프라이즈 버전의 프런트 엔드 풀에 쉽게 제거할 수 있도록 합니다. 이러한 공격에 잘못 된 외부 트래픽이 발생 하는 네트워크의 경우에는 디렉터에서 트래픽이 종료 됩니다. 디렉터 사용에 대 한 자세한 내용은 [Lync Server 2013에서 디렉터에 대 한 시나리오](lync-server-2013-scenarios-for-the-director.md)를 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에 대 한 하드웨어 부하 분산 장치 요구 사항](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

