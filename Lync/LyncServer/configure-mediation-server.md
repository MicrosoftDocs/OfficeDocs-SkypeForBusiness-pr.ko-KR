---
title: 중재 서버 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 389c6e5c017594bf386109541a379bd5ae2f7e01
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>중재 서버 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-28_

이 절차에서는 레거시 Office Communications Server 2007 R2 중재 서버가 아닌 Lync server 2013 중재 서버를 사용 하도록 Lync Server 2013 풀을 구성 하는 단계를 자세히 설명 합니다.

서버 역할을 추가하거나 제거할 때 토폴로지를 성공적으로 게시하거나 사용 또는 사용하지 않도록 설정하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹 구성원인 사용자로 로그인해야 합니다. 또한 서버 역할을 추가하는 데 적절한 관리자 권한 및 사용 권한을 위임할 수 있습니다. 자세한 내용은 Standard Edition 서버 또는 Enterprise Edition 서버 배포 설명서에서 설정 권한 위임을 참조하십시오. 기타 구성을 변경하려는 경우에는 RTCUniversalServerAdmins 그룹 구성원 자격만 있으면 됩니다.

<div>


> [!NOTE]  
> Lync Server 2013에서 작동 하는 정규화 된 PSTN 게이트웨이, IP Pbx 및 SIP 트렁크 서비스를 찾는 방법에 대 한 최신 정보는에서 <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>"Microsoft 통합 커뮤니케이션 오픈 상호 운용성 프로그램"을 참조 하십시오.



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>토폴로지 작성기를 사용하여 중재 서버를 구성하려면

1.  토폴로지 작성기에서 기존 토폴로지를 엽니다.

2.  왼쪽 창에서 **PSTN 게이트웨이**로 이동합니다.

3.  **PSTN 게이트웨이**를 마우스 오른쪽 단추로 클릭한 다음 **새 IP/PSTN 게이트웨이**를 클릭합니다.

4.  **새 IP/PSTN 게이트웨이 정의** 페이지에서 다음 정보를 작성합니다.
    
      - 게이트웨이의 FQDN 또는 IP 주소를 입력합니다. 게이트웨이에서 TLS 프로토콜을 사용하는 경우 게이트웨이의 FQDN이 필요합니다.
    
      - **IP/PSTN 게이트웨이용 수신 대기 포트**의 기본값을 사용하거나 값이 수정된 경우 새 수신 대기 포트를 입력합니다.
    
      - **SIP 전송 프로토콜**을 설정합니다.

5.  왼쪽 창에서 **Enterprise Edition 프런트 엔드 풀** 또는 **Standard Edition 서버**로 이동합니다.

6.  풀을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 클릭합니다.

7.  **중재 서버**에서 **수신 대기 포트**를 설정합니다.

8.  그런 다음 새로 만든 PSTN 게이트웨이를 선택하고 **추가**를 클릭하여 연결합니다.

9.  **토폴로지 작성기**에서 맨 위에 있는 **Lync Server** 노드를 선택합니다.

10. **동작** 메뉴에서 **토폴로지 게시**를 선택한 후 **다음**을 클릭합니다.

11. **게시 마법사**가 완료되면 **마침**을 클릭하여 마법사를 닫습니다.

<div>


> [!NOTE]  
> 음성 경로가 올바른 중재 서버를 가리키는지 확인 하려면 다음 항목을 완료 하 여 <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">새 Lync server 2013 중재 서버를 사용 하도록 음성 경로를 변경</A> 해야 합니다.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

