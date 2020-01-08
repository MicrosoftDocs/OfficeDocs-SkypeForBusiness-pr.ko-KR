---
title: 'Lync Server 2013: 가상 컴퓨터에서 Lync 2013 로그인 및 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3b890f008b30ecf008bd2e6f03803fbfe6c1674
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a>가상 컴퓨터에서 Lync 2013 로그인 및 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-03_

VDI 플러그 인을 사용 하도록 설정한 후에는 사용자가 Lync 2013에 로그인 할 때 다음 단계가 수행 됩니다.

1.  사용자는 가상 컴퓨터에서 실행 되는 Lync 2013 클라이언트에 자신의 자격 증명을 입력 합니다.

2.  Lync가 VDI 플러그 인의 가용성을 감지 하면 Lync에서 사용자에 게 해당 자격 증명을 다시 입력 하 라는 메시지를 표시 합니다. 이 대화 상자에서 사용자가 다음에 로그인 할 때 자격 증명을 입력할 필요가 없도록 **암호 저장** 확인란을 선택 하는 것이 좋습니다.

3.  Lync는 VDI 플러그 인과 페어링을 시작 합니다. 페어링이 완료 되기 전에 클라이언트는 Lync 상태 표시줄에 두 개의 아이콘을 표시 합니다. 왼쪽 아래에 있는 아이콘은 사용할 수 있는 오디오 장치가 없고 오른쪽 아래에 깜박이는 아이콘은 VDI 페어링이 진행 중임을 나타냅니다.
    
    성공적인 페어링을(images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "표시") 하는 lync vdi 아이콘에 ![성공한 연결 표시]  

4.  VDI 페어링에 성공한 후에는 전화 및 VDI 페어링 성공에 사용 되는 오디오 장치를 나타내기 위해 아이콘이 변경 됩니다.
    
    성공 여부를(images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "보여 주는 성공 LYNC vdi 페어링 아이콘이") ![표시 된 lync vdi 페어링 아이콘]  

5.  Lync 쌍이 VDI 플러그 인을 사용 하는 경우 사용자는 로컬 컴퓨터에 연결 된 Lync 호환 장치에서 현재 상태를 볼 수 있습니다. 이제 사용자가 평소 대로 전화를 걸고 응답할 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

