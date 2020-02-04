---
title: 'Lync Server 2013: 통합 연락처 저장소에 사용자 사용'
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
ms.openlocfilehash: 3df3cbd4d71a1decc3607263f2e98b159dc29b2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a>Lync Server 2013에서 통합 연락처 저장소에 사용자 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-07_

Lync Server 2013을 배포 하 고 토폴로지를 게시 하면 모든 사용자가 기본적으로 통합 된 대화 상대 저장소를 사용할 수 있습니다. Lync Server 2013을 배포한 후에는 통합 된 대화 상대 저장소를 사용 하도록 설정 하기 위해 추가 작업을 수행할 필요가 없습니다. 그러나 **Set-Csuser서비스 정책** cmdlet을 사용 하 여 통합 된 연락처 저장소를 사용할 수 있는 사용자를 사용자 지정할 수 있습니다. 사이트, 테 넌 트 또는 개인 또는 개인 그룹 별로 전역으로이 기능을 사용 하도록 설정할 수 있습니다.

<div>

## <a name="to-enable-users-for-unified-contact-store"></a>통합 된 대화 상대 저장소에 대해 사용자를 사용 하도록 설정 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  다음 중 하나를 수행 합니다.
    
      - 모든 Lync Server 사용자에 대해 통합 된 대화 상대 저장소를 전역으로 사용 하도록 설정 하려면 명령줄에 다음을 입력 합니다.
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - 특정 사이트의 사용자에 대해 통합 된 연락처 저장소를 사용 하도록 설정 하려면 명령줄에 다음을 입력 합니다.
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        예를 들면 다음과 같습니다.
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - 테 넌 트에서 통합 대화 상대 저장소를 사용 하도록 설정 하려면 명령줄에 다음을 입력 합니다.
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        예를 들면 다음과 같습니다.
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - 특정 사용자에 대해 통합 된 대화 상대 저장소를 사용 하도록 설정 하려면 명령줄에 다음을 입력 합니다.
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > 사용자 표시 이름 대신 사용자 별칭 또는 SIP URI를 사용할 수도 있습니다.

        
        </div>
        
        예를 들면 다음과 같습니다.
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > 앞의 예제에서 첫 번째 명령은 UcsAllowed 플래그가 True로 설정 된 <EM>UCS를 사용</EM> 하는 사용자 별 정책을 새로 만듭니다. 두 번째 명령은 표시 이름: 진구 Myer를 사용 하 여 사용자에 게 정책을 할당 하며,이는: 진구 Myer이 이제 통합 연락처 저장소에 대해 사용 하도록 설정 됨을 의미 합니다.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

