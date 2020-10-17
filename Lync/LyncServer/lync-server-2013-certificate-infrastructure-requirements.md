---
title: Lync Server 2013 인증서 인프라 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18666f33becabcbdf61370a32900ae7a4819e0cb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508025"
---
# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013의 인증서 인프라 요구 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-06-23_

Lync Server 2013에서는 TLS 및 상호 TLS (MTLS) 연결을 지원 하기 위해 PKI (공개 키 인프라)를 사용 해야 합니다.

Lync Server에서는 다음 용도로 인증서를 사용 합니다.

  - 클라이언트와 서버 간의 TLS 연결

  - 서버 간의 MTLS 연결

  - 파트너의 자동 DNS 검색을 사용한 페더레이션

  - IM(인스턴트 메시징)에 대한 원격 사용자 액세스

  - A/V(오디오/비디오) 세션, 응용 프로그램 공유 및 웹 회의에 대한 외부 사용자 액세스

  - 웹 서비스 자동 검색을 사용하는 모바일 요청

Lync Server의 경우 다음과 같은 일반적인 요구 사항이 적용 됩니다.

  - 모든 서버 인증서는 서버 권한 부여(서버 EKU)를 지원해야 합니다.

  - 모든 서버 인증서에는 CDP(CRL 배포 지점)가 포함되어 있어야 합니다.

  - 모든 인증서는 운영 체제에서 지 원하는 서명 알고리즘을 사용 하 여 서명 해야 합니다. Lync Server 2013는 다이제스트 크기의 sha-1 및 SHA-2 제품군 (224, 256, 384 및 512 비트)을 지원 하며 운영 체제 요구 사항을 충족 하거나 초과 합니다. 운영 체제 지원에 대해서는를 참조 하세요 [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002) .
    
    <div>
    

    > [!NOTE]  
    > RSASSA 서명 알고리즘을 사용 하는 것은 지원 되지 않으며 다른 문제 중에서 로그인 및 착신 전환 문제에 대 한 오류가 발생할 수 있습니다.

    
    </div>

  - Lync Server를 실행 하는 내부 서버에 대해 자동 등록이 지원 됩니다.

  - Lync Server에 지 서버에 대해서는 자동 등록이 지원 되지 않습니다.

  - Windows Server 2003 CA로 웹 기반 인증서 요청을 전송할 때는 Windows Server 2003 SP2 또는 Windows XP를 실행하는 컴퓨터에서 요청을 전송해야 합니다.
    
    KB 922706에서는 Windows Server 2003 인증서 서비스 웹 등록에 대해 웹 인증서를 등록할 때 발생하는 문제를 해결하기 위한 지원 정보가 제공되지만, Windows Server 2008, Windows Vista 또는 Windows 7을 사용하여 Windows Server 2003 CA에서 인증서를 요청할 수는 없습니다.

  - 1024, 2048 및 4096의 암호화 키 길이는 지원 됩니다. 키 길이가 2048 이상인 경우 권장 됩니다.

  - 기본 다이제스트 또는 해시 서명 알고리즘은 RSA입니다. ECDH \_ P256, ecdh \_ P384 및 ecdh \_ P521 알고리즘도 지원 됩니다. 

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013의 외부 사용자 액세스에 대 한 인증서 요구 사항](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Lync Server 2013의 영구 채팅 서버에 대 한 인증서 요구 사항](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Lync Server 2013의 모바일 기능에 대 한 인증서 요구 사항](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

