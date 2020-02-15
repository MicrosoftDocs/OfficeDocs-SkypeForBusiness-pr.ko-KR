---
title: 'Lync Server 2013: 클라이언트 버전 구성 설정 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version configuration settings
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923062(v=OCS.15)
ms:contentKeyID: 50675353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4213008c20181f7525c7cf62eb316820abe66f3f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-client-version-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 클라이언트 버전 구성 설정 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

클라이언트 버전 구성 설정은 클라이언트 버전 제어를 설정하거나 해제하는 데 사용됩니다. 전역 클라이언트 버전 구성은 Lync Server 2013을 사용 하 여 설치 되며, 전체 서버 배포에 대해 클라이언트 버전 제어를 사용 하거나 사용 하지 않도록 설정 하는 데 사용 됩니다. 전역 구성을 사용하도록 설정하면 포함되어 있는 모든 클라이언트 버전 정책이 사용자의 로그온 시도 시 적용됩니다. Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸에서 클라이언트 버전 구성 설정을 볼 수 있습니다.

<div>


> [!NOTE]  
> 익명 사용자는 사용자, 사이트 또는 서비스와 연결되지 않으므로 전역 수준 정책에만 영향을 받습니다.



</div>

<div>

## <a name="to-view-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 클라이언트 버전 구성 설정을 확인 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 하 고 **클라이언트 버전 구성** 탐색 단추를 클릭 합니다.

4.  보려는 클라이언트 버전 구성의 이름을 두 번 클릭 합니다.

</div>

<div>

## <a name="viewing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 클라이언트 버전 구성 설정 보기

**Get-CsClientVersionConfiguration** cmdlet을 사용 하 여 클라이언트 버전 구성 설정을 볼 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-view-client-version-configuration-information"></a>클라이언트 버전 구성 정보를 보려면

  - 모든 클라이언트 버전 구성 설정에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.
    
        Get-CsClientVersionConfiguration
    
    그러면 다음과 같은 정보가 반환됩니다.
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

</div>

자세한 내용은 [Get-help Clientversionconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

