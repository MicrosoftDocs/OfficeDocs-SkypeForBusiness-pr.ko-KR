---
title: 'Lync Server 2013: 영구 채팅 서버에 대 한 기술 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba8e3e02efeddc1229d3616c0cdcaf4ca241bf24
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42024409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013의 영구 채팅 서버에 대 한 기술 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-01-06_

영구 채팅 서버를 호스트 하는 각 컴퓨터에는 다음과 같은 구성 요소를 포함 하는 기존 Lync Server 2013 토폴로지에 대 한 액세스 권한이 있어야 합니다.

  - **Lync Server 2013, 프런트 엔드 서버**  프런트 엔드 서버는 SIP (Session 착수 프로토콜) 라우팅의 기반 이며 영구 채팅 서버를 실행 하는 컴퓨터와 가능한 영구 채팅 기능을 사용 하 여 통신을 수행 합니다. 영구 채팅 서버 배포를 시작 하기 전에 Lync server 2013, Standard Edition 또는 lync server 프런트 엔드 풀의 배포와 lync server를 실행 하는 다른 모든 내부 컴퓨터 (조직에 적합)를 확인 합니다.

다음 섹션에서는 영구 채팅 서버 및 영구 채팅 데이터를 저장 하는 데이터베이스에 대 한 특정 요구 사항에 대해 설명 합니다.

<div>

## <a name="persistent-chat-server-requirements"></a>영구 채팅 서버 요구 사항

Lync Server 및 최신 버전의 영구 채팅 서버를 배포 하는 데 권장 되는 하드웨어에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md) 을 참조 하십시오.

Lync Server 및 영구 채팅 서버에 대 한 서버 및 도구 운영 체제 지원에 대 한 자세한 내용은 지원 가능성 설명서의 [server and tools 운영 체제 지원에서 Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) 를 참조 하십시오.

영구 채팅 서버를 배포 하는 데 필요한 추가 소프트웨어에 대 한 자세한 내용은 다음 표를 참조 하십시오.

### <a name="persistent-chat-server-software-prerequisites"></a>영구 채팅 서버 소프트웨어 필수 구성 요소

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>소프트웨어</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>메시지 큐</p></td>
<td><p>영구 채팅 서버 및 영구 채팅 준수 서비스 (배포 된 경우)에 사용 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a>영구 채팅 서버 데이터베이스 요구 사항

영구 채팅 서버는 채팅 기록, 구성 및 사용자 프로 비전 데이터를 저장 하기 위해 영구 채팅 데이터베이스를 사용 합니다. 필요한 경우 영구 채팅 준수 데이터베이스를 사용 하 여 준수 데이터를 저장 합니다.

<div>


> [!IMPORTANT]  
> 영구 채팅 데이터베이스 (mgc) 및 준수 데이터베이스 (mgccomp)는 동일한 SQL Server 인스턴스나 다른 SQL 서버에 있을 수 있습니다.



</div>

데이터베이스 서버 플랫폼을 준비 하려면 각 컴퓨터가 하드웨어 요구 사항을 충족 하는지 확인 한 다음 필수 구성 요소 소프트웨어를 설치 해야 합니다.

영구 채팅 데이터베이스 서버에 대 한 서버 플랫폼은 Lync Server 백 엔드 데이터베이스 서버와 동일한 하드웨어를 사용 해야 합니다. 자세한 내용은 지원 가능성 설명서에서 [Lync server 2013에 대 한 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md) 을 참조 하십시오.

데이터베이스 서버에서 다음 소프트웨어 응용 프로그램 중 하나가 설치 되어 있는지 확인해 보십시오.

  - Microsoft SQL Server 2012 Microsoft SQL Server 2012을 설치 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559)"SQL Server 2012 설치"를 참조 하십시오.

  - Microsoft SQL Server 2008 R2 Microsoft SQL Server 2008 r 2를 설치 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702)"Sql server 설치 (sql Server 2008 R2)"를 참조 하십시오.

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a>영구 채팅 서버 인증서 요구 사항

인증서 획득, SQL Server 데이터베이스 만들기 및 파일 저장소 만들기에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013 배포](lync-server-2013-deploying-lync-server.md) 를 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

