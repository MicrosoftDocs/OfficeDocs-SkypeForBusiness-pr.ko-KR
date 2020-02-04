---
title: 'Lync Server 2013: 허용되는 외부 도메인 지원 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31aa2ab9db9ffccd3acda90e9651dfad20b85e96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a>Lync Server 2013에서 허용되는 외부 도메인 지원 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

페더레이션 파트너에 대 한 지원을 구성한 경우 조직과 페더레이션 할 수 있는 특정 도메인을 관리할 수 있습니다. 하나 이상의 특정 외부 도메인을 허용 된 페더레이션 도메인으로 구성 합니다. 이렇게 하려면 허용 된 도메인 목록에 각 도메인을 추가 합니다. 조직에서 파트너 검색을 사용할 수 있는 경우에도 사용자의 1000 이상 통신 해야 하는 페더레이션 파트너인 경우와 초당 20 개 이상의 메시지를 보내야 하는 경우이 작업을 수행 합니다. 조직에서 파트너 검색을 사용할 수 없는 경우 허용 된 도메인 목록에 추가 되는 외부 도메인의 사용자만이 조직의 사용자와 IM 및 회의에 참가할 수 있습니다. 페더레이션 도메인에 대 한 액세스를 페더레이션 파트너의 액세스에 지 서비스를 실행 하는 특정 서버로 제한 하려는 경우 허용 된 도메인 목록에 있는 각 도메인에 대 한 액세스 경계 서비스를 실행 하는 서버의 도메인 이름을 지정할 수 있습니다.

<div>


> [!NOTE]  
> 이 절차는 특정 도메인에 대 한 지원을 구성 하는 방법에 대해 설명 하지만, 페더레이션 사용자에 대 한 지원을 구현 하려면 조직의 페더레이션 사용자에 대 한 지원을 사용 하도록 설정 하 고 정책을 구성 및 적용 하 여 사용자가 수행할 수 있는 작업 제어 페더레이션 사용자와 공동 작업 페더레이션 사용자에 대 한 지원을 설정 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을</A>참조 하세요. 관리를 제어 하도록 정책을 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013에서 페더레이션된 사용자 액세스를 제어 하도록 정책 구성을</A>참조 하세요.



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>허용 된 도메인 목록에 외부 도메인을 추가 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 한 다음 **페더레이션 도메인**을 클릭 합니다.

4.  **페더레이션 도메인** 페이지에서 **새로 만들기**를 클릭 한 다음 허용 된 **도메인**을 클릭 합니다.

5.  **새 페더레이션 도메인**에서 다음을 수행 합니다.
    
      - **도메인 이름 (또는 FQDN)** 에 페더레이션 파트너 도메인의 이름을 입력 합니다.
        
        <div>
        

        > [!NOTE]  
        > 이 이름은 고유 해야 하며 액세스에 지 서비스를 실행 하는이 서버에 허용 되는 도메인으로 이미 존재 하는 것이 아니어야 합니다. 이름 길이가 256 자를 초과할 수 없습니다.<BR>페더레이션 파트너 도메인 이름에서 검색 하면 접미사 일치가 수행 됩니다. 예를 들어 <STRONG>contoso.com</STRONG>를 입력 하는 경우 검색 에서도 도메인 <STRONG>it.contoso.com</STRONG>반환 됩니다.<BR>페더레이션 파트너 도메인은 동시에 차단 및 허용 될 수 없습니다. Lync Server 2013에서이 문제가 발생 하 여 목록을 동기화 할 필요가 없습니다.

        
        </div>
    
      - 이 페더레이션 도메인에 대 한 액세스를 액세스에 지 서비스를 실행 하는 특정 서버의 사용자에 게 제한 하려면 액세스 edge 서비스 **(FQDN)** 에 액세스에 지 서비스를 실행 하는 페더레이션 도메인 서버의 FQDN을 입력 합니다.
    
      - 추가 정보를 제공 하려는 경우 **설명**에이 구성에 대 한 다른 시스템 관리자와 공유 하려는 정보를 입력 합니다.

6.  **커밋**을 클릭합니다.

7.  허용 하려는 각 페더레이션 파트너 도메인에 대해 4 ~ 6 단계를 반복 합니다.

페더레이션 사용자 액세스를 사용 하도록 설정 하려면 조직에서 페더레이션된 사용자 액세스에 대 한 지원도 사용 하도록 설정 해야 합니다. 자세한 내용은 [Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을](lync-server-2013-enable-or-disable-remote-user-access.md)참조 하세요.

또한 페더레이션 사용자와 공동 작업을 수행할 수 있는 사용자에 게 정책을 구성 하 고 적용 해야 합니다. 자세한 내용은 [Lync Server 2013에서 페더레이션된 사용자 액세스를 제어 하도록 정책 구성을](lync-server-2013-configure-policies-to-control-federated-user-access.md)참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

