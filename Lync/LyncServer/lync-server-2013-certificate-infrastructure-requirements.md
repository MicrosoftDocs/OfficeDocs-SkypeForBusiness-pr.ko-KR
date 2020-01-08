---
title: Lync Server 2013 인증서 인프라 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59089e9e44110809374ef0bf11fb2dc97705d0d1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013에 대한 인증서 인프라 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-06-23_

Lync Server 2013에는 TLS 및 상호 TLS (MTLS) 연결을 지원 하기 위한 PKI (공개 키 인프라)가 필요 합니다.

Lync Server는 다음과 같은 목적으로 인증서를 사용 합니다.

  - 클라이언트와 서버 간의 TLS 연결

  - 서버 간 MTLS 연결

  - 파트너의 자동 DNS 검색을 사용 하는 페더레이션

  - IM (인스턴트 메시징)에 대 한 원격 사용자 액세스

  - 오디오/비디오 (A/V) 세션, 응용 프로그램 공유, 회의에 대 한 외부 사용자 액세스

  - 웹 서비스의 자동 검색을 사용 하는 모바일 요청

Lync Server의 경우 다음과 같은 일반적인 요구 사항이 적용 됩니다.

  - 모든 서버 인증서는 서버 권한 부여 (서버 EKU)를 지원 해야 합니다.

  - 모든 서버 인증서에는 CDP (CRL 배포 지점이)가 포함 되어 있어야 합니다.

  - 모든 인증서는 운영 체제에서 지원 되는 서명 알고리즘을 사용 하 여 서명 해야 합니다. Lync Server 2013는 다이제스트 크기의 SHA-1 및 SHA-2 제품군 (224, 256, 384, 512 비트)을 지원 하 고 운영 체제 요구 사항을 충족 하거나 초과 합니다. 운영 체제 지원은을 참조 [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002)하세요.
    
    <div>
    

    > [!NOTE]  
    > RSASSA 서명 알고리즘을 사용 하는 것은 지원 되지 않으며,이 경우 로그인 및 착신 전환 문제에 대 한 오류가 발생할 수 있습니다 (다른 여러 가지 문제).

    
    </div>

  - Lync Server를 실행 하는 내부 서버에 대해 자동 등록이 지원 됩니다.

  - Lync Server Edge 서버에는 자동 등록이 지원 되지 않습니다.

  - Windows Server 2003 CA에 웹 기반 인증서 요청을 제출 하는 경우 Windows Server 2003 SP2 또는 Windows XP를 실행 하는 컴퓨터에서 제출 해야 합니다.
    
    KB922706는 Windows Server 2003 인증서 서비스 웹 등록에 대해 웹 인증서 등록 문제를 해결할 수 있도록 지원 하지만, Windows Server 2008, Windows Vista 또는 Windows 7을 사용 하 여 다음을 요청 하는 것은 불가능 합니다. Windows Server 2003 CA의 인증서

  - 1024, 2048, 4096의 암호화 키 길이가 지원 됩니다. 2048 이상의 키 길이를 권장 합니다.

  - 기본 다이제스트 또는 해시 서명 알고리즘은 RSA입니다. ECDH\_P256, ecdh\_P384, ecdh\_P521 알고리즘도 지원 됩니다. 

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 내부 서버에 대한 인증서 요구 사항](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013의 외부 사용자 액세스에 대한 인증서 요구 사항](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Lync Server 2013의 영구 채팅 서버에 대한 인증서 요구 사항](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Lync Server 2013의 모바일 기능에 대한 인증서 요구 사항](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

