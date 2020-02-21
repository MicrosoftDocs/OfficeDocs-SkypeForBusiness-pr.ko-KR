---
title: 'Lync Server 2013: 아웃 바운드 통화에 대 한 음성 경로 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a697dae1be3d59692746303f230968782db4f38f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a>Lync Server 2013에서 아웃 바운드 통화에 대 한 음성 경로 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

Lync Server 2013 음성 경로는 대상 전화 번호를 하나 이상의 PSTN (공중 전화망) 게이트웨이 또는 SIP 트렁크와 하나 이상의 PSTN 사용 레코드와 연결 합니다.

**Lync Server 제어판을 사용 하 여 음성 경로를 보려면**

1.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

2.  **음성 라우팅**을 클릭합니다.

3.  **경로**를 클릭합니다.

4.  음성 경로를 두 번 클릭하여 음성 경로 목록에서 추가 속성을 보거나 경로를 선택하고 **편집**을 클릭한 후 **세부 정보 표시**를 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 한 번에 하나씩 단일 경로에 대한 자세한 정보만 볼 수 있습니다.

    
    </div>

**Windows PowerShell을 사용 하 여 음성 경로를 보려면**

  - **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다. 음성 경로는 Windows PowerShell 및 **get-csvoiceroute** cmdlet을 사용 하 여 볼 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.
    
    모든 음성 경로에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.
    
        Get-CsVoiceRoute
    
    그러면 다음과 같은 정보가 반환됩니다.
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> 자세한 내용은 계획 설명서에서 <A href="lync-server-2013-voice-routes.md">Lync Server 2013의 음성 경로</A> 를 참조 하십시오.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)

  - [Lync Server 2013에서 음성 경로 수정](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 음성 라우팅 관리](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

