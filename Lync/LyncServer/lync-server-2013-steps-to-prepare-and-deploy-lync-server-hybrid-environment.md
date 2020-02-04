---
title: 'Lync Server 2013: Lync Server 하이브리드 환경을 준비 및 배포하기 위한 단계'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ebcce8d0021789a409c8f41b5f635d82284b7bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a>Lync Server 2013 하이브리드 환경을 준비 및 배포하기 위한 단계

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-12-08_

다음 표에는 비즈니스용 Skype Online 및 Microsoft Office 365의 하이브리드 배포를 위한 환경을 준비 하는 데 필요한 단계가 나와 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>완료?</th>
<th>단계만</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p>Office 365에 대 한 테 넌 트 계정 만들기 및 Lync Online 사용</p></td>
<td><p>Office <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">365</a>에서 office 365 및 Lync Online에 대해 알아보세요.</p>
<p>Office 365에 대 한 환경이 준비 되었는지 확인 하려면 <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">시스템 요구 사항을</a>참조 하세요.</p>
<p>Office 365 설정에 대 한 자세한 내용은 <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">office 365 시작</a> 및 <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">office 365 설정을</a>참조 하세요.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>도메인 추가 및 소유권 확인</p></td>
<td><p>도메인을 <em>vanity 도메인</em>이라고 하기도 합니다. Office 365 테 넌 트에 도메인을 추가한 다음 단계를 따라 Office 365 도메인의 유효성을 검사 해야 합니다. 이는 사용자가 도메인의 소유자 인지 확인 하는 것입니다.</p>
<p>Office 365 테 넌 트에 도메인을 추가 하려면 <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">도메인을 office 365에 추가</a>에 설명 된 단계를 따릅니다.</p>
<p>Office 365 서비스에 대 한 DNS 레코드 편집을 포함 &quot;하 여 항목의 각 섹션에 있는 모든 단계를 완료 합니다.&quot;</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>환경 준비 확인</p></td>
<td><p>Office 365 설치 도우미를 사용 하 여 Office 365을 배포 하는 데 도움이 될 수 있습니다. 자세한 내용은 <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">설치 도우미를 사용 하 여 Office 365 준비 상태 확인</a>을 참조 하세요.</p>
<p>도구를 사용 하 고 Office 365를 배포 하는 방법에 대 한 자세한 내용은 <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Office 365 배포 가이드</a>를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Active Directory 동기화 준비</p></td>
<td><p>Active Directory 동기화는 온-프레미스 Active Directory를 계속 해 서 Office 365와 동기화 상태로 유지 합니다. 이렇게 하면 각 사용자 계정 및 그룹의 동기화 된 버전을 만들 수 있으며 로컬 Microsoft Exchange Server 환경에서 Microsoft Exchange Online으로 GAL (전체 주소 목록) 동기화를 사용할 수도 있습니다.</p>
<div>

> [!IMPORTANT]  
> 사용자가 Lync Online으로 이동 하지 않은 경우에도 조직에 있는 모든 Lync 사용자의 광고 계정을 온-프레미스 및 온라인 Lync 배포로 동기화 해야 합니다. 모든 사용자를 동기화 하지 않으면 조직에서 온-프레미스 및 온라인 사용자 간의 통신이 예상 대로 작동 하지 않을 수 있습니다.


</div>
<p>Active Directory 동기화를 위해 환경을 준비 하려면 single sign-on 설정을 포함 하 여 <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">디렉터리 동기화 로드맵</a>에 설명 된 단계를 따릅니다.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>AD FS (Active Directory Federation Services)에 대 한 인증서 만들기</p></td>
<td><p>Office 365에서 id 페더레이션에 사용 되는 인증서를 만들어야 합니다. 자세한 내용은 검사 목록의 single sign-on 항목에 사용 하기 위한 AD FS 계획 및 배포의 "페더레이션 서버 인증서" 섹션을 참조 하세요 <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">. AD fs를 사용 하 여 single sign-on을 구현 하 고 관리</a>합니다.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>AD FS에 대 한 인증서 할당</p></td>
<td><p>Office 365에서 id 페더레이션에 사용 되는 인증서를 만든 후에는이를 설치 하 고 할당 해야 합니다.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>파일럿 사용자를 비즈니스용 Skype Online으로 이동</p></td>
<td><p>비즈니스용 Skype Online에 대 한 환경을 준비 하 고 구성 하는 단계를 완료 한 후에는 파일럿 사용자를 Lync Online으로 이동 하는 것을 시작할 수 있습니다.</p>
<p><a href="lync-server-2013-move-users-to-lync-online.md">Lync Server 2013에서 Lync Online으로 사용자 이동을</a>참조 하세요.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>하이브리드 배포에서 사용자 관리</p></td>
<td><p>하이브리드 배포에서 사용자를 관리 하는 방법에 대 한 자세한 내용은 <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">하이브리드 Lync Server 2013 배포에서 사용자 관리</a>를 참조 하세요.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

