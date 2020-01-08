---
title: 'Lync Server 2013: 보관 된 데이터 내보내기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exporting archived data
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48183347
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4974971912b0b64652aa939368f0a86e2e2484a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a><span data-ttu-id="67e27-102">Lync Server 2013에서 보관 된 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="67e27-102">Exporting archived data from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67e27-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="67e27-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="67e27-104">보관 데이터베이스에 보관 된 데이터는 검색 가능 하거나 읽을 수 있는 형식 이지만 내보내기-CsArchivingData cmdlet을 사용 하 여 데이터베이스에서 레코드를 추출 하 고 Outlook 전자 메일 (EML) 파일로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67e27-104">Data archived in Archiving databases is not searchable or in a readable format, but you can use the Export-CsArchivingData cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span> <span data-ttu-id="67e27-105">보관 된 데이터 내보내기에 대 한 자세한 내용은 작업 설명서의 [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="67e27-105">For details about exporting archived data, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) in the Operations documentation.</span></span>

<span data-ttu-id="67e27-106">Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 데이터가 Exchange 2013 저장소에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67e27-106">If you enable Microsoft Exchange integration, data is archived in Exchange 2013 stores.</span></span> <span data-ttu-id="67e27-107">Exchange 2013에서 보관 된 데이터를 검색 하 고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67e27-107">Data archived in Exchange 2013 is searchable and discoverable.</span></span> <span data-ttu-id="67e27-108">Exchange 2013 및 Lync Server 2013의 통합 된 통신 지원에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 Exchange server 및 SharePoint 통합 지원을](lync-server-2013-exchange-and-sharepoint-integration-support.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="67e27-108">For details about support for integrated communications for Exchange 2013 and Lync Server 2013, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="67e27-109">Exchange에 보관 된 데이터에 액세스 하는 방법에 대 한 자세한 내용은 Exchange 2013 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="67e27-109">For details about accessing data that is archived in Exchange, see the Exchange 2013 documentation.</span></span>

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="67e27-110">Windows PowerShell Cmdlet을 사용 하 여 데이터 보관 내보내기</span><span class="sxs-lookup"><span data-stu-id="67e27-110">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="67e27-111">데이터 보관은 Export-CSArchivingData cmdlet을 사용 하 여 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67e27-111">Archiving data can be exported by using the Export-CSArchivingData cmdlet.</span></span> <span data-ttu-id="67e27-112">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67e27-112">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="67e27-113">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="67e27-113">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="67e27-114">**보관 데이터를 내보내려면**</span><span class="sxs-lookup"><span data-stu-id="67e27-114">**To export archiving data**</span></span>

  - <span data-ttu-id="67e27-115">이 명령은 2012 년 6 월 1 일 이후 보관 데이터베이스 atl-sql-001.litwareinc.com에 기록 된 모든 보관 데이터를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="67e27-115">This command exports all the archiving data written to the archiving database atl-sql-001.litwareinc.com since June 1, 2012.</span></span> <span data-ttu-id="67e27-116">결과 출력 파일은 C:\\ArchivingExports 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67e27-116">The resulting output file will be stored in the folder C:\\ArchivingExports.</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

<span data-ttu-id="67e27-117">**단일 사용자에 대 한 보관 데이터를 내보내려면**</span><span class="sxs-lookup"><span data-stu-id="67e27-117">**To export archiving data for a single user**</span></span>

  - <span data-ttu-id="67e27-118">다음 명령은 단일 사용자에 대 한 보관 데이터를 kenmyer@litwareinc.com로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="67e27-118">The following command exports archiving data for a single user: kenmyer@litwareinc.com.</span></span> <span data-ttu-id="67e27-119">이 작업은 UserUri 매개 변수와 사용자의 SIP 주소를 차례로 포함 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67e27-119">This is done by including the UserUri parameter followed by the user’s SIP address.</span></span> <span data-ttu-id="67e27-120">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="67e27-120">For example:</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="67e27-121">자세한 내용은 [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="67e27-121">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="67e27-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="67e27-122">See Also</span></span>


[<span data-ttu-id="67e27-123">Lync Server 2013의 Exchange Server 및 SharePoint 통합 지원</span><span class="sxs-lookup"><span data-stu-id="67e27-123">Exchange Server and SharePoint integration support in Lync Server 2013</span></span>](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[<span data-ttu-id="67e27-124">Export-CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="67e27-124">Export-CsArchivingData</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[<span data-ttu-id="67e27-125">Lync Server 2013 보관 관리</span><span class="sxs-lookup"><span data-stu-id="67e27-125">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

