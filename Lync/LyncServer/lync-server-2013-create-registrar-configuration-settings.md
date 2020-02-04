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
ms.openlocfilehash: 81aec9ee6923dc125769ad16a26390b23155852c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 등록자 구성 설정 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-17_

레지스트라를 사용 하 여 프록시 서버 인증 방법을 구성할 수 있습니다. 지정 하는 인증 프로토콜은 풀의 서버가 클라이언트에 발급 하는 챌린지 유형을 결정 합니다. 사용할 수 있는 프로토콜은 다음과 같습니다.

  - **Kerberos**   클라이언트가 사용할 수 있는 가장 강력한 암호 기반 인증 체계 이지만, 일반적으로 키 배포 센터 (Kerberos 도메인 컨트롤러)에 대 한 클라이언트 연결이 필요 하기 때문에 엔터프라이즈 클라이언트만 사용할 수 있습니다. 이 설정은 서버에서 엔터프라이즈 클라이언트만 인증 하는 경우에 적합 합니다.

  - **NTLM**   암호에 챌린지 응답 해싱 스키마를 사용 하는 클라이언트가 사용할 수 있는 암호 기반 인증입니다. 이것은 원격 사용자와 같은 키 배포 센터 (Kerberos 도메인 컨트롤러)에 연결 되지 않고 클라이언트가 사용할 수 있는 유일한 인증 형태입니다. 서버에서 원격 사용자만 인증 하는 경우 NTLM을 선택 해야 합니다.

  - **인증서 인증**   서버에서 lync Phone Edition 클라이언트, 공통 지역 전화, lync 2013 및 lync Windows 스토어 앱에서 인증서를 가져와야 하는 경우이 방법이 새로운 인증 방법입니다. Lync Phone Edition 클라이언트에서 사용자가 로그인 하 고 PIN (개인 식별 번호)을 제공 하 여 성공적으로 인증 한 후에는 Lync Server 2013에서 SIP URI를 전화기에 프로 비전 하 고 Lync Server에 서명 된 인증서 또는 Joe (Ex: SN=joe@contoso.com)를 식별 하는 사용자 인증서를 해당 전화기로 프로 비전 합니다. 이 인증서는 레지스트라 및 웹 서비스를 사용 하 여 인증 하는 데 사용 됩니다.

<div>


> [!NOTE]  
> 서버에서 원격 및 엔터프라이즈 클라이언트에 대 한 인증을 지 원하는 경우 Kerberos와 NTLM을 모두 사용 하도록 설정 하는 것이 좋습니다. Edge 서버와 내부 서버는 원격 클라이언트에만 NTLM 인증만 제공 되도록 통신 합니다. 이러한 서버에서 Kerberos만 사용 하도록 설정 된 경우에는 원격 사용자를 인증할 수 없습니다. 엔터프라이즈 사용자도 서버에 대해 인증 하는 경우 Kerberos가 사용 됩니다.<BR>Lync Windows 스토어 앱 클라이언트를 사용 하는 경우 인증서 인증을 사용 하도록 설정 해야 합니다.



</div>

새 등록자를 만들려면 다음 단계를 따르세요.

<div>

## <a name="to-create-new-registrar-configuration-settings"></a>새 등록자 구성 설정을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **등록자**를 클릭 합니다.

4.  **등록자** 페이지에서 **새로 만들기** 클릭

5.  **서비스 선택**에서 등록 기관에 적용할 서비스를 클릭 한 다음 **확인**을 클릭 합니다.

6.  **새 등록자 설정**에서 해당 환경의 클라이언트 및 지원 기능에 따라 다음 중 하나 이상을 선택 합니다.
    
      - Kerberos **인증을 사용** 하 여 풀의 서버에서 kerberos 인증을 사용 하 여 문제를 해결 하도록 합니다.
    
      - **Ntlm 인증을 사용** 하 여 풀의 서버에서 ntlm을 사용 하는 데 문제가 있는지 확인 합니다.
    
      - **인증서 인증을 사용 하도록 설정** 하 여 풀의 서버가 클라이언트에 인증서를 발급 하도록 합니다.

7.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

