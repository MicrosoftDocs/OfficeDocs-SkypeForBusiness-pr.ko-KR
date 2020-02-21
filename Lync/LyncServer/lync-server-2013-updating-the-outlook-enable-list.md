---
title: 'Lync Server 2013: Outlook 사용 목록 업데이트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7b4bc93f78ed72515270557e3224195df7ecd81
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a>Lync Server 2013에서 Outlook 사용 목록 업데이트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-01-07_

Outlook 용 추가 기능 관리 목록에 Microsoft Lync 2013에 대 한 온라인 모임 추가 기능이 항상 사용 하도록 설정 되어 있는지 확인할 수 있습니다. 추가 기능 관리 목록 정책은 그룹 정책 관리 콘솔에 대한 Office 관리 템플릿 파일에 포함됩니다. \\HKCU\\소프트웨어 정책\\아래에 Microsoft\\Office\\15.0\\Outlook15\\복구\\AddinList의 레지스트리 키를 만듭니다. 이 키에 c u c l i c e c i c e c i c e c i c c e c e c의 값을 추가 하 고이 값을 사용 하도록 설정 하 여 사용자가 수동으로 사용 하지 않도록 설정할 수 없도록

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a>Outlook 추가 기능 목록에 기타 기능을 추가 하려면

  - \\HKCU\\소프트웨어 정책\\아래에 있는 AddinList 레지스트리 키 (Microsoft\\Office\\15.0\\Outlook15\\복원성\\AddinList에 있음)에 다음 값을 추가 합니다.
    
      - 레지스트리 유형 = REG\_SZ
    
      - 이름 = ucaddin.dll
    
      - 값 = 1(추가 기능이 항상 설정되고 최종 사용자가 관리할 수 없도록 지정)

</div>

</div>

<span> </span>

</div>

</div>

</div>

