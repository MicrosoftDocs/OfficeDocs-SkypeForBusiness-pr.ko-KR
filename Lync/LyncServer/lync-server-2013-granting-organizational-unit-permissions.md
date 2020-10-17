---
title: 'Lync Server 2013: 조직 구성 단위 사용 권한 부여'
description: 'Lync Server 2013: 조직 구성 단위 사용 권한을 부여 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47ad862241e409190620afa7dbf4fa73adf339de
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554514"
---
# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a>Lync Server 2013에서 조직 구성 단위 사용 권한 부여

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-05-14_

포리스트 준비에서 만든 RTC 유니버설 그룹의 구성원이 Domain Admins 그룹의 구성원이 되지 않고도 지정된 OU(조직 구성 단위)에 있는 개체에 액세스할 수 있도록 **Grant-CsOuPermission** cmdlet을 사용하여 해당 개체에 권한을 부여할 수 있습니다. 지정된 OU에 추가된 권한은 도메인 준비가 진행되는 동안 **Enable-CsAdDomain** cmdlet이 컴퓨터 및 사용자 컨테이너에 추가하는 권한과 동일합니다.

**Test-CsOuPermission** cmdlet을 사용하여, **Grant-CsOuPermission** cmdlet을 사용하여 설정한 권한을 확인합니다.

**Revoke-CsOuPermission** cmdlet을 사용하여, **Grant-CsOuPermission** cmdlet을 사용하여 부여한 권한을 제거할 수 있습니다.

<div>

## <a name="to-grant-ou-permissions"></a>OU 권한을 부여하려면

1.  OU 사용 권한을 부여 하려는 도메인에서 Lync Server 2013을 실행 하는 컴퓨터에 로그온 합니다. Domain Admins 그룹 또는 Enterprise Admins 그룹(OU가 다른 하위 도메인에 있는 경우)의 구성원인 계정을 사용합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  을 실행합니다.
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Domain 매개 변수를 지정하지 않는 경우에는 로컬 도메인이 기본값으로 사용됩니다.

</div>

<div>

## <a name="to-verify-ou-permissions"></a>OU 권한을 확인하려면

1.  **부여-CsOuPermission** cmdlet을 사용 하 여 부여한 OU 권한을 확인 하려는 도메인에서 Lync Server 2013을 실행 하는 컴퓨터에 로그온 합니다. Domain Admins 그룹 또는 Enterprise Admins 그룹(OU가 다른 하위 도메인에 있는 경우)의 구성원인 계정을 사용합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  을 실행합니다.
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Domain 매개 변수를 지정하지 않는 경우에는 로컬 도메인이 기본값으로 사용됩니다.

</div>

<div>

## <a name="to-revoke-ou-permissions"></a>OU 권한을 해지하려면

1.  **부여-CsOuPermission** cmdlet에서 부여 된 OU 권한을 해지할 도메인에서 Lync Server 2013을 실행 하는 컴퓨터에 로그온 합니다. Domain Admins 그룹 또는 Enterprise Admins 그룹(OU가 다른 하위 도메인에 있는 경우)의 구성원인 계정을 사용합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  을 실행합니다.
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Domain 매개 변수를 지정하지 않는 경우에는 로컬 도메인이 기본값으로 사용됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

