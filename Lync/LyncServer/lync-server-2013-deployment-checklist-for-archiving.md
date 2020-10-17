---
title: 'Lync Server 2013: 보관용 배포 검사 목록'
description: 'Lync Server 2013: 보관용 배포 검사 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e9fb3085950aa1e8a750d36a0aeb8592bc18113
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557714"
---
# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a>Lync Server 2013의 보관을 위한 배포 검사 목록

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-18_

보관은 Lync Server 2013 배포의 각 프런트 엔드 서버에 자동으로 설치 되지만 사용 하기 전에 설정 해야 합니다. 이 섹션에 요약된 설정에 필요한 단계에 따라 보관을 배포할 수 있습니다.

<div>

## <a name="deployment-sequence"></a>배포 순서

보관 설정 방법은 선택한 저장소 옵션에 따라 달라집니다.

  - 배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하는 경우 사용자에 대해 Lync Server 2013 보관 정책을 구성할 필요가 없습니다. 대신 Exchange 2013에 있는 사용자에 대 한 보관을 지원 하도록 Exchange In-Place 보존 정책을 구성 하 고 해당 사서함을 In-Place 보류에 배치 합니다. 이러한 정책을 구성 하는 방법에 대 한 자세한 내용은 Exchange 2013 제품 설명서를 참조 하십시오.

  - 배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하지 않는 경우에는 Lync Server 보관 데이터베이스 (SQL Server 데이터베이스)를 토폴로지에 추가 하 고 게시 한 다음 사용자에 대 한 정책 및 설정을 구성 하 여 해당 사용자에 대 한 데이터를 보관 해야 합니다. 보관 데이터베이스는 토폴로지를 처음 배포할 때 함께 배포하거나 하나 이상의 프런트 엔드 풀 또는 Standard Edition 서버를 배포한 후에 배포할 수 있습니다. 이 문서에서는 기존 배포에 보관 데이터베이스를 추가하여 배포하는 방법에 대해 설명합니다.

하나의 프런트 엔드 풀 또는 Standard Edition 서버에서 보관을 사용하도록 설정한 경우 배포에 포함된 다른 모든 프런트 엔드 풀 및 Standard Edition 서버에 대해서도 보관을 사용하도록 설정해야 합니다. 통신을 보관해야 하는 사용자가 다른 풀에서 호스팅되는 그룹 IM 대화 또는 모임에 초대될 수 있기 때문입니다. 대화 또는 모임이 호스팅되는 풀에 보관이 설정되어 있지 않으면 전체 세션이 보관되지 않을 수 있습니다. 이러한 경우 보관이 설정된 사용자의 IM은 보관할 수 있지만 회의 콘텐츠 파일 및 회의 입장 또는 퇴장 이벤트가 보관되지 않습니다.

<div>


> [!IMPORTANT]  
> 조직에서 규정 준수를 위해 보관이 중요 한 경우에는 보관을 배포 하 고 적절 한 수준에서 정책 및 기타 옵션을 구성 하 고 모든 해당 2013 사용자에 대해 사용 하도록 설정 해야 합니다.



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a>보관 배포 프로세스

다음 표에서는 기존 토폴로지에 보관을 배포하는 데 필요한 단계에 대한 개요를 제공합니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>단계</th>
<th>단계</th>
<th>역할 및 그룹 구성원 자격</th>
<th>설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>하드웨어 및 소프트웨어 필수 구성 요소 설치</strong></p></td>
<td><ul>
<li><p>Microsoft Exchange 통합 (일부 또는 모든 사용자에 대 한 보관 저장소의 경우 Exchange 2013 사용)을 사용 하려면 기존 Exchange 2013 배포가 필요 합니다.</p></li>
<li><p>일부 또는 모든 사용자의 보관 저장소로 별도의 보관 데이터베이스(SQL Server 데이터베이스 사용)를 사용하려는 경우 해당 서버에서 보관 데이터를 저장할 SQL Server</p></li>
</ul>
<div>

> [!NOTE]  
> 보관은 엔터프라이즈 풀의 프런트 엔드 서버 및 Standard Edition 서버에서 실행됩니다. 이러한 서버를 설치하는 데 필요한 것 외에 추가 하드웨어 또는 소프트웨어 요구 사항은 없습니다.


