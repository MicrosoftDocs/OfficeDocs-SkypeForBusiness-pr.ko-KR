---
title: 'Lync Server 2013: hot desking 사용 또는 사용 안 함'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5d9f2d168a06b5624375dcd005da58b4d3d5fd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a>Lync Server 2013에서 핫 desking 사용 또는 사용 안 함

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-20_

일반 전화를 휴대 *전화*전화기로 설정할 수 있습니다. 휴대 전화를 통해 사용자는 자신의 사용자 계정에 로그온 할 수 있으며, 로그온 한 후에는 Lync Server 기능 및 고유한 사용자 프로필 설정을 사용 합니다. 핫 desking는 클라이언트 정책을 사용 하 여 관리 됩니다. 핫 desking를 사용 하거나 사용 하지 않도록 설정 하려면 공용 지역 전화에서 사용 하는 클라이언트 정책을 수정 해야 합니다. 공통 지역 전화에 할당 된 회의 정책을 확인 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 일반적인 영역 전화 정보 보기](lync-server-2013-view-common-area-phone-information.md)를 참조 하세요.

다음과 같이 **새 CSClientPolicy** Cmdlet 또는 **Set Csclientpolicy** cmdlet의 EnableHotdesking 매개 변수를 사용 하 여 휴대폰에서 hot desking를 사용 하거나 사용 하지 않도록 설정할 수 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 이러한 cmdlet을 실행 합니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>


<div>

## <a name="enabling-hot-desking"></a>핫 desking 사용

  - 일반 지역 전화기에 대해 핫 desking을 사용 하도록 설정 하려면 해당 휴대폰 또는 전화 모음에 할당 된 클라이언트 정책을 수정 해야 합니다.
    
    수정 해야 하는 정책을 식별 한 후 다음 단계는 **Set CsClientPolicy** cmdlet을 사용 하 여 EnableHotdesking 매개 변수를 True로 설정 하는 것입니다. 예를 들면 다음과 같습니다.
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - 또는 **새 CsClientPolicy** cmdlet을 사용 하 여 핫 desking을 사용 하도록 설정 하는 새 클라이언트 정책을 만들 수 있습니다. 예를 들면 다음과 같습니다.
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> 이 정책을 만든 후에는 적절 한 공통 지역 전화에이를 할당 해야 합니다. 자세한 내용은 <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Lync Server 2013에서 공통 영역 전화로 정책 할당</A>을 참조 하세요.



</div>

<div>

## <a name="disabling-hot-desking"></a>Hot desking 사용 안 함

  - 공통 영역 휴대폰에 대해 핫 desking를 사용 하지 않도록 설정 하려면, **Set CsClientPolicy** Cmdlet의 EnableHotdesking 매개 변수를 기본값인 False로 다시 설정 합니다. 예를 들면 다음과 같습니다.
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

자세한 내용은 [새 csclientpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) Cmdlet 및 [Set csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) Cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

