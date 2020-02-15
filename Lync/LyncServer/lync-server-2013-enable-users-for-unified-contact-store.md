---
title: 'Lync Server 2013: 사용자가 통합 연락처 저장소를 사용 하도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b99fd96b16d19305ea5bb63ea9f84096ef6117c7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a>Lync Server 2013에서 통합 연락처 저장소에 사용자 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-07_

Lync Server 2013을 배포 하 고 토폴로지를 게시 하면 기본적으로 모든 사용자에 대해 통합 연락처 저장소가 사용 되도록 설정 됩니다. Lync Server 2013을 배포한 후에는 통합 연락처 저장소를 사용 하도록 설정 하기 위해 추가 작업을 수행할 필요가 없습니다. 하지만 **Set-CsUserServicesPolicy** cmdlet을 사용해서 통합 연락처 저장소를 사용할 수 있는 사용자를 사용자 지정할 수 있습니다. 이 기능은 전역, 사이트별, 테넌트별 또는 개인이나 개인 그룹별로 설정할 수 있습니다.

<div>

## <a name="to-enable-users-for-unified-contact-store"></a>통합 연락처 저장소에 대해 사용자를 설정하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  다음을 수행합니다.
    
      - 모든 Lync Server 사용자에 대해 통합 연락처 저장소를 전역적으로 사용 하도록 설정 하려면 명령줄에 다음을 입력 합니다.
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - 특정 사이트의 사용자에 대해 통합 연락처 저장소를 사용하도록 설정하려면 명령줄에 다음을 입력합니다.
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        예:
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - 테넌트별로 통합 연락처 저장소를 사용하도록 설정하려면 명령줄에 다음을 입력합니다.
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        예:
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - 특정 사용자에 대해 통합 연락처 저장소를 사용하도록 설정하려면 명령줄에 다음을 입력합니다.
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > 또한 사용자 표시 이름 대신 사용자의 별칭 또는 SIP URI를 사용할 수도 있습니다.

        
        </div>
        
        예:
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > 위 예제에서 첫 번째 명령은 UcsAllowed 플래그가 True로 설정된 <EM>UCS Enabled Users</EM>라는 새로운 사용자별 정책을 만듭니다. 두 번째 명령은 정책을 Ken Myer라는 표시 이름의 사용자에게 지정합니다. 즉, Ken Myer가 통합 연락처 저장소를 사용할 수 있도록 설정됩니다.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

