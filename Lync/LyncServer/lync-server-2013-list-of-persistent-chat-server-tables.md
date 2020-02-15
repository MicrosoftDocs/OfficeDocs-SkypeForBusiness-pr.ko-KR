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
ms.openlocfilehash: 4327e2a72f91e17fd71cd198940ea01d10423b00
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a>Lync Server 2013의 영구 채팅 서버 테이블 목록

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-06_

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
<th>목차가</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladcookie.md">Lync Server 2013의 tblADCookie</a></p></td>
<td><p>현재 LDAP (Lightweight Directory Access Protocol) 동기화 쿠키가 들어 있습니다. 각 행은 영구 채팅 서버가 적극적으로 변경 내용을 모니터링 하는 Active Directory 도메인 서비스 도메인에 해당 합니다. (이 표에는 영구 채팅 서버와 관련 된 Active Directory 도메인만 표시 됩니다.)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">Lync Server 2013의 tblPrincipalMemberDifference</a></p></td>
<td><p>나중에 Active Directory 동기화 단계에서 아직 처리 되지 않은 그룹 구성원 자격 변경 내용 (추가 및 제거 된 구성원)을 포함 하며, Active Directory 동기화의 첫 단계에서 사용 되는 임시 테이블 (tblADUpdates 테이블 포함) 중 하나입니다.</p>
<p>멤버 자격 변경 내용은 tblPrincipal 테이블에 나열 된 그룹에 대해서만 저장 또는 처리 되거나 둘 다에 있거나 이미 나열 된 멤버를 포함 하 고 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">Lync Server 2013의 tblADUpdates</a></p></td>
<td><p>후속 Active Directory 동기화 단계에서 아직 처리 되지 않고 active directory의 첫 단계에서 사용 되는 임시 테이블 (tblPrincipalMemberDifference과 함께) 중 하나인 Active Directory 도메인 서비스에 대 한 변경 내용을 포함 합니다. Activesync.</p>
<p>Active Directory에 대 한 변경 내용은 tblPrincipal 테이블에 이미 나열 된 보안 주체에 대해서만 저장 또는 처리 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">Lync Server 2013의 tblPrincipalMembers</a></p></td>
<td><p>보안 주체 구성원을 포함 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">Lync Server 2013의 tblPrincipalMeta</a></p></td>
<td><p>Active Directory에서 새로 고쳐야 하는 보안 주체를 포함 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">Lync Server 2013의 tblSkippedAffiliations</a></p></td>
<td><p>일반적으로 Active Directory 액세스 오류로 인해 새로 고칠 수 없는 이유를 포함 합니다.</p>
<p>이 테이블은 정보를 제공 하기 위한 것입니다. 해당 콘텐츠는 사용 되지 않습니다.</p>
<p>올바르게 새로 고칠 수 없는 인이 있는 주체는 tblPrincipalMeta 테이블에 보관 되며 또 다른 새로 고칠 수도 있습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a>보안 주체, 소속, 노드, 범위 및 역할


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>목차가</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipaltype.md">Lync Server 2013의 tblPrincipalType</a></p></td>
<td><p>TblPrincipal 테이블에 있는 것을 분류 하기 위한 보안 주체 유형이 포함 되어 있습니다. 정적 테이블입니다. 데이터베이스를 만드는 동안 설정 되며 변경 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">Lync Server 2013의 tblPrincipal</a></p></td>
<td><p>모든 보안 주체 (사용자, 폴더, 그룹 등)를 포함 합니다. 영구 채팅 서버는이를 단순 유형이 다른 목록으로 처리 합니다. 각 보안 주체의 유형을 기반으로 하는 여러 열이 있습니다.</p>
<p>이러한 보안 주체 대부분은 Active Directory에 저장 된 개체의 캐시 된 복사본입니다. 이러한 Active Directory 개체의 주 테이블에 캐시 된 복사본을 만드는 것을 <em>프로 비전</em>이라고 합니다.</p>
<p>일부 보안 주체는 다른 사용자 보다 적극적으로 만들어지며 일부 Active Directory 개체는 무시 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">Lync Server 2013의 tblPrincipalAffiliations</a></p></td>
<td><p>Active Directory 보안 그룹, Active Directory 컨테이너 등에 있는 구성원을 설명 하는 보안 주체를 포함 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">Lync Server 2013의 tblNode</a></p></td>
<td><p>Lync Server 제어판의 관리 되는 범주 노드를 포함 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">Lync Server 2013의 tblRoleType</a></p></td>
<td><p>역할 유형 및 연결 된 권한 집합을 포함 합니다. 이 코드 체계표가 static입니다.</p></td>
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
<td><p>TblNode 테이블에서 &quot;사용&quot; 되 &quot;는&quot; 하드 코드 된 Visibility 및 Behavior 특성만 포함 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">Lync Server 2013의 tblEnumValue</a></p></td>
<td><p>TblNode 테이블에서 사용 되 &quot;는 하드 코드 된 Visibility&quot; "및" Behavior 특성의 값을 포함 합니다.</p></td>
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
<th>목차가</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalinvites.md">Lync Server 2013의 tblPrincipalInvites</a></p></td>
<td><p>자동 초대가 설정 된 모든 노드에 대해 시스템에서 프로 비전 된 모든 사용자에 대 한 초대를 포함 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblchat.md">Lync Server 2013의 tblChat</a></p></td>
<td><p>모든 채팅 메시지를 포함 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbllastinviteid.md">Lync Server 2013의 tblLastInviteId</a></p></td>
<td><p>각 사용자에 대해 생성 (및 tblPrincipalInvites 테이블에서 사용) 된 마지막 초대 ID를 포함 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">Lync Server 2013의 tblLastChatId</a></p></td>
<td><p>각 사용자에 대해 생성 (및 tblChat 테이블에서 사용) 된 마지막 채팅 ID를 포함 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">Lync Server 2013의 tblPreference 설정</a></p></td>
<td><p>사용자 클라이언트 기본 설정을 포함 합니다 (레거시 클라이언트만 사용 됨).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">Lync Server 2013의 tblFileToken</a></p></td>
<td><p>파일 전송 용도로 사용 되는 임시 토큰이 들어 있습니다. 파일이 업로드 되거나 다운로드 될 때마다 영구 채팅 서비스가 클라이언트에서 웹 서비스 파일 저장소에 액세스 하는 데 사용 하는 토큰을 생성 합니다.</p></td>
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
<th>목차가</th>
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
<td><p>일부 관리자 명령을 실행 하는 관리자 잠금을 포함 합니다. 각 잠금 릴리스 후에는 tblSystemRevision 테이블의 시스템 수정 항목이 증가 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">Lync Server 2013의 tblSystemRevision</a></p></td>
<td><p>TblAdminLock 테이블과 함께 여러 서버 간에 일관성을 유지 하는 데 사용 되는 수정 번호 항목을 포함 합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">Lync Server 2013의 tblActivePeers</a></p></td>
<td><p>영구 채팅 서비스 간의 현재 피어-투-피어 연결을 포함 합니다.</p></td>
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

