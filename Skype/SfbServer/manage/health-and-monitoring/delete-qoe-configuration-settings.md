---
title: 사용자 환경의 경험 품질 구성 설정 비즈니스용 Skype 서버
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
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: '요약: QoE(QoE) 설정을 삭제하는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: 036944af245b608ccae9836670133f99f8004068
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763666"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>사용자 환경의 경험 품질 구성 설정 비즈니스용 Skype 서버
 
**요약:** QoE(QoE) 설정을 삭제하는 방법을 비즈니스용 Skype 서버.
  
QoE(체감 품질) 메트릭은 손실된 네트워크 패킷 수, 백그라운드 노이즈, "지터"(패킷 지연의 차이) 크기 등 조직의 오디오 및 비디오 통화 품질을 추적합니다. 이러한 메트릭은 통화 정보 기록과 같은 기타 데이터와 별도로 데이터베이스에 저장되므로 다른 데이터 기록에 관계없이 QoE를 설정 및 해제할 수 있습니다.
  
QoE 비즈니스용 Skype 서버 컬렉션을 설치하면 단일 전역 QoE 구성 설정 컬렉션이 만들어집니다. 관리자는 또한 개별 사이트에 적용할 수 있는 사용자 지정 설정 컬렉션을 만들 수 있습니다. 이러한 설정은 전역 범위 또는 사이트 범위에서 구성할 수 있습니다. 사이트 범위의 설정을 삭제할 경우 QoE는 전역 설정을 사용하여 해당 사이트에서 관리됩니다.
  
전역 설정을 "삭제"할 수도 있습니다. 그러나 전역 설정을 사실상 삭제되지 않습니다. 대신에, 해당 모음에 있는 모든 속성이 기본값으로 다시 설정됩니다. 예를 들면 기본적으로 지우기는 QoE 구성 설정 모음에서 사용할 수 있습니다. 지우기를 사용할 수 없도록 전역 모음을 수정한다고 가정하겠습니다. 나중에 전역 설정을 삭제하면 모든 속성이 기본값으로 다시 설정됩니다. 따라서 이 경우에는 지우기를 다시 사용할 수 있게 됩니다.
  
제어판 또는 [Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet을 사용하여 비즈니스용 Skype 서버 QoE 구성 설정을 제거할 수 있습니다.
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 QoE 구성 비즈니스용 Skype 서버 삭제하려면

1.  RTCUniversalServerAdmins 그룹의 구성원이나 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다. 자세한 내용은 **Delegate Setup Permissions** 을 참조하십시오.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.  
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **체감 품질 데이터** 를 클릭합니다.
    
4. **체감 품질 데이터** 페이지에서 원하는 정책을 클릭하고 **편집** 을 클릭한 다음 **삭제** 를 클릭합니다.
    
5. **확인** 을 클릭합니다.
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Cmdlet을 설정 QoE 구성 Windows PowerShell 제거

**Remove-CsQoEConfiguration** cmdlet 및 Windows PowerShell 사용하여 QoE 구성 설정을 삭제할 수 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 세션에서 실행할 수 Windows PowerShell. 원격 응용 Windows PowerShell 연결에 대한 자세한 비즈니스용 Skype 서버 [Microsoft Lync Remote PowerShell Administration 을 참조합니다.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) 프로세스는 동일한 비즈니스용 Skype 서버.
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>지정된 QoE 구성 설정 모음을 제거하려면

 이 명령은 Redmond 사이트에 적용된 QoE 구성 설정을 제거합니다.
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>사이트 범위에 적용된 모든 QoE 구성 설정을 제거하려면

 이 명령은 사이트 범주에 적용된 모든 QoE 구성 설정을 제거합니다.
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>QoE 모니터링을 사용할 수 없는 경우 모든 QoE 구성 설정을 제거하려면

 이 명령은 QoE 모니터링을 사용할 수 없는 경우 모든 QoE 구성 설정을 제거합니다.
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

자세한 내용은 [Remove-CsQoEConfiguration을 참조합니다.](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)
  
## <a name="see-also"></a>참고 항목

[통화 정보 기록 및 경험 품질 데이터베이스를 수동으로 비즈니스용 Skype 서버](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)