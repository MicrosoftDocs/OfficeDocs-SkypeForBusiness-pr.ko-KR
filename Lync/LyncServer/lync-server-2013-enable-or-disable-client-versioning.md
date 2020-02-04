---
title: 'Lync Server 2013: 클라이언트 버전 관리 사용 또는 사용 안 함'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f413df3ec1d35438155492a32d9fdff449aec3c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a>Lync Server 2013에서 클라이언트 버전 관리 사용 또는 사용 안 함

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

클라이언트 버전 구성 설정은 전역 또는 특정 사이트에 대해 클라이언트 버전 제어를 설정 또는 해제 하는 데 사용 됩니다. 전역 클라이언트 버전 구성은 Lync Server 2013와 함께 설치 되며 전체 서버 배포에 대해 클라이언트 버전 제어를 사용 하거나 사용 하지 않도록 설정 하는 데 사용 됩니다. 전역 구성을 사용 하도록 설정한 경우 사용자가 로그온 할 때 현재 위치에 있는 모든 클라이언트 버전 정책이 적용 됩니다. 클라이언트 버전 제어를 수행 하지 않으려면 전역 클라이언트 버전 구성을 사용 하지 않도록 설정할 수 있습니다. Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸에서 클라이언트 버전 관리를 사용 하거나 사용 하지 않도록 설정할 수 있습니다.

<div>


> [!NOTE]  
> 익명 사용자는 사용자, 사이트 또는 서비스와 연결되지 않으므로 전역 수준 정책에만 영향을 받습니다.



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 클라이언트 버전 관리를 사용 하거나 사용 하지 않도록 설정 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **클라이언트 버전 구성** 탐색 단추를 클릭 합니다.

4.  이렇게 하려면 다음을 수행합니다.
    
      - 클라이언트 버전 관리를 전역적으로 사용 하거나 사용 하지 않도록 설정 하려면 **전역** 구성을 두 번 클릭 한 다음 설정을 수정 합니다.
    
      - 특정 사이트에 대 한 클라이언트 버전 관리를 사용 하거나 사용 하지 않도록 설정 하려면 **새로 만들기**를 클릭 하 고 사이트를 선택한 다음 **확인**을 클릭 하 고 사이트에 대 한 설정을 수정 합니다.

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 클라이언트 버전 관리 사용 또는 사용 안 함

**Set-CsClientVersionConfiguration** cmdlet을 사용 하 여 클라이언트 버전 관리를 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-enable-client-versioning"></a>클라이언트 버전 관리를 사용 하도록 설정 하려면

  - **Enabled** 속성을 True ($True)로 설정 하 여 클라이언트 버전 관리를 사용 하도록 설정할 수 있습니다.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a>클라이언트 버전 관리를 사용 하지 않으려면

  - **Enabled** 속성을 False ($False)로 설정 하 여 클라이언트 버전 관리를 사용 하지 않도록 설정할 수 있습니다.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

자세한 내용은 [Set CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

