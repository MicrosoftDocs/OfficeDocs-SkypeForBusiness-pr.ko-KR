---
title: 'Lync Server 2013: 사이트에서 Kerberos 인증을 제거 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6546ac3e13795871461dcdd425e96e801ee19e9d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042910"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a>Lync Server 2013에서 사이트에서 Kerberos 인증 제거

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-01-16_

이 절차를 성공적으로 완료하려면 RTCUniversalServerAdmins 그룹의 구성원인 사용자로 로그온해야 합니다.

사이트에서 Kerberos 인증을 제거하거나 사이트를 폐기해야 하는 경우 **Remove-CsKerberosAccountAssignment** cmdlet을 사용하여 사이트에서 Kerberos 인증 계정 할당을 제거해야 합니다. 다음 절차를 사용하여 Kerberos 인증 계정 할당을 제거하면 사이트의 모든 컴퓨터에서 할당이 제거됩니다.

<div class=" ">


> [!WARNING]  
> Kerberos 사용 가능 계정을 영구적으로 해제 하는 경우에는 할당을 제거한 후 Active Directory 사용자 및 컴퓨터를 사용 하 여 Active Directory 도메인 서비스에서이를 삭제 해야 합니다. 나중에 개체를 사용하려는 경우 Active Directory 개체를 유지하고자 할 수 있습니다.



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a>사이트에서 Kerberos 인증을 제거하려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 Lync Server 2013 또는 관리 도구가 설치 된 컴퓨터에 있는 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령줄에서 다음의 두 명령을 실행합니다.
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    예:
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > 계정 추가 또는 계정 제거와 같은 Kerberos 인증을 변경한 후에는 Lync Server 관리 셸 명령 프롬프트에서 <STRONG>Enable-enable-cstopology</STRONG> 을 실행 해야 합니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

