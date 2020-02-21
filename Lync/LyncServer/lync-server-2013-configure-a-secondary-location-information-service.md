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
ms.openlocfilehash: 0a13e99aa7f9e3da9ddd04f5c8e7763c7de1481a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a>Lync Server 2013에서 보조 위치 정보 서비스 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-30_

Lync Server 2013는 SLS (보조 위치 원본) 데이터베이스를 가리키도록 위치 정보 서비스를 지정 하는 데 사용할 수 있는 웹 서비스 인터페이스를 제공 합니다. SLS 데이터베이스에 연결 되는 웹 서비스 인터페이스는 위치 정보 서비스 WSDL을 준수 해야 합니다. 위치 데이터베이스와 보조 위치 데이터베이스를 모두 구성 하는 경우에는 위치 정보 서비스가 먼저 위치 데이터베이스를 쿼리하고 일치 하는 항목이 없으면 클라이언트의 위치 요청을 SLS 데이터베이스에 전송 합니다. SLS에 위치가 있으면 위치 정보 서비스에서 해당 위치를 클라이언트로 다시 보냅니다.

자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.

  - **Set-cswebserviceconfiguration**

<div>

## <a name="to-configure-secondary-location-database"></a>보조 위치 데이터베이스를 구성하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  다음 cmdlet을 실행하여 보조 위치 데이터베이스의 위치에 대해 URL을 구성합니다.
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

