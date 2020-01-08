---
title: 비즈니스용 Skype Online reporting cmdlet 및 REST 웹 서비스
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2b1e11b4c9d68dbc5e177d684cd3053a83df8ea
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2019
ms.locfileid: "40983719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a>비즈니스용 Skype Online reporting cmdlet 및 REST 웹 서비스

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-09-05_

보고 기능과 함께 비즈니스용 Skype Online에서는 이러한 보고서를 생성 하는 데 도움이 되는 5 개의 Windows PowerShell cmdlet에 대 한 액세스를 제공 하며 관리자가 사용자 지정 보고 데이터를 반환 하는 데도 사용할 수 있습니다. 비즈니스용 Skype Online에는 개발자가 사용자 지정 된 보고 정보를 검색 하는 데 사용할 수 있는 나머지 (Representational 상태 이전)도 포함 되어 있습니다.

관리자가 사용할 수 있는 보고 cmdlet에는 다음이 포함 됩니다.

  - 활성 사용자 수에 대 한 정보를 제공 하는 가져오기-CsActiveUserReport (즉, 비즈니스용 Skype Online에 로그온 하 고 하나 이상의 컨퍼런스 또는 피어 투 피어 통신 세션에 참가 한 사용자).

  - CsAVConferenceTimeReport-오디오/비디오 회의에서 사용자가 사용한 시간 (분)에 대 한 정보를 제공 하는 get-help.

  - CsConferenceReport-사용자가 참여 한 컨퍼런스 수 및 종류에 대 한 정보를 제공 합니다.

  - CsP2PAVTimeReport-오디오 및/또는 비디오가 포함 된 피어 투 피어 세션에서 사용자가 사용한 시간 (분)에 대 한 정보를 제공 하는 get-help.

  - CsP2PSessionReport-사용자가 참여 한 피어 투 피어 세션의 수 및 종류에 대 한 정보를 제공 하는 get-help

대부분의 관리자는 Microsoft 365 관리 센터에서 사용할 수 있는 보고서를 사용 합니다. 또한 자동으로 생성 되는 보고서는 물론,이를 통해 반환 되는 원시 숫자 값 보다 해석 하기도 더 쉬운 데이터의 그래픽 표현을 제공 합니다. 보고 cmdlet. 그러나 Windows PowerShell에 익숙한 관리자는 보고 cmdlet을 사용 하 여 Lync Online 보고서에서 쉽게 사용할 수 없는 데이터를 반환할 수 있습니다. 예를 들어 보고 cmdlet은 세션 기간 (각 세션이 얼마나 지속 되었는지 시간 (분)에 대 한 정보를 반환 합니다. Lync Online 보고서를 사용 하 여 개별 세션 기간을 사용할 수 없습니다. 마찬가지로 일별 보기에서 Lync Online 보고서에는 이전 14 일간의 정보만 표시 됩니다. 다른 요일에 대 한 일일 합계를 검토 하려는 경우 (예: 4 개월 전의 날짜) 보고 cmdlet을 사용 하 여 해당 작업을 수행할 수 있습니다.

관리자는 Excel을 사용 하 여 Microsoft Excel의 OData 데이터 쿼리 기능을 사용 하 여 사용자 지정 office 365 보고서를 만드는 방법을 설명 하는 [office 365 보고 데이터를 검색 하](http://msdn.microsoft.com/en-us/library/dn781442.aspx)는 방법에 관심을 가질 수도 있습니다. 사용자 지정 보고서를 통해 Office 365 보고 서비스에서 반환 되는 데이터 (및 데이터 양)를 지시할 수 있습니다. 또한 사용자 지정 보고서를 사용 하 여 데이터를 정렬 하 고 그룹화 하는 방법을 지정 하 고 관리 센터에 표시 되지 않는 정보에 대 한 액세스를 제공 하는 등의 작업을 수행할 수 있습니다.

개발 배경이 있는 관리자는 REST 웹 서비스를 사용 하 여 비즈니스용 Skype Online 관리 센터에 표시 되지 않는 정보를 얻을 수 있습니다. REST 서비스는 각 기술이 클라이언트와 서버 간에 XML 데이터를 전송 하는 방법을 제공 한다는 점에서 SOAP 서비스와 유사 합니다. 그러나 REST 서비스의 SOAP 서비스에는 두 가지 이상의 장점이 있습니다. 다른 하나는 ATOM 신디케이션 형식 이라는 표준화 된 형식을 사용 하 여 XML 데이터 전송을 수행 합니다. 반대로 데이터 전송 시 비 표준 형식을 사용 하는 SOAP. 또한 REST는 GET 및 POST 이외의 HTTP 동사를 차단 하는 네트워크 간에 데이터를 전송할 수 있습니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Online 보고](https://technet.microsoft.com/en-us/library/dn362827\(v=ocs.15\))  


[Office 365 보고 웹 서비스](http://msdn.microsoft.com/en-us/library/office/jj984325.aspx)  
[Office 365 보고 웹 서비스에 대 한 학습](http://msdn.microsoft.com/en-us/library/office/jj984321.aspx)  
[Exchange Online 보고 Cmdlet](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)  
[Excel을 사용 하 여 Office 365 보고 데이터 검색](http://msdn.microsoft.com/en-us/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

