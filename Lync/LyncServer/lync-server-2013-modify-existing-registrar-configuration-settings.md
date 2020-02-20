---
title: 'Lync Server 2013: 기존 등록자 구성 설정 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Registrar configuration settings
ms:assetid: a8931511-3e66-49ed-a3ec-03bcd61ce1f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182566(v=OCS.15)
ms:contentKeyID: 48185095
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32d59c31497f4a7d1a67087f47175184bd5665f9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-existing-registrar-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 기존 등록자 구성 설정 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

등록자를 사용하여 프록시 서버 인증 프토토콜을 구성할 수 있습니다. 사용 가능한 프로토콜에 대 한 자세한 내용은 [Create 등록자 구성 설정의 Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md)을 참조 하십시오.

<div>


> [!NOTE]  
> 서버에서 원격 클라이언트 및 엔터프라이즈 클라이언트 둘 다에 대한 인증을 지원할 경우 Kerberos 및 NTLM을 모두 사용하도록 설정하는 것이 좋습니다. 이렇게 하면 원격 클라이언트에는 NTLM 인증만 제공되도록 에지 서버와 내부 서버가 통신합니다. 이 서버에서 Kerberos만 사용하도록 설정한 경우에는 원격 사용자를 인증할 수 없습니다. 서버에 대해 엔터프라이즈 사용자를 인증할 경우에도 Kerberos가 사용됩니다.



</div>

다음 단계에 따라 기존의 등록자를 수정할 수 있습니다.

<div>

## <a name="to-modify-existing-registrar-configuration-settings"></a>기존 등록자 구성 설정을 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 표시줄에서 **보안**, **등록자**를 차례로 클릭합니다.

4.  **등록자** 페이지에서 서비스를 클릭하고 **편집**, **자세한 정보 표시**를 차례로 클릭합니다.

5.  환경의 지원 및 클라이언트 기능에 따라 **등록자 설정 편집**에서 다음 중 하나 이상을 선택합니다.
    
      - **Kerberos 인증 사용** - 이 풀의 서버가 Kerberos 인증을 사용하여 시도합니다.
    
      - **NTLM 인증 사용** - 이 풀의 서버가 NTLM을 사용하여 시도합니다.
    
      - **인증서 인증 사용** - 이 풀의 서버가 클라이언트에 대한 인증서를 발급합니다.

6.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

