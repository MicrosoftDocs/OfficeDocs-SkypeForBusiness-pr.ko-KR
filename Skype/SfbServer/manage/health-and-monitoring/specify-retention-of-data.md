---
title: CDR 데이터의 보존을 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: '요약: 사용자에 대한 CDR(통화 정보 기록) 데이터를 관리하는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: ac021da1c2235256e4b9bffc2f8664a1572d27d1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60742134"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>CDR 데이터의 보존을 비즈니스용 Skype 서버
 
**요약:** 사용자에 대한 CDR(통화 정보 기록) 데이터를 관리하는 방법을 비즈니스용 Skype 서버.
  
기본적으로 CDR(통화 정보 기록) 데이트는 60일 이후에 삭제됩니다. **통화 정보 기록** 페이지의 설정을 사용하여 데이터를 60일 이상 보존하거나 60일보다 짧게 보존할 수 있습니다. CDR을 사용하지 않도록 설정한 경우 CDR을 사용하도록 설정하기 전에 캡처한 데이터도 삭제됩니다.
  
> [!NOTE]
> CDR 및 QoE(체감 품질)의 데이터 보존 일수는 동일하게 구성해야 합니다. 모니터링 서버 보고서 홈 페이지에 있는 CDR(통화 정보 보고서)의 각 통화에는 CDR 및 QoE 정보가 포함됩니다. CDR 및 QoE의 삭제 기간이 다를 경우 일부 통화에는 CDR 데이터만 포함되고 또 다른 일부 통화에는 QoE 데이터만 포함될 수 있습니다. 
  
CDR 데이터에 대한 삭제 설정을 구성하려면 다음 절차를 따릅니다. 
  
### <a name="to-specify-retention-of-cdr-data"></a>CDR 데이터 보존 기간을 지정하려면

1. RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)의 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 배포한 네트워크의 컴퓨터에 비즈니스용 Skype 서버.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.  
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **통화 정보 기록** 을 클릭합니다.
    
4. **통화 정보 기록** 페이지의 테이블에서 적합한 사이트를 클릭하고 **편집**, **자세한 정보 표시** 를 차례로 클릭합니다.
    
5. 삭제를 설정하려면 **CDR(통화 정보 기록) 삭제 사용** 을 선택합니다.
    
6. **최대 기간(일) 동안 통화 정보 기록 유지:** 에서 통화 정보 기록을 보존할 최대 일수를 선택합니다.
    
7. **최대 기간(일) 동안 오류 보고서 데이터 유지:** 에서 오류 보고서를 보존할 최대 일수를 선택합니다.
    
8. **커밋** 을 클릭합니다.
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 CDR Windows PowerShell 지정

Windows PowerShell 및 Set-CsCdrConfiguration cmdlet을 사용하여 CDR 보존 설정을 만들 수 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 세션에서 실행할 수 Windows PowerShell. 원격 응용 Windows PowerShell 연결에 대한 자세한 비즈니스용 Skype 서버 [Microsoft Lync Remote PowerShell Administration 을 참조합니다.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) 프로세스는 동일한 비즈니스용 Skype 서버.
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a>특정 위치에 대한 CDR 보존을 지정하려면

- 이 명령은 Redmond 사이트에 대해 CDR 데이터 삭제를 사용하도록 설정하고 20일 동안 CDR 데이터 및 오류 보고서 데이터를 유지하도록 구성합니다.
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a>여러 위치에 대한 CDR 보존을 지정하려면

- 이 명령은 조직에서 사용 중인 모든 CDR 구성 설정에 대해 CDR 보존을 구성합니다.
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

자세한 내용은 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.
  
## <a name="see-also"></a>참고 항목

[CDR(통화 정보 기록)비즈니스용 Skype 서버](call-detail-recording-cdr.md)