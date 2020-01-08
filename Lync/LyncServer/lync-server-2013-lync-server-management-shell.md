---
title: 'Lync Server 2013: Lync Server 관리 셸'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29fdc8e5f13687d2bed0e0c35609187c57d11592
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a>Lync Server 2013 관리 셸

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2017-09-20_

<div>


> [!NOTE]  
> 비즈니스용 Skype cmdlet 참조가 docs.microsoft.com으로 이동 했습니다. 아래 링크를 클릭 하면 새 docs.microsoft.com 페이지로 이동 합니다. 이제 콘텐츠가 열리고, GitHub를 통해 커뮤니티에서 기고 가능 합니다. 참여 하는 데 관심이 있으십니까? 여기에 있는 리포지토리의 추가 정보를 확인 하세요.<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

Microsoft Lync Server 2010에는 Microsoft Office Communications Server 2007 R2에서 제공 하는 것과 비교 하 여 다양 한 새롭고 향상 된 기능이 도입 되었습니다. 한 가지 개선 사항은 구현을 관리 하는 방법입니다. 예를 들어 Lync Server 제어판 이라는 새 사용자 인터페이스가 있는데,이는 대부분의 사용자가 Microsoft 관리 콘솔에서 사용 하는 대규모 이동을 나타내는 것입니다. 관리 효율성에 대 한 그 밖의 주요 개선 사항은 Windows PowerShell을 포함 하는 것입니다.

Windows PowerShell을 사용 하면 명령줄에서 Microsoft 응용 프로그램을 관리할 수 있습니다. 여기에는 명령줄 환경, 제품별 명령, 전체 스크립팅 언어가 포함됩니다. Windows PowerShell은 먼저 2006에서 발생 하는 Windows 운영 체제의 다운로드 가능한 릴리스로 도입 되었으며 Microsoft Exchange Server 2007의 관리 효율성을 위한 명령줄 인터페이스로 통합 되었습니다. 그 당시에는 microsoft Lync Server 2013의 최신 버전을 Microsoft 서버 제품에 통합 하는 것이 더 커지고 있습니다. Lync Server 2010는 배포의 모든 측면을 관리 하는 데 사용할 수 있는 550 제품별 cmdlet을 도입 했습니다.

다음 섹션에는 cmdlet 및 해당 설명 목록이 나와 있습니다. 이 정보는 명령줄에서 직접 확인할 수도 있습니다. Lync Server 관리 셸 명령 프롬프트에서 다음을 입력 하면 됩니다.

    Get-Help <cmdlet name> -Full

예를 들어 명령 프롬프트에서 **New-CsVoicePolicy** cmdlet에 대한 도움말을 검색하려면 다음을 입력합니다.

    Get-Help New-CsVoicePolicy -Full

Lync Server 2013의 Windows PowerShell에 대해 알아야 할 사항:

  - Lync Server cmdlet을 실행 하려면 Lync Server 관리 셸을 엽니다.
    
    <div>
    

    > [!WARNING]  
    > Lync Server 관리 셸이 아닌 Windows PowerShell 창을 여는 경우 기본적으로 Lync Server cmdlet을 실행할 수 없습니다. Windows PowerShell에서 Lync Server cmdlet을 실행 하려면 먼저 Windows PowerShell 명령 프롬프트에서 다음을 입력 합니다.<BR>가져오기-모듈 Lync

    
    </div>

  - Lync server 관리 셸은 모든 Lync Server Enterprise Edition 프런트 엔드 서버 또는 Standard Edition 서버에 자동으로 설치 됩니다.

  - Windows PowerShell 및 Microsoft Lync Server 2013 cmdlet에 대 한 새로운 및 업데이트 된 정보, 샘플 스크립트, 시작 및 학습에 대 한 도움말은 Lync Server Windows PowerShell 블로그에서 [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)제공 됩니다.

</div>

<span> </span>

</div>

</div>

</div>

