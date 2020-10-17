---
title: 비즈니스용 Skype Online cmdlet을 다른 Windows PowerShell cmdlet과 결합
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb395820f9f90060ac24b737fab08c7d615727c2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499615"
---
# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>비즈니스용 Skype Online cmdlet을 다른 Windows PowerShell cmdlet과 결합

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-07-05_

Windows PowerShell을 사용 하 여 비즈니스용 Skype Online에 연결할 때 약 40 비즈니스용 Skype 온라인 cmdlet을 사용할 수 있습니다. 그러나 비즈니스용 Skype Online을 관리할 때 이러한 40 cmdlet만 사용 하는 것으로 제한 되지는 않습니다. 비즈니스용 Skype 온라인 cmdlet 외에, 컴퓨터에 설치 된 다른 Windows PowerShell cmdlet을 사용할 수도 있습니다. Windows PowerShell 3.0을 설치 하면 수백 개의 핵심 Windows PowerShell cmdlet도 설치 됩니다. 이 명령은 비즈니스용 Skype 온라인 cmdlet 및 컴퓨터에서 사용할 수 있는 다른 모든 cmdlet을 혼합 하 고 일치 시킬 수 있습니다.

Windows PowerShell 3.0의 전체 과정은이 문서의 범위를 벗어나지만 cmdlet을 혼합 하 여 일치 시킬 수 있는 이유를 보여 주는 몇 가지 예는 다음과 같습니다. 첫째, 비즈니스용 Skype Online cmdlet에는 인쇄 명령이 포함 되지 않으며, 이러한 명령을 Windows PowerShell 콘솔에서 찾을 수 없습니다. 그렇다면 cmdlet에서 검색 된 정보를 출력 하려면 어떻게 해야 합니까? 한 가지 방법은 정보를 검색 한 다음이 정보를 **출력** 하는 데 사용 되는 cmdlet입니다.

    Get-CsTenant | Out-Printer

추가 매개 변수가 포함 되지 않으므로 **출력을 사용** 하는 모든 정보가 기본 프린터로 인쇄 됩니다.

마찬가지로 비즈니스용 Skype Online cmdlet에는 데이터를 파일에 저장할 수 있는 매개 변수가 포함 되어 있지 않습니다. 그러나이 명령은 다음 명령을 사용 **하 여 반환** 되는 정보를 텍스트 파일 C: \\ LogsTenants.txt에 저장 합니다. \\

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

그리고이 명령은 **Select-Object** cmdlet을 사용 하 여 화면에 반환 되 고 표시 되는 데이터를 제한 합니다. 이 예에서 [get-csonlineuser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet은 모든 비즈니스용 Skype Online 사용자에 대 한 정보를 검색 한 다음, **Select-Object** cmdlet을 사용 하 여 표시 되는 데이터를 사용자의 id 값 및 보관 정책으로 제한 합니다.

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

컴퓨터에서 사용할 수 있는 cmdlet은 수백 개 이므로 비즈니스용 Skype 온라인 cmdlet을 사용 하는 cmdlet을 결정 하는 데 어려움이 있을 수 있습니다. 비즈니스용 Skype Online cmdlet (및 비즈니스용 Skype Online cmdlet)의 목록을 반환 하려면 먼저 비즈니스용 Skype 온라인 cmdlet이 모두 포함 된 임시 Windows PowerShell 모듈의 이름을 확인 해야 합니다. 이렇게 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.

    Get-Module

화면에 다음과 같은 정보가 표시 됩니다.

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

ModuleType 스크립트가 있는 모듈은 비즈니스용 Skype Online cmdlet이 포함 된 모듈입니다. 이러한 cmdlet의 목록을 반환 하려면 스크립트 모듈 이름을 모듈 이름으로 사용 하 여 **Get-Command** cmdlet을 실행 합니다.

    Get-Command -Module tmp_5astd3uh.m5v

스크립트와 같은 ModuleType이 포함 된 모듈이 여러 개 있을 수 있습니다. 이 경우 다음 명령을 실행 하 여 **CsTenant** cmdlet이 포함 된 모듈을 확인할 수 있습니다.

    Get-Command Get-CsTenant

**CsTenant** cmdlet에 대해 반환 되는 모듈은 비즈니스용 Skype Online cmdlet이 모두 포함 된 모듈입니다.

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>참고 항목


[Windows PowerShell 및 비즈니스용 Skype 온라인 소개](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

