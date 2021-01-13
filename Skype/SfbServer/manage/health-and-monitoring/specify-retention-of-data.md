---
title: 비즈니스용 Skype 서버에서 CDR 데이터 보존 지정
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
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: '요약: 비즈니스용 Skype 서버의 CDR(통화 정보 기록) 데이터를 관리하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 01b4765a9fa98a898255c1374115e17c4966e797
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814218"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 CDR 데이터 보존 지정
 
**요약:** 비즈니스용 Skype 서버의 CDR(통화 정보 기록) 데이터를 관리하는 방법을 설명하는 정보를 제공합니다.
  
기본적으로 CDR(통화 정보 기록) 데이트는 60일 이후에 삭제됩니다. **통화 정보 기록** 페이지의 설정을 사용하여 데이터를 60일 이상 보존하거나 60일보다 짧게 보존할 수 있습니다. CDR을 사용하지 않도록 설정한 경우 CDR을 사용하도록 설정하기 전에 캡처한 데이터도 삭제됩니다.
  
> [!NOTE]
> CDR 및 QoE(체감 품질)의 데이터 보존 일수는 동일하게 구성해야 합니다. 모니터링 서버 보고서 홈 페이지에 있는 CDR(통화 정보 보고서)의 각 통화에는 CDR 및 QoE 정보가 포함됩니다. CDR 및 QoE의 삭제 기간이 다를 경우 일부 통화에는 CDR 데이터만 포함되고 또 다른 일부 통화에는 QoE 데이터만 포함될 수 있습니다. 
  
CDR 데이터에 대한 삭제 설정을 구성하려면 다음 절차를 따릅니다. 
  
### <a name="to-specify-retention-of-cdr-data"></a>CDR 데이터 보존 기간을 지정하려면

1. RTCUniversalServerAdmins 그룹의 구성원인 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.
    
2. 브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.  
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **통화 정보 기록** 을 클릭합니다.
    
4. **통화 정보 기록** 페이지의 테이블에서 적합한 사이트를 클릭하고 **편집**, **자세한 정보 표시** 를 차례로 클릭합니다.
    
5. 삭제를 설정하려면 **CDR(통화 정보 기록) 삭제 사용** 을 선택합니다.
    
6. **최대 기간(일) 동안 통화 정보 기록 유지:** 에서 통화 정보 기록을 보존할 최대 일수를 선택합니다.
    
7. **최대 기간(일) 동안 오류 보고서 데이터 유지:** 에서 오류 보고서를 보존할 최대 일수를 선택합니다.
    
8. **커밋** 을 클릭합니다.
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 CDR Windows PowerShell 지정

Windows PowerShell 및 Set-CsCdrConfiguration cmdlet을 사용하여 CDR 보존 설정을 만들 수 있습니다. 비즈니스용 Skype 서버 관리 셸 또는 원격 세션에서 이 cmdlet을 실행할 수 Windows PowerShell. 원격 서버를 사용하여 비즈니스용 Skype Windows PowerShell 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를](https://go.microsoft.com/fwlink/p/?linkId=255876)참조하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.
  
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

자세한 내용은 [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버의 CDR(통화 정보 기록)](call-detail-recording-cdr.md)
