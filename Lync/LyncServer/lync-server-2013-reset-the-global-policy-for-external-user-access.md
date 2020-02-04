---
title: 'Lync Server 2013: 외부 사용자 액세스에 대한 전역 정책 다시 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 971239018f3a8e1bcc92c036f50ed36616256ac7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013에서 외부 사용자 액세스에 대한 전역 정책 다시 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-22_

전역 정책은 완전히 삭제할 수 없습니다. 전역 정책에 대해 **Delete** 옵션을 사용 하면 전역 정책만 기본 설정으로 재설정 되며,이는 외부 사용자 액세스 옵션에 대 한 지원을 포함 하지 않습니다.

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>전역 정책을 기본 설정으로 다시 설정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 하 고 **외부 액세스 정책을**클릭 합니다.

4.  **외부 액세스 정책** 탭에서 전역 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.

5.  삭제를 확인 하는 메시지가 표시 되 면 **확인**을 클릭 합니다. 전역 정책이 재설정 되었음을 알리는 메시지가 페이지 맨 위에 표시 됩니다.

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 전역 외부 액세스 정책 다시 설정

전역 외부 액세스 정책은 Windows PowerShell 및 CsExternalAccessPolicy cmdlet을 사용 하 여 다시 설정할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸에서 또는 원격 세션 Windows PowerShell에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-reset-the-global-external-access-policy"></a>전역 외부 액세스 정책을 다시 설정 하려면 다음을 실행 합니다.

  - 이 명령은 글로벌 외부 액세스 정책을 다시 설정 합니다.
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

자세한 내용은 [제거 CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

