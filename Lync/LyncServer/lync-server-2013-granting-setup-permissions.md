---
title: 'Lync Server 2013: 설치 권한 부여'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a4642a9e0c77d9cf3aa77c146ff692a7fa7a6c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a>Lync Server 2013에서 설치 권한 부여

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-08-27_

**부여-CsSetupPermission** cmdlet을 사용 하 여 지정 된 ACTIVE Directory OU (조직 구성 단위)에 대 한 RTCUniversalServerAdmins 그룹에 읽기, 쓰기, Readspn 및 WriteSPN 사용 권한을 추가할 수 있습니다. 그런 다음 해당 OU에 있는 RTCUniversalServerAdmins 그룹의 구성원이 Domain Admins 그룹의 구성원이 아닌 지정 된 도메인에서 Lync Server 2013를 실행 하는 서버를 설치할 수 있습니다.

**테스트-** cssetuppermission 사용 권한 cmdlet을 사용 하 여 권한 **부여** 를 사용 하 여 설정한 권한을 확인 합니다.

권한 **부여-CsSetupPermission** cmdlet을 사용 하 여 부여한 권한을 제거할 수 있습니다. **-cssetuppermission** cmdlet을 사용 합니다.

<div>

## <a name="to-grant-setup-permissions"></a>설치 권한을 부여 하려면

1.  설치 권한을 부여 하려는 도메인의 Lync Server 2013를 실행 하는 컴퓨터에 로그온 합니다. 도메인 관리자 그룹의 구성원 인 계정이 나 OU가 다른 자식 도메인에 있는 경우 엔터프라이즈 관리자 그룹을 사용 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  런
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    ComputerOu 매개 변수를 지정 된 도메인의 기본 명명 컨텍스트에 대 한 상대적으로 지정할 수 있습니다 (예: CN = computers). 또는이 매개 변수를 전체 DN (OU 고유 이름)으로 지정할 수 있습니다 (예: "CN = computers, DC = Contoso, DC = com"). 후자의 경우에는 지정한 도메인과 일치 하는 OU DN을 지정 해야 합니다.
    
    Domain 매개 변수를 지정 하지 않으면 로컬 도메인이 기본값이 됩니다.

</div>

<div>

## <a name="to-verify-setup-permissions"></a>설정 사용 권한을 확인 하려면

1.  **허용-CsSetupPermission** cmdlet을 사용 하 여 부여한 설치 권한을 확인할 도메인에서 Lync Server 2013을 실행 하는 컴퓨터에 로그온 합니다. 도메인 관리자 그룹의 구성원 인 계정이 나 OU가 다른 자식 도메인에 있는 경우 엔터프라이즈 관리자 그룹을 사용 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  런
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    ComputerOu 매개 변수를 지정 된 도메인의 기본 명명 컨텍스트에 대 한 상대적으로 지정할 수 있습니다 (예: CN = computers). 또는이 매개 변수를 전체 DN (OU 고유 이름)으로 지정할 수 있습니다 (예: "CN = computers, DC = Contoso, DC = com"). 후자의 경우에는 지정한 도메인과 일치 하는 OU DN을 지정 해야 합니다.
    
    Domain 매개 변수를 지정 하지 않으면 로컬 도메인이 기본값이 됩니다.

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>설치 권한을 취소 하려면

1.  **허용-CsSetupPermission** cmdlet에서 부여한 설치 권한을 취소 하려는 도메인의 Lync Server 2013를 실행 하는 컴퓨터에 로그온 합니다. 도메인 관리자 그룹의 구성원 인 계정이 나 OU가 다른 자식 도메인에 있는 경우 엔터프라이즈 관리자 그룹을 사용 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  런
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    ComputerOu 매개 변수를 지정 된 도메인의 기본 명명 컨텍스트에 대 한 상대적으로 지정할 수 있습니다 (예: CN = computers). 또는이 매개 변수를 전체 DN (OU 고유 이름)으로 지정할 수 있습니다 (예: "CN = computers, DC = Contoso, DC = com"). 후자의 경우에는 지정한 도메인과 일치 하는 OU DN을 지정 해야 합니다.
    
    Domain 매개 변수를 지정 하지 않으면 로컬 도메인이 기본값이 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

