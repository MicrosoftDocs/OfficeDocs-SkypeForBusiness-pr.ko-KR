---
title: 'Lync Server 2013: 주소 유효성 검사'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4054af0ec8adbe219b2cc8dd33aac4fe52cf5ead
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42121611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a>Lync Server 2013에서 주소 유효성 검사

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-17_

위치 데이터베이스를 게시 하기 전에 SIP 트렁크 또는 PSTN (공중 전화망) E9-1-1 서비스 공급자가 유지 관리 하는 MSAG (마스터 주소 가이드)에 대해 새 위치를 확인 해야 합니다.

SIP 트렁크 E9-1-1 서비스 공급자에 대 한 자세한 내용은 [E9-1-1 서비스 공급자 선택에서 Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md)를 참조 하세요.

주소 유효성 검사에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.

  - **CsLisServiceProvider**

  - **CsLisServiceProvider**

  - **CsLisServiceProvider을 제거 합니다.**

  - **Test-csliscivicaddress**

  - **Test-csliscivicaddress**

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a>위치 데이터베이스에 있는 주소를 확인 하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  다음 cmdlet를 실행 하 여 응급 서비스 공급자 연결을 구성 합니다.
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  다음 cmdlet를 실행 하 여 위치 데이터베이스의 주소를 확인 합니다.
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    **Test-csliscivicaddress** cmdlet을 사용 하 여 개별 주소를 확인할 수도 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

