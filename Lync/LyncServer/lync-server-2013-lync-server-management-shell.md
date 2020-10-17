---
title: 'Lync Server 2013: Lync Server 관리 셸'
description: 'Lync Server 2013: Lync Server 관리 셸.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45727c42899defcf20ce36e2a27a9268a52ecd71
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543184"
---
# <a name="lync-server-2013-management-shell"></a>Lync Server 2013 관리 셸

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2017-09-20_

<div>


> [!NOTE]  
> 비즈니스용 Skype cmdlet 참조가 docs.microsoft.com로 이동 되었습니다. 아래 링크를 클릭 하면 새 docs.microsoft.com 페이지로 이동 합니다. 이제 콘텐츠가 사용 가능 하 게 열리고 GitHub를 통한 커뮤니티 기고에 사용할 수 있습니다. 참여에 관심이 있으십니까? 여기에 있는 리포지토리의 추가 정보를 확인 하세요. <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

Microsoft Lync Server 2010에서는 Microsoft Office Communications Server 2007 r 2에서 제공 하는 것과 비교 하 여 다양 한 새 기능과 향상 된 기능이 도입 되었습니다. 개선된 기능 중 하나는 구현을 관리하는 방식입니다. 예를 들어 Lync Server 제어판 이라는 새로운 사용자 인터페이스를 사용 하 여 대부분의 사용자가 Microsoft Management Console을 사용할 수 있는 대규모 이동을 나타냅니다. 관리 효율성이 향상 되는 또 다른 주요 기능은 Windows PowerShell을 포함 하는 것입니다.

Windows PowerShell을 사용 하면 명령줄에서 Microsoft 응용 프로그램을 관리할 수 있습니다. 명령줄 환경, 제품별 명령 및 전체 스크립트 언어를 포함 합니다. Windows PowerShell은 처음에 2006의 Windows 운영 체제에 대 한 다운로드 가능한 릴리스로 도입 되었으며, Microsoft Exchange Server 2007의 관리 효율성을 위한 명령줄 인터페이스로 통합 되었습니다. 이 시점이 계속 해 서 증가 하 고 있으며, 대부분의 Microsoft Server 제품에 통합 되어 있으며, 이러한 제품은 가장 최근 microsoft Lync Server 2013입니다. Lync Server 2010에서는 배포의 모든 측면을 관리 하는 데 사용할 수 있는 550 제품 관련 cmdlet이 도입 되었습니다.

다음 섹션에는 cmdlet 및 해당 설명 목록이 나와 있습니다. 이 정보는 명령줄에서 직접 확인할 수도 있습니다. Lync Server 관리 셸 명령 프롬프트에 다음을 입력 하기만 하면 됩니다.

    Get-Help <cmdlet name> -Full

예를 들어 명령 프롬프트에서 **New-CsVoicePolicy** cmdlet에 대한 도움말을 검색하려면 다음을 입력합니다.

    Get-Help New-CsVoicePolicy -Full

Lync Server 2013의 Windows PowerShell에 대해 알아야 할 사항:

  - Lync Server cmdlet을 실행 하려면 Lync Server 관리 셸을 엽니다.
    
    <div>
    

    > [!WARNING]  
    > Lync Server 관리 셸이 아닌 Windows PowerShell 창을 여는 경우 기본적으로 Lync Server cmdlet을 실행할 수 없게 됩니다. Windows PowerShell 내에서 Lync Server cmdlet을 실행 하려면 먼저 Windows PowerShell 명령 프롬프트에 다음을 입력 합니다.<BR>Import-Module Lync

    
    </div>

  - Lync Server 관리 셸은 모든 Lync Server Enterprise Edition 프런트 엔드 서버 또는 Standard Edition 서버에 자동으로 설치 됩니다.

  - Lync Server Windows PowerShell 블로그에서 Windows PowerShell 및 Microsoft Lync Server 2013 cmdlet에 대 한 새로운 정보와 업데이트 된 정보, 예제 스크립트 및 시작 하는 방법에 대 한 도움말을 확인할 수 있습니다 [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150) .

</div>

<span> </span>

</div>

</div>

</div>

