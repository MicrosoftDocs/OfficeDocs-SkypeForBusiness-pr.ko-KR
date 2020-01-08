---
title: 'Lync Server 2013: Outlook 사용 목록 업데이트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20c7ee75e70b52a4edd01230fe10aeb46f6e6e40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a>Lync Server 2013에서 Outlook 사용 목록 업데이트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-01-07_

Outlook 용 추가 기능 관리 목록에서 Microsoft Lync 2013의 온라인 모임 추가 기능을 포함 하는 정책을 만들어 사용자가 항상 사용 하도록 설정 되어 있는지 확인할 수 있습니다. 추가 기능 관리 목록 정책은 그룹 정책 관리 콘솔의 Office 관리 템플릿 파일에 포함 되어 있습니다. 이 프로그램은 HKCU\\소프트웨어\\정책\\아래에 Microsoft\\Office\\15.0\\Outlook15\\복구\\AddinList 레지스트리 키를 만듭니다. 이 키에 추가 기능 .dll에 대 한 값을 추가할 수 있으며,이를 사용 하 여 사용자가 수동으로 사용 하지 못하도록 할 수 없도록 하는 .addin addin 값을 구성

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a>Outlook 추가 기능 목록에 추가 하는 dll

  - AddinList 레지스트리 키 (HKCU\\소프트웨어\\정책\\아래에 있음 Microsoft\\Office\\15.0\\Outlook15\\복원\\AddinList에서 다음 값을 추가 합니다.
    
      - 레지스트리 형식 = REG\_SZ
    
      - Name = 추가 합니다. d i l
    
      - 값 = 1 (추가 기능이 항상 사용 하도록 설정 되어 있으며 최종 사용자가 관리할 수 없음을 지정 합니다.)

</div>

</div>

<span> </span>

</div>

</div>

</div>

