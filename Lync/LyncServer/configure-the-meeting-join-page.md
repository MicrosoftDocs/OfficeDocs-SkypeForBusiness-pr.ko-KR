---
title: 모임 참가 페이지 구성
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: 036c9d03-ad95-4d63-a3d8-6cae1a8ad530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204635(v=OCS.15)
ms:contentKeyID: 48183260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 208f2d24d5617da703b04ea9888dd8b187f31476
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503325"
---
# <a name="configure-the-meeting-join-page"></a>모임 참가 페이지 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-12-14_

사용자가 모임 요청에서 모임 링크를 클릭 하면 모임 참가 페이지에서 Lync 2013 클라이언트가 사용자 컴퓨터에 이미 설치 되어 있는지 여부를 검색 합니다. 클라이언트가 이미 설치되어 있으면 클라이언트가 열리고 모임에 참가합니다. 클라이언트가 설치 되어 있지 않으면 기본적으로 2013 버전의 Lync Web App이 열립니다.

사용자가 Office Communicator 2007 R2 또는 Lync 2010 Attendant와 모임에 참가할 수 있도록 허용 하려는 경우에는 모임 참가 페이지의 동작을 수정할 수 있습니다. 이러한 구성 옵션은 Lync Server 2013 제어판에서 제거 되었지만 Set-cswebserviceconfiguration cmdlet을 사용 하 여 구성 합니다.

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a>모임 참가 페이지 CsWebServiceConfiguration 매개 변수

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>CsWebServiceConfiguration 매개 변수</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>True로 설정 하면 Lync 이외의 클라이언트 응용 프로그램을 사용 하 여 모임에 참가 하는 사용자에 게 Office Communicator 2007 R2를 사용 하 여 모임에 참가할 수 있는 기회가 제공 됩니다. 기본값은 False입니다.</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>True로 설정하면 Office Communicator 2007 R2 등 온라인 전화 회의 참가를 위한 대체 옵션이 자동으로 확장되어 사용자에게 표시됩니다. 기본값인 False로 설정하면 해당 옵션을 사용할 수는 있지만 사용자가 옵션 목록을 직접 표시해야 합니다.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>Lync Server 2013 관리 셸을 사용 하 여 모임 참가 페이지를 구성 하려면

1.  Lync Server 2013 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **lync server 관리 셸을**클릭 합니다.

2.  다음 cmdlet을 실행합니다.
    
        Get-CsWebServiceConfiguration
    
    이 cmdlet는 웹 서비스 구성 설정을 반환합니다.

3.  기본 설정 (이 cmdlet의 매개 변수에 대 한 자세한 내용은 Lync Server 2013 Management Shell 설명서 참조)에 따라 매개 변수를 True 또는 False로 설정한 다음 명령을 실행 합니다.
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

