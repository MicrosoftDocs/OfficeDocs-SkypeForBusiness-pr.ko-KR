---
title: 비즈니스용 Skype 서버에서 외부 사용자에 대 한 보관 부인 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: '요약: 비즈니스용 Skype 서버에 대 한 보관 거부를 구성 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.'
ms.openlocfilehash: d6c08b6fe2eaa6c74231b96346661488c3f8e2b0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001058"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 외부 사용자에 대 한 보관 부인 구성
 
**요약:** 비즈니스용 Skype 서버용 보관 고 지 사항 구성 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
  
조직이 외부 파트너와 통신 하는 경우에는 사용자가 통신을 보관 하 고 있다는 것을 알려야 합니다. Edge 서버를 배포 하 고 조직에 대해 페더레이션을 사용 하는 경우 외부 파트너에 게 자동으로 보관 거부를 보낼지 묻는 메시지가 표시 됩니다. 
  
이 구성을 변경 해야 하는 경우 비즈니스용 Skype 서버 제어판 또는 Windows PowerShell **CsAccessEdgeConfiguration** cmdlet을 사용할 수 있습니다. Cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.
  
외부 사용자가 비즈니스용 Skype 서버 배포에서 사용자와 공동 작업할 수 있도록 하려면 외부 사용자 액세스를 지원 하기 위해 하나 이상의 외부 액세스 정책을 구성 해야 합니다. 자세한 내용은 조직의 XMPP 페더레이션 파트너 관리를 참조 하세요. 특정 페더레이션 도메인에 대 한 액세스 제어에 대 한 자세한 내용은 개별 페더레이션 도메인에의 한 액세스 제어를 참조 하세요.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>제어판을 사용 하 여 보관 고 지 사항 사용 또는 사용 안 함

1. RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
    
3. 왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭 한 다음 **액세스 경계 구성을**클릭 합니다.
    
4. **액세스 경계 구성** 탭에서 **전역**을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
5. **액세스에 지 구성 편집**의 **페더레이션 및 공용 IM 연결 사용**에서 페더레이션 **파트너에 게 보관** 고 지 사항 보내기 확인란을 선택 하거나 선택을 취소 하 여 보관 거부를 자동으로 보내는 기능을 설정 하거나 해제 합니다.
    
6. **커밋**을 클릭합니다.
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 보관 거부 사용 또는 사용 안 함

보관 부인를 사용 하도록 설정 하려면 **EnableArchivingDisclaimer** 속성 값을 True ($True)로 설정 합니다.
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

보관 고 지 사항을 사용 하지 않으려면 **EnableArchivingDisclaimer** 속성 값을 False ($False)로 설정 합니다.
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


