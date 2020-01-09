---
title: 비즈니스용 Skype 서버에서 기존 CDR 구성 설정 모음 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: '요약: 비즈니스용 Skype 서버에서 CDR 구성 설정을 제거 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 16b797fb59e16038411c722ce064e14ab756cdfa
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992435"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 기존 CDR 구성 설정 모음 삭제
 
**요약:** 비즈니스용 Skype 서버에서 CDR 구성 설정을 제거 하는 방법에 대해 알아봅니다.
  
CDR (통화 정보 기록)를 사용 하면 피어 투 피어 인스턴트 메시지 세션, VoIP (Voice over 인터넷 프로토콜) 전화 통화, 회의 통화 등의 사용 현황을 추적할 수 있습니다. 이 사용 현황 데이터에는 누가 누구에 게, 그들이 통화 되었는지, 그리고 그에 얼마나 오랜 시간에 대 한 정보가 포함 됩니다.
  
비즈니스용 Skype 서버를 설치 하면 사용자를 위해 CDR 구성 설정의 단일 전역 컬렉션이 만들어집니다. 또한 관리자는 개별 사이트에 적용할 수 있는 사용자 지정 설정 모음을 만드는 옵션도 있습니다. 사이트 범위에서 구성 된 설정은 전역 범위에서 구성 된 설정 보다 우선 하므로 디자인에 따라 적용 됩니다. 사이트 범위 설정을 삭제 하는 경우에는 전역 설정을 사용 하 여 해당 사이트에서 CDR가 관리 됩니다.
  
전역 설정을 "삭제" 할 수도 있습니다. 그러나 전역 설정은 실제로 제거 되지 않습니다. 대신 해당 컬렉션의 모든 속성이 기본값으로 다시 설정 됩니다. 예를 들어, CDR 구성 설정 컬렉션에서 기본적으로 제거를 사용할 수 있습니다. 제거를 사용할 수 없도록 전역 컬렉션을 수정 한다고 가정 합니다. 나중에 전역 설정을 삭제 하면 모든 속성이 기본값으로 다시 설정 됩니다. 이 경우 제거를 다시 사용할 수 있습니다.
  
비즈니스용 Skype Server 제어판 또는 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet을 사용 하 여 CDR 구성 설정을 제거할 수 있습니다.
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판에서 CDR 구성 설정을 제거 하려면

1. 비즈니스용 Skype Server 제어판에서 **모니터링 및 보관**을 클릭 합니다. 
    
2. **통화 정보 기록** 탭에서 제거할 CDR 설정 모음 (또는 컬렉션)을 선택 합니다. 여러 컬렉션을 선택 하려면 첫 번째 컬렉션을 클릭 하 고 Ctrl 키를 누른 상태에서 추가 모음을 클릭 합니다.
    
3. **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.
    
4. 비즈니스용 Skype Server 제어판 대화 상자에서 **확인**을 클릭 합니다.
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 CDR 구성 설정 제거

Windows PowerShell 및 **CsCdrConfiguration** cmdlet을 사용 하 여 통화 정보 기록 구성 설정을 삭제할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>지정 된 CDR 구성 설정 모음을 제거 하려면

 이 명령은 Redmond 사이트에 적용 된 CDR 구성 설정을 제거 합니다.
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>사이트 범위에 적용 된 모든 CDR 구성 설정을 제거 하려면

 이 명령은 사이트 범위에 적용 된 모든 CDR 구성 설정을 제거 합니다.
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

자세한 내용은 [제거 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 통화 정보 기록 및 경력 데이터베이스의 품질을 수동으로 제거](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

