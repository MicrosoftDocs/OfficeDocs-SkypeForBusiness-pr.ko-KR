---
title: 'Lync Server 2013: 디렉터 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad5c885e032800e4233aaa58c5238c066a87a1df
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a>Lync Server 2013에서 디렉터 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-08_

이 단계에서는 디렉터나 디렉터 풀이 구성되어 있지만 DNS(Domain Name System) SRV 항목에서 여전히 클라이언트에게 풀이나 Standard Edition Server를 사용하여 로그온하라고 지시합니다. Lync 2013 클라이언트에서 디렉터를 사용 하 여 자동으로 로그온 하도록 DNS 레코드를 변경 하기 전에 디렉터를 수동으로 가리켜 클라이언트를 테스트 합니다.

<div>

## <a name="to-test-the-deployment"></a>배포를 테스트하려면

1.  **Csadministrator** 그룹에 속하는 도메인 계정을 사용 하 여 Lync Server 제어판이 설치 된 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  탐색 창에서 **토폴로지**를 클릭 하 고 **상태** 열에서 디렉터 또는 디렉터 풀에 대 한 화살표 ( ![녹색 화살표가 있는 서버 아이콘](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "녹색 화살표가 있는 서버 아이콘"))가 있는 녹색 서버가 있는지 확인 합니다.

4.  Lync Server 2013 클라이언트를 설치한 두 대의 클라이언트 컴퓨터를 연결 하 고 각 컴퓨터에 Lync Server 2013에 대해 사용 하도록 설정 된 다른 사용자 계정을 사용 하 여 로그온 합니다.

5.  클라이언트 컴퓨터 중 한 대에서 **옵션** 메뉴를 클릭하고 **개인** 설정 그룹을 선택한 다음 **고급**, **수동 구성**을 차례로 클릭하고 **내부 서버 이름 또는 IP 주소**를 새 디렉터나 디렉터 풀의 FQDN(정규화된 도메인 이름)으로 설정합니다.

6.  두 클라이언트에 모두 로그온하고 디렉터를 사용한 클라이언트 로그온이 제대로 로그온되는지를 확인하고 다른 사용자의 현재 상태를 확인한 다음 두 사용자가 인스턴트 메시지를 교환할 수 있는지 확인합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

