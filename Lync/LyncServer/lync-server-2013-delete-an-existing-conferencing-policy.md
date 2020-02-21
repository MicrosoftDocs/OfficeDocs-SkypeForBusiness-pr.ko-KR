---
title: 'Lync Server 2013: 기존 회의 정책 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing conferencing policy
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49733688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 679d88a1d359ea9590262d78e49ab8fa7fbc3906
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-conferencing-policy-in-lync-server-2013"></a>Lync Server 2013에서 기존 회의 정책 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

사용자 수준 또는 사이트 수준 회의 정책을 삭제하려면 다음 단계를 수행합니다.

<div>


> [!NOTE]  
> 전역 회의 정책은 삭제할 수 없습니다.



</div>

<div>

## <a name="to-delete-a-site-or-user-conferencing-policy"></a>사이트 또는 사용자 회의 정책을 삭제하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **회의**를 클릭하고 **회의 정책**을 클릭합니다.

4.  회의 정책 목록에서 삭제 하려는 사이트 또는 사용자 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.

</div>

<div>

## <a name="removing-conferencing-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 회의 정책 제거

Lync Server 관리 셸 및 **get-csconferencingpolicy** cmdlet을 사용 하 여 회의 정책을 삭제할 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-remove-a-specified-conferencing-policy"></a>지정된 회의 정책을 제거하려면

  - 다음 명령은 ID RedmondConferencingPolicy가 포함된 회의 정책을 제거합니다.
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-policies-applied-to-the-per-user-scope"></a>사용자별 범위에 적용된 모든 회의 정책을 제거하려면

  - 다음 명령은 사용자별 범위에 구성된 모든 회의 정책을 제거합니다.
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-polices-that-allow-recording-by-external-users"></a>외부 사용자의 기록을 허용하는 모든 회의 정책을 제거하려면

  - 다음 명령은 외부 사용자가 회의를 기록하도록 허용하는 모든 회의 정책을 삭제합니다.
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

</div>

자세한 내용은 [Remove-get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy)를 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

