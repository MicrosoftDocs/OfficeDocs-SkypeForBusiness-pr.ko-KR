---
title: 'Lync Server 2013: 향상 된 현재 상태 개인 정보 보호 모드 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32c8622e2c32af698d599b4ed541945b4d1de0a7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a>Lync Server 2013에서 향상 된 현재 상태 개인 정보 보호 모드 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-12-08_

향상 된 현재 상태 개인 정보 보호 모드를 사용 하는 경우 사용자는 해당 Lync 2013 연락처 목록에 나열 된 연락처에만 표시 되도록 현재 상태 정보를 제한할 수 있습니다. **Get-csprivacyconfiguration** 및 **get-csprivacyconfiguration** cmdlet에는이 옵션을 제어 하는 EnablePrivacyMode 매개 변수가 있습니다. EnablePrivacyMode가 True로 설정 되 면 Lync 2013 상태 옵션에서 현재 상태 정보를 연락처로 제한 하는 옵션을 사용할 수 있게 됩니다. EnablePrivacyMode가 False로 설정 되 면 사용자는 항상 모든 사용자가 현재 상태 정보를 볼 수 있도록 허용 하거나 관리자가 개인 정보 모드를 변경 하는 모든 변경을 따르도록 할 수도 있습니다.

<div>


> [!IMPORTANT]  
> Lync 2013 및 Lync 2010 개인 정보 설정은 이전 버전에서는 허용 되지 않습니다 (Microsoft Office Communicator 2007 R2 또는 Microsoft Office Communicator 2007). 이전 버전의 Office Communicator에서 로그인이 허용 된 경우 Lync 2013 사용자의 상태, 연락처 정보 또는 사진을 볼 수 있는 권한이 없는 사용자가 볼 수 있습니다. 또한 나중에 이전 버전의 Communicator를 사용 하 여 로그인 한 경우 Lync 2013 사용자의 개인 정보 설정이 다시 설정 됩니다.<BR>따라서 마이그레이션 시나리오에서 향상 된 현재 상태 개인 정보 보호 모드를 사용 하도록 설정 하기 전에 다음을 수행 합니다. 
> <UL>
> <LI>
> <P>모든 사용자에 게 Lync 2013이 설치 되어 있는지 확인 합니다.</P>
> <LI>
> <P>이전 버전의 Communicator에서 로그인 하지 못하도록 클라이언트 버전 정책 규칙을 정의 합니다.</P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a>향상 된 현재 상태 개인 정보 보호 모드를 사용 하도록 설정 하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  다음 명령을 실행합니다.
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    이 명령은 조직에서 현재 사용 중인 모든 개인 정보 구성 설정에 대해 개인 정보 보호 모드를 사용 하도록 설정 합니다. Lync Server 향상 된 현재 상태 개인 정보 보호 모드 정책 구성에서 Lync 2013 클라이언트에 대 한 대화 상대 현재 상태를 관리 하는 방법에 대 한 자세한 내용은 Microsoft 기술 자료 문서 사용 안 함 [Lync Server 향상 된 현재 상태 개인 정보 보호 모드에서는 일부 Lync 대화 상대의 현재 상태가 "사용할 수 없음"](https://support.microsoft.com/kb/3020057)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Get-csprivacyconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[Get-csprivacyconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[Get-csprivacyconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

