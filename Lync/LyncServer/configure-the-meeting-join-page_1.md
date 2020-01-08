---
title: 모임 참가 페이지 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure the meeting join page
ms:assetid: a87319b7-3124-4262-8f9d-18138870ee2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205145(v=OCS.15)
ms:contentKeyID: 48185030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4de88d5c277cb1cef2decb8c51c1c87471dae77
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "40983724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a>모임 참가 페이지 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-12-14_

사용자가 모임 요청에서 모임 링크를 클릭 하면 모임 참가 페이지에서 Lync 2013 클라이언트가 사용자의 컴퓨터에 이미 설치 되어 있는지 여부를 감지 합니다. 클라이언트가 이미 설치 되어 있는 경우 해당 클라이언트에서 모임에 참가 하 고 참석 합니다. 클라이언트가 설치 되어 있지 않으면 기본적으로 2013 버전의 Microsoft Lync Web App이 열립니다.

사용자가 Office Communicator 2007 R2 또는 Lync 2010 수행자와 모임에 참가할 수 있도록 허용 하려면 모임 참가 페이지의 동작을 수정할 수 있습니다. 이러한 구성 옵션은 Lync Server 2013 제어판에서 제거 되었지만 CsWebServiceConfiguration cmdlet을 사용 하 여 구성 합니다.

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
<td><p>True로 설정 되 면 Lync 이외의 클라이언트 응용 프로그램을 사용 하 여 모임에 참가 하는 사용자에 게 Office Communicator 2007 R2를 사용 하 여 모임에 참가할 수 있는 기회가 제공 됩니다. 기본값은 False입니다.</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>True로 설정 하면 온라인 회의에 참가 하는 대체 옵션 (예: Office Communicator 2007 R2)이 자동으로 확장 되어 사용자에 게 표시 됩니다. False (기본값)로 설정 하는 경우 이러한 옵션을 사용할 수 있지만, 사용자는 자동으로 옵션 목록을 표시 해야 합니다.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>Lync Server 2013 관리 셸을 사용 하 여 모임 참가 페이지를 구성 하려면

1.  Lync Server 2013 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync Server 2013**, **lync server Management Shell**을 차례로 클릭 합니다.

2.  다음 cmdlet을 실행 합니다.
    
        Get-CsWebServiceConfiguration
    
    이 cmdlet은 웹 서비스 구성 설정을 반환 합니다.

3.  기본 설정에 따라 매개 변수를 True 또는 False로 설정 하 고 다음 명령을 실행 합니다 (이 cmdlet의 매개 변수에 대 한 자세한 내용은 Lync Server 2013 관리 셸 설명서 참조).
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

