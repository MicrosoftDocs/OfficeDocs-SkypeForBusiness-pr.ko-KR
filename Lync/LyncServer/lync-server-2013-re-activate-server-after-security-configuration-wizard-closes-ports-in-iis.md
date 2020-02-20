---
title: 보안 구성 마법사가 IIS에서 포트를 닫은 후 서버 다시 활성화
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 064a21e5ec5a324dedae29aab2fb83d16c49b258
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>보안 구성 마법사가 IIS에서 포트를 닫은 후 서버 다시 활성화

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

일부 Lync Server 2013 역할은 IIS (인터넷 정보 서비스) 포트 4443에서 웹 서비스를 실행 합니다. Lync Server 배포 마법사를 실행 하거나, 부트스트래퍼가 나 **Enable-CsComputer** cmdlet을 사용 하 여 방화벽에서 예외를 만들고 포트를 엽니다. 그런 다음 Windows Server 2008 R2 보안 구성 마법사 또는 기타 강화 스크립트를 실행 하면 포트 4443이 차단 되 고 외부 클라이언트에서 웹 서비스에 연결할 수 없게 됩니다. 포트를 다시 열려면 방화벽 예외를 직접 수정하거나 서버를 다시 활성화하면 됩니다.

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>배포 마법사를 사용하여 서버를 다시 활성화하려면

1.  Lync Server 배포 마법사 페이지에서 **2 단계: Lync Server 구성 요소 설치 또는 제거**옆의 **실행** 을 클릭 합니다.

2.  **Lync Server 구성 요소 설치** 페이지에서 **다음**을 클릭합니다.

3.  **명령 실행** 페이지에서 작업 상태가 완료됨으로 표시되면 **마침**을 클릭합니다.
    
    <div>
    

    > [!NOTE]
    > bootstrapper.exe 또는 <STRONG>Enable-CsComputer</STRONG>를 사용하여 서버를 다시 활성화할 수도 있습니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

