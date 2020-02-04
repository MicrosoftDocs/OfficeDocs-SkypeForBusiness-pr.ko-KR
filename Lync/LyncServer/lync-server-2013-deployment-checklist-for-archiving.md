---
title: 'Lync Server 2013: 보관용 배포 검사 목록'
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
ms.openlocfilehash: e55e2471a71c985861c35c4ec2e07582dbfa0f23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a>Lync Server 2013의 보관용 배포 검사 목록

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-18_

사용자의 Lync Server 2013 배포에서 각 프런트 엔드 서버에 보관이 자동으로 설치 되지만, 사용 하기 전에이를 설정 해야 합니다. 이 섹션에 요약 된 것 처럼 설정 하는 데 필요한 단계는 보관 배포를 구성 합니다.

<div>

## <a name="deployment-sequence"></a>배포 순서

보관을 설정 하는 방법은 어떤 저장소 옵션을 선택 하느냐에 따라 달라 집니다.

  - 배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하는 경우 사용자를 위해 Lync Server 2013 보관 정책을 구성할 필요가 없습니다. 대신 exchange 2013에 있는 사용자의 보관을 지원 하도록 Exchange 원본 위치 유지 정책을 구성 하 고 해당 사서함이 원본 위치 유지에 배치 합니다. 이러한 정책을 구성 하는 방법에 대 한 자세한 내용은 Exchange 2013 제품 설명서를 참조 하세요.

  - 배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하지 않는 경우에는 Lync Server 보관 데이터베이스 (SQL Server 데이터베이스)를 토폴로지에 추가 하 고 게시 하 고 사용자에 대 한 정책 및 설정을 구성 하 고 나 서, 다음을 수행 해야 합니다. 해당 사용자의 데이터를 보관 합니다. 초기 토폴로지를 배포 하거나 적어도 하나 이상의 프런트 엔드 풀 또는 Standard Edition 서버를 배포한 후에는 보관 데이터베이스를 배포할 수 있습니다. 이 문서에서는 보관 데이터베이스를 기존 배포에 추가 하 여 배포 하는 방법을 설명 합니다.

프런트 엔드 풀 또는 Standard Edition 서버 중 하나에서 보관을 사용 하도록 설정 하는 경우 배포의 다른 모든 프런트 엔드 풀 및 Standard Edition 서버에 대해이 기능을 사용 하도록 설정 해야 합니다. 이는 통신을 보관 해야 하는 사용자가 다른 풀에서 호스트 되는 그룹 메신저 대화 또는 모임에 초대 될 수 있기 때문입니다. 대화 또는 모임이 호스팅되는 풀에서 보관을 사용할 수 없는 경우 전체 세션이 보관 되지 않을 수 있습니다. 이러한 경우에는 보관을 사용 하는 사용자를 포함 한 메신저 대화를 계속 보관할 수 있지만 회의 콘텐츠 파일 및 회의 참가 또는 종료 이벤트는 보관이 불가능 합니다.

<div>


> [!IMPORTANT]  
> 조직에서 규정 준수를 위해 보관 하는 것이 중요 한 경우에는 보관을 배포 하 고 적절 한 수준에서 정책 및 기타 옵션을 구성한 다음 모든 해당 사용자에 대해 사용 하도록 설정 하 고 해당 사용자를 Lync Server 2013에 대해 사용 하도록 설정 해야 합니다.



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a>보관 배포 프로세스

다음 표에서는 기존 토폴로지에서 보관을 배포 하는 데 필요한 단계에 대해 간략하게 설명 합니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>단계의</th>
<th>방법은</th>
<th>역할 및 그룹 구성원</th>
<th>설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>필수 하드웨어 및 소프트웨어 설치</strong></p></td>
<td><ul>
<li><p>Exchange 2013를 사용 하 여 일부 또는 모든 사용자의 저장소를 보관 하는 Microsoft Exchange 통합을 사용 하려면 기존 Exchange 2013 배포가 필요 합니다.</p></li>
<li><p>SQL Server 데이터베이스를 사용 하 여 별도의 보관 데이터베이스를 사용 하 여 보관 데이터를 저장 하는 서버의 SQL Server 인 일부 또는 모든 사용자에 대해 저장소를 보관 합니다.</p></li>
</ul>
<div>

