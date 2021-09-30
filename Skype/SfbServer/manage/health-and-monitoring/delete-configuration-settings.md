---
title: CDR 구성 설정의 기존 컬렉션을 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: '요약: 이 문서에서 CDR 구성 설정을 제거하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: bcc7330a2f09568159259e3a73cd0fd61a8dc6e4
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60015102"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>CDR 구성 설정의 기존 컬렉션을 비즈니스용 Skype 서버
 
**요약:** 사용자 계정에서 CDR 구성 설정을 제거하는 비즈니스용 Skype 서버.
  
CDR(통화 정보 기록)을 사용하면 피어 투 피어 인스턴트 메시징 세션, VoIP(Voice over Internet Protocol) 전화 통화, 전화 회의 통화 등의 사용 현황을 추적할 수 있습니다. 이러한 사용 내역 데이터에는 누가 누구에게 전화를 걸었는지, 언제 전화를 걸었는지 및 얼마나 오래 통화했는지에 대한 정보가 포함됩니다.
  
설치 비즈니스용 Skype 서버 CDR 구성 설정의 전역 컬렉션이 하나만 만들어집니다. 관리자는 또한 개별 사이트에 적용할 수 있는 사용자 지정 설정 컬렉션을 만들 수 있습니다. 사이트 범위에서 구성된 설정은 기본적으로 전역 범위에서 구성된 설정보다 우선 적용됩니다. 사이트 범위 설정을 삭제할 경우 해당 사이트에서 전역 설정을 사용하여 CDR이 관리됩니다.
  
전역 설정을 "삭제"할 수도 있습니다. 그러나 전역 설정을 사실상 삭제되지 않습니다. 대신 해당 컬렉션의 모든 속성이 기본값으로 다시 설정됩니다. 예를 들어, CDR 구성 설정의 컬렉션에서는 기본적으로 삭제를 사용할 수 있도록 설정되어 있습니다. 삭제를 사용하지 않도록 전역 컬렉션을 수정한다고 가정해보겠습니다. 나중에 전역 설정을 삭제하면 모든 속성이 기본값으로 다시 설정됩니다. 따라서 이 경우에는 지우기를 다시 사용할 수 있게 됩니다.
  
CDR 구성 설정은 제어판 또는 [remove-비즈니스용 Skype 서버](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) 사용하여 제거할 수 있습니다.
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>제어판에서 CDR 구성 비즈니스용 Skype 서버 제거하려면

1. 비즈니스용 Skype 서버 제어판에서 모니터링 **및 보관을 클릭합니다.** 
    
2. **통화 정보 기록** 탭에서 제거하려는 CDR 설정의 컬렉션을 선택합니다. 여러 컬렉션을 선택하려면 첫 번째 컬렉션을 클릭하고 Ctrl 키를 누른 상태로 추가 컬렉션을 클릭합니다.
    
3. **편집** 을 클릭한 다음 **삭제** 를 클릭합니다.
    
4. 제어판 비즈니스용 Skype 서버 대화 상자에서 확인을 **클릭합니다.**
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 CDR 구성 Windows PowerShell 제거

통화 정보 기록 구성 설정은 **Remove-CsCdrConfiguration** cmdlet과 Windows PowerShell 삭제할 수 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 세션에서 실행할 수 Windows PowerShell. 원격 응용 Windows PowerShell 연결에 대한 자세한 비즈니스용 Skype 서버 [Microsoft Lync Remote PowerShell Administration 을 참조합니다.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) 프로세스는 동일한 비즈니스용 Skype 서버.
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>CDR 구성 설정의 지정된 컬렉션을 제거하려면

 이 명령은 Redmond 사이트에 적용된 CDR 구성 설정을 제거합니다.
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>사이트 범위에 적용된 모든 CDR 구성 설정을 제거하려면

 이 명령은 사이트 범위에 적용된 모든 CDR 구성 설정을 제거합니다.
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

자세한 내용은 [Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.
  
## <a name="see-also"></a>참고 항목

[통화 정보 기록 및 경험 품질 데이터베이스를 수동으로 비즈니스용 Skype 서버](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)