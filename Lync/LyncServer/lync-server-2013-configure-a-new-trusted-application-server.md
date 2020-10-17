---
title: 'Lync Server 2013: 새 신뢰할 수 있는 응용 프로그램 서버 구성'
description: 'Lync Server 2013: 새 신뢰할 수 있는 응용 프로그램 서버를 구성 합니다.'
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
ms.openlocfilehash: f3cc13c747c5755297b01ae36f27f06d19591acc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552124"
---
# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a>Lync Server 2013에서 신뢰할 수 있는 새 응용 프로그램 서버 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

신뢰할 수 있는 응용 프로그램은 Microsoft Lync Server 2013에서 신뢰할 수 있는 Microsoft 통합 커뮤니케이션 관리 API (가) 3.0 Core SDK를 기반으로 하는 응용 프로그램입니다. 부분 MA 응용 프로그램에 대 한 자세한 내용은의 "통합 커뮤니케이션 관리 API 3.0 Core SDK 설명서"를 참조 하세요 [https://go.microsoft.com/fwlink/p/?linkId=210320](https://go.microsoft.com/fwlink/p/?linkid=210320) .

Microsoft OWA (Outlook web Access) 및 Lync Server 2013을 구성 하는 방법에 대 한 자세한 내용은 Microsoft Exchange Server 2013 설명서에서 "Outlook Web App 및 Lync Server 2010 통합 구성"을 참조 하십시오.

서버 역할을 추가하거나 제거할 때 토폴로지를 게시, 사용하도록 설정 또는 사용하지 않도록 설정하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹의 구성원인 사용자로 로그온해야 합니다. 적절한 관리자 권한을 위임하여 서버 역할을 추가할 수도 있습니다. 자세한 내용은 배포 설명서에서 [Lync Server 2013의 대리인 설치 권한](lync-server-2013-delegate-setup-permissions.md) 를 참조 하십시오. 기타 구성을 변경하려는 경우에는 RTCUniversalServerAdmins 그룹 구성원 자격만 있으면 됩니다.

<div>

## <a name="to-configure-a-trusted-application-server"></a>신뢰할 수 있는 응용 프로그램 서버를 구성하려면

1.  토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.

2.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

3.  **기존 배포에서 토폴로지 다운로드** 및 **확인**을 차례로 클릭합니다.

4.  토폴로지를 **다른 이름으로 저장** 대화 상자에서 사용할 토폴로지 작성기 파일을 클릭 한 다음 **저장**을 클릭 합니다.

5.  왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버**를 마우스 오른쪽 단추로 클릭 하 고 **새 신뢰할 수 있는 응용 프로그램 풀**을 클릭 합니다.

6.  신뢰할 수 있는 응용 프로그램 풀에 대한 **풀 FQDN**을 입력하고 단일 서버로 설정할지 다중 서버로 설정할지 여부를 선택한 후 **다음**을 클릭합니다.

7.  **다음 홉 선택** 페이지의 목록에서 Lync Server 2013 프런트 엔드 풀을 선택 합니다.

8.  **마침**을 클릭합니다.

9.  최상위 노드 **Lync Server 2013**을 선택한 다음 **동작** 메뉴에서 **토폴로지 게시**를 클릭 합니다.
    
    **신뢰할 수 있는 응용 프로그램 풀이** 성공적으로 만들어졌으며 올바른 프런트 엔드 풀과 연결 되어 있어야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

