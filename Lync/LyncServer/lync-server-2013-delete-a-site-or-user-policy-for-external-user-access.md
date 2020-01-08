---
title: 'Lync Server 2013: 외부 사용자 액세스에 대한 사이트 또는 사용자 정책 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a site or user policy for external user access
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e5539f1d6e55e94845e63b0f42c0ef855694d56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013에서 외부 사용자 액세스에 대한 사이트 또는 사용자 정책 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-22_

**외부 액세스 정책** 페이지의 Lync Server 제어판에 나열 된 사이트 또는 사용자 정책을 삭제할 수 있습니다. 전역 정책을 삭제 해도 실제로 삭제 되지는 않지만 기본 설정으로 다시 설정 되며, 외부 사용자 액세스 옵션에 대 한 지원이 포함 되지 않습니다. 전역 정책 다시 설정에 대 한 자세한 내용은 [Lync Server 2013에서 외부 사용자 액세스에 대 한 전역 정책 다시 설정을](lync-server-2013-reset-the-global-policy-for-external-user-access.md)참조 하세요.

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>외부 사용자 액세스에 대 한 사이트 또는 사용자 정책을 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  **외부 사용자 액세스**를 클릭 하 고 **외부 액세스 정책을**클릭 합니다.

4.  **외부 액세스 정책** 탭에서 삭제 하려는 사이트 또는 사용자 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.

5.  삭제를 확인 하는 메시지가 표시 되 면 **확인**을 클릭 합니다.

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 PIN 정책 제거

Windows PowerShell 및 CsExternalAccessPolicy cmdlet을 사용 하 여 외부 액세스 정책을 삭제할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-remove-a-specific-external-access-policy"></a>특정 외부 액세스 정책 제거

  - 이 명령은 Redmond 사이트에 적용 된 외부 액세스 정책을 제거 합니다.
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>사용자별 범위에 적용 된 모든 외부 액세스 정책을 제거 하려면

  - 이 명령은 사용자 단위 범위에서 구성 된 외부 액세스 정책을 모두 제거 합니다.
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>외부 사용자 액세스를 사용할 수 없는 외부 액세스 정책을 모두 제거 하려면

  - 이 명령은 외부 사용자 액세스를 사용 하지 않도록 설정한 외부 액세스 정책을 모두 삭제 합니다.
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

자세한 내용은 [제거 CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

