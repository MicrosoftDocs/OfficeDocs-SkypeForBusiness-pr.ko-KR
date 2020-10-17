---
title: 'Lync Server 2013: 공용 SIP 페더레이션 공급자 만들기 또는 편집'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58b0ffdc009d48ef82d1bdf3ba8662cd4072ea1c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514855"
---
# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a>Lync Server 2013에서 공용 SIP 페더레이션 공급자 만들기 또는 편집

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

공용 im (인스턴트 메시징) 연결을 사용 하면 조직의 사용자가 IM을 통해 Windows Live Messenger, Yahoo 및 AOL을 비롯 한 공용 메신저 서비스 공급자가 제공 하는 IM 서비스 사용자와 통신할 수 있습니다 \! .

Lync Server 2013에는 미국 온라인, Windows Live 및 Yahoo에 대 한 공용 공급자 구성이 있습니다.\! 인스턴트 메시징에 대한 공용 공급자 구성이 포함됩니다. 각 공용 공급자는 공급자의 에지 서버 정규화된 도메인 이름과 기본 확인 수준인 **이 공급자를 사용하는 연락처 목록의 사용자와만 통신할 수 있도록 허용**으로 구성됩니다.

기본 설정에서는 어떠한 공용 공급자도 사용하도록 설정되지 않습니다. 공용 공급자를 사용하도록 설정하기 전에 사용권 계약 및 프로비전 작업을 완료해야 합니다. 라이선스 설정 및 프로비전 작업을 완료하기 전에도 해당 공급자를 사용하도록 설정할 수 있습니다. 하지만 필수 구성 요소 작업을 완료하기 전까지는 사용자가 해당 공급자의 연락처와 통신할 수 없습니다. 공용 공급자의 라이선스 및 프로 비전에 대 한 자세한 내용은 [Lync Server 2013에서 공용 사용자 액세스를 제어 하도록 정책 구성을](lync-server-2013-configure-policies-to-control-public-user-access.md)참조 하십시오.

다음 절차를 수행하여 공용 공급자를 만들거나 편집합니다.

<div>

## <a name="to-create-or-edit-public-providers"></a>공용 공급자를 만들거나 편집하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭한 다음 **SIP 페더레이션 공급자**를 클릭합니다.

4.  새 공용 공급자를 만들려면 **새로 만들기**를 클릭하고 **공용 공급자**를 클릭합니다.

5.  공용 공급자 목록에서 항목을 편집해야 하는 경우 해당 공용 공급자를 선택하고 **편집**을 클릭한 후 **세부 정보 표시**를 클릭합니다.

6.  **SIP 페더레이션 공급자 편집** 페이지에서는 다음 설정을 입력하거나 편집할 수 있습니다.
    
      - **이 공급자**     와의 통신 사용 이 설정을 선택 하면이 공급자의 사용자와 IM을 사용할 수 있습니다.
    
      - **공급자 이름:**     SIP 페더레이션 공급자 목록에 반영할 공급자의 이름을 입력 하는 데 필요한 속성입니다.
    
      - **액세스에 지 서비스 (FQDN):**     필요한 속성에는 구성 하는 공급자의 액세스에 지 서비스에 대 한 정규화 된 도메인 이름을 입력 합니다. 이 정보는 기본 항목으로 제공되며, 공용 공급자가 액세스 에지 서비스의 FQDN을 바꿀 경우에만 변경해야 합니다.
    
      - **기본 확인 수준:**     기본 설정인 **사용자가 대화 상대 목록에서이 공급자를 사용 하는 사용자와 통신할 수 있도록 허용** 은 수락 하 여 대화 상대 목록에 있는 대화 상대와의 통신을 제한 합니다.
        
        **이 공급자를 사용하는 모든 사람과 통신할 수 있도록 허용**을 선택하면 연락처 초대를 수신하고 허용해야 하는 제한 사항이 제거됩니다. 이 설정은 공용 공급자의 네트워크에서 사용자에게 연락할 수 있는 사람을 제한하지 않습니다.

7.  설정 구성을 마쳤으면 **커밋**을 클릭해서 저장하거나 **취소**를 클릭해서 변경 내용을 취소합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 공용 사용자 액세스를 제어 하도록 정책 구성](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Lync Server 2013에서 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

