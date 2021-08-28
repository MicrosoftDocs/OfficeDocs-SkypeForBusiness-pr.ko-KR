---
title: 보관 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
ROBOTS: NOINDEX, NOFOLLOW
description: 보관 구성을 사용하여 다음 옵션을 사용하도록 설정하고 사용하지 비즈니스용 Skype 서버 배포에 대한 보관 옵션을 제어할 수 있습니다.
ms.openlocfilehash: 08849f41248d78d28f2feb972bcedcde7a2cc768
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622860"
---
# <a name="archiving-configuration"></a>보관 구성
 
보관 구성을 사용하여 다음 옵션을 사용하도록 설정하고 사용하지 비즈니스용 Skype 서버 배포에 대한 보관 옵션을 제어할 수 있습니다.
  
- 보관에 실패할 경우 메신저 대화 또는 회의 세션 차단
    
- 저장소에 Exchange 사용자에 대한 통합 Exchange
    
- 보관된 데이터 삭제
    
보관 구성에는 전역 구성과 하나 이상의 사이트 및 풀 보관 구성(선택 사항)이 포함됩니다.
  
- **전역 구성** 전역 구성은 모든 전역 배포에서 비즈니스용 Skype 서버 생성됩니다. 전역 구성을 편집할 수는 있지만 이 보관 구성을 삭제할 수는 없습니다. 해당 구성을 삭제하려고 하면 모든 옵션이 기본값으로 다시 설정됩니다.
    
- **사이트 구성(선택 사항)** 하나 이상의 사이트 보관 구성을 지정할 수 있습니다. 각 구성은 특정 사이트에 대한 보관 옵션을 제어하도록 구성할 수 있습니다. 사이트 구성은 보관 사이트 구성에 지정된 사이트에 한해 전역 구성을 재정의합니다. 사이트 구성은 편집하거나 삭제할 수 있습니다.
    
- **풀 구성(선택 사항)** 하나 이상의 풀 보관 구성을 지정하여 특정 풀에 대한 보관 옵션을 제어할 수 있습니다. 풀 구성은 보관 풀 구성에 지정된 풀에 한해 전역 구성 및 사이트 구성을 재정의합니다. 풀 구성은 편집하거나 삭제할 수 있습니다.
    
> [!NOTE]
> 보관 구성은 비즈니스용 Skype 서버 있는 사용자에게 적용하고, Exchange 사용하여 Microsoft Exchange에 보관 데이터를 저장하는 경우 Exchange 에 있는 사용자에 대해 약간 다르게 구현됩니다Exchange. 다음 섹션에서 이러한 차이에 대해 설명합니다. 
  
**보관 구성** 페이지에는 배포에 대해 구성된 각 보관 정책이 나열됩니다. 또한 정책 이름, 범위(글로벌/사이트/풀) 및 각 보관 구성에 대해 사용하도록 설정된 보관 옵션도 표시됩니다. **보관 구성** 페이지에서는 다음 옵션이 제공됩니다.
- **새로 추가** 다음의 선택적 보관 구성 중 하나 이상을 추가할 수 있습니다.
    
  - 사이트 구성
    
  - 풀 구성
    
- **편집** 페이지에 나열된 보관 구성의 옵션을 변경할 수 있습니다. 이 옵션을 사용하여 다음을 할 수 있습니다.
    
  - **세부 정보 표시** 이 옵션을 선택하면 선택한 보관 구성에 대한 보관 옵션을 변경할 수 있는 대화 상자가 열립니다. 한 번의 보관 구성에 대한 세부 정보만 한 번만 표시될 수 있습니다.
    
  - **모두 선택** 이 옵션은 목록의 모든 보관 구성을 선택합니다.
    
  - **삭제** 이 옵션은 선택한 모든 보관 구성을 삭제합니다.
    
- **작업** 이 옵션을 사용하면 구성을 편집하는 대신 페이지에 나열된 모든 구성에서 IM 세션 또는 웹 회의 세션의 보관을 빠르게 설정하거나 사용하지 않도록 설정할 수 있습니다. 동작에서 사용할 수 있는 **옵션은** 현재 보관 구성에 지정된 옵션에 따라 다릅니다. 보관 구성에 현재 적용 중인 옵션을 제외한 모든 옵션을 사용할 수 있습니다. 옵션은 다음과 같습니다.
    
  - **IM 세션 보관**
    
  - **메신저 대화 및 웹 회의 세션 보관**
    
  - **보관 사용 안 함**
    
- **새로 고침** 보관 구성 페이지를 새로 **고쳐** 모든 보관 구성의 옵션 상태를 확인할 수 있습니다.
    
Exchange 통합을 비롯한 보관 기능에 대한 자세한 내용은 plan for [archiving in 비즈니스용 Skype 서버,](../../../plan-your-deployment/archiving/archiving.md)Deploy [archiving for 비즈니스용 Skype 서버](../../../deploy/deploy-archiving/deploy-archiving.md)및 [Manage archiving in 비즈니스용 Skype 서버.](../../../manage/archiving/archiving.md)

