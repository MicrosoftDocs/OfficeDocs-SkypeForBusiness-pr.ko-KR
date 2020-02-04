---
title: 'Lync Server 2013: 신뢰할 수 있는 새 응용 프로그램 서버 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dae7e02d7642fed5fea60235283eaa0d7d7e1e35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a>Lync Server 2013에서 신뢰할 수 있는 새 응용 프로그램 서버 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

신뢰할 수 있는 응용 프로그램은 Microsoft Lync Server 2013에서 신뢰 하는 Microsoft 통합 커뮤니케이션 관리 API (인스턴스 MA) 3.0 Core SDK를 기반으로 하는 응용 프로그램입니다. (C) MA 응용 프로그램에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)"통합 커뮤니케이션 관리 API 3.0 Core SDK 설명서"를 참조 하세요.

Microsoft OWA (Outlook Web Access) 및 Lync Server 2013를 구성 하는 방법에 대 한 자세한 내용은 Microsoft Exchange Server 2013 설명서의 "Outlook Web App 및 Lync Server 2010 통합 구성"을 참조 하세요.

서버 역할을 추가 하거나 제거할 때 토폴로지를 성공적으로 게시, 사용 또는 사용 하지 않도록 설정 하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹의 구성원 인 사용자로 로그온 해야 합니다. 또한 적절 한 관리자 권한과 서버 역할 추가 권한을 위임할 수 있습니다. 자세한 내용은 배포 설명서의 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md) 참조 하세요. 다른 구성 변경의 경우 RTCUniversalServerAdmins 그룹의 구성원만 필요 합니다.

<div>

## <a name="to-configure-a-trusted-application-server"></a>신뢰할 수 있는 응용 프로그램 서버를 구성 하려면

1.  도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 토폴로지 작성기가 설치 된 컴퓨터에 로그온 합니다.

2.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

3.  **기존 배포에서 토폴로지 다운로드**를 선택한 다음 **확인**을 클릭 합니다.

4.  **다른 이름으로 토폴로지 저장** 대화 상자에서 사용할 토폴로지 작성기 파일을 클릭 한 다음 **저장**을 클릭 합니다.

5.  왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버**를 마우스 오른쪽 단추로 클릭 한 다음 **새 신뢰할 수 있는 응용 프로그램 풀**을 클릭 합니다.

6.  신뢰할 수 있는 응용 프로그램 풀의 **풀 FQDN** 을 입력 하 고,이를 단일 서버 또는 다중 서버 중에서 선택 하 고 **다음**을 클릭 합니다.

7.  **다음 홉 선택** 페이지의 목록에서 Lync Server 2013 프런트 엔드 풀을 선택 합니다.

8.  **마침**을 클릭합니다.

9.  최상위 노드 **Lync Server 2013**을 선택한 다음 **작업** 메뉴에서 **토폴로지 게시**를 클릭 합니다.
    
    **신뢰할 수 있는 응용 프로그램 풀이** 성공적으로 만들어지고 올바른 프런트 엔드 풀에 연결 되어 있어야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

