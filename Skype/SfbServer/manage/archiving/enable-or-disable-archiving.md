---
title: 비즈니스용 Skype 서버에서 보관 사용 또는 사용 안 함
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: '요약: 비즈니스용 Skype 서버에서 보관을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 0e4ef4dde27ffa5856f2b73b69ffbadc24399c59
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190374"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 보관 사용 또는 사용 안 함

**요약:** 비즈니스용 Skype 서버에서 보관을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대해 알아봅니다.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>제어판을 사용 하 여 보관 사용 또는 사용 안 함

1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다. 
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.
    
4. 보관 구성 목록에서 적절 한 전역, 사이트 또는 풀 구성을 선택 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 하 고 다음을 수행 합니다.
    
   - IM (인스턴트 메시징) 세션에 대해서만 보관을 사용 하도록 설정 하려면 **im 세션 보관**을 클릭 합니다.
    
   - IM 세션과 회의 모두에 대해 보관을 사용 하도록 설정 하려면 **im 및 회의 세션 보관**을 클릭 합니다.
    
   - 구성에 대 한 보관을 사용 하지 않도록 설정 하려면 **보관 사용 안 함을**클릭 합니다.
    
5. **커밋**을 클릭합니다.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 보관 사용 또는 사용 안 함

**Set-CsArchivingConfiguration** cmdlet을 사용 하 여 보관을 사용 하거나 사용 하지 않도록 설정할 수도 있습니다. 예를 들어 다음 명령은 IM 세션만 보관 되도록 모든 보관 구성 설정을 수정 합니다. 이 명령은 현재 조직에서 사용 중인 모든 보관 구성 설정을 반환 하기 위해 매개 변수 없이 **CsArchivingConfiguration** cmdlet을 호출 합니다. 그런 다음이 컬렉션은 EnableArchiving 속성이 (-eq) "ImAndWebConf"와 동일한 설정만 선택 하는 **Where 개체** cmdlet으로 파이프 됩니다. 그런 다음 필터링 된 컬렉션이 컬렉션의 각 항목을 가져와 EnableArchiving 값을 "ImOnly"로 변경 하는 **집합-CsArchivingConfiguration** cmdlet으로 파이프 됩니다.
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
