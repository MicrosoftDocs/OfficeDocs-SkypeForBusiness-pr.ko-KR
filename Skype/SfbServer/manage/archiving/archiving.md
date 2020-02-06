---
title: 비즈니스용 Skype 서버에서 보관 관리
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
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: '요약: 비즈니스용 Skype 서버용 보관을 관리 하는 방법에 대해 알아보세요.'
ms.openlocfilehash: 46b0937a00f289ad5383d3bb1a4acf890bf48390
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819000"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 보관 관리

**요약:** 비즈니스용 Skype 서버용 보관을 관리 하는 방법에 대해 알아봅니다.
  
조직의 보관을 배포 하는 경우 배포 중에 초기 구성을 지정 합니다. 그러나 일 대 일 관리에 대 한 보관 지원을 구현 하는 방법이 나 조직의 새로운 요구 사항을 충족 하는 방법을 변경 해야 하는 경우도 있습니다. 예를 들어 특정 사이트, 특정 풀 또는 조직 내의 특정 사용자에 대해 보관 지원을 다르게 설정 해야 할 수 있습니다. 비즈니스용 Skype Server에 속한 사용자의 경우, 보관 구성 옵션 및 사용자 정책을 만들고 사용자 지정 하 여이 작업을 수행 합니다. 
  
이 항목을 읽기 전에 비즈니스용 [Skype 서버에서 보관을 계획](../../plan-your-deployment/archiving/archiving.md) 하 고 비즈니스용 [skype 서버용 보관을 배포](../../deploy/deploy-archiving/deploy-archiving.md)하는 방법에 대 한 정보를 숙지 해야 합니다.
  
> [!NOTE]
> 배포에 Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange 정책은 Exchange를 사용 하는 사용자에 대해 보관을 사용할 수 있는지 여부를 제어 하 고 사서함이 원본 위치 유지에 배치 되도록 합니다. 자세한 내용은 비즈니스용 [Skype 서버에서 보관 계획](../../plan-your-deployment/archiving/archiving.md) 및 비즈니스용 [skype 서버에 대 한 Exchange 저장소 통합 구성](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)을 참조 하세요. 
  
## <a name="archiving-configuration-options"></a>보관 구성 옵션

보관 구성 옵션 다음 중 선택 여부를 지정 합니다.
  
- 보관을 사용하거나 사용하지 않도록 설정
    
- IM 세션 보관
    
- 웹 회의 세션 보관
    
- 보관을 사용할 수 없는 경우 활동 차단
    
- Exchange 통합 사용
    
- 데이터 제거 및 내보내기 설정
    
이러한 옵션은 전역, 사이트 또는 풀 수준에서 설정할 수 있습니다. 자세한 내용은 비즈니스용 [Skype 서버의 보관 옵션 관리](options.md)를 참조 하세요.
  
## <a name="archiving-policies"></a>보관 정책

보관 정책은 다음을 보관할지 여부를 결정 합니다.
  
- 내부 통신
    
- 외부 통신
    
이러한 정책은 전역, 사이트 또는 사용자 수준에서 설정할 수 있습니다. 자세한 내용은 비즈니스용 [Skype 서버에서 보관 정책 관리](policies.md)를 참조 하세요.
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>제어판을 사용 하거나 Windows PowerShell을 사용 하 여 보관 관리

제어판을 사용 하거나 Windows PowerShell을 사용 하 여 보관을 관리할 수 있습니다. 다음 표에는 보관을 관리 하는 데 사용할 수 있는 cmdlet이 요약 되어 있습니다. 사용 가능한 모든 매개 변수를 포함 하 여 구문에 대 한 자세한 내용은 비즈니스용 [Skype Server Management Shell](../management-shell.md)을 참조 하세요. 


|**은**|**설명**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |비즈니스용 Skype 서버 보관 데이터베이스에 저장 된 레코드를 내보냅니다.  <br/> |
|Get-CsArchivingConfiguration  <br/> |조직의 보관 구성 설정에 대 한 정보를 반환 합니다.  <br/> |
|Get-CsArchivingPolicy  <br/> |내부 및 외부 통신을 위한 조직의 보관 정책에 대 한 정보를 반환 합니다.  <br/> |
|부여-CsArchivingPolicy  <br/> |사용자 또는 사용자 집합에 IM (인스턴트 메시징) 세션 보관 정책을 할당 합니다. 이러한 정책을 사용 하면 내부 사용자 간에 발생 하는 모든 IM 세션을 보관 하거나 내부 사용자와 외부 파트너 간에 발생 하는 모든 IM 세션을 보관할 수 있습니다.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |보관 데이터베이스에서 레코드를 수동으로 제거합니다.  <br/> |
|새로운 CsArchivingConfiguration  <br/> |메신저 세션의 자동 저장을 사용 하거나 사용 하지 않도록 설정 하 고 보관할 수 없는 모든 인스턴트 메시지를 차단 하는 데 사용할 수 있는 메신저 (인스턴트 메시징)의 새 집합을 만듭니다.  <br/> |
|New-CsArchivingPolicy  <br/> |새 IM (인스턴트 메시징) 세션 보관 정책을 만듭니다. 이러한 정책을 사용 하면 내부 사용자 간에 발생 하는 모든 IM 세션을 보관 하거나 내부 사용자와 외부 파트너 간에 발생 하는 모든 IM 세션을 보관할 수 있습니다.  <br/> |
|제거-CsArchivingConfiguration  <br/> |IM (인스턴트 메시징) 세션의 자동 저장을 사용 하거나 사용 하지 않도록 설정 하는 데 사용 되는 지정 된 보관 설정 컬렉션을 제거 하 고, 선택적으로 보관할 수 없는 인스턴트 메시지를 차단 합니다.  <br/> |
|Remove-CsArchivingPolicy  <br/> |비즈니스용 Skype 서버가 내부 사용자와 페더레이션 파트너 간에 발생 하는 모든 im 세션을 자동으로 저장 하는지 여부를 결정 하는 지정 된 IM (인스턴트 메시징) 보관 정책을 제거 합니다.  <br/> |
|Set-CsArchivingConfiguration  <br/> |기존 IM (인스턴트 메시징) 보관 구성 옵션의 컬렉션을 수정 합니다.  <br/> |
|Set-CsArchivingPolicy  <br/> |기존 IM (인스턴트 메시징) 보관 정책을 수정 합니다. 보관 정책을 통해 내부 사용자 간에 발생 하는 모든 IM 세션과 회의를 보관할 수 있습니다. 내부 사용자와 페더레이션 파트너 간에 발생 하는 세션만 보관할 수도 있습니다.  <br/> |
|Set-CsArchivingServer  <br/> |하나 이상의 보관 서버에 대 한 새 데이터베이스 위치를 지정할 수 있습니다.  <br/> |
   

