---
title: 'Lync Server 2013: Windows PowerShell 3.0 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 471fd6bd04dd1ec0839aa32c4e71d171dea28de7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a>Lync Server 2013용 Windows PowerShell 3.0 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-06-27_

Lync Server 2013를 성공적으로 배포 하려면 Lync Server 토폴로지의 일부인 각 컴퓨터에 Windows PowerShell 3.0이 필요 합니다.

이제 Windows Server 2012 또는 Windows Server 2012 R2를 실행 하는 시스템의 경우이 작업을 수행할 필요가 없으며 PowerShell 3.0이 해당 운영 체제에 포함 되어 있기 때문에 다음 배포 단계로 진행할 수 있습니다.

<div>


> [!IMPORTANT]  
> 그러나 Windows Server 2008 R2 SP1을 실행 하는 시스템의 경우 Lync Server 2013을 설치 하기 전에 PowerShell 3.0을 필수 구성 요소로 설치 하거나 작업을 수행 하지 않는 것이 필요 합니다. PowerShell 3.0를 설치 하려면 <A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows 관리 프레임 워크 3.0</A>을 참조 하세요. 이는 PowerShell 3.0 다운로드 페이지에 대 한 직접 링크 이며 성공적으로 설치 하는 데 관련 된 정보를 보여 주는 것입니다.



</div>

설치를 완료 한 경우 또는 Lync Server 배포를 계속 하기 전에 확인 하려는 경우에는 다음을 수행 하는 경우 PowerShell 3.0이 서버에 있는지 확인 하는 것이 매우 간단 합니다.

1.  확인 하려는 서버에서 **시작**, **모든 프로그램**, **보조 프로그램**, **windows powershell**, **windows powershell**을 차례로 클릭 합니다.

2.  Windows PowerShell 콘솔의 명령 프롬프트에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Get-Host | Select-Object Version

3.  Windows PowerShell 3.0이 설치 되어 있는 경우 다음과 같은 출력이 표시 됩니다.
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

