---
title: 'Lync Server 2013: 영구 채팅 서버 테이블 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server tables
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48183659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4902f0710752dd38c146b01bddcc44e135735201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a>Lync Server 2013의 영구 채팅 서버 테이블 목록

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-06_

영구 채팅 데이터베이스 스키마는 다음 테이블로 구성 됩니다.

<div>

## <a name="active-directory-sync"></a>Active Directory 동기화


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>테이블로</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladcookie.md">Lync Server 2013의 tblADCookie</a></p></td>
<td><p>현재 LDAP (Lightweight Directory Access Protocol) 동기화 쿠키가 포함 됩니다. 각 행은 영구 채팅 서버에서 변경 내용을 적극적으로 모니터링 하는 Active Directory 도메인 서비스 도메인에 해당 합니다. (이 표에는 영구 채팅 서버와 관련 된 Active Directory 도메인만 표시 됩니다.)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">Lync Server 2013의 tblPrincipalMemberDifference</a></p></td>
<td><p>Active directory 동기화 단계에 의해 아직 처리 되지 않은 그룹 구성원 변경 내용 (구성원 추가 및 제거 됨)이 포함 되어 있으며 Active Directory Sync의 첫 번째 단계에서 사용 되는 임시 테이블 (tblADUpdates 테이블 포함) 중 하나입니다.</p>
<p>멤버 자격 변경 내용은 tblPrincipal 테이블에 나열 된 그룹 또는 이미 나열 된 구성원에만 저장, 처리 또는 모두 포함 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">Lync Server 2013의 tblADUpdates</a></p></td>
<td><p>Active directory 동기화 단계에 의해 아직 처리 되지 않은 Active Directory 도메인 서비스에 대 한 변경 내용이 포함 되어 있으며, 임시 테이블 (tblPrincipalMemberDifference 테이블 포함) 중 하나를 사용 하 여 Active Directory의 첫 번째 단계에서 사용 됨 시키십시오.</p>
<p>Active Directory에 대 한 변경 내용은 tblPrincipal 테이블에 이미 나열 된 보안 주체에 대해서만 저장, 처리 또는 모두 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">Lync Server 2013의 tblPrincipalMembers</a></p></td>
<td><p>주도자 구성원 자격을 포함 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">Lync Server 2013의 tblPrincipalMeta</a></p></td>
<td><p>Active Directory에서 새로 고쳐야 하는 사용자를 포함 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">Lync Server 2013의 tblSkippedAffiliations</a></p></td>
<td><p>일반적으로 Active Directory access 오류로 인해 몇 가지 이유로 새로 고칠 수 없는 소속을 포함 합니다.</p>
<p>이 표는 정보를 제공 하기 위한 것입니다. 해당 콘텐츠는 사용 되지 않습니다.</p>
<p>올바르게 새로 고칠 수 없는 소속을 포함 하는 주체는 tblPrincipalMeta 테이블에 보관 되며 또 다른 새로 고칠 기회가 제공 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a>주도자, 소속, 노드, 범위, 역할


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>테이블로</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipaltype.md">Lync Server 2013의 tblPrincipalType</a></p></td>
<td><p>TblPrincipal 테이블에 있는 항목을 분류 하는 principal 형식이 포함 되어 있습니다. 이 테이블은 정적입니다. 데이터베이스를 만드는 동안 설정 되며 변경 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">Lync Server 2013의 tblPrincipal</a></p></td>
<td><p>모든 주체 (사용자, 폴더, 그룹 등)를 포함 합니다. 영구 채팅 서버는이를 단순한 혼합 목록으로 처리 합니다. 다양 한 열은 각 주체의 유형을 기반으로 합니다.</p>
<p>이러한 주도자는 대부분 Active Directory에 저장 된 개체의 캐시 복사본입니다. 이러한 Active Directory 개체의 주 테이블에서 캐시 된 복사본을 만드는 것을 <em>프로비저닝</em>이라고 합니다.</p>
<p>일부 주도자는 다른 사용자 보다 적극적으로 만들어지고 일부 Active Directory 개체는 무시 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">Lync Server 2013의 tblPrincipalAffiliations</a></p></td>
<td><p>Active Directory 보안 그룹, Active Directory 컨테이너 등의 멤버 자격을 설명 하는 사용자의 소속을 포함 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">Lync Server 2013의 tblNode</a></p></td>
<td><p>Lync Server 제어판에서 관리 되는 category 노드를 포함 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">Lync Server 2013의 tblRoleType</a></p></td>
<td><p>역할 유형 및 연결 된 사용 권한 집합을 포함 합니다. 이 조회 테이블은 정적입니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblscopeprincipal.md">Lync Server 2013의 tblScopePrincipal</a></p></td>
<td><p>노드에 할당 된 범위를 포함 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalrole.md">Lync Server 2013의 tblPrincipalRole</a></p></td>
<td><p>노드에 할당 된 역할을 포함 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblsiopwhitelist.md">Lync Server 2013의 tblSiopWhiteList</a></p></td>
<td><p>노드와 연결할 수 있는 등록 된 추가 기능을 포함 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblenumattribute.md">Lync Server 2013의 tblEnumAttribute</a></p></td>
<td><p>TblNode 테이블에 &quot;사용&quot; 되 &quot;는&quot; 하드 코드 된 Visibility 및 Behavior 특성만 포함 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">Lync Server 2013의 tblEnumValue</a></p></td>
<td><p>TblNode 테이블에 사용 되 &quot;는 하드 코드 된 Visibility&quot; "및" Behavior 특성의 값이 포함 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a>초대, 채팅 및 기타 클라이언트 지원


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>테이블로</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalinvites.md">Lync Server 2013의 tblPrincipalInvites</a></p></td>
<td><p>자동 초대를 사용 하는 모든 노드에 대해 시스템에서 프로 비전 된 모든 사용자에 대 한 초대를 포함 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblchat.md">Lync Server 2013의 tblChat</a></p></td>
<td><p>모든 채팅 메시지를 포함 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbllastinviteid.md">Lync Server 2013의 tblLastInviteId</a></p></td>
<td><p>각 사용자에 대해 생성 된 마지막 초대 ID (및 tblPrincipalInvites 테이블에 사용 됨)를 포함 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">Lync Server 2013의 tblLastChatId</a></p></td>
<td><p>각 사용자에 대해 생성 된 마지막 채팅 ID (and, tblChat 테이블에서 사용 됨)를 포함 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">Lync Server 2013의 tblPreference</a></p></td>
<td><p>사용자 클라이언트 기본 설정이 포함 되어 있습니다 (레거시 클라이언트에만 사용 됨).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">Lync Server 2013의 tblFileToken</a></p></td>
<td><p>파일 전송 목적에 대 한 임시 토큰이 포함 되어 있습니다. 파일을 업로드 하거나 다운로드할 때마다 영구 채팅 서비스에서 클라이언트가 웹 서비스 파일 저장소에 액세스 하는 데 사용 하는 토큰을 생성 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a>서버 지원


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>테이블로</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblserveridentity.md">Lync Server 2013의 tblServerIdentity</a></p></td>
<td><p>영구 채팅 서버 풀의 활성 서버를 포함 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbladminlock.md">Lync Server 2013의 tblAdminLock</a></p></td>
<td><p>일부 관리자 명령을 실행 하기 위한 관리자 잠금을 포함 합니다. TblSystemRevision 테이블의 시스템 수정 항목이 잠금의 각 릴리스에 대해 증가 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">Lync Server 2013의 tblSystemRevision</a></p></td>
<td><p>여러 서버에서 일관성을 유지 하기 위해 사용 되는 수정 번호 항목 (tblAdminLock 테이블과 함께)이 포함 되어 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">Lync Server 2013의 tblActivePeers</a></p></td>
<td><p>영구 채팅 서비스 간의 현재 피어 투 피어 연결을 포함 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">Lync Server 2013의 tblConfig</a></p></td>
<td><p>영구 채팅 서버에서 지원 되지 않는 구성을 포함 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

