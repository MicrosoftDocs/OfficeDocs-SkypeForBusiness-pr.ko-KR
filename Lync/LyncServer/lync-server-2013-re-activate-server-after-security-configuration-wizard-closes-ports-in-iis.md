---
title: 보안 구성 마법사가 IIS에서 포트를 닫은 후 서버 다시 활성화
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c939996c10c85141d3c3751ce84b0cf642007b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>보안 구성 마법사가 IIS에서 포트를 닫은 후 서버 다시 활성화

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

일부 Lync Server 2013 역할은 IIS (인터넷 정보 서비스) 포트 4443에서 웹 서비스를 실행 합니다. Lync Server 배포 마법사 실행, 부트스트래퍼 또는 **Enable-CsComputer** cmdlet을 사용 하 여 방화벽에서 예외를 만들고 포트를 엽니다. 그런 다음 Windows Server 2008 R2 보안 구성 마법사 (또는 기타 강화 스크립트)를 실행 하면 포트 4443이 차단 되 고 외부 클라이언트가 웹 서비스에 연결할 수 없게 됩니다. 포트를 다시 열려면 방화벽 예외를 직접 수정 하거나 서버를 다시 활성화 하면 됩니다.

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>배포 마법사를 사용 하 여 서버를 다시 활성화 하려면

1.  Lync Server 배포 마법사 페이지에서 **2 단계: Lync Server 구성 요소 설정 또는 제거**옆의 **실행** 을 클릭 합니다.

2.  **Lync Server 구성 요소 설정** 페이지에서 **다음**을 클릭 합니다.

3.  **명령 실행** 페이지에서 작업 상태가 완료로 표시 되 면 **마침을**클릭 합니다.
    
    <div>
    

    > [!NOTE]
    > 또한 부트스트래퍼가 나 <STRONG>-CsComputer</STRONG> 를 사용 하 여 서버를 다시 활성화할 수도 있습니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

