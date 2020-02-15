---
title: 기존 모임 구성 설정 모음 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of meeting configuration settings
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49733736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dee4aeac6c7fad8b82d2b34fd9d4a51b8984e716
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 기존 모임 구성 설정 모음 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

사이트 구성 또는 사용자 구성은 삭제할 수 있습니다. 전역 정책은 제거할 수 없습니다. 전역 구성을 삭제하는 경우 자동으로 구성이 기본값으로 다시 설정됩니다.

<div>

## <a name="to-delete-a-site-or-user-meeting-configuration"></a>사이트 또는 사용자 모임 구성을 삭제하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 표시줄에서 **회의**, **모임 구성**을 차례로 클릭합니다.

4.  모임 구성 목록에서 삭제할 사이트 또는 풀 구성을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.

</div>

<div>

## <a name="removing-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 모임 구성 설정 제거

모임 설정은 Windows PowerShell 및 Get-csmeetingconfiguration cmdlet을 사용 하 여 삭제할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-remove-a-specified-collection-of-meeting-configuration-settings"></a>지정 된 모임 구성 설정 모음을 제거 하려면

  - 다음 명령은 Redmond 사이트에 적용된 모임 구성 설정을 제거합니다.
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-applied-to-the-site-scope"></a>사이트 범위에 적용 된 모든 모임 구성 설정을 제거 하려면

  - 다음 명령은 사이트 범위에 적용된 모든 모임 구성 설정을 제거합니다.
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-that-admit-anonymous-users-by-default"></a>기본적으로 익명 사용자를 허용 하는 모든 모임 구성 설정을 제거 하려면

  - 그리고 다음 명령은 기본적으로 익명 사용자가 승인되도록 허용하는 모든 설정을 제거합니다.
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

</div>

자세한 내용은 [get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

