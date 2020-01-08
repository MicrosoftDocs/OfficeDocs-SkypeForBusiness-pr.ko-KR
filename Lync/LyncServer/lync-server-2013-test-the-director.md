---
title: 'Lync Server 2013: 디렉터 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f889d548ddc9b177113aa3e395ac181095de8008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a>Lync Server 2013에서 디렉터 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-08_

이 단계에서는 디렉터 또는 디렉터 풀이 구성 되어 있지만 DNS (Domain Name System) SRV 항목은 여전히 클라이언트에서 풀 또는 Standard Edition 서버를 사용 하 여 로그온 할 수 있도록 지정 합니다. Lync 2013 클라이언트가 디렉터를 사용 하 여 자동으로 로그온 하도록 DNS 레코드를 변경 하기 전에 디렉터를 수동으로 가리켜 클라이언트를 테스트 합니다.

<div>

## <a name="to-test-the-deployment"></a>배포를 테스트 하려면

1.  **Csadministrator** 그룹의 일부인 도메인 계정으로 Lync Server 제어판이 설치 되어 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  탐색 창에서 **토폴로지**를 클릭 하 고 **상태** 열에서 디렉터 또는 디렉터 풀에 대 한 화살표 (즉 녹색 화살표(images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "서버 아이콘과 녹색")화살표가 있는 ![서버 아이콘])가 있는 녹색 서버가 있는지 확인 합니다.

4.  Lync Server 2013 클라이언트를 설치한 두 대의 클라이언트 컴퓨터를 연결 하 고 Lync Server 2013에 대해 사용 하도록 설정 된 다른 사용자 계정으로 각 컴퓨터에 로그온 합니다.

5.  클라이언트 컴퓨터 중 하나에서 **옵션** 메뉴를 클릭 하 고, **개인** 설정 그룹, **고급**, **수동 구성을**차례로 클릭 한 다음 **내부 서버 이름 또는 IP 주소** 를 새 디렉터 또는 디렉터 풀의 FQDN (정규화 된 도메인 이름)으로 설정 합니다.

6.  두 클라이언트에 로그온 하 고 디렉터를 사용 하 여 로그온 하는 클라이언트가 성공적으로 로그온 할 수 있는지 확인 하 고, 다른 사용자의 현재 상태를 확인 하 고, 인스턴트 메시지를 교환할 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

