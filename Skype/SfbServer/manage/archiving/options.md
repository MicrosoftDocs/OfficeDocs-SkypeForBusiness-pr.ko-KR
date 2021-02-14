---
title: 비즈니스용 Skype 서버에서 보관 옵션 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: '요약: 비즈니스용 Skype 서버의 보관 옵션을 구성하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: ee0145ac0896e1bbb8d18c6a51116f2ddd75ee05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817538"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 보관 옵션 관리

**요약:** 비즈니스용 Skype 서버에 대한 보관 옵션을 구성하는 방법을 자세히 알아보고,
  
처음에는 배포 시 보관을 구성하지만 배포 후 구성을 변경, 추가 및 삭제할 수 있습니다. 보관 옵션에 따라 다음을 할지 여부가 결정됩니다. 
  
- 보관을 활성화 또는 비활성화
    
- IM 세션 보관
    
- 웹 회의 세션 보관
    
- 보관을 사용할 수 없는 경우 활동 차단
    
- Exchange 통합 사용
    
- 데이터 제거 및 내보내기 설정
    
다음 수준에서 구성 옵션을 지정할 수 있습니다.
  
- 비즈니스용 Skype 서버를 배포할 때 기본적으로 생성되는 전역 수준 구성
    
- 특정 사이트에 대해 보관을 구현하는 방법을 지정하는 선택적 사이트 수준 구성
    
- 특정 풀에 대해 보관을 구현하는 방법을 지정하는 선택적 풀 수준 구성
    
사이트 구성 또는 풀 구성은 삭제할 수 있지만 전역 구성은 삭제할 수 없습니다. 전역 구성을 삭제하는 경우 자동으로 구성이 기본값으로 다시 설정됩니다. 보관 구성을 구현하는 방법 및 보관 구성의 계층 구조에 대한 자세한 내용은 비즈니스용 Skype 서버의 보관 [계획(Plan for archiving)을 참조하세요.](../../plan-your-deployment/archiving/archiving.md)
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>제어판을 사용하여 보관 옵션 구성

다음과 같이 제어판을 사용하여 보관 옵션을 구성할 수 있습니다.
  
1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다. 
    
2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다. 
    
3. 왼쪽 탐색 모음에서 보관 **구성을 클릭합니다.**
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>보관 옵션을 구성하는 방법을 Windows PowerShell

또한 다음 표에 나열된 Windows PowerShell cmdlet을 사용하여 보관 옵션을 구성할 수 있습니다. 사용 가능한 모든 매개 변수를 포함하여 구문에 대한 자세한 내용은 [비즈니스용 Skype 서버 관리 셸을 참조하세요.](../management-shell.md)
  

|**Cmdlet**|**설명**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |조직의 보관 구성 설정에 대한 정보를 반환합니다.  <br/> |
|New-CsArchivingConfiguration  <br/> |메신저 세션 자동 저장을 활성화 또는 사용하지 않도록 설정하고 보관할 수 없는 인스턴트 메시지를 차단하는 데 사용할 수 있는 새 IM(인스턴트 메시징) 설정 집합을 만듭니다.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |IM(인스턴트 메시징) 세션의 자동 저장을 활성화 또는 사용하지 않도록 설정하고 보관할 수 없는 인스턴트 메시지를 선택적으로 차단하는 데 사용되는 보관 설정의 지정된 컬렉션을 제거합니다.  <br/> |
|Set-CsArchivingConfiguration  <br/> |IM(인스턴트 메시징) 보관 구성 옵션의 기존 컬렉션을 수정합니다.  <br/> |
