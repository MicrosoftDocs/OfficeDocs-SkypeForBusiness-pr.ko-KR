---
title: 'Lync Server 2013: 호스팅된 SIP 페더레이션 공급자 만들기 또는 편집'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8be79e53b0215cdfabd89e9d66f7c9e417ba40e9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a>호스팅된 SIP 페더레이션 공급자 만들기 또는 편집 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

호스트 된 공급자 IM (인스턴트 메시징) 연결을 사용 하면 조직의 사용자가 Microsoft Office 365 및 Lync Online을 포함 하 여 호스트 된 공급자가 제공 하는 IM 서비스 사용자와 통신할 수 있습니다.

각 호스트된 공급자는 공급자의 에지 서버 정규화된 도메인 이름 및 기본 확인 수준 **대화 상대 목록에서 이 공급자를 사용하는 사용자와의 통신만 허용**을 사용하여 구성됩니다.

다음 절차에 따라 호스트된 공급자를 만들거나 편집합니다.

<div>

## <a name="to-create-or-edit-hosted-providers"></a>호스트된 공급자를 만들거나 편집하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭한 다음 **SIP 페더레이션 공급자**를 클릭합니다.

4.  새 호스트된 공급자를 만들어야 하는 경우 **새로 만들기**를 클릭하고 **호스트된 공급자**를 클릭합니다.

5.  호스트된 공급자 목록의 항목을 편집해야 하는 경우 호스트된 공급자를 선택하고 **편집**을 클릭한 다음 **자세한 정보 표시**를 클릭합니다.

6.  **SIP 페더레이션 공급자 편집** 페이지에서는 다음 설정을 입력하거나 편집할 수 있습니다.
    
      - **이 공급자**   와의 통신 사용이 설정을 선택 하면이 공급자의 사용자와 통신할 수 있습니다.
    
      - **공급자 이름:**   필요한 속성에는 SIP 페더레이션 공급자 목록에 반영할 공급자의 이름을 입력 합니다.
    
      - **액세스에 지 서비스 (FQDN):**   필요한 속성에 구성 중인 호스트 된 공급자의 액세스에 지 서비스에 대 한 정규화 된 도메인 이름을 입력 합니다. 이 정보는 호스팅된 공급자가 제공 해야 하며 호스팅된 공급자가 호스트 된 공급자에서 액세스에 지 서비스의 FQDN을 변경 하는 경우에만 변경 해야 합니다.
    
      - **기본 확인 수준:**   기본 설정인 **사용자가이 공급자를 사용 하는 대화 상대 목록에서 사용자와 통신할 수 있도록 허용** 은 수락 하 여 대화 상대 목록에 있는 대화 상대와의 통신을 제한 합니다.
        
        **이 공급자를 사용하는 모든 사용자와의 통신 허용**을 선택하면 대화 상대 초대를 받아 수락할 때 적용된 제한이 제거됩니다. 이 설정은 호스트된 공급자 네트워크에서 사용자와 대화를 할 수 있는 사람을 제한하지 않습니다.

7.  설정을 모두 구성한 후에 **커밋**을 클릭하여 변경 내용을 저장하거나 **취소**를 클릭하여 변경을 취소합니다.

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

