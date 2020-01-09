---
title: 'Lync Server 2013: 사이트에서 Kerberos 인증 제거'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 372c8d4689a2c594c853819ced6ccb92adfa6944
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a>Lync Server 2013의 사이트에서 Kerberos 인증 제거

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-01-16_

이 절차를 성공적으로 완료 하려면 RTCUniversalServerAdmins 그룹의 구성원 인 사용자로 로그온 해야 합니다.

사이트에서 Kerberos 인증을 제거 하거나 사이트를 중지 해야 하는 경우 **CsKerberosAccountAssignment** cmdlet을 사용 하 여 사이트에서 kerberos 인증 계정 할당을 제거 해야 합니다. 다음 절차를 사용 하 여 사이트의 모든 컴퓨터에서 할당을 제거 하는 Kerberos 인증 계정 할당을 제거 합니다.

<div class=" ">


> [!WARNING]  
> Kerberos 사용 계정을 영구적으로 사용 중지 하는 경우 할당을 제거한 후 active directory 사용자 및 컴퓨터에서 active directory 도메인 서비스를 삭제 해야 합니다. 앞으로 개체를 사용 하려는 경우 Active Directory 개체를 유지 하는 것이 좋습니다.



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a>사이트에서 Kerberos 인증을 제거 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 Lync Server 2013를 실행 하는 도메인의 컴퓨터 또는 관리 도구가 설치 된 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  명령줄에서 다음 두 명령을 실행 합니다.
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    예를 들면 다음과 같습니다.
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > 계정 추가 또는 계정 제거와 같은 Kerberos 인증을 변경한 후에는 Lync Server Management Shell 명령 프롬프트에서 <STRONG>Enable-CsTopology</STRONG> 을 실행 해야 합니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

