---
title: WMI 이전 버전과의 호환성 패키지 설치
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c3b8d474ff451a488124ebfbae0ff0872a6cca1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a>WMI 이전 버전과의 호환성 패키지 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-02_

WMI 이전 버전과의 호환성 패키지를 설치 하지 않고 토폴로지 작성기 병합 마법사를 실행 하려고 하면 다음과 같은 오류가 표시 됩니다.

![WMI 오류 메시지](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI 오류 메시지")

WMI 이전 버전과의 호환성 패키지를 설치 하지 않고 **CsLegacytopology** cmdlet을 실행 하려고 하면 다음과 같은 오류가 표시 됩니다.

![Windows PowerShell WMI 공급자 오류](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI 공급자 오류")

WMI 이전 버전과의 호환성 패키지를 설치 하려면

1.  설치 \\미디어에서 setup\\AMD64\\설치\\ocswmibc로 이동 합니다. MSI.

2.  OCSWMIBC를 설치 합니다. MSI.
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC. msi는 토폴로지 작성기 병합 마법사가 실행 되는 컴퓨터에 설치 되어 있어야 합니다. 그러나 토폴로지의 모든 프런트 엔드 서버에 OCSWMIBC. msi를 설치 하는 것이 좋습니다.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC. msi는 Lync Server 2013 Core 구성 요소와 Lync Server 2013 관리 셸이 설치 되어 있는 도메인의 컴퓨터에 설치할 수 있으며, Office Communications Server 2007 R2 토폴로지 (WMI 공급자에 대 한 Active Directory 도메인에 대 한 액세스 권한이 있음) 서비스 (AD DS) 및 SQL Server).

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

