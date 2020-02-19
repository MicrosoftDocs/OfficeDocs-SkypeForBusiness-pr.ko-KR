---
title: 'Lync Server 2013: 그룹 구성원 자격 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93c1a79d39a70c21e353799a43c76599cc7af2b5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a>Lync Server 2013에 대 한 그룹 구성원 자격 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-05_

다음 표에는 Lync Server 2013을 성공적으로 설치, 관리 및 문제 해결 하기 위해 사용자가 속해 있어야 하는 그룹이 요약 되어 있습니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lync Server 2013 실행 파일</th>
<th>필요한 그룹 구성원 자격</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Setup.exe – Lync</strong> Server 2013 관리 도구 설치를 시작 하는 실행 파일입니다.</p></td>
<td><p>실행 파일이 실행되는 컴퓨터에서 로컬 Administrators 그룹의 구성원. Active Directory 도메인 서비스에서 정보를 읽을 수 있도록 Domain Users 그룹의 구성원 이어야 합니다. 로컬 컴퓨터에서 필수 MSI 패키지를 자동으로 설치하려면 Program Files 디렉터리와 같은 보호된 로컬 컴퓨터 리소스와 Local Machine 하이브와 같은 보호된 레지스트리를 읽고 쓸 수 있는 권한이 필요하므로 이 사용 권한 수준이 필요합니다.</p>
<div>

> [!TIP]  
> 또한 도메인 관리자 그룹의 구성원 자격을 부여하지 않으려는 사용자 또는 그룹에 설치 권한을 위임할 수 있습니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013의 설치 권한 부여</A> 를 참조 하십시오.


</div></td>
</tr>
<tr class="even">
<td><p><strong>deploy.exe</strong> - setup.exe에 의해 호출되는 deploy.exe는 서버 역할에 대한 소프트웨어 구성 요소를 배포하는 작업을 담당합니다.</p></td>
<td><p>실행 파일이 실행되는 컴퓨터에서 로컬 Administrators 그룹의 구성원. AD DS의 정보를 읽을 수 있는 도메인 사용자 그룹의 구성원. 로컬 컴퓨터에서 필수 MSI 패키지를 자동으로 설치하려면 Program Files 디렉터리와 같은 보호된 로컬 컴퓨터 리소스와 Local Machine 하이브와 같은 보호된 레지스트리를 읽고 쓸 수 있는 권한이 필요하므로 이 사용 권한 수준이 필요합니다. 중앙 관리 저장소를 읽으려면 RtcUniversalReadOnlyAdmins 그룹의 구성원 자격이 필요 합니다.</p>
<div>

> [!NOTE]  
> Windows Vista 운영 체제 또는 Windows 7 운영 체제를 실행 하는 경우에는 UAC (사용자 계정 컨트롤)를 통해 설치를 계속 진행할 것인지 묻는 메시지가 표시 됩니다. 표준 사용자 계정으로 로그온한 경우 소프트웨어를 설치할 권한이 있는 계정이 필요하다는 메시지가 표시되면 로컬 Administrators 그룹 구성원이 자격 증명을 제공해야 합니다.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>bootstrapper.exe</strong> - setup.exe에 의해 호출되는 bootstrapper.exe는 서버 역할을 배포 및 구성하는 작업을 담당합니다.</p></td>
<td><p>실행 파일이 실행되는 컴퓨터에서 로컬 Administrators 그룹의 구성원. Bootstrapper.exe를 실행하려는 경우 RTCUniversalServerAdmins 그룹의 구성원. AD DS의 정보를 읽을 수 있는 Domain Users 그룹의 구성원. 로컬 컴퓨터에서 필수 MSI 패키지를 자동으로 설치하려면 Program Files 디렉터리와 같은 보호된 로컬 컴퓨터 리소스와 Local Machine 하이브와 같은 보호된 레지스트리를 읽고 쓸 수 있는 권한이 필요하므로 이 사용 권한 수준이 필요합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>TopologyBuilder</strong> – 마법사 기반 사용자 인터페이스 Lync Server 2013 토폴로지를 만들고, 보고, 조정 하 고, 유효성을 검사 합니다.</p></td>
<td><p>토폴로지를 표시하기 위해 실행 파일이 실행되는 컴퓨터에서 로컬 Administrators 그룹의 구성원. 구성 설정을 변경하기 위한 RTCUniversalServerAdmins 그룹의 구성원. 토폴로지를 게시하기 위한 RTCUniversalServerAdmins 그룹 및 Domain Admins 그룹의 구성원 또는 RTCUniversalServerAdmins 그룹의 구성원(그룹에 대리인 설치 권한이 부여된 경우만). RTCUniversalServerAdmins 그룹의 구성원이 Domain Admins 그룹의 구성원이 아닌 토폴로지를 게시할 수 있도록 설정 권한을 위임 하는 방법에 대 한 자세한 내용은 배포 설명서에서 <a href="lync-server-2013-granting-setup-permissions.md">Lync Server 2013의 설치 권한 부여</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Adminuihost</strong> -Lync Server 2013을 관리 하기 위한 웹 기반 그래픽 사용자 인터페이스입니다.</p></td>
<td><p>특정 관리 작업이 할당된 CsAdministrator 그룹의 구성원 또는 다른 RBAC(역할 기반 액세스 제어) 역할의 구성원. Lync Server 2013 제어판은 Lync Server 2013 관리 셸 cmdlet을 실행 하 여 구성을 변경 하는 방법을 구현 합니다. 미리 정의 된 역할 및 cmdlet 구성원의 실행을 허용 하는 목록은 계획 설명서의 <a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013에서 역할 기반 액세스 제어에 대 한 계획</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p>Lync server <strong>2013 모듈이 로드</strong> 된 명령줄 관리 도구인 lync server 2013의 관리와 관련 된 cmdlet이 포함 된 PowerShell .exe</p></td>
<td><p>특정 cmdlet이 할당된 CsAdministrator 그룹의 구성원 또는 다른 RBAC 역할의 구성원. 미리 정의 된 역할 및 cmdlet 구성원의 실행을 허용 하는 목록은 계획 설명서의 <a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013에서 역할 기반 액세스 제어에 대 한 계획</a> 을 참조 하십시오.</p>
<p>또는 cmdlet에 따라 다음 그룹 중 하나 이상의 구성원</p>
<ul>
<li><p>RTCUniversalServerAdmins</p></li>
<li><p>RTCUniversalUserAdmins</p></li>
<li><p>RTCUniversalReadOnlyAdmins</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

