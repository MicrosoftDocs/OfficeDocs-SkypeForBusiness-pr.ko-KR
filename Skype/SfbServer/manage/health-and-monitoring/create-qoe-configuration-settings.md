---
title: 사용자 환경의 경험 품질 구성 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: '요약: QoE(QoE) 설정에 대해 비즈니스용 Skype 서버.'
ms.openlocfilehash: 842e9bbf3100efc30346e88b4b5f660cdd42ec53
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858325"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>사용자 환경의 경험 품질 구성 비즈니스용 Skype 서버
 
**요약:** QoE(QoE) 설정에 대해 비즈니스용 Skype 서버.
  
QoE(체감 품질) 메트릭은 손실된 네트워크 패킷 수, 백그라운드 노이즈, "지터"(패킷 지연의 차이) 크기 등 조직의 오디오 및 비디오 통화 품질을 추적합니다. 이러한 메트릭은 통화 정보 기록과 같은 기타 데이터와 별도로 데이터베이스에 저장되므로 다른 데이터 기록에 관계없이 QoE를 설정 및 해제할 수 있습니다.
  
QoE 비즈니스용 Skype 서버 컬렉션을 설치하면 단일 전역 QoE 구성 설정 컬렉션이 만들어집니다. 관리자에게는 또한 사이트 범위에서 사용자 지정 설정을 만드는 옵션이 제공됩니다. 이러한 사이트 범위 설정을 사용할 때마다 전역 설정보다 우선 적용됩니다. 예를 들어 Redmond 사이트에 대해 사이트 범위의 설정을 만들었으면 해당 설정(전역 설정이 아니라)이 Redmond의 QoE를 관리하는 데 사용됩니다.
  
QoE 구성 설정은 제어판 또는 [New-비즈니스용 Skype 서버](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet을 사용하여 만들 수 있습니다. 제어판을 비즈니스용 Skype 서버 새 설정을 만드는 경우 다음 옵션을 사용할 수 있습니다.
  
|**UI 설정**|**PowerShell 매개 변수**|**설명**|
|:-----|:-----|:-----|
|이름  <br/> |ID  <br/> |만들려는 설정에 대한 고유한 식별자입니다. QoE 구성 설정은 사이트 범위에서만 만들 수 있습니다.  <br/> |
|QoE 데이터에 대한 모니터링 사용  <br/> |EnableQoE  <br/> |QoE 레코드를 수집하고 모니터링 데이터베이스에 저장할지 여부를 지정합니다.  <br/> |
|QoE 데이터에 대한 삭제 사용  <br/> |EnablePurging  <br/> |**QoE 데이터 보관 최대 기간(일 수)** 속성에 정의된 기간이 경과한 후 레코드를 삭제할지 여부를 지정합니다. <br/> |
|QoE 데이터 보관 최대 기간(일 수)  <br/> |KeepQoEDataForDays  <br/> |데이터베이스에서 삭제되기 전에 QoE 데이터를 저장할 기간(일)입니다. 삭제를 사용하지 않도록 설정하면 이 값이 무시됩니다.  <br/> |
   
> [!NOTE]
> 이 New-CsQoEConfiguration cmdlet에는 제어판에서 사용할 수 없는 추가 비즈니스용 Skype 서버 포함되어 있습니다. 자세한 내용은 [New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) 도움말 항목을 참조하십시오.
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 QoE 구성 설정을 비즈니스용 Skype 서버

1. RTCUniversalServerAdmins 그룹의 구성원이나 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다. 자세한 내용은 **Delegate Setup Permissions** 을 참조하십시오.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.  
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **체감 품질 데이터** 를 클릭합니다.
    
4. **체감 품질 데이터** 페이지에서 **새로 만들기** 를 클릭합니다.
    
5. **사이트 선택** 에서 정책을 적용할 사이트를 클릭하고 **확인** 을 클릭합니다.
    
6. **새 체감 품질 설정** 에서 다음을 수행합니다.
    
   - **QoE 데이터 모니터링 사용** 을 선택하여 모니터링을 설정합니다.
    
   - **QoE 데이터 삭제 사용** 을 선택하여 삭제를 설정합니다.
    
   - **QoE 보관 최대 기간(일 수)** 에서 QoE 레코드를 보관할 최대 기간(일 수)을 선택합니다.
    
7. **커밋** 을 클릭합니다.
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Cmdlet을 설정 QoE 구성 Windows PowerShell 만들기

QoE 구성 설정은 Windows PowerShell cmdlet을 사용하여 New-CsQoEConfiguration 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 세션에서 실행할 수 Windows PowerShell. 원격 응용 Windows PowerShell 연결에 대한 자세한 비즈니스용 Skype 서버 [Microsoft Lync Remote PowerShell Administration 을 참조합니다.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) 프로세스는 동일한 비즈니스용 Skype 서버.
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>QoE 구성 설정의 새 컬렉션을 만들려면

 이 명령은 Redmond 사이트에 적용되는 QoE 구성 설정의 새 컬렉션을 만듭니다.
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>QoE 모니터링이 사용하지 않도록 설정된 QoE 구성 설정의 새 컬렉션을 만들려면

 이전 명령에서 매개 변수(필수 Identity 매개 변수 제외)가 지정되지 않았기 때문에 구성 설정의 새 컬렉션에는 모든 속성에 대해 기본값이 사용됩니다. 다른 속성 값을 사용하는 설정을 만들려면 단순히 적합한 매개 변수와 매개 변수 값을 포함합니다. 예를 들어 기본적으로 QoE 기록을 사용하지 않도록 설정하는 QoE(체감 품질) 구성 설정의 컬렉션을 만들려면 다음과 같은 명령을 사용합니다.
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>QoE 구성 설정의 새 컬렉션을 만들 때 여러 속성 값을 지정하려면

 여러 매개 변수를 포함하여 여러 속성 값을 지정할 수 있습니다. 예를 들어 다음 명령은 QoE 데이터를 30일 동안 보관하고 오전 3시에 오래된 데이터를 삭제하도록 지정하는 새 설정을 구성합니다.
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

자세한 내용은 [New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.
