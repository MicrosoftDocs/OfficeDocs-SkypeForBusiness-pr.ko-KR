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
ms.openlocfilehash: 397c1037937e100f1981a689f0860362d852ed10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a>Lync Server 2013에서 주소 유효성 검사

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-17_

위치 데이터베이스를 게시 하기 전에 SIP 트렁크 또는 PSTN (공개 교환 전화 네트워크) E9-1-1 서비스 공급자가 유지 관리 하는 MSAG (마스터 주소 가이드)에 대해 새 위치를 확인 해야 합니다.

SIP 트렁크 E9-1-1 서비스 공급자에 대 한 자세한 내용은 [Lync Server 2013에 대 한 E9-1-1 서비스 공급자 선택을](lync-server-2013-choosing-an-e9-1-1-service-provider.md)참조 하세요.

주소 유효성 검사에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.

  - **Get-CsLisServiceProvider**

  - **Set-CsLisServiceProvider**

  - **제거-CsLisServiceProvider**

  - **Get-CsLisCivicAddress**

  - **테스트-CsLisCivicAddress**

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a>위치 데이터베이스에 있는 주소의 유효성을 검사 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  다음 cmdlet을 실행 하 여 응급 서비스 공급자 연결을 구성 합니다.
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  다음 cmdlet을 실행 하 여 위치 데이터베이스에서 주소의 유효성을 검사 합니다.
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    **테스트 CsLisCivicAddress** cmdlet을 사용 하 여 개별 주소의 유효성을 검사할 수도 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

