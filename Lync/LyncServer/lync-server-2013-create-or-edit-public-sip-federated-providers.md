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
ms.openlocfilehash: 33303217e6e1a1fefb502f1e9b364a46adc85e02
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a>Lync Server 2013에서 공용 SIP 페더레이션 공급자 만들기 또는 편집

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

공용 인스턴트 메시징 (IM) 연결을 통해 조직의 사용자는 Windows Live Messenger, Yahoo\!및 AOL을 포함 하 여 공용 IM 서비스 공급자가 제공 하는 im 서비스 사용자와 통신할 수 있습니다.

Lync Server 2013에는 미국 온라인, Windows Live 및 Yahoo 용 공용 공급자 구성이 있습니다.\! 인스턴트 메시지. 각 공용 공급자는 공급자의 Edge 서버 정규화 된 도메인 이름으로 구성 되며, 기본 확인 수준을 **통해 사용자는이 공급자를 사용 하는 대화 상대 목록에 있는 사용자와만 통신할 수**있습니다.

기본 설정으로는 공용 공급자가 사용 하도록 설정 되어 있지 않습니다. 공용 공급자를 사용 하도록 설정 하기 전에 라이선스 계약 및 프로비저닝 작업을 완료 해야 합니다. 라이선스 및 프로비저닝 작업을 완료 하기 전에 공급자를 사용 하도록 설정할 수 있습니다. 필수 작업 시간이 완료 될 때까지 사용자는 해당 공급자의 대화 상대와 통신할 수 없게 됩니다. 공용 공급자의 라이선스 및 제공에 대 한 자세한 내용은 [Lync Server 2013에서 공용 사용자 액세스를 제어 하는 정책 구성을](lync-server-2013-configure-policies-to-control-public-user-access.md)참조 하세요.

공용 공급자를 만들거나 편집 하려면 다음 절차를 사용 합니다.

<div>

## <a name="to-create-or-edit-public-providers"></a>공용 공급자를 만들거나 편집 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭 한 다음 **SIP 페더레이션된 공급자**를 클릭 합니다.

4.  새 공용 공급자를 만들어야 하는 경우 **새로 만들기** 를 클릭 한 다음 **공용 공급자**를 클릭 합니다.

5.  공용 공급자 목록에서 항목을 편집 해야 하는 경우에는 공용 공급자를 선택 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

6.  **SIP 페더레이션 공급자 편집** 페이지에서 다음 설정을 입력 하거나 편집할 수 있습니다.
    
      - **이 공급자**   와 통신 사용이 설정을 선택 하면이 공급자의 사용자와의 IM이 활성화 됩니다.
    
      - **공급자 이름:**   필요한 속성에는 공급자 이름을 SIP 페더레이션된 공급자 목록에 반영할 형식으로 입력 합니다.
    
      - **FQDN (액세스에 지 서비스):**   필수 속성인 경우 구성 중인 공급자의 액세스에 지 서비스에 대 한 정규화 된 도메인 이름을 입력 합니다. 이 정보는 기본 항목으로 제공 되며 공용 공급자가 공용 공급자에서 액세스 경계 서비스의 FQDN을 변경할 경우에만 변경 되어야 합니다.
    
      - **기본 확인 수준:**    **이 공급자를 사용 하는 사용자가 대화 상대 목록에 있는 사용자와 통신할 수 있도록 허용** 하는 기본 설정은 수락 하 고 연락처 목록에 있는 연락처와의 통신을 제한 합니다.
        
        **사용자가이 공급자를 사용 하는 모든 사용자와 통신 하도록 허용을** 선택 하면 연락처 초대를 받아서 수락 해야 하는 제한이 제거 됩니다. 이 설정은 공용 공급자의 네트워크에서 사용자에 게 연락할 수 있는 사용자를 제한 하지 않습니다.

7.  설정 구성을 완료 했으면 **커밋을** 클릭 하 여 저장 하거나 **취소** 를 클릭 하 여 변경 내용을 취소 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 공용 사용자 액세스를 제어하도록 정책 구성](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

