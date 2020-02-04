---
title: 'Lync Server 2013: 핀 정책 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a PIN policy
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521020(v=OCS.15)
ms:contentKeyID: 48184609
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc11f1383ec652c512fe5542d9a6780ce028c516
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-pin-policy-in-lync-server-2013"></a>Lync Server 2013에서 핀 정책 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

PIN (개인 식별 번호) 정책을 삭제 하려면 다음 단계를 따르세요.

<div>


> [!NOTE]  
> 글로벌 PIN 정책은 삭제할 수 없습니다.



</div>

<div>

## <a name="to-delete-a-pin-policy-in-lync-server-2013-control-panel"></a>Lync Server 2013 제어판에서 핀 정책을 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **고정 정책을**클릭 합니다.

4.  **PIN 정책** 페이지에서 검색 필드에 삭제 하려는 정책의 이름 전체 또는 일부를 입력 합니다.

5.  정책 목록에서 원하는 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.

6.  **확인**을 클릭합니다.

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 PIN 정책 제거

Windows PowerShell 및 CsPinPolicy cmdlet을 사용 하 여 PIN 정책을 삭제할 수 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-remove-a-specific-pin-policy"></a>특정 PIN 정책 제거

  - 이 명령은 Id RedmondPinPolicy를 사용 하 여 PIN 정책을 제거 합니다.
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

</div>

<div>

## <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>사이트 범위에 적용 된 모든 PIN 정책을 제거 하려면

  - 이 명령은 사이트 범위에서 구성 된 PIN 정책을 모두 제거 합니다.
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

</div>

<div>

## <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>공통 패턴을 사용할 수 있는 PIN 정책을 모두 제거 하려면

  - 이 항목은 일반 패턴을 사용할 수 있는 PIN 정책 (: G)을 모두 제거 합니다.
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

</div>

자세한 내용은 [제거 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

