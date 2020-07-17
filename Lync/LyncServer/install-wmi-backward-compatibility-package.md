---
title: WMI 이전 버전과의 호환성 패키지 설치
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35be17aa08cf26f93a9d4002b23dacdfb35c5143
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a>WMI 이전 버전과의 호환성 패키지 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-02_

WMI 이전 버전과의 호환성 패키지를 설치하지 않고 토폴로지 작성기 병합 마법사를 실행하려고 하면 다음과 같은 오류가 표시됩니다.

![WMI 오류 메시지](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI 오류 메시지")

WMI 이전 버전과의 호환성 패키지를 설치하지 않고 **Merge-CsLegacytopology** cmdlet을 실행하려고 하면 다음과 같은 오류가 표시됩니다.

![Windows PowerShell WMI 공급자 오류](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI 공급자 오류")

WMI 이전 버전과의 호환성 패키지를 설치하려면

1.  설치 미디어에서 \\ SETUP \\ AMD64 setupOCSWMIBC.MSI으로 이동 \\ \\ 합니다.

2.  OCSWMIBC.MSI를 설치합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC.msi는 토폴로지 작성기 병합 마법사가 실행되는 컴퓨터에 설치해야 합니다. 그러나 토폴로지의 모든 프런트 엔드 서버에 OCSWMIBC.msi를 설치하는 것이 좋습니다.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC.msi은 Lync Server 2013 핵심 구성 요소와 Lync Server 2013 관리 셸이 설치 되어 있는 도메인의 컴퓨터에 설치할 수 있으며 Office Communications Server 2007 R2 토폴로지 (WMI 공급자에 게 AD DS (Active Directory 도메인 서비스) 및 SQL Server)에 대 한 액세스 권한이 있습니다.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

