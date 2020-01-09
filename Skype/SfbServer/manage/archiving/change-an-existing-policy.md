---
title: 비즈니스용 Skype 서버에서 기존 보관 정책 변경
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: '요약: 비즈니스용 Skype 서버에 대 한 사용자 보관 정책을 변경 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 00f22b9afa5332bd7075b03823d321d35a0e4b8b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992775"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 기존 보관 정책 변경
 
**요약:** 비즈니스용 Skype 서버에 대 한 사용자 보관 정책을 변경 하는 방법에 대해 알아봅니다.
  
비즈니스용 Skype 서버를 처음 배포 하는 경우 배포의 사용자에 대해 보관을 구현 하는 방법을 결정 하는 초기 보관 정책을 설정 합니다. 이 항목에서는 정책을 관리 하 고 수정 하는 방법에 대해 설명 합니다. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>제어판을 사용 하 여 보관 정책 변경

1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다. 
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **보관 정책을**클릭 합니다.
    
4. 정책 목록에서 다음 중 하나를 수행 합니다. 
    
   - 전체 배포에 대 한 정책을 변경 하려면 정책 목록에서 **전역** 을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
   - 단일 사이트의 정책을 변경 하려면 정책 목록에서 사이트 이름을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
   - 단일 사용자 또는 사용자 그룹에 대 한 정책을 변경 하려면 정책 목록에서 사용자 또는 사용자 그룹 이름을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
5. **보관 정책 편집** 페이지에서 다음을 수행 합니다.
    
   - 정책에 대 한 내부 보관을 사용 하거나 사용 하지 않도록 설정 하려면 **내부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.
    
   - 정책에 대해 외부 보관을 사용 하거나 사용 하지 않도록 설정 하려면 **외부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.
    
6. **커밋**을 클릭합니다.
    
    > [!IMPORTANT]
    > 사용자 정책 설정은 정책을 적용 하는 특정 사용자 및 사용자 그룹에만 적용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버에서 사용자에 게 보관 정책 적용](apply-a-policy-to-users.md)을 참조 하세요. 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 보관 정책 변경

Windows PowerShell **CsArchivingPolicy** cmdlet을 사용 하 여 보관 정책을 변경할 수도 있습니다.
  
### <a name="enable-archiving-policies"></a>보관 정책 사용

내부 통신 세션 보관을 사용 하도록 설정 하려면 ArchiveInternal 매개 변수의 값을 True ($True)로 설정 합니다. 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

외부 통신 세션 보관을 사용 하도록 설정 하려면 ArchiveExternal 매개 변수의 값을 True ($True)로 설정 합니다. 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

내부 및 외부 통신 세션을 모두 보관할 수 있도록 하려면 ArchiveInternal 및 ArchiveExternal 매개 변수의 값을 모두 True로 설정 합니다. 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>보관 정책 사용 안 함

보관을 완전히 사용 하지 않도록 설정 하려면 ArchiveInternal 및 ArchiveExternal 매개 변수 값을 모두 False ($False)로 설정 합니다. 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
