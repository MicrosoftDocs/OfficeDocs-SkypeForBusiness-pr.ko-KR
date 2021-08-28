---
title: 보관 구성 새로 만들기 또는 기존 기능 편집
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 49096960-c442-4846-be8f-03c167acea41
ROBOTS: NOINDEX, NOFOLLOW
description: 보관 구성을 사용하여 배포에 대한 보관 옵션을 제어합니다. 보관 구성에는 전역 구성과 하나 이상의 사이트 및 풀 구성(선택 사항)이 포함됩니다.
ms.openlocfilehash: 01c14b482fb546a83d9cff8bdbbfd75f8f81f1bd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597732"
---
# <a name="archiving-configuration-create-new-or-edit-existing"></a>보관 구성: 새로 만들기 또는 기존 항목 편집
 
보관 구성을 사용하여 배포에 대한 보관 옵션을 제어합니다. 보관 구성에는 전역 구성과 하나 이상의 사이트 및 풀 구성(선택 사항)이 포함됩니다.
  
- **전역 구성** 전역 구성은 기본적으로 만들어집니다. 전역 구성을 편집할 수는 있지만 이 보관 구성을 삭제할 수는 없습니다. 해당 구성을 삭제하려고 하면 모든 옵션이 기본값으로 다시 설정됩니다.
    
- **사이트 구성(선택 사항)** 하나 이상의 사이트 보관 구성을 지정할 수 있습니다. 각 구성은 특정 사이트에 대한 보관 옵션을 제어하도록 구성할 수 있습니다. 사이트 구성은 보관 사이트 구성에 지정된 사이트에 한해 전역 구성을 재정의합니다. 사이트 구성은 편집하거나 삭제할 수 있습니다.
    
- **풀 구성(선택 사항)** 하나 이상의 풀 보관 구성을 지정하여 특정 풀에 대한 보관 옵션을 제어할 수 있습니다. 풀 구성은 보관 풀 구성에 지정된 풀에 한해 전역 구성 및 사이트 구성을 재정의합니다. 풀 구성은 편집하거나 삭제할 수 있습니다.
    
> [!NOTE]
> 보관 구성은 비즈니스용 Skype 서버 있는 사용자에게 적용될 수 있으며, Microsoft Exchange 통합 옵션을 사용하여 microsoft Exchange에 보관 데이터를 저장하도록 설정하는 경우 Exchange 에 있는 사용자에게는 Exchange. 그러나 일부 옵션은 다음 섹션에 설명된 Exchange 사용자에 대해 약간 다르게 구현됩니다. 
  
새 보관 구성 또는 기존 보관 구성의 설정을 구성하려면 다음 옵션을 지정합니다.
- **이름** 각 보관 구성에는 이름이 필요합니다. 이름은 추가 또는 편집할 구성 유형에 따라 결정됩니다.
    
  - **전역 구성** 기본 이름은 Global입니다. 예를 들면 'Contoso 북미 조직'과 같은 이름을 사용할 수 있습니다.
    
  - **사이트 구성** 목록에는 배포에서 사용 가능한 사이트가 포함되어 있습니다. 사이트 하나를 클릭하여 선택합니다. 예를 들면 'Redmond 데이터 센터'와 같습니다.
    
  - **풀 구성** 적절한 이름을 지정합니다. 이 이름은 배포의 특정 프런트 엔드 풀 또는 Standard Edition 서버의 이름일 수 있습니다. 예를 들면 '마케팅 부문'과 같습니다.
    
- **설명** 이는 선택 사항입니다. 구성의 범위 또는 사용과 같은 추가 세부 정보를 제공하는 데 사용할 수 있습니다. 예를 들어 다른 사이트의 법률 부서와 조정합니다.
    
- **보관 설정** 옵션은 다음과 같습니다.
    
  - **IM 세션 보관**
    
  - **메신저 대화 및 웹 회의 세션 보관**
    
  - **보관 사용 안 함**
    
- **보관에 실패할** 경우 IM(인스턴트 메시징) 또는 웹 회의 세션 차단 오류에는 다음이 포함됩니다.
    
  - **IM** 저장소 서비스에 문제가 있는 경우 전체 데이터베이스가 오류일 수 있습니다. 이 경우 보관을 사용하도록 설정된 사용자의 IM이 차단됩니다.
    
  - **회의** 파일 공유를 사용할 수 없거나 저장소 서비스에 문제가 있을 수 있습니다. 이 경우 오류 시점에 풀에 호스팅된 모든 활성 회의가 제한 모드로 전환되고 새로운 회의를 활성화할 수 없습니다.
    
    오류가 수정된 다음에는 IM 및 회의 모두 자동으로 복구됩니다.
    
- **Microsoft Exchange 통합** 사용자가 현재 사용 중이면 이 옵션을 Exchange. 이 옵션을 Exchange 사서함이 보류된 경우 해당 사용자에 대한 데이터를 저장하는 In-Place 사용됩니다. 모든 사용자가 Exchange 경우 보관 데이터 저장을 위해 별도의 SQL Server 데이터베이스를 설정할 필요가 없습니다.
    
- **보관 데이터** 제거 사용 지우기를 사용하도록 설정하고 다음과 같은 제거 옵션을 지정하려면 이 옵션을 선택합니다.
    
  - 지정한 특정 기간(일) 후 삭제
    
  - 보관 데이터를 내보냈을 때 삭제(Microsoft Exchange 통합을 사용하도록 설정한 경우 Exchange 데이터를 포함합니다.
    
    > [!NOTE]
    > Microsoft Exchange 통합을 사용하도록 설정하면 Exchange 및 사서함이 In-Place 사용자에 대한 제거는 Exchange. 유일한 예외는 Lync Server 파일 공유에 저장되는 회의 파일에 대한 것입니다. 이러한 파일은 보관 데이터를 내보낸 후 데이터를 삭제하는 옵션을 선택하는 경우에는 파일을 내보내 해당 파일이 Exchange에 업로드된 후에, 그리고 최대 보존 기간(일)을 지정하는 경우에는 지정된 최대 기간(일) 후에 파일 공유에서 삭제됩니다. 
  
Exchange 통합을 비롯한 보관 기능에 대한 자세한 내용은 plan for [archiving in 비즈니스용 Skype 서버,](../../../plan-your-deployment/archiving/archiving.md)Deploy [archiving for 비즈니스용 Skype 서버](../../../deploy/deploy-archiving/deploy-archiving.md)및 [Manage archiving in 비즈니스용 Skype 서버.](../../../manage/archiving/archiving.md)

