---
title: 'Lync Server 2013: 보관 정책 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving policy
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48184043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 926cc7e45fe3e57c189b01ff92da49342506dc2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a>Lync Server 2013에서 보관 정책 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

사용자 정책 또는 사이트 정책을 삭제할 수 있습니다. 전역 정책은 제거할 수 없습니다. 전역 정책을 삭제 하려고 하면 Lync Server 2013에서 자동으로 정책을 기본값으로 다시 설정 합니다.

<div>


> [!NOTE]  
> 배포에 Microsoft Exchange 통합을 사용 하도록 설정한 경우 Exchange 정책은 Exchange 2013에 있는 사용자에 대해 보관을 사용할 수 있는지 여부를 제어 하 고 사서함이 원본 위치 유지에 배치 되도록 합니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하세요.



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a>보관을 위해 사용자 또는 사이트 정책을 삭제 하려면

1.  CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **보관 정책을**클릭 합니다.

4.  보관 정책 목록에서 삭제 하려는 사용자 또는 사이트 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.

5.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 보관 정책 제거

Windows PowerShell 및 **CsArchivingPolicy** cmdlet을 사용 하 여 보관 정책을 삭제할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-remove-a-specified-archiving-policy"></a>지정 된 보관 정책을 제거 하려면

  - 예를 들어, **CsArchivingPolicy** 는 id 사이트: Redmond를 사용 하 여 정책을 삭제 합니다. 사이트 범위에서 구성 된 정책을 삭제 하는 경우 이전에 사이트 정책에서 관리 하는 사용자는 전역 보관 정책에 의해 자동으로 제어 됩니다. 다음 명령은 Redmond 사이트에 적용 된 보관을 제거 합니다.
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a>사용자별 범위에 적용 된 모든 보관 정책을 제거 하려면

  - 이 명령은 사용자별 범위에 적용 된 모든 보관 정책을 제거 합니다.
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a>내부 보관을 사용 하지 않도록 설정 하는 모든 보관 정책을 제거 하려면

  - 이 명령은 내부 보관을 사용 하지 않도록 설정한 모든 보관 정책을 제거 합니다.
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

자세한 내용은 [제거 CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 내부 및 외부 통신 보관 관리](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

