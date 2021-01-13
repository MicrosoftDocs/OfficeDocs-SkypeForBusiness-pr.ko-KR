---
title: 비즈니스용 Skype 서버에서 외부 사용자에 대한 보관 고지 조항 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: '요약: 이 항목을 읽고 비즈니스용 Skype 서버에 대한 보관 고지 사항 구성 방법을 배워야 합니다.'
ms.openlocfilehash: 055c94f0fba18dcd9de35ff5a73e37de0b45595b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820668"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 외부 사용자에 대한 보관 고지 조항 구성
 
**요약:** 이 항목을 읽고 비즈니스용 Skype 서버에 대한 보관 고지 조항을 구성하는 방법을 배워야 합니다.
  
조직이 외부 파트너와 통신하는 경우 해당 파트너와의 통신을 보관하고 있는 것을 알려야 합니다. 에지 서버를 배포하고 조직에 대해 페더링을 사용하도록 설정하는 경우 보관 고지 조항을 외부 파트너에게 자동으로 보낼지 여부를 묻는 메시지를 표시해야 합니다. 
  
이 구성을 변경해야 하는 경우 비즈니스용 Skype 서버 제어판 또는 **Set-CsAccessEdgeConfiguration** cmdlet을 Windows PowerShell 수 있습니다. Cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버의 원격 세션에서 실행할 수 Windows PowerShell.
  
외부 사용자가 비즈니스용 Skype 서버 배포에서 사용자와 공동 작업을 할 수 있도록 설정하려면 외부 사용자 액세스를 지원하도록 하나 이상의 외부 액세스 정책도 구성해야 합니다. 자세한 내용은 조직에 대한 XMPP 페더리트 파트너 관리를 참조하세요. 특정 페더링 도메인에 대한 액세스를 제어하는 데 대한 자세한 내용은 개별 페더링 도메인의 액세스 제어를 참조합니다.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>제어판을 사용하여 보관 고지 조항 사용 또는 사용 안 하도록 설정

1. RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)인 사용자 계정에서 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.
    
2. 브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다. 
    
3. 왼쪽 탐색 모음에서 연결 및 외부 액세스를 클릭한 다음 **액세스 에지 구성을 클릭합니다.**
    
4. **액세스 에지 구성** 탭에서 **전역**, **편집**, **자세한 정보 표시** 를 차례로 클릭합니다.
    
5. 액세스 **에지** 구성 편집의 페더링 및 공용 **IM** 연결  사용에서 페더링 파트너에 대한 보관 고지 조항 보내기 확인란을 선택하거나 선택 취소하여 보관 고지 조항을 자동으로 보내거나 보내지 않도록 설정할 수 있습니다.
    
6. **커밋** 을 클릭합니다.
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>보관 고지 조항을 사용하여 보관 고지 Windows PowerShell

보관 고지 사항을 사용하도록 설정하려면 **EnableArchivingDisclaimer** 속성 값을 True($True)로 설정합니다.
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

보관 고지 사항을 사용하지 않도록 설정하려면 **EnableArchivingDisclaimer** 속성 값을 False($False)로 설정합니다.
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


