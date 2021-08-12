---
title: CDR 구성 정보를 비즈니스용 Skype 서버
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
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: '요약: CDR(통화 정보 기록)을 사용하는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: 058a6538c8486c52fd47354fe4116e339c83a8b9479ec2da214c4f39d8558308
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341883"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>CDR 구성 정보를 비즈니스용 Skype 서버
 
**요약:** CDR(통화 정보 기록)을 사용하는 방법을 비즈니스용 Skype 서버.
  
CDR(통화 정보 기록)을 사용하면 피어 투 피어 인스턴트 메시징 세션, VoIP(Voice over Internet Protocol) 전화 통화, 전화 회의 통화 등의 사용 현황을 추적할 수 있습니다. 이러한 사용 내역 데이터에는 누가 누구에게 전화를 걸었는지, 언제 전화를 걸었는지 및 얼마나 오래 통화했는지에 대한 정보가 포함됩니다.
  
설치 비즈니스용 Skype 서버 CDR 구성 설정의 전역 컬렉션이 하나만 만들어집니다. 관리자는 또한 개별 사이트에 적용할 수 있는 사용자 지정 설정 컬렉션을 만들 수 있습니다. 제어판 또는 [Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet을 사용하여 조직에서 사용 비즈니스용 Skype 서버 CDR 구성 설정을 볼 수 있습니다.
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 CDR 구성 비즈니스용 Skype 서버 확인하려면

1. 비즈니스용 Skype 서버 제어판에서 **모니터링 및 보관을 클릭합니다.**
    
2. 모든 CDR 구성 설정에 대한 목록은 **통화 정보 기록** 탭에 표시됩니다. 설정의 각 컬렉션에 대해 컬렉션 **이름** 이 표시되고, CDR이 설정되었는지 여부(**CDR** 속성), 삭제가 설정되었는지 여부(**CDR 삭제** 속성)가 표시됩니다. 컬렉션에 대한 자세한 내용을 보려면 해당 컬렉션을 두 번 클릭하거나 적합한 컬렉션을 선택하고, **편집** 을 클릭한 후 **세부 정보 표시** 를 클릭합니다. CDR 구성 설정은 한 번에 하나의 단일 컬렉션에 대한 자세한 정보만 확인할 수 있습니다.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 CDR 구성 Windows PowerShell 보기

CDR 구성 설정은 Windows PowerShell cmdlet을 사용하여 Get-CsCdrConfiguration 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 세션에서 실행할 수 Windows PowerShell. 원격 서버를 사용하여 Windows PowerShell 연결하는 비즈니스용 Skype 서버 ["빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)블로그 문서를 참조하십시오. 프로세스는 동일한 비즈니스용 Skype 서버.
  
### <a name="to-view-cdr-configuration-information"></a>CDR 구성 정보를 보려면

- 모든 CDR 구성 설정에 대한 정보를 확인하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력한 다음 Enter를 누를 수 있습니다.
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    그러면 다음과 같은 정보가 반환됩니다.
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

자세한 내용은 [Get-CsCdrConfiguration](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.
