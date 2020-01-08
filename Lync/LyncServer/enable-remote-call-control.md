---
title: 원격 통화 제어 사용
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 310a140d3497a77ddcaeb8ba32403aa8f28b68e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a>원격 통화 제어 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-02_

원격 통화 제어를 통해 사용자는 Lync Server 2013를 사용 하 여 데스크톱 개인 PBX (사설 분기 교환) 전화를 제어할 수 있습니다. 레거시 환경에서 원격 통화 제어를 배포 하 고이를 Lync Server 2013로 마이그레이션하려면 다음 작업을 수행 해야 합니다.

1.  SIP/CSTA 게이트웨이를 설치 하 고 PBX와 통신 하도록 구성 합니다. Lync Server 2013 파일럿 풀을 배포 하는 경우이 단계를 수행 해야 합니다.

2.  토폴로지를 병합 하 고 정책 및 설정을 마이그레이션한 후에는 Lync Server 2013에서 SIP/CSTA 게이트웨이에 CSTA 요청을 라우팅하도록 구성 합니다. 이 단계는 자동화 된 마이그레이션에 따르는 수동 단계입니다. CSTA 요청에 대 한 라우팅을 구성 하려면 다음을 수행 합니다.
    
      - 레거시 권한 있는 호스트 항목을 제거 합니다 (Lync Server 2013의 *신뢰할 수 있는 서버 항목* 이라고 함). 레거시 배포에서 사용자를 마이그레이션하는 경우에는 Lync Server 2013 파일럿 풀에서 신뢰할 수 있는 새 응용 프로그램 항목을 구성 하기 전에 먼저 SIP/CSTA 게이트웨이에 대해 만든 기존의 모든 권한 있는 호스트 항목을 제거 해야 합니다. 레거시 권한 있는 호스트 항목을 제거 하는 방법에 대 한 자세한 내용은 [권한이 부여 된 호스트 항목 제거](remove-an-authorized-host-entry.md)를 참조 하세요.
    
      - 원격 통화 제어를 위한 고정 경로를 구성 합니다. 원격 통화 제어를 지원 하려는 개별 풀에 대 한 고정 경로를 구성 하거나 풀 수준 고정 경로로 구성 되지 않은 각 풀에 대해 전역 고정 경로를 사용 하도록 전역 고정 경로를 구성할 수 있습니다. 고정 경로를 구성 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 원격 통화 제어에 대 한 고정 경로 구성을](lync-server-2013-configure-a-static-route-for-remote-call-control.md) 참조 하세요.
    
      - 원격 통화 제어를 지원 하려는 각 풀에서 원격 통화 제어에 대 한 신뢰할 수 있는 응용 프로그램 항목을 구성 합니다. 신뢰할 수 있는 응용 프로그램 항목을 구성 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 원격 통화 제어에 대 한 신뢰할 수 있는 응용 프로그램 항목 구성을](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) 참조 하세요.

3.  TCP (전송 제어 프로토콜)를 사용 하 여 Lync Server 2013에 연결 하는 SIP/CSTA 게이트웨이를 배포한 경우 토폴로지 작성기에서 게이트웨이의 IP 주소를 정의 합니다. IP 주소를 정의 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 SIP/CSTA 게이트웨이 IP 주소 정의](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) 를 참조 하세요.

4.  원격 통화 제어를 사용 하도록 설정 하 고 회선 서버 URI (Uniform Resource Identifier) 및 줄 URI를 할당 하 여 Lync 2013 사용자에 게 원격 통화 제어권을 구성 합니다. 레거시 배포에서 Lync Server 2013로 사용자를 마이그레이션하면 원격 통화 제어 설정이 다른 사용자 설정과 함께 마이그레이션됩니다.

5.  레거시 배포에서 주소록 전화 번호 정규화 규칙을 사용자 지정한 경우 정책 및 설정의 자동화 된 마이그레이션을 완료 한 후 사용자 지정 정규화 규칙을 마이그레이션하면 몇 가지 수동 작업을 수행 해야 합니다. 정규화 규칙을 사용자 지정 하지 않은 경우 주소록과 나머지 토폴로지가 함께 마이그레이션됩니다. 사용자 지정 정규화 규칙을 수동으로 마이그레이션하는 방법에 대 한 자세한 내용은 [주소록 마이그레이션을](migrate-address-book_1.md)참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

