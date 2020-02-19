---
title: 'Lync Server 2013: 영구 채팅 서버에 대 한 배포 검사 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a67d8a755a5647424a00aa7e534f736a4c0b5aa3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013의 영구 채팅 서버에 대 한 배포 검사 목록

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-16_

Lync Server 2013, 영구 채팅 서버를 배포 하려면 올바른 순서로 배포 하 고 필요한 모든 배포 단계를 완료 해야 합니다.

<div>

## <a name="deployment-sequence"></a>배포 순서

하나 이상의 Lync Server 2013, 프런트 엔드 풀 또는 Lync Server 2013, Standard Edition 서버를 포함 하 여 초기 토폴로지를 배포한 후 영구 채팅 서버를 배포할 수 있습니다. 이 항목에서는 영구 채팅 서버를 기존 배포에 추가 하 여 배포 하는 방법에 대해 설명 합니다.

</div>

<div>

## <a name="deployment-process"></a>배포 프로세스

다음 표에는 영구 채팅 서버를 배포 하 고 자세한 내용을 볼 수 있는 링크를 제공 하는 기본 단계가 나와 있습니다.

### <a name="persistent-chat-server-deployment-process"></a>영구 채팅 서버 배포 프로세스

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>작업</th>
<th>단계</th>
<th>필요한 역할 및 그룹 구성원 자격</th>
<th>관련 항목</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>하드웨어 및 소프트웨어 필수 구성 요소 설치</strong></p></td>
<td><p>시스템 요구 사항을 충족하는 하드웨어에 다음을 설치합니다.</p>
<ul>
<li><p>영구 채팅 서버 프런트 엔드 서버에서 다음을 수행 합니다.</p></li>
</ul>
<ul>
<li><p>시스템 요구 사항을 충족 하는 운영 체제</p></li>
<li><p>Lync Server 2013을 실행 하는 컴퓨터에 대 한 소프트웨어 필수 구성 요소</p></li>
<li><p>영구 채팅 서버 데이터베이스를 호스팅할 서버의 SQL Server</p></li>
</ul>
<p>영구 채팅 서버를 준수 해야 하는 경우:</p>
<ul>
<li><p>영구 채팅 서버 준수 데이터베이스를 호스팅할 서버의 SQL Server</p></li>
</ul></td>
<td><p>로컬 Administrators 그룹의 구성원 인 모든 사용자</p></td>
<td><p>지원 가능성 설명서의 <a href="lync-server-2013-supported-hardware.md">Lync Server 2013에 대해 지 원하는 하드웨어</a></p>
<p>지원 가능성 설명서의 <a href="lync-server-2013-server-software-and-infrastructure-support.md">서버 소프트웨어 및 인프라 지원 (Lync Server 2013</a> )</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013에 대 한 시스템 요구 사항 확인</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Lync Server 2013의 영구 채팅 서버에 대 한 기술 요구 사항</a></p></td>
</tr>
<tr class="even">
<td><p><strong>영구 채팅 서버 및 선택적으로 영구 채팅 준수를 지원 하기 위한 적절 한 내부 토폴로지 만들기</strong></p></td>
<td><p>토폴로지 작성기를 실행 하 여 토폴로지에 영구 채팅 서버 풀을 추가 합니다.</p>
<ul>
<li><p>토폴로지에 영구 채팅 서버 구성 요소 추가</p></li>
<li><p>영구 채팅 서버 저장소에 대 한 SQL Server 데이터베이스 만들기 (재해 복구용 백업 SQL Server)</p></li>
<li><p>영구 채팅 서버 파일용으로 새 Lync 파일 저장소를 정의 하거나 기존 Lync 파일 저장소를 사용 합니다.</p></li>
<li><p>요청을 라우팅할 수 있는 Lync Server 2013 풀을이 영구 채팅 서버 풀에 연결 합니다.</p></li>
</ul>
<p>영구 채팅 준수가 필요한 경우:</p>
<ul>
<li><p>영구 채팅 준수 저장소 추가</p></li>
<li><p>준수를 사용 하도록 설정 하려면 영구 채팅 서버 풀 정의 확인란을 클릭 합니다.</p></li>
<li><p>토폴로지 게시</p></li>
</ul>
<p>Standard Edition에 영구 채팅 서버를 설치 하는 경우 영구 채팅 서버 풀의 FQDN (정규화 된 도메인 이름)이 Standard Edition Server와 일치 해야 하며 SQL Server 데이터베이스가 표준의 SQL Server Express 인스턴스에서 배치 된 됩니다. Edition server</p></td>
<td><p>토폴로지를 정의 하려면 로컬 사용자 그룹의 구성원 인 계정입니다.</p>
<p>토폴로지를 게시 하려면 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원 인 계정인 사용자에 게 영구 채팅 서버 파일용 Lync 파일 저장소에 대 한 모든 권한 (읽기/쓰기/수정)이 있어야 합니다 (토폴로지 작성기에서 필요한 Dacl을 구성할 수 있음).</p></td>
<td><p>배포 설명서의 <a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync Server 2013에서 배포에 영구 채팅 서버 추가</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>영구 채팅 서버 배포</strong></p></td>
<td><p>영구 채팅 서버를 실행 하는 모든 컴퓨터에서 Lync Server 설치 프로그램을 실행 합니다. 영구 채팅 서버 설치 프로그램은 다음 지침을 제공 하는 Lync Server 2013 배포 마법사에 통합 되어 있습니다.</p>
<ul>
<li><p>로컬 관리 저장소 배포</p></li>
<li><p>영구 채팅 서버 서비스 설치</p></li>
<li><p>인증서 요청 및 할당</p></li>
<li><p>서비스 실행 및 시작</p></li>
</ul></td>
<td><p>로컬 Administrators 그룹의 구성원 인 모든 사용자</p></td>
<td><p>배포 설명서의 <a href="lync-server-2013-deploying-persistent-chat-server.md">Lync server 2013에서 영구 채팅 서버 배포</a></p></td>
</tr>
<tr class="even">
<td><p><strong>영구 채팅 관리자 만들기</strong></p></td>
<td><p>CsPersistentChatAdministrator 보안 그룹에 사용자를 추가 합니다.</p></td>
<td><p>도메인 관리자의 구성원 인 모든 사용자</p></td>
<td><p>배포 설명서의 <a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Lync Server 2013에서 영구 채팅 관리자 추가</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>영구 채팅 서버 구성</strong></p></td>
<td><p>사용자 구성:</p>
<ul>
<li><p>영구 채팅 서버에 액세스 하려면 사용자가 정책에 따라 설정 되어야 합니다. 기본적으로 정책은 모든 사용자에 대해 해제 되며 전역/사이트/풀/사용자 범위에서 정의 될 수 있습니다.</p></li>
<li><p>설정 구성</p></li>
</ul></td>
<td><p>사용자는 CsPersistentChatAdministrator의 구성원 이어야 합니다. 정책을 변경 하려면 사용자가 CsUserAdministrator에 최소한 있어야 합니다.</p></td>
<td><p>배포 설명서의 <a href="lync-server-2013-configuring-persistent-chat-server.md">Lync server 2013에서 영구 채팅 서버 구성</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> 하나 이상의 영구 채팅 서버 풀을 배포할 수 있습니다. 지정 된 지역에서 생성 된 데이터가 해당 지역에 유지 해야 하는 규정 이유로 여러 영구 채팅 서버 풀을 지원 합니다. 예를 들어 시카고에 영구 채팅 서버 풀을 배포 하는 경우, 스위스의 데이터에 대 한 규정을 준수 하기 위해 취리히 정규에서 사용 하는 경우 사용자는 액세스 권한이 있으면 영구 채팅 서버 풀의 대화방에 연결할 수 있습니다.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

