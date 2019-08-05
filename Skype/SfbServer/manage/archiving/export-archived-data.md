---
title: 비즈니스용 Skype 서버에서 보관 된 데이터 내보내기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8214bb0a-baa7-414f-9eee-313b65223fa3
description: '요약: 비즈니스용 Skype 서버용 보관 된 데이터를 내보내는 방법에 대해 알아보세요.'
ms.openlocfilehash: 6914b4c32c22165b551bb56ece8d7b3b9c21fdbe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190362"
---
# <a name="export-archived-data-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 보관 된 데이터 내보내기

**요약:** 비즈니스용 Skype 서버용 보관 된 데이터를 내보내는 방법에 대해 알아봅니다.
  
보관 데이터베이스에 보관 된 데이터는 검색 가능 하거나 읽을 수 있는 형식 이지만 **내보내기-CsArchivingData** cmdlet을 사용 하 여 데이터베이스에서 레코드를 추출 하 고 Outlook 전자 메일 (EML) 파일로 저장할 수 있습니다.
  
Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 데이터는 Exchange 저장소에 보관 됩니다. Exchange에 저장 된 데이터는 검색 및 검색할 수 있습니다. Exchange에 보관 된 데이터에 액세스 하는 방법에 대 한 자세한 내용은 Exchange 설명서를 참조 하세요.
  
## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 데이터 보관 내보내기

Export-CSArchivingData cmdlet을 사용 하 여 보관 된 데이터를 내보낼 수 있습니다. 
  
다음 명령은 2012 년 6 월 1 일 이후 보관 데이터베이스 atl-sql-001.contoso.com에 기록 된 모든 보관 데이터를 내보냅니다. 결과 출력 파일이 폴더에 저장 됩니다 C:\ArchivingExports.
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"
```

다음 명령은 단일 사용자에 대 한 보관 데이터를 kenmyer@contoso.com로 내보냅니다. 이 작업은 UserUri 매개 변수와 사용자의 SIP 주소를 차례로 포함 하 여 수행 됩니다. 예를 들면 다음과 같습니다. 
  
```
Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.contoso.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@contoso.com"
```

자세한 내용은 [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/export-csarchivingdata?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.
  

