---
title: 'Lync Server 2013: 보관 된 데이터 내보내기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting archived data
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48183347
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f06c4208e3830db2e32dc9866747b78a93b567e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528365"
---
# <a name="exporting-archived-data-from-lync-server-2013"></a><span data-ttu-id="0a705-102">Lync Server 2013에서 보관 된 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="0a705-102">Exporting archived data from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a705-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0a705-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0a705-104">보관 데이터베이스에 보관된 데이터는 검색 가능하거나 읽기 가능한 형식은 아니지만, Export-CsArchivingData cmdlet을 사용하면 데이터베이스에서 레코드를 추출한 다음 Outlook EML(전자 메일) 파일로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a705-104">Data archived in Archiving databases is not searchable or in a readable format, but you can use the Export-CsArchivingData cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span> <span data-ttu-id="0a705-105">보관된 데이터를 내보내는 방법에 대한 자세한 내용은 작업 설명서에서 [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0a705-105">For details about exporting archived data, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) in the Operations documentation.</span></span>

<span data-ttu-id="0a705-106">Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 데이터가 Exchange 2013 저장소에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a705-106">If you enable Microsoft Exchange integration, data is archived in Exchange 2013 stores.</span></span> <span data-ttu-id="0a705-107">Exchange 2013에서 보관 된 데이터를 검색 하 고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a705-107">Data archived in Exchange 2013 is searchable and discoverable.</span></span> <span data-ttu-id="0a705-108">Exchange 2013 및 Lync Server 2013에 대 한 통합 된 통신 지원에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync server 2013의 Exchange server 및 SharePoint 통합 지원](lync-server-2013-exchange-and-sharepoint-integration-support.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0a705-108">For details about support for integrated communications for Exchange 2013 and Lync Server 2013, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="0a705-109">Exchange에 보관 된 데이터에 액세스 하는 방법에 대 한 자세한 내용은 Exchange 2013 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0a705-109">For details about accessing data that is archived in Exchange, see the Exchange 2013 documentation.</span></span>

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0a705-110">Windows PowerShell Cmdlet을 사용 하 여 보관 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="0a705-110">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0a705-111">Export-CSArchivingData cmdlet을 사용하여 보관 데이터를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a705-111">Archiving data can be exported by using the Export-CSArchivingData cmdlet.</span></span> <span data-ttu-id="0a705-112">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a705-112">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0a705-113">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="0a705-113">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="0a705-114">**보관 데이터를 내보내려면**</span><span class="sxs-lookup"><span data-stu-id="0a705-114">**To export archiving data**</span></span>

  - <span data-ttu-id="0a705-115">다음 명령은 2012년 6월 1일 이후 보관 데이터베이스 atl-sql-001.litwareinc.com에 기록된 모든 보관 데이터를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="0a705-115">This command exports all the archiving data written to the archiving database atl-sql-001.litwareinc.com since June 1, 2012.</span></span> <span data-ttu-id="0a705-116">결과 출력 파일은 C: ArchivingExports 폴더에 저장 됩니다 \\ .</span><span class="sxs-lookup"><span data-stu-id="0a705-116">The resulting output file will be stored in the folder C:\\ArchivingExports.</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

<span data-ttu-id="0a705-117">**단일 사용자에 대 한 보관 데이터를 내보내려면**</span><span class="sxs-lookup"><span data-stu-id="0a705-117">**To export archiving data for a single user**</span></span>

  - <span data-ttu-id="0a705-p105">다음 명령은 단일 사용자(kenmyer@litwareinc.com)에 대한 보관 데이터를 내보냅니다. 이 작업은 UserUri 매개 변수와 사용자의 SIP 주소를 차례로 포함하여 수행합니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0a705-p105">The following command exports archiving data for a single user: kenmyer@litwareinc.com. This is done by including the UserUri parameter followed by the user’s SIP address. For example:</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="0a705-121">자세한 내용은 [export-csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0a705-121">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0a705-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a705-122">See Also</span></span>


[<span data-ttu-id="0a705-123">Lync Server 2013의 Exchange Server 및 SharePoint 통합 지원</span><span class="sxs-lookup"><span data-stu-id="0a705-123">Exchange Server and SharePoint integration support in Lync Server 2013</span></span>](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[<span data-ttu-id="0a705-124">Export-csarchivingdata</span><span class="sxs-lookup"><span data-stu-id="0a705-124">Export-CsArchivingData</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[<span data-ttu-id="0a705-125">Lync Server 2013 보관 관리</span><span class="sxs-lookup"><span data-stu-id="0a705-125">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