</div></td>
<td><p>로컬 Administrators 그룹의 구성원인 도메인 사용자</p></td>
<td><p>지원 가능성 설명서의 <a href="lync-server-2013-supported-hardware.md">Lync Server 2013에 대해 지 원하는 하드웨어</a> 입니다.</p>
<p>지원 가능성 설명서의 <a href="lync-server-2013-server-software-and-infrastructure-support.md">서버 소프트웨어 및 인프라 지원 (Lync Server 2013</a> )</p>
<p>계획 설명서의 <a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013에 보관에 대 한 기술 요구 사항</a></p>
<p>배포 설명서의 <a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Lync Server 2013에서 보관용 시스템 및 인프라 설정</a></p>
<p>지원 가능성 설명서의 <a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange server 및 SharePoint 통합 지원은 Lync Server 2013</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>보관을 지원 하기 위한 적절 한 내부 토폴로지 만들기 (배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하지 않는 경우에만)</strong></p></td>
<td><p>토폴로지 작성기를 실행 하 여 Lync Server 2013 보관 데이터베이스 (SQL Server 데이터베이스)를 토폴로지에 추가 하 고 토폴로지를 게시 합니다.</p></td>
<td><p>보관 데이터베이스를 사용하도록 토폴로지를 정의하려는 경우 로컬 Users 그룹의 구성원인 계정</p>
<p>토폴로지를 게시 하려면 domain admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원 인 계정 이며 Lync Server 2013 파일 저장소에 사용할 파일 공유에 대 한 모든 권한 (읽기/쓰기/수정)을 포함 하 고, 토폴로지 작성기에서 필요한 Dacl을 구성할 수 있도록 하는 것입니다.</p></td>
<td><p>배포 설명서의 <a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">기존 Lync Server 2013 배포에 보관 데이터베이스 추가</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>서버 간 인증 구성 (Microsoft Exchange 통합을 사용 하는 경우에만)</strong></p></td>
<td><p>Lync Server 2013 및 Exchange 2013 간에 인증을 사용 하도록 서버를 구성 합니다. 보관을 사용 하도록 설정 하기 전에 <strong>Test-CsExchangeStorageConnectivity testuser_sipUri-Folder 휴지통</strong> 를 실행 하 여 Exchange 보관 저장소 연결을 확인 하는 것이 좋습니다.</p></td>
<td><p>서버에서 인증서를 관리하기 위한 적합한 권한이 있는 계정</p></td>
<td><p>배포 설명서 또는 작업 설명서의 <a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Lync server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리</a></p></td>
</tr>
<tr class="even">
<td><p><strong>보관 정책 및 구성 설정</strong></p></td>
<td><p>Microsoft Exchange 통합, 전역 정책 및 모든 사이트 및 사용자 정책 (모든 데이터 저장소에 대해 Microsoft Exchange 통합을 사용 하지 않을 때)을 사용할지 여부와 중요 모드 및 데이터 내보내기 및 제거와 같은 특정 보관 옵션을 포함 하 여 보관을 구성 합니다.</p>
<p>Microsoft Exchange 통합을 사용 하는 경우 Exchange In-Place 보존 정책을 적절 하 게 구성 합니다.</p></td>
<td><p>RTCUniversalServerAdmins 그룹(Windows PowerShell만) 또는 사용자를 CSArchivingAdministrator 또는 CSAdministrator 역할에 지정</p></td>
<td><p>배포 설명서의 <a href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013에서 보관에 대 한 지원 구성</a></p>
<p>Exchange 제품 설명서 (Microsoft Exchange 통합을 사용 하는 경우)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a>다른 포리스트에 Lync Server 및 Microsoft Exchange 배포

Microsoft Exchange Server를 Lync Server와 같은 포리스트에 배포 하지 않은 경우 다음 Exchange Active Directory 특성이 Lync Server를 배포 하는 포리스트와 동기화 되었는지 확인 해야 합니다.

1.  msExchUserHoldPolicies

2.  proxyAddresses

이 특성은 다중 값 특성입니다. 이 특성을 동기화할 때는 기존 값이 손실되지 않도록 값을 대체하지 않고 병합해야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

