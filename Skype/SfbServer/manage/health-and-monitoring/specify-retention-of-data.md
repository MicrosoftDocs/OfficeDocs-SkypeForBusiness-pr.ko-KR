---
title: 비즈니스용 Skype 서버에서 CDR 데이터 보존 지정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: '요약: 비즈니스용 Skype 서버용 CDR (통화 정보 기록) 데이터를 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: a775098a4c41bccca42fe1d95c5f1dbf0d22f2bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188676"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 CDR 데이터 보존 지정
 
**요약:** 비즈니스용 Skype 서버용 CDR (통화 정보 기록) 데이터를 관리 하는 방법에 대해 알아봅니다.
  
기본적으로, 60 일 후에 CDR (통화 정보 기록) 데이터가 제거 됩니다. **통화 정보 기록** 페이지의 설정을 사용 하 여 오래 되거나 짧은 시간 동안 데이터를 유지할 수 있습니다. CDR를 사용 하지 않도록 설정 하는 경우 CDR를 사용 하도록 설정 하기 전에 캡처한 데이터도 제거 될 수 있습니다.
  
> [!NOTE]
> 동일한 일 수 동안 데이터를 보존 하도록 CDR 및 경력 (체감 품질)을 구성 해야 합니다. 모니터링 서버 보고서 웹 페이지에서 사용할 수 있는 CDRs (통화 정보 보고서)의 각 통화에는 CDR 및 체감 품질 정보가 포함 됩니다. CDR 및 체감 품질의 제거 기간이 서로 다른 경우 일부 통화에는 CDR 데이터만 포함 될 수 있으며, 그 외에는 체감 품질 데이터만 포함 될 수 있습니다. 
  
CDR 데이터에 대 한 지우기 설정을 구성 하려면 다음 절차를 사용 합니다. 
  
### <a name="to-specify-retention-of-cdr-data"></a>CDR 데이터 보존을 지정 하려면

1. RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.  
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **통화 정보 기록을**클릭 합니다.
    
4. **통화 정보 기록** 페이지에서 표의 해당 사이트를 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
5. 제거를 설정 하려면 **CDRs 제거 사용**을 선택 합니다.
    
6. **최대 기간 (일) 동안 CDRs 유지:** 통화 정보 기록을 보존 해야 하는 최대 일 수를 선택 합니다.
    
7. **최대 기간 (일)에 대 한 오류 보고 데이터 유지:** 오류 보고서를 유지 해야 하는 최대 일 수를 선택 합니다.
    
8. **커밋**을 클릭합니다.
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Windows PowerShell cmdlet을 사용 하 여 CDR 보존 지정

Windows PowerShell 및 Set-CsCdrConfiguration cmdlet을 사용 하 여 CDR 보존 설정을 만들 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a>특정 위치에 대 한 CDR 보존을 지정 하려면

- 이 명령을 사용 하 여 Redmond 사이트에 대 한 CDR 데이터를 제거 하 고, 사이트를 구성 하 여 CDR 데이터와 오류 보고 데이터를 모두 20 일 동안 유지 하도록 합니다.
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a>여러 위치에 대 한 CDR 보존을 지정 하려면

- 이 명령은 조직에서 사용 중인 모든 CDR 구성 설정에 대해 CDR 보존을 구성 합니다.
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

자세한 내용은 [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버의 전화 정보 기록 (CDR)](call-detail-recording-cdr.md)
