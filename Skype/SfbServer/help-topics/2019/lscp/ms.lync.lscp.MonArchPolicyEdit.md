---
title: 보관 정책 새로 만들기 또는 기존 데이터 편집
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a4f948e7-e8f6-449a-8907-f61c5b143c05
ROBOTS: NOINDEX, NOFOLLOW
description: 보관 정책을 사용하여 배포에 있는 사용자에 대한 내부 및 외부 통신 보관을 비즈니스용 Skype 서버. 보관 정책에는 글로벌 정책과 하나 이상의 사이트 및 사용자 정책(선택 사항)이 포함됩니다.
ms.openlocfilehash: 93cd0f65c9ecfb2667b9c66a99baff974d01166cab4e7fd9880af5d00ededac2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279276"
---
# <a name="archiving-policy-create-new-or-edit-existing"></a>보관 정책: 새로 만들기 또는 기존 항목 편집
 
보관 정책을 사용하여 배포에 있는 사용자에 대한 내부 및 외부 통신 보관을 비즈니스용 Skype 서버. 보관 정책에는 글로벌 정책과 하나 이상의 사이트 및 사용자 정책(선택 사항)이 포함됩니다.
  
- **글로벌 정책** 전역 정책은 모든 전역 배포에서 비즈니스용 Skype 서버 생성됩니다. 글로벌 정책을 편집할 수는 있지만 이 정책을 삭제할 수는 없습니다. 해당 정책을 삭제하려고 하면 모든 옵션이 기본값으로 다시 설정됩니다.
    
- **사이트 정책(선택 사항)** 하나 이상의 사이트 보관 정책을 지정할 수 있으며, 각 정책은 특정 사이트에 대한 내부 또는 외부 통신 보관을 사용하도록 설정하고 사용하지 않도록 구성할 수 있습니다. 사이트 정책은 보관 정책에 지정된 사이트에 한해 글로벌 정책을 재정의합니다. 사이트 정책은 편집하거나 삭제할 수 있습니다.
    
- **사용자 정책(선택 사항)** 하나 이상의 사용자 보관 정책을 지정할 수 있으며, 각 정책은 특정 사용자에 대한 내부 또는 외부 통신에 대해 보관을 사용하도록 설정하고 사용하지 않도록 구성할 수 있습니다. 사용자 정책은 사용자 정책을 할당하는 사용자에 한해 글로벌 정책 및 사이트 정책을 재정의합니다. 사용자 정책은 편집하거나 삭제할 수 있습니다.
    
> [!NOTE]
> Microsoft Exchange 통합을 사용하여 Microsoft Exchange 보관 데이터를 저장하는 경우 Exchange 정책이 사용자에 대한 보관을 Exchange. 이러한 사용자에 대해 보관을 사용하도록 설정하려면 사용자의 사서함이 보류된 In-Place 합니다. 
  
새 보관 정책 또는 기존 보관 정책의 설정을 구성하려면 다음 옵션을 지정합니다.
- **이름** 각 보관 정책에는 이름이 필요합니다. 이름은 추가 또는 편집하는 정책 유형에 따라 결정됩니다.
    
  - **글로벌 정책** 기본 이름은 Global입니다. 보다 설명적인 이름으로 변경할 수 있습니다. 예를 들면 'Contoso 북미 조직'과 같은 이름을 사용할 수 있습니다.
    
  - **사이트 정책** 이 대화 상자에 나열된 사이트에는 배포에서 사용 가능한 모든 사이트가 포함됩니다. 사이트 하나를 클릭하여 선택합니다. 예를 들면 'Redmond 데이터 센터'와 같습니다.
    
  - **사용자 정책** 특정 사용자의 이름이나 조직에 있는 사용자 그룹 또는 팀의 이름과 같은 적절한 이름을 지정합니다. 예를 들어 '법률 부서'와 같이 지정할 수 있습니다.
    
- **설명** 이는 선택 사항입니다. 정책의 범위 또는 사용과 같은 추가 세부 정보를 제공하는 데 사용할 수 있습니다. 예를 들어 다른 사이트의 법률 부서와 조정합니다.
    
- **내부 통신 보관** 내부 네트워크에 통신 보관을 사용하도록 설정하려면 이 확인란을 선택합니다. 기본적으로 이 설정은 모든 정책에서 사용하도록 설정되지 않습니다.
    
- **외부 통신 보관** 원격 사용자(익명 및 PIC 설정 사용자 포함) 및 페더링 파트너와 같은 외부 사용자를 포함한 통신을 보관할 수 있도록 설정하려면 이 확인란을 선택합니다. 기본적으로 이 설정은 모든 정책에서 사용하도록 설정되지 않습니다.
    
Exchange 통합을 비롯한 보관 기능에 대한 자세한 내용은 plan for [archiving in 비즈니스용 Skype 서버,](../../../plan-your-deployment/archiving/archiving.md)Deploy [archiving for 비즈니스용 Skype 서버](../../../deploy/deploy-archiving/deploy-archiving.md)및 [Manage archiving in 비즈니스용 Skype 서버.](../../../manage/archiving/archiving.md)

