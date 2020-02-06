---
title: 비즈니스용 Skype 서버의 보관 옵션 관리
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
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: '요약: 비즈니스용 Skype 서버에 대 한 보관 옵션을 구성 하는 방법을 알아보세요.'
ms.openlocfilehash: af5c8f90cd49f556e1e787e5f550b54da1976c45
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818900"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 보관 옵션 관리

**요약:** 비즈니스용 Skype 서버용 보관 옵션을 구성 하는 방법에 대해 알아봅니다.
  
배포 후 처음으로 보관을 구성한 후에는 배포 후에 구성을 변경, 추가, 삭제할 수 있습니다. 보관 옵션에 따라 다음 중 어느 것이 선택 되는지 여부 
  
- 보관을 사용하거나 사용하지 않도록 설정
    
- IM 세션 보관
    
- 웹 회의 세션 보관
    
- 보관을 사용할 수 없는 경우 활동 차단
    
- Exchange 통합 사용
    
- 데이터 제거 및 내보내기 설정
    
다음과 같은 수준으로 구성 옵션을 지정할 수 있습니다.
  
- 비즈니스용 Skype 서버를 배포할 때 기본적으로 만들어지는 전역 수준 구성
    
- 특정 사이트에 대해 보관을 구현 하는 방법을 지정 하는 선택적 사이트 수준 구성
    
- 특정 풀에 대해 보관을 구현 하는 방법을 지정 하는 선택적 풀 수준 구성
    
사이트 구성 또는 풀 구성을 삭제할 수 있지만, 전역 구성은 삭제할 수 없습니다. 전역 구성을 삭제 하면 자동으로 기본 값으로 다시 설정 됩니다. 보관 구성을 구현 하는 방법과 보관 구성의 계층 구조에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 보관 계획](../../plan-your-deployment/archiving/archiving.md)을 참고 하세요.
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>제어판을 사용 하 여 보관 옵션 구성

다음과 같이 제어판을 사용 하 여 보관 옵션을 구성할 수 있습니다.
  
1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다. 
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
    
3. 왼쪽 탐색 모음에서 **보관 구성을**클릭 합니다.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 보관 옵션 구성

다음 표에 나열 된 Windows PowerShell cmdlet을 사용 하 여 보관 옵션을 구성할 수도 있습니다. 사용 가능한 모든 매개 변수를 포함 하 여 구문에 대 한 자세한 내용은 비즈니스용 [Skype Server Management Shell](../management-shell.md)을 참조 하세요.
  

|**은**|**설명**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |조직의 보관 구성 설정에 대 한 정보를 반환 합니다.  <br/> |
|새로운 CsArchivingConfiguration  <br/> |메신저 세션의 자동 저장을 사용 하거나 사용 하지 않도록 설정 하 고 보관할 수 없는 모든 인스턴트 메시지를 차단 하는 데 사용할 수 있는 메신저 (인스턴트 메시징)의 새 집합을 만듭니다.  <br/> |
|제거-CsArchivingConfiguration  <br/> |IM (인스턴트 메시징) 세션의 자동 저장을 사용 하거나 사용 하지 않도록 설정 하는 데 사용 되는 지정 된 보관 설정 컬렉션을 제거 하 고, 선택적으로 보관할 수 없는 인스턴트 메시지를 차단 합니다.  <br/> |
|Set-CsArchivingConfiguration  <br/> |기존 IM (인스턴트 메시징) 보관 구성 옵션의 컬렉션을 수정 합니다.  <br/> |
