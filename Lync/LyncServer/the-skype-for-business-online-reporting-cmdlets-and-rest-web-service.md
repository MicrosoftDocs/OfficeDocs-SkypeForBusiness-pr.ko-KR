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

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a><span data-ttu-id="88afe-102">비즈니스용 Skype Online 보고 cmdlet 및 REST 웹 서비스</span><span class="sxs-lookup"><span data-stu-id="88afe-102">The Skype for Business Online reporting cmdlets and REST web service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88afe-103">_**마지막으로 수정 된 항목:** 2014-09-05_</span><span class="sxs-lookup"><span data-stu-id="88afe-103">_**Topic Last Modified:** 2014-09-05_</span></span>

<span data-ttu-id="88afe-104">보고 기능과 함께, 비즈니스용 Skype Online에서는 이러한 보고서를 생성 하는 데 도움이 되는 5 개의 Windows PowerShell cmdlet에 대 한 액세스를 제공 하며 관리자가 사용자 지정 된 보고 데이터를 반환 하는 데도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-104">In conjunction with the reporting features, Skype for Business Online provides access to five Windows PowerShell cmdlets that help generate those reports and are also can be used by administrators to return customized reporting data.</span></span> <span data-ttu-id="88afe-105">비즈니스용 Skype Online에는 개발자가 사용자 지정 된 보고 정보를 검색 하는 데 사용할 수 있는 REST (Representational 상태 전송)도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-105">Skype for Business Online also includes the REST (Representational State Transfer), which can be used by developers to retrieve customized reporting information.</span></span>

<span data-ttu-id="88afe-106">관리자가 사용할 수 있는 보고 cmdlet은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-106">The reporting cmdlets available to administrators include:</span></span>

  - <span data-ttu-id="88afe-107">Get-CsActiveUserReport-활성 사용자 수 (즉, 비즈니스용 Skype Online에 로그온 하 고 하나 이상의 회의 또는 피어 투 피어 통신 세션에 참가 한 사용자)에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-107">Get-CsActiveUserReport, which provides information about the number of active users (that is, users who have logged on to Skype for Business Online and participated in at least one conference or peer-to-peer communication session).</span></span>

  - <span data-ttu-id="88afe-108">Get-csavconferencetimereport-오디오/비디오 회의에 소비 된 시간 (분)에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-108">Get-CsAVConferenceTimeReport, which provides information about the amount of time (in minutes) users spent in audio/video conferences.</span></span>

  - <span data-ttu-id="88afe-109">Get-csconferencereport-사용자가 참여 하는 전화 회의의 수와 유형에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-109">Get-CsConferenceReport, which provides information about the number and type of conferences that users participated in.</span></span>

  - <span data-ttu-id="88afe-110">Get-csp2pavtimereport-사용자가 오디오 및/또는 비디오를 포함 하는 피어 투 피어 세션에서 사용한 시간 (분)에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-110">Get-CsP2PAVTimeReport, which provides information about the amount of time (in minutes) users spent in peer-to-peer sessions that included audio and/or video.</span></span>

  - <span data-ttu-id="88afe-111">Get-csp2psessionreport-사용자가 참여 한 피어 투 피어 세션의 수와 유형에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-111">Get-CsP2PSessionReport, which provides information about the number and type of peer-to-peer sessions that users participated in.</span></span>

<span data-ttu-id="88afe-112">대부분의 관리자는 Microsoft 365 관리 센터에서 제공 되는 보고서를 사용 합니다. 자동으로 생성 되는 보고서는 아니지만,이를 통해 반환 되는 데이터를 그래픽으로 표시 하는 것도 도움이 될 수 있지만 보고 cmdlet</span><span class="sxs-lookup"><span data-stu-id="88afe-112">Most administrators will use the reports available in the Microsoft 365 admin center: not only are those reports auto-generated, but they also provide a graphical representation of the data that is often easier to interpret than the raw number values returned by the reporting cmdlets.</span></span> <span data-ttu-id="88afe-113">그러나 Windows PowerShell에 익숙한 관리자는 보고 cmdlet을 사용 하 여 Lync Online 보고서에서 즉시 사용할 수 없는 데이터를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-113">However, administrators familiar with Windows PowerShell can use the reporting cmdlets to return data that is not readily available from the Lync Online reports.</span></span> <span data-ttu-id="88afe-114">예를 들어 보고 cmdlet은 세션 기간 (각 세션이 지속 되는 시간 (분)에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-114">For example, the reporting cmdlets return information about session duration (the amount of time, in minutes, that each session lasted).</span></span> <span data-ttu-id="88afe-115">개별 세션 기간은 Lync Online 보고서를 사용 하 여 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-115">Individual session durations are not available using the Lync Online reports.</span></span> <span data-ttu-id="88afe-116">마찬가지로 일별 보기에서는 Lync Online 보고서에 이전 14 일간의 정보만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-116">Likewise, in daily view the Lync Online reports display information only for the preceding 14 days.</span></span> <span data-ttu-id="88afe-117">하루 동안의 일별 합계를 검토 하려는 경우 (예: 4 달 전 날짜) 보고 cmdlet을 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-117">If you would like to review the daily totals for a different day (for example, a date from four months ago) you can do so by using the reporting cmdlets.</span></span>

