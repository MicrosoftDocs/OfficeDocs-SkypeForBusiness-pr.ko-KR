---
title: 'Lync Server 2013: 보조 위치 정보 서비스 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b7ee9383939e8df5466d615f6fda4a2af33c2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a>Lync Server 2013에서 보조 위치 정보 서비스 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-30_

Lync Server 2013는 위치 정보 서비스를 보조 위치 원본 (SLS) 데이터베이스에 가리키는 데 사용할 수 있는 웹 서비스 인터페이스를 제공 합니다. SLS 데이터베이스에 연결 하는 웹 서비스 인터페이스는 위치 정보 서비스 WSDL을 준수 해야 합니다. 위치 데이터베이스와 보조 위치 데이터베이스가 모두 구성 되어 있는 경우 위치 정보 서비스는 위치 데이터베이스에 먼저 쿼리 하 고 일치 하는 항목이 없으면 클라이언트의 위치 요청을 SLS 데이터베이스에 보냅니다. 위치가 SLS에 있는 경우에는 위치 정보 서비스에서 해당 위치를 다시 클라이언트로 보냅니다.

자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.

  - **Set-CsWebServiceConfiguration**

<div>

## <a name="to-configure-secondary-location-database"></a>보조 위치 데이터베이스를 구성 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  다음 cmdlet을 실행 하 여 보조 위치 데이터베이스의 위치에 대 한 URL을 구성 합니다.
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