> [!NOTE]  
> 보관은 엔터프라이즈 풀 및 Standard Edition 서버의 프런트 엔드 서버에서 실행 됩니다. 해당 서버를 설치 하는 데 필요한 사항 외에 추가 하드웨어 또는 소프트웨어 요구 사항이 없습니다.


</div></td>
<td><p>로컬 관리자 그룹의 구성원 인 도메인 사용자입니다.</p></td>
<td><p>지원 가능성 설명서의 <a href="lync-server-2013-supported-hardware.md">Lync Server 2013에 대해 지원 되는 하드웨어</a></p>
<p>지원 가능성 설명서의 <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013의 서버 소프트웨어 및 인프라 지원</a> .</p>
<p>계획 설명서의 <a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013에서 보관을 위한 기술 요구 사항</a></p>
<p>배포 설명서의 <a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Lync Server 2013에서 보관 하는 시스템 및 인프라 설정</a></p>
<p><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Lync server 2013의 Exchange server 및 SharePoint 통합 지원은</a> 지원 가능성 문서에 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>보관을 지원 하기 위해 적절 한 내부 토폴로지 만들기 (배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하지 않는 경우에만 해당)</strong></p></td>
<td><p>토폴로지 작성기를 실행 하 여 Lync Server 2013 보관 데이터베이스 (SQL Server 데이터베이스)를 토폴로지에 추가한 다음 토폴로지를 게시 합니다.</p></td>
<td><p>보관 데이터베이스를 통합 하는 토폴로지를 정의 하려면 로컬 사용자 그룹의 구성원 인 계정입니다.</p>
<p>토폴로지를 게시 하려면 도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원 이며 Lync Server 2013 파일 저장소에 사용할 파일 공유에 대 한 모든 권한 (읽기/쓰기/수정)이 있는 계정 (토폴로지 작성기가 필수 Dacl을 구성할 수 있도록)이 있어야 합니다.</p></td>
<td><p>배포 설명서의 <a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">기존 Lync Server 2013 배포에 보관 데이터베이스를 추가</a> 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>서버 간 인증 구성 (Microsoft Exchange 통합을 사용 하는 경우에만 해당)</strong></p></td>
<td><p>서버를 구성 하 여 Lync Server 2013와 Exchange 2013 간에 인증을 사용 하도록 설정 합니다. 보관을 사용 하도록 설정 하기 전에 <strong>Test-CsExchangeStorageConnectivity testuser_sipUri – 폴더 Dumpster</strong> 를 실행 하 여 Exchange 보관 저장소 연결을 확인 하는 것이 좋습니다.</p></td>
<td><p>서버에서 인증서를 관리 하기 위한 적절 한 사용 권한이 있는 계정입니다.</p></td>
<td><p>배포 설명서 또는 운영 설명서의 <a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Lync server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리</a></p></td>
</tr>
<tr class="even">
<td><p><strong>보관 정책 및 구성 구성</strong></p></td>
<td><p>Microsoft Exchange 통합, 전역 정책, 모든 사이트 및 사용자 정책 (모든 데이터 저장소에 대해 Microsoft Exchange 통합을 사용 하지 않는 경우), 특정 보관 옵션 (예: 중요 모드 및 데이터)을 포함 하 여 보관을 구성 합니다. 내보내기를 제거 합니다.</p>
<p>Microsoft Exchange 통합을 사용 하는 경우 Exchange 원본 위치 유지 정책을 적절 하 게 구성 합니다.</p></td>
<td><p>RTCUniversalServerAdmins 그룹 (Windows PowerShell에만 해당) 또는 사용자를 CSArchivingAdministrator 또는 CSAdministrator 역할에 할당할 수 있습니다.</p></td>
<td><p>배포 설명서의 <a href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013에서 보관에 대 한 지원을 구성</a> 합니다.</p>
<p>Exchange 제품 설명서 (Microsoft Exchange 통합을 사용 하는 경우)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a>다른 포리스트에 Lync 서버 및 Microsoft Exchange 배포

Microsoft Exchange Server가 Lync Server와 같은 포리스트에 배포 되지 않은 경우 다음 Exchange Active Directory 특성이 Lync Server를 배포 하는 포리스트와 동기화 되었는지 확인 해야 합니다.

1.  msExchUserHoldPolicies

2.  proxyAddresses

이것은 다중 값 특성입니다. 이 특성을 동기화 할 때 기존 값이 손실 되지 않도록 값을 바꾸지 않고 병합 해야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

