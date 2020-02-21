---
title: 'Lync Server 2013: cmdlet을 사용 하 여 도메인 준비 반전'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac26e17ad9e0ab13529da438bc2e12bec210808d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a>Cmdlet을 사용 하 여 Lync Server 2013에 대 한 도메인 준비 되돌리기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-29_

**Disable-CsAdDomain** cmdlet을 사용하여 도메인 준비 단계를 반전합니다.

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a>cmdlet을 사용하여 도메인 준비를 반전하려면

1.  도메인의 서버에 Domain Admins 그룹 구성원으로 로그온합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  를 실행합니다.
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    예를 들면 다음과 같습니다.
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    Force 매개 변수가 있으면 도메인에서 하나 이상의 프런트 엔드 서버 또는 A/V 회의 서버가 활성화 된 경우에도 도메인 준비를 롤백합니다. Force 매개 변수가 없는 경우 도메인의 프런트 엔드 서버 또는 A/V 회의 서버가 활성화 되 면 도메인 준비 롤백이 종료 됩니다.
    
    <div>
    

    > [!NOTE]  
    > GlobalSettingsDomainController 매개 변수를 통해 전역 설정이 저장되어 있는 위치를 나타낼 수 있습니다. 설정이 시스템 컨테이너에 저장되어 있는 경우(전역 설정이 구성 컨테이너로 마이그레이션되지 않은 업그레이드 배포에서 일반적임) Active Directory 포리스트의 루트에서 도메인 컨트롤러를 정의합니다. 전역 설정이 구성 컨테이너에 있는 경우(설정이 구성 컨테이너로 마이그레이션된 업그레이드 배포 또는 새 배포에서 일반적임) 포리스트에서 도메인 컨트롤러를 정의합니다. 이 매개 변수를 지정 하지 않으면 cmdlet은 설정이 구성 컨테이너에 저장 된 것으로 가정 하 고 AD&nbsp;DS의 모든 도메인 컨트롤러를 참조 합니다.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에 대 한 도메인 준비 실행](lync-server-2013-running-domain-preparation.md)  


[Lync Server 2013에 대 한 도메인 준비](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

