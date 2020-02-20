---
title: 비즈니스용 Skype Online 보고 cmdlet 및 REST 웹 서비스
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0476b90659ced152a4d24fbb3890ac224bdf0d91
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a>비즈니스용 Skype Online 보고 cmdlet 및 REST 웹 서비스

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-09-05_

보고 기능과 함께, 비즈니스용 Skype Online에서는 이러한 보고서를 생성 하는 데 도움이 되는 5 개의 Windows PowerShell cmdlet에 대 한 액세스를 제공 하며 관리자가 사용자 지정 된 보고 데이터를 반환 하는 데도 사용할 수 있습니다. 비즈니스용 Skype Online에는 개발자가 사용자 지정 된 보고 정보를 검색 하는 데 사용할 수 있는 REST (Representational 상태 전송)도 포함 되어 있습니다.

관리자가 사용할 수 있는 보고 cmdlet은 다음과 같습니다.

  - Get-CsActiveUserReport-활성 사용자 수 (즉, 비즈니스용 Skype Online에 로그온 하 고 하나 이상의 회의 또는 피어 투 피어 통신 세션에 참가 한 사용자)에 대 한 정보를 제공 합니다.

  - Get-csavconferencetimereport-오디오/비디오 회의에 소비 된 시간 (분)에 대 한 정보를 제공 합니다.

  - Get-csconferencereport-사용자가 참여 하는 전화 회의의 수와 유형에 대 한 정보를 제공 합니다.

  - Get-csp2pavtimereport-사용자가 오디오 및/또는 비디오를 포함 하는 피어 투 피어 세션에서 사용한 시간 (분)에 대 한 정보를 제공 합니다.

  - Get-csp2psessionreport-사용자가 참여 한 피어 투 피어 세션의 수와 유형에 대 한 정보를 제공 합니다.

대부분의 관리자는 Microsoft 365 관리 센터에서 제공 되는 보고서를 사용 합니다. 자동으로 생성 되는 보고서는 아니지만,이를 통해 반환 되는 데이터를 그래픽으로 표시 하는 것도 도움이 될 수 있지만 보고 cmdlet 그러나 Windows PowerShell에 익숙한 관리자는 보고 cmdlet을 사용 하 여 Lync Online 보고서에서 즉시 사용할 수 없는 데이터를 반환할 수 있습니다. 예를 들어 보고 cmdlet은 세션 기간 (각 세션이 지속 되는 시간 (분)에 대 한 정보를 반환 합니다. 개별 세션 기간은 Lync Online 보고서를 사용 하 여 사용할 수 없습니다. 마찬가지로 일별 보기에서는 Lync Online 보고서에 이전 14 일간의 정보만 표시 됩니다. 하루 동안의 일별 합계를 검토 하려는 경우 (예: 4 달 전 날짜) 보고 cmdlet을 사용 하 여이 작업을 수행할 수 있습니다.

관리자는 Excel을 사용 하 여 Microsoft Excel에서 OData 데이터 쿼리 기능을 사용 하 여 사용자 지정 office 365 보고서를 만드는 방법에 대해 설명 하는 [Office 365 보고 데이터를 검색 하](http://msdn.microsoft.com/library/dn781442.aspx)는 문서에도 관심이 있을 수 있습니다. 사용자 지정 보고서를 통해 Office 365 보고 서비스에서 반환 되는 데이터 (및 데이터 양)를 지정할 수 있습니다. 또한 사용자 지정 보고서를 사용 하면 데이터 정렬 및 그룹화 방법을 지정 하 고 관리 센터에 표시 되지 않는 정보에 대 한 액세스를 제공 하는 등의 작업을 수행할 수 있습니다.

개발 배경의 관리자는 REST 웹 서비스를 사용 하 여 비즈니스용 Skype Online 관리 센터에 표시 되지 않는 정보를 가져올 수 있습니다. 각 기술은 클라이언트와 서버 간에 XML 데이터를 전송 하는 방법을 제공 한다는 점에서 REST 서비스는 SOAP 서비스와 비슷합니다. 그러나 REST 서비스에는 SOAP 서비스에 비해 두 가지 이상의 이점이 있습니다. 한 가지 REST는 ATOM 신디케이션 형식 이라는 표준화 된 형식을 사용 하 여 XML 데이터 전송을 수행 합니다. 반면, SOAP는 데이터 전송 시 비표준 형식을 사용 합니다. 또한 REST는 GET 및 POST가 아닌 다른 HTTP 동사를 차단 하는 네트워크 간에 데이터를 전송할 수 있습니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Online 보고](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))  


[Office 365 보고 웹 서비스](http://msdn.microsoft.com/library/office/jj984325.aspx)  
[Office 365 보고 웹 서비스에 대해 자세히 알아보기](http://msdn.microsoft.com/library/office/jj984321.aspx)  
[Exchange Online 보고 Cmdlet](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)  
[Excel을 사용하여 Office 365 보고 데이터 검색](http://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

