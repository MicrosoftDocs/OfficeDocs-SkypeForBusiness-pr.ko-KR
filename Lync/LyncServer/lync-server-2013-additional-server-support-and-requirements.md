---
title: 'Lync Server 2013: 추가 서버 지원 및 요구 사항'
description: 'Lync Server 2013: 추가 서버 지원 및 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3af9b3489ba62b3b2dc7cf4fa16cabfe80003e1e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542334"
---
# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a>Lync Server 2013의 추가 서버 지원 및 요구 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-12-09_

이 지원 가능성 설명서의 다른 섹션에 설명 된 소프트웨어 지원 외에도 Lync Server 2013에는 다음과 같은 지원 제한이 있습니다.

  - Lync Server 2013에서는 특정 서버 역할에 대해 DNS (Domain Name System) 및 하드웨어 부하 분산을 지원 합니다. 또한 중재 서버에 대해 응용 프로그램 부하 분산을 지원합니다(해당되는 경우). 각 부하 분산을 사용하는 경우에 대한 자세한 내용은 계획 설명서를 참조하십시오.

  - Lync Server 2013에서는 DLX (메일 그룹 확장 프로토콜)를 사용 하 여 메일 그룹을 확장 합니다. 이 프로토콜은 메일 그룹의 구성원을 가져오는 데 사용되는 웹 서비스 메서드를 지정합니다. Microsoft Exchange Server는 정적으로 할당 된 구성원이 없는 동적 그룹을 지원 합니다. 대신, 그룹이 확장될 때 평가된 쿼리를 저장합니다. DLX는 동적 메일 그룹을 지원하지 않습니다. 이 DLX 제한은 모든 버전의 Lync Server에 적용 됩니다.

  - 사용자 사용 마법사는 영어가 아닌 문자의 SIP 호환 URI로의 자동 변환을 지원하지 않으므로 SIP 주소를 수동으로 수정해야 합니다.

  - 바이러스 백신 소프트웨어를 실행 하는 서버의 경우 제안 된 바이러스 제외 및 기타 보안 관련 권장 사항에 대해 [Lync Server 2013에 대 한 바이러스 백신 검사 제외](lync-server-2013-antivirus-scanning-exclusions.md) 를 참조 하세요.

  - IPsec를 사용하는 경우 오디오 및 비디오 트래픽에 사용되는 포트 범위에서 IPSec를 사용하지 않는 것이 좋습니다. 자세한 내용은 계획 설명서에서 [Lync Server 2013의 IPsec 예외](lync-server-2013-ipsec-exceptions.md) 를 참조 하십시오.

  - 조직에서 QoS(서비스 품질) 인프라를 사용하는 경우 미디어 하위 시스템은 이러한 기존 인프라 내에서 작동하도록 설계됩니다. QoS를 구현 하는 방법에 대 한 자세한 내용은 작업 설명서에서 [Lync Server 2013의 qos (서비스 품질) 관리](lync-server-2013-managing-quality-of-service-qos.md) 를 참조 하세요.

  - 운영 체제 방화벽 사용이 지원됩니다. Lync Server 2013에서는 Microsoft SQL Server 데이터베이스 소프트웨어를 제외 하 고 운영 체제 방화벽에 대 한 방화벽 예외를 관리 합니다. SQL Server 방화벽 요구 사항에 대한 자세한 내용은 SQL Server 설명서를 참조하십시오.

  - 외부 사용자 액세스에 대한 지원을 구현하는 데 사용되는 외부 인터페이스는 내부 인터페이스와 같은 네트워크가 *아니라* 별도의 서브넷에 있어야 합니다.

  - Lync Server 2013의 XMPP 기능은 Google 대화를 사용한 인스턴트 메시징 페더레이션을 위해 Microsoft에서 테스트 하 고 지원 합니다. 다른 XMPP 시스템의 경우 타사 공급 업체에 문의 하 여 Lync Server 2013의 페더레이션과 모든 배포 또는 문제 해결 권장 사항을 지원 하는지 확인 합니다.

  - Lync Server 2013 누적 2013 업데이트 릴리스는 이제 Lync Server 2013에서 2 단계 인증을 지원 합니다. 자세한 내용은 [Lync Server 2013의 2 단계 인증](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md)을 참조 하세요.

  - 대부분의 내부 서버에는 OAuth ( **Open Authentication** )로 정의 된 인증서 유형이 필요 합니다. Lync Server 배포 마법사의 **요청, 인증서 설치 및 할당** 단계 중에 OAuth 인증서를 요청 하 고 할당 해야 합니다. OAuth 인증서 키의 최소 크기는 1024 비트입니다. 키 길이가 2048 비트 (길이) 보다 작은 인증서를 요청 하면 경고가 표시 될 수 있습니다. 경고 대신 키 길이가 2048이 적용 되는 경우 발생 하는 문제를 방지 하려면 OAuth 인증서에 대해 키 길이 2048를 항상 사용 하는 것이 좋습니다.

  - Windows Server 2008 R2 운영 체제가 시스템 암호화에 FIPS 140-2 알고리즘을 사용 하도록 구성 된 경우 Lync Server 2013 및 Microsoft Exchange Server 2010 서비스 팩 1 (SP1)은 FIPS (정보 처리 표준) 140-2 알고리즘을 지원 합니다. FIPS 지원을 구현 하려면 Lync Server 2013를 실행 하는 각 서버가 지원 되도록 구성 해야 합니다. FIPS 규격 알고리즘 및 FIPS 지원을 구현 하는 방법에 대 한 자세한 내용은 Microsoft 기술 자료 문서 811833, "시스템 암호화: 암호화, 해싱 및 서명에 FIPS 호환 알고리즘 사용 보안 설정 (Windows XP 및 이후 버전의 Windows)을 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833) . Exchange 2010의 FIPS 140-2 지원 및 제한 사항에 대 한 자세한 내용은에서 "Exchange 2010 SP1 및 FIPS 호환 알고리즘에 대 한 지원"을 참조 하세요 [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335) .

Lync Server 2013를 사용 하려면 배포 전 또는 중에 특정 구성 요소에 다른 소프트웨어를 설치 해야 합니다. 여기에는 Lync Server 2013을 설치 하는 동안 자동으로 설치 되는 운영 체제, 다운로드 가능한 소프트웨어 및 소프트웨어에서 사용할 수 있는 소프트웨어가 포함 되어 있습니다. 필요할 수 있는 추가 소프트웨어 목록은 다음과 같습니다.

  - Windows Update

  - Windows Identity Foundation

  - Microsoft .NET 4.5 프레임 워크

  - Microsoft Vba 2012 재배포 가능 패키지
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013을 설치 하면 Microsoft Visual c + + 2012 재배포 가능이 자동으로 설치 됩니다. 다른 버전은 설치 및 사용 하면 안 됩니다.

    
    </div>

  - URL 재작성 모듈 버전 2.0 재배포 가능 패키지

  - Windows Media 형식 런타임

  - Windows PowerShell 버전 3.0

  - Microsoft Silverlight 4 브라우저 플러그 인(Lync Server 제어판의 경우 Silverlight 4.0.50524.0 또는 최신 버전)

  - Active Directory 도메인 서비스 도구

이러한 소프트웨어 요구 사항 중 일부는 특정 서버 역할 또는 구성 요소에만 적용됩니다. 이러한 소프트웨어 요구 사항에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 추가 소프트웨어 요구 사항을](lync-server-2013-additional-software-requirements.md) 참조 하십시오.

</div>

<span> </span>

</div>

</div>

</div>

