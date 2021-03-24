---
title: 비즈니스용 Skype 서버에서 보관된 데이터 내보내기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: '요약: 비즈니스용 Skype 서버의 보관된 데이터를 내보내는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: e69c283304395d697e99ef0607e2aec1eb7960e4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095382"
---
# <a name="export-archived-data-in-skype-for-business-server"></a><span data-ttu-id="a1f46-103">비즈니스용 Skype 서버에서 보관된 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="a1f46-103">Export archived data in Skype for Business Server</span></span>

<span data-ttu-id="a1f46-104">**요약:** 비즈니스용 Skype 서버의 보관된 데이터를 내보내는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1f46-104">**Summary:** Learn how to export archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="a1f46-105">보관 데이터베이스에 보관된 데이터는 검색 가능하거나 읽을 수 있는 형식으로 제공되지 않지만 **Export-CsArchivingData** cmdlet을 사용하여 데이터베이스에서 레코드를 추출하여 Outlook EML(전자 메일) 파일로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1f46-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the **Export-CsArchivingData** cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span>
  
<span data-ttu-id="a1f46-106">Microsoft Exchange 통합을 사용하도록 설정하면 데이터가 Exchange 저장소에 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1f46-106">If you enable Microsoft Exchange integration, data is archived in Exchange stores.</span></span> <span data-ttu-id="a1f46-107">Exchange에 보관된 데이터는 검색 가능하고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1f46-107">Data archived in Exchange is searchable and discoverable.</span></span> <span data-ttu-id="a1f46-108">Exchange에 보관된 데이터에 액세스하는 데 대한 자세한 내용은 Exchange 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a1f46-108">For details about accessing data that is archived in Exchange, see the Exchange documentation.</span></span>
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a1f46-109">Cmdlet을 사용하여 보관 Windows PowerShell 내보내기</span><span class="sxs-lookup"><span data-stu-id="a1f46-109">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a1f46-110">이 cmdlet을 사용하여 보관된 데이터를 내보낼 Export-CSArchivingData 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1f46-110">You can export archived data by using the Export-CSArchivingData cmdlet.</span></span> 
  
<span data-ttu-id="a1f46-111">다음 명령은 2012년 6월 1일 atl-sql-001.contoso.com 보관 데이터베이스에 기록된 모든 보관 데이터를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1f46-111">The following command exports all the archiving data written to the archiving database atl-sql-001.contoso.com since June 1, 2012.</span></span> <span data-ttu-id="a1f46-112">결과 출력 파일은 C:\ArchivingExports 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1f46-112">The resulting output file will be stored in the folder C:\ArchivingExports.</span></span>
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

<span data-ttu-id="a1f46-113">다음 명령은 단일 사용자에 대한 보관 데이터를 내보낼 수 kenmyer@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a1f46-113">The following command exports archiving data for a single user: kenmyer@contoso.com.</span></span> <span data-ttu-id="a1f46-114">이 수행은 UserUri 매개 변수와 사용자의 SIP 주소를 포함하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1f46-114">This is done by including the UserUri parameter followed by the user's SIP address.</span></span> <span data-ttu-id="a1f46-115">예:</span><span class="sxs-lookup"><span data-stu-id="a1f46-115">For example:</span></span> 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="a1f46-116">자세한 내용은 [Export-CsArchivingData](/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a1f46-116">For more information, see the help topic for the [Export-CsArchivingData](/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet.</span></span>
