---
title: 'Lync Server 2013: 공통 영역 전화 연락처 개체 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17ab84f88417a6f5cb1c96c4cf7b6df45fa24b16
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a>Lync Server 2013에서 공통 영역 휴대폰 연락처 개체 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-20_

일반 지역 전화와 연결 된 contact 개체를 삭제 하는 것이 좋습니다. 예를 들어 직원 \ ()에서 전화를 제거 하는 경우 해당 휴대폰에 연결 된 연락처 개체를 사용할 필요가 없습니다. **CsCommonAreaPhone** cmdlet은 일반적인 지역 전화 계정을 삭제 하는 방법을 제공 합니다. 이 cmdlet을 실행 하면 **CsCommonAreaPhone**에서 반환 되는 일반적인 지역 전화 목록에서 전화가 삭제 됩니다. 또한이 휴대폰에 연결 된 contact 개체는 Active Directory 도메인 서비스에서 삭제 됩니다.

**CsCommonAreaPhone** 를 사용 하 여 표시 이름 또는 국가 및 지역 번호와 같은 공통 요소가 있는 하나의 공통 영역 전화기 또는 모든 공통 영역 전화기를 제거 합니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a>지정 된 공통 영역 전화 제거

  - 다음 명령은 SIP 주소 sip:mainlobby@litwareinc.com를 사용 하 여 일반적인 지역 전화를 제거 합니다.
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a>표시 이름에 따라 공통 영역 전화 제거

  - 이 명령은 표시 이름에 문자열 값 "빌딩 14"가 포함 된 공통 영역 전화기를 모두 제거 합니다.
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a>국가 및 지역 코드를 기준으로 공통 지역 전화 제거

  - 이 명령은 미국 (국가 코드 1) 및 지역 번호 425에 대 한 공통 영역 전화를 모두 제거 합니다.
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

자세한 내용은 [제거 CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

