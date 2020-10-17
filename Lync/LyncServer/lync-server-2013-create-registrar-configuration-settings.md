---
title: 'Lync Server 2013: 등록자 구성 설정 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2baa4cd40ae0f6421dbb01facecf0ab41825fc31
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501595"
---
# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 등록자 구성 설정 만들기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-17_

등록자를 사용 하 여 프록시 서버 인증 방법을 구성할 수 있습니다. 사용자가 지정 하는 인증 프로토콜에 따라 풀의 서버가 클라이언트에 발급할 문제 유형이 결정 됩니다. 사용 가능한 프로토콜은 다음과 같습니다.

  - **Kerberos**     클라이언트에서 사용할 수 있는 가장 강력한 암호 기반 인증 구성표 이며, 일반적으로 키 배포 센터 (Kerberos 도메인 컨트롤러)에 대 한 클라이언트 연결이 필요 하기 때문에 엔터프라이즈 클라이언트만 사용할 수 있습니다. 이 설정은 서버에서 엔터프라이즈 클라이언트만 인증 하는 경우에 적합 합니다.

  - **NTLM**     이 인증은 암호에 챌린지-응답 해시 체계를 사용 하는 클라이언트에서 사용할 수 있습니다. 이 인증 양식은 원격 사용자와 같은 키 배포 센터 (Kerberos 도메인 컨트롤러)에 연결 하지 않고는 클라이언트에만 사용할 수 있습니다. 서버에서 원격 사용자만 인증 하는 경우 NTLM을 선택 해야 합니다.

  - **인증서 인증**     서버가 Lync Phone Edition 클라이언트, 공통 영역 전화, Lync 2013 및 Lync Windows 스토어 앱에서 인증서를 가져와야 하는 경우 새 인증 방법입니다. Lync Phone Edition 클라이언트에서 사용자가 로그인 하 고 개인 식별 번호 (PIN)를 제공 하 여 인증 되 면 Lync Server 2013는 SIP URI를 휴대폰에 프로 비전 하 고, SN=joe@contoso.com를 식별 하는 Lync Server 서명 인증서 또는 사용자 인증서를 프로 비전 합니다. 이 인증서는 등록자 및 웹 서비스를 사용 하 여 인증 하는 데 사용 됩니다.

<div>


> [!NOTE]  
> 서버에서 원격 클라이언트 및 엔터프라이즈 클라이언트 둘 다에 대한 인증을 지원할 경우 Kerberos 및 NTLM을 모두 사용하도록 설정하는 것이 좋습니다. 이렇게 하면 원격 클라이언트에는 NTLM 인증만 제공되도록 에지 서버와 내부 서버가 통신합니다. 이 서버에서 Kerberos만 사용하도록 설정한 경우에는 원격 사용자를 인증할 수 없습니다. 서버에 대해 엔터프라이즈 사용자를 인증할 경우에도 Kerberos가 사용됩니다.<BR>Lync Windows 스토어 앱 클라이언트를 사용 하는 경우에는 인증서 인증을 사용 하도록 설정 해야 합니다.



</div>

새 등록자를 만들려면 다음 단계를 수행 합니다.

<div>

## <a name="to-create-new-registrar-configuration-settings"></a>새 등록자 구성 설정을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 표시줄에서 **보안**, **등록자**를 차례로 클릭합니다.

4.  **등록자** 페이지에서 **새로 만들기** 를 클릭 합니다.

5.  **서비스 선택**에서 등록자를 적용할 서비스를 클릭 하 고 **확인**을 클릭 합니다.

6.  **새 등록자 설정**에서 환경의 클라이언트 기능 및 지원에 따라 다음 중 하나 이상을 선택 합니다.
    
      - **Kerberos 인증 사용** - 이 풀의 서버가 Kerberos 인증을 사용하여 시도합니다.
    
      - **NTLM 인증 사용** - 이 풀의 서버가 NTLM을 사용하여 시도합니다.
    
      - **인증서 인증 사용** - 이 풀의 서버가 클라이언트에 대한 인증서를 발급합니다.

7.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

