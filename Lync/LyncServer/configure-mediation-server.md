---
title: 중재 서버 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60bacd308249536aee49101cbcab739a0876343e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>중재 서버 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-28_

이 절차에서는 레거시 Office Communications Server 2007 R2 중재 서버 대신 Lync server 2013 조정 서버를 사용 하도록 Lync Server 2013 풀을 구성 하는 단계에 대해 자세히 설명 합니다.

서버 역할을 추가 하거나 제거할 때 토폴로지를 성공적으로 게시, 사용 또는 사용 하지 않도록 설정 하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹의 구성원 인 사용자로 로그인 해야 합니다. 또한 적절 한 관리자 권한 및 서버 역할 추가 권한을 위임할 수 있습니다. 자세한 내용은 Standard Edition server 또는 Enterprise Edition server 배포 설명서에서 설치 권한 위임을 참조 하세요. 다른 구성 변경의 경우 RTCUniversalServerAdmins 그룹의 구성원만 필요 합니다.

<div>


> [!NOTE]  
> Lync Server 2013와 작동 하는 정규화 된 PSTN 게이트웨이, IP Pbx 및 SIP 트렁크 서비스를 찾는 방법에 대 한 최신 정보는에서 <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>"Microsoft 통합 커뮤니케이션 오픈 상호 운용성 프로그램"을 참조 하세요.



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>토폴로지 작성기를 사용 하 여 중재 서버를 구성 하려면

1.  토폴로지 작성기에서 기존 토폴로지를 엽니다.

2.  왼쪽 창에서 **PSTN 게이트웨이로**이동 합니다.

3.  **PSTN 게이트웨이**를 마우스 오른쪽 단추로 클릭 한 다음 **새 IP/PSTN 게이트웨이**를 클릭 합니다.

4.  다음 정보를 사용 하 여 **새 IP/PSTN 게이트웨이 정의** 페이지를 완료 합니다.
    
      - 게이트웨이 FQDN 또는 IP 주소를 입력 합니다. 게이트웨이에서 TLS 프로토콜을 사용 하는 경우 게이트웨이의 FQDN이 필요 합니다.
    
      - **IP/PSTN 게이트웨이의 기본 수신 포트** 값을 적용 하거나, 수정 된 경우 새 수신 대기 포트를 입력 합니다.
    
      - **Sip 전송 프로토콜**을 설정 합니다.

5.  왼쪽 창에서 **Enterprise Edition 프런트 엔드 풀** 또는 **Standard Edition 서버로**이동 합니다.

6.  풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

7.  **중재 서버**에서 **수신 대기 포트**를 설정 합니다.

8.  다음으로 새로 만든 PSTN 게이트웨이를 선택 하 고 **추가**를 클릭 하 여 연결 합니다.

9.  **토폴로지 작성기**에서 최상위 노드 **Lync 서버**를 선택 합니다.

10. **작업** 메뉴에서 **토폴로지 게시** 를 선택 하 고 **다음**을 클릭 합니다.

11. **게시 마법사** 가 완료 되 면 **마침을** 클릭 하 여 마법사를 닫습니다.

<div>


> [!NOTE]  
> <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">새로운 Lync server 2013 조정 서버를 사용 하</A> 여 음성 경로가 올바른 중재 서버를 가리키고 있는지 확인 하려면 다음 항목을 완료 하는 것이 중요 합니다.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