<span data-ttu-id="88afe-118">관리자는 Excel을 사용 하 여 Microsoft Excel에서 OData 데이터 쿼리 기능을 사용 하 여 사용자 지정 office 365 보고서를 만드는 방법에 대해 설명 하는 [Office 365 보고 데이터를 검색 하](http://msdn.microsoft.com/library/dn781442.aspx)는 문서에도 관심이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-118">Administrators might also be interested in the article [Using Excel to Retrieve Office 365 Reporting Data](http://msdn.microsoft.com/library/dn781442.aspx), which explains how to use the OData data querying feature in Microsoft Excel to create custom office 365 report.</span></span> <span data-ttu-id="88afe-119">사용자 지정 보고서를 통해 Office 365 보고 서비스에서 반환 되는 데이터 (및 데이터 양)를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-119">Custom reports give you the ability to dictate which data (and how much data) is returned from the Office 365 reporting service.</span></span> <span data-ttu-id="88afe-120">또한 사용자 지정 보고서를 사용 하면 데이터 정렬 및 그룹화 방법을 지정 하 고 관리 센터에 표시 되지 않는 정보에 대 한 액세스를 제공 하는 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-120">Custom reports also enable you to do such things as specify how the data should be sorted and grouped, and provide access to information that is not displayed in the admin center.</span></span>

<span data-ttu-id="88afe-121">개발 배경의 관리자는 REST 웹 서비스를 사용 하 여 비즈니스용 Skype Online 관리 센터에 표시 되지 않는 정보를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-121">Administrators with a development background can use the REST web service to obtain information not displayed in the Skype for Business Online admin center.</span></span> <span data-ttu-id="88afe-122">각 기술은 클라이언트와 서버 간에 XML 데이터를 전송 하는 방법을 제공 한다는 점에서 REST 서비스는 SOAP 서비스와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-122">The REST service is similar to the SOAP service, in that each technology provides a way to transfer XML data between a client and a server.</span></span> <span data-ttu-id="88afe-123">그러나 REST 서비스에는 SOAP 서비스에 비해 두 가지 이상의 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-123">However, the REST service has at least two advantages over the SOAP service.</span></span> <span data-ttu-id="88afe-124">한 가지 REST는 ATOM 신디케이션 형식 이라는 표준화 된 형식을 사용 하 여 XML 데이터 전송을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-124">For one, REST performs XML data transfers using a standardized format known as the ATOM syndication format.</span></span> <span data-ttu-id="88afe-125">반면, SOAP는 데이터 전송 시 비표준 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-125">By contrast, SOAP using a non-standard format when transferring data.</span></span> <span data-ttu-id="88afe-126">또한 REST는 GET 및 POST가 아닌 다른 HTTP 동사를 차단 하는 네트워크 간에 데이터를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88afe-126">In addition, REST is able to transfer data across networks that block HTTP verbs other than GET and POST.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="88afe-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88afe-127">See Also</span></span>


<span data-ttu-id="88afe-128">[Lync Online 보고](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="88afe-128">[Lync Online reporting](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span></span>  


[<span data-ttu-id="88afe-129">Office 365 보고 웹 서비스</span><span class="sxs-lookup"><span data-stu-id="88afe-129">The Office 365 Reporting Web Service</span></span>](http://msdn.microsoft.com/library/office/jj984325.aspx)  
[<span data-ttu-id="88afe-130">Office 365 보고 웹 서비스에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="88afe-130">Learning About the Office 365 Reporting Web Service</span></span>](http://msdn.microsoft.com/library/office/jj984321.aspx)  
<span data-ttu-id="88afe-131">[Exchange Online 보고 Cmdlet](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span><span class="sxs-lookup"><span data-stu-id="88afe-131">[The Exchange Online Reporting Cmdlets](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span></span>  
[<span data-ttu-id="88afe-132">Excel을 사용하여 Office 365 보고 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="88afe-132">Using Excel to Retrieve Office 365 Reporting Data</span></span>](http://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

