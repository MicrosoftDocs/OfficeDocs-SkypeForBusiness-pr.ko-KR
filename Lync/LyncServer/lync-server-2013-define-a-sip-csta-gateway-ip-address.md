---
title: 'Lync Server 2013: SIP/CSTA 게이트웨이 IP 주소 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6143b4b92c8927375dcaa772360e0b3f870dae25
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a>Lync Server 2013에서 SIP/CSTA 게이트웨이 IP 주소 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

Lync Server가 TCP (전송 제어 프로토콜) 연결을 사용 하 여 원격 통화 제어를 위해 배포한 SIP/CSTA 게이트웨이에 연결 하는 경우에는 토폴로지 작성기에서 게이트웨이의 IP 주소를 정의 해야 합니다. TLS (전송 계층 보안) 연결을 지 원하는 게이트웨이에는이 단계가 필요 하지 않습니다. TLS 연결을 지 원하는 게이트웨이에서는 lync [Server 2013의 원격 통화 제어를 위해 lync 사용자 설정](lync-server-2013-enable-lync-users-for-remote-call-control.md)의 단계에 따라이 절차를 건너뛰고 원격 통화 제어를 계속 배포할 수 있습니다.

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a>토폴로지 작성기를 사용 하 여 SIP/CSTA 게이트웨이 IP 주소를 정의 하려면

1.  도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 토폴로지 작성기가 설치 된 컴퓨터에 로그온 합니다.

2.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

3.  기존 토폴로지를 다운로드 하는 옵션을 선택 합니다.

4.  **신뢰할 수 있는 응용 프로그램 서버** 노드를 확장 합니다.

5.  [Lync Server 2013의 원격 통화 제어에 대 한 신뢰할 수 있는 응용 프로그램 항목 구성](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)에서 설명한 대로 만든 신뢰할 수 있는 응용 프로그램 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

6.  **이 풀에 구성 데이터 복제 사용** 확인란의 선택을 취소 합니다.

7.  **선택한 IP 주소로 서비스 사용량 제한을**클릭 합니다. 기본 설정은 구성 된 **모든 IP 주소를 사용 하**는 것입니다.

8.  **기본 IP 주소** 텍스트 상자에 SIP/CSTA 게이트웨이의 IP 주소를 입력 합니다.

9.  중앙 관리 저장소의 토폴로지를 업데이트 하려면 콘솔 트리에서 **Lync Server**를 클릭 한 다음 **작업** 창에서 **게시**를 클릭 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 원격 통화 제어에 대한 고정 경로 구성](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Lync Server 2013에서 원격 통화 제어를 위한 신뢰할 수 있는 응용 프로그램 항목 구성](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

