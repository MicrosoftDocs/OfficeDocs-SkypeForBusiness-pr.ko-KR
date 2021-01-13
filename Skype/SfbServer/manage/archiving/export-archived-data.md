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
ms.openlocfilehash: caff65e829b24dc83760c7a505e344905c9e09e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817568"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 보관된 데이터 내보내기

**요약:** 비즈니스용 Skype 서버의 보관된 데이터를 내보내는 방법을 자세히 알아보는 방법을 배워야 합니다.
  
보관 데이터베이스에 보관된 데이터는 검색 가능하거나 읽을 수 있는 형식으로 검색할 수 없지만 **Export-CsArchivingData** cmdlet을 사용하여 데이터베이스에서 레코드를 추출한 다음 Outlook EML(전자 메일) 파일로 저장할 수 있습니다.
  
Microsoft Exchange 통합을 사용하도록 설정하면 데이터가 Exchange 저장소에 보관됩니다. Exchange에 보관된 데이터는 검색 가능하고 검색할 수 있습니다. Exchange에 보관된 데이터에 액세스하는 데 대한 자세한 내용은 Exchange 설명서를 참조하십시오.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 보관 Windows PowerShell 내보내기

이 cmdlet을 사용하여 보관된 데이터를 내보낼 Export-CSArchivingData 있습니다. 
  
다음 명령은 2012년 6월 1일 atl-sql-001.contoso.com 보관 데이터베이스에 기록된 모든 보관 데이터를 내보낼 수 있습니다. 결과 출력 파일은 C:\ArchivingExports 폴더에 저장됩니다.
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

다음 명령은 단일 사용자에 대한 보관 데이터를 내보낼 수 kenmyer@contoso.com. 이 수행은 UserUri 매개 변수와 사용자의 SIP 주소를 포함하여 수행됩니다. 예제: 
  
```PowerShell
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

자세한 내용은 [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.
  

