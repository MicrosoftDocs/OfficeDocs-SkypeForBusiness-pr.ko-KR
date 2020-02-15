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
ms.openlocfilehash: 4bb0bcb30c49a44fe92920d4db77d6bf9697cd9e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a>Lync Server 2013에서 보관 된 데이터 내보내기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

보관 데이터베이스에 보관된 데이터는 검색 가능하거나 읽기 가능한 형식은 아니지만, Export-CsArchivingData cmdlet을 사용하면 데이터베이스에서 레코드를 추출한 다음 Outlook EML(전자 메일) 파일로 저장할 수 있습니다. 보관된 데이터를 내보내는 방법에 대한 자세한 내용은 작업 설명서에서 [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)를 참조하십시오.

Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 데이터가 Exchange 2013 저장소에 보관 됩니다. Exchange 2013에서 보관 된 데이터를 검색 하 고 검색할 수 있습니다. Exchange 2013 및 Lync Server 2013에 대 한 통합 된 통신 지원에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync server 2013의 Exchange server 및 SharePoint 통합 지원](lync-server-2013-exchange-and-sharepoint-integration-support.md) 를 참조 하세요. Exchange에 보관 된 데이터에 액세스 하는 방법에 대 한 자세한 내용은 Exchange 2013 설명서를 참조 하십시오.

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 보관 데이터 내보내기

Export-CSArchivingData cmdlet을 사용하여 보관 데이터를 내보낼 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

**보관 데이터를 내보내려면**

  - 다음 명령은 2012년 6월 1일 이후 보관 데이터베이스 atl-sql-001.litwareinc.com에 기록된 모든 보관 데이터를 내보냅니다. 결과 출력 파일은 C:\\ArchivingExports 폴더에 저장 됩니다.
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**단일 사용자에 대 한 보관 데이터를 내보내려면**

  - 다음 명령은 단일 사용자(kenmyer@litwareinc.com)에 대한 보관 데이터를 내보냅니다. 이 작업은 UserUri 매개 변수와 사용자의 SIP 주소를 차례로 포함하여 수행합니다. 예를 들면 다음과 같습니다.
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

자세한 내용은 [export-csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 Exchange Server 및 SharePoint 통합 지원](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[Export-csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[Lync Server 2013 보관 관리](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

