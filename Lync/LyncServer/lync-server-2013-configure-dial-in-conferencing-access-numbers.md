---
title: 'Lync Server 2013: 전화 접속 회의 액세스 번호 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8de52d7472e6be409ea7cc628ad5f334d048a09
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>Lync Server 2013에서 전화 접속 회의 액세스 번호 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2011-07-17_

전화 접속 회의를 배포하려면 회의의 오디오 부분에 참가하기 위해 사용자가 PSTN(공중 전화망)을 통해 전화를 걸 수 있는 전화 번호를 설정해야 합니다. 이러한 전화 접속 액세스 번호는 모임 초대장 및 전화 접속 회의 설정 웹 페이지에 표시됩니다.

전화 접속 액세스 번호를 만들려면 먼저 전화 접속 회의 지역을 계획한 다음 해당 지역이 포함된 다이얼 플랜을 구성해야 합니다. 지역에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 전화 접속 회의 요구 사항](lync-server-2013-dial-in-conferencing-requirements.md) 를 참조 하십시오. 전화 접속 회의에 대 한 다이얼 플랜을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 전화 접속 회의에 대 한 다이얼 플랜 구성을](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)참조 하십시오.

<div>


> [!NOTE]  
> 해당 액세스 번호의 AD&nbsp;DS (Active Directory 도메인 서비스) 복제가 완료 될 때까지 새 전화 접속 액세스 번호를 사용할 수 없습니다. 복제 작업은 몇 시간이 소요될 수 있습니다.



</div>

<div>


> [!NOTE]  
> 전화 접속 액세스 번호를 만든 후 사용자가 올바른 액세스 번호를 보다 쉽게 식별할 수 있도록 Active Directory 대화 상대 개체에 대한 표시 이름을 수정할 수 있습니다. 표시 이름은 <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet를 사용하여 수정할 수 있습니다. Active Directory 개체는 수동으로 수정할 수 없습니다. 액세스 번호를 수정 하는 방법에 대 한 자세한 내용은 <STRONG>get-csdialinconferencingaccessnumber</STRONG> cmdlet에 대 한 Lync Server Management Shell 설명서를 참조 하십시오.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

[Lync Server 2013에서 전화 접속 회의 액세스 번호 만들기 또는 수정](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 전화 접속 회의 요구 사항](lync-server-2013-dial-in-conferencing-requirements.md)  


[Lync Server 2013에서 전화 접속 회의에 대 한 다이얼 플랜 구성](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

