---
title: 비즈니스용 Skype 서버에서 환경 품질 구성 설정 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: '요약: 비즈니스용 Skype 서버에서 체감 품질 (환경 품질) 설정을 삭제 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 08c002b45db7e8dd9617f2314c49d3d43057d545
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818018"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 환경 품질 구성 설정 삭제
 
**요약:** 비즈니스용 Skype 서버에서 체감 품질 (환경 품질) 설정을 삭제 하는 방법에 대해 알아봅니다.
  
경력 (체감 품질) 메트릭은 손실 된 네트워크 패킷 수, 배경 잡음, "지터"의 양 (패킷 지연의 차이) 등을 포함 하 여 조직에서 오디오 및 비디오 통화의 품질을 추적 합니다. 이러한 메트릭은 다른 데이터 (예: 호출 정보 레코드)와는 별도로 데이터베이스에 저장 되며,이를 사용 하 여 기타 데이터 기록과 독립적으로 체감 품질를 활성화 및 비활성화할 수 있습니다.
  
비즈니스용 Skype 서버를 설치 하면 체감 품질 구성 설정의 단일 전역 컬렉션이 만들어집니다. 또한 관리자는 개별 사이트에 적용할 수 있는 사용자 지정 설정 모음을 만드는 옵션도 있습니다. 사이트 범위에서 구성 된 설정은 전역 범위에서 구성 된 설정 보다 우선 하므로 디자인에 따라 적용 됩니다. 사이트 범위 설정을 삭제 하면 전역 설정을 사용 하 여 해당 사이트에서 체감 품질가 관리 됩니다.
  
전역 설정을 "삭제" 할 수도 있습니다. 그러나 전역 설정은 실제로 제거 되지 않습니다. 대신 해당 컬렉션의 모든 속성이 기본값으로 다시 설정 됩니다. 예를 들어 체감 품질 구성 설정 컬렉션에서 기본적으로 제거를 사용할 수 있습니다. 제거를 사용할 수 없도록 전역 컬렉션을 수정 한다고 가정 합니다. 나중에 전역 설정을 삭제 하면 모든 속성이 기본값으로 다시 설정 됩니다. 이 경우 제거를 다시 사용할 수 있습니다.
  
비즈니스용 Skype Server 제어판을 사용 하거나 [remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet을 사용 하 여 체감 품질 구성 설정을 제거할 수 있습니다.
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용 하 여 체감 품질 구성 설정을 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 **대리인 설정 사용**을 참조 하세요.
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.  
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **경력 데이터 품질**을 클릭 합니다.
    
4. **경력 데이터** 페이지에서 원하는 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.
    
5. **확인**을 클릭합니다.
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 체감 품질 구성 설정 제거

Windows PowerShell 및 **Remove-CsQoEConfiguration** cmdlet을 사용 하 여 체감 품질 구성 설정을 삭제할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>지정 된 체감 품질 구성 설정 컬렉션을 제거 하려면

 이 명령은 Redmond 사이트에 적용 된 체감 품질 구성 설정을 제거 합니다.
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>사이트 범위에 적용 된 모든 체감 품질 구성 설정을 제거 하려면

 이 명령은 사이트 범위에 적용 된 모든 체감 품질 구성 설정을 제거 합니다.
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>체감 품질 모니터링을 사용 하지 않도록 설정 된 체감 품질 구성 설정을 모두 제거 하려면

 이 명령은 체감 품질 모니터링을 사용 하지 않도록 설정한 모든 체감 품질 구성 설정을 제거 합니다.
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

자세한 내용은 [제거-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)를 참조 하세요.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 통화 정보 기록 및 경력 데이터베이스의 품질을 수동으로 제거](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

