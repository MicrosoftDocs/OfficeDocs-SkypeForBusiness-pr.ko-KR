---
title: 비즈니스용 Skype 서버에서 환경 품질 구성 설정 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: '요약: 비즈니스용 Skype 서버의 체감 품질 (환경 품질) 설정에 대해 알아보세요.'
ms.openlocfilehash: d87938fdab64f3a77b96f427363c846829081f44
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197646"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 환경 품질 구성 설정 만들기
 
**요약:** 비즈니스용 Skype 서버의 체감 품질 (환경 품질) 설정에 대해 알아보세요.
  
경력 (체감 품질) 메트릭은 손실 된 네트워크 패킷 수, 배경 잡음, "지터"의 양 (패킷 지연의 차이) 등을 포함 하 여 조직에서 오디오 및 비디오 통화의 품질을 추적 합니다. 이러한 메트릭은 다른 데이터 (예: 호출 정보 레코드)와는 별도로 데이터베이스에 저장 되며,이를 사용 하 여 기타 데이터 기록과 독립적으로 체감 품질를 활성화 및 비활성화할 수 있습니다.
  
비즈니스용 Skype 서버를 설치 하면 체감 품질 구성 설정의 단일 전역 컬렉션이 만들어집니다. 또한 관리자는 사이트 범위에서 사용자 지정 설정을 만드는 옵션도 있습니다. 이러한 사이트 범위 설정이 사용 될 때마다 전역 설정 보다 우선적으로 적용 됩니다. 예를 들어 Redmond 사이트에 대 한 사이트 범위 설정을 만드는 경우 전역 설정이 아닌 해당 설정을 사용 하 여 Redmond의 체감 품질를 관리 합니다.
  
체감 품질 구성 설정은 비즈니스용 Skype 서버 제어판 또는 [CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet을 사용 하 여 만들 수 있습니다. 비즈니스용 Skype Server 제어판을 사용 하 여 새 설정을 만드는 경우 다음 옵션을 사용할 수 있습니다.
  
|**UI 설정**|**PowerShell 매개 변수**|**설명**|
|:-----|:-----|:-----|
|이름  <br/> |Identity  <br/> |만들려는 설정의 고유 식별자입니다. 체감 품질 구성 설정은 사이트 범위 에서만 만들 수 있습니다.  <br/> |
|체감 품질 데이터 모니터링 사용  <br/> |EnableQoE  <br/> |체감 품질 레코드를 수집 하 여 모니터링 데이터베이스에 저장할지 여부를 지정 합니다.  <br/> |
|체감 품질 데이터 제거 사용  <br/> |EnablePurging  <br/> |**최대 기간에 대해 체감 품질 데이터 유지 (days)** 속성에 정의 된 기간이 경과한 후 레코드를 제거할지 여부를 지정 합니다. <br/> |
|최대 기간 (일) 동안 체감 품질 데이터 유지  <br/> |KeepQoEDataForDays  <br/> |데이터베이스에서 삭제 되기 전에 데이터가 저장 되는 일 수 체감 품질. 제거를 사용할 수 없는 경우이 값은 무시 됩니다.  <br/> |
   
> [!NOTE]
> 새로운 CsQoEConfiguration cmdlet에는 비즈니스용 Skype Server 제어판에서 사용할 수 없는 추가 옵션이 포함 되어 있습니다. 자세한 내용은 [새로운 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) 도움말 항목을 참조 하세요.
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용 하 여 체감 품질 구성 설정을 만들려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 **대리인 설정 사용**을 참조 하세요.
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.  
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **경력 데이터 품질**을 클릭 합니다.
    
4. **경력 데이터** 페이지에서 **새로 만들기**를 클릭 합니다.
    
5. **사이트 선택**에서 정책을 적용할 사이트를 클릭 하 고 **확인**을 클릭 합니다.
    
6. **새로운 환경 품질 설정**에서 다음을 수행 합니다.
    
   - 모니터링을 켜려면 **체감 품질 데이터 모니터링 사용** 을 선택 합니다.
    
   - 제거를 켜려면 **체감 품질 데이터 제거 사용** 을 선택 합니다.
    
   - **최대 기간 (일 수)에 대해 체감 품질 유지**를 선택 하 고, 체감 품질 레코드를 보존 해야 하는 최대 기간 (일)을 선택 합니다.
    
7. **커밋**을 클릭합니다.
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 체감 품질 구성 설정 만들기

Windows PowerShell 및 New-CsQoEConfiguration cmdlet을 사용 하 여 체감 품질 구성 설정을 만들 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>체감 품질 구성 설정의 새 컬렉션을 만들려면

 이 명령은 Redmond 사이트에 적용 된 체감 품질 구성 설정의 새 컬렉션을 만듭니다.
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>체감 품질 모니터링을 사용 하지 않도록 설정 된 체감 품질 구성 설정의 새 컬렉션을 만들려면

 앞의 명령에서 필수 Id 매개 변수 이외의 매개 변수를 지정 하지 않았으므로 새 구성 설정 모음에는 해당 속성에 대 한 기본값이 사용 됩니다. 다른 속성 값을 사용 하는 설정을 만들려면 간단히 적절 한 매개 변수와 매개 변수 값을 포함 합니다. 예를 들어 기본적으로 체감 품질 녹화 사용 안 함을 허용 하는 환경 구성 설정의 컬렉션을 만들려면 다음과 같은 명령을 사용 합니다.
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>체감 품질 구성 설정의 새 컬렉션을 만들 때 여러 속성 값을 지정 하려면

 여러 매개 변수를 포함 하 여 여러 속성 값을 사용할 수 있습니다. 예를 들어이 명령은 체감 품질 데이터를 30 일간 유지 하 고 3:00 AM에 오래 된 데이터를 제거 하도록 새 설정을 구성 합니다.
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

자세한 내용은 [새 CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.
  

