---
title: 비즈니스용 Skype 서버에 대한 보관 정책 구성
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
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: '요약: 이 항목을 읽고 비즈니스용 Skype 서버 사용자에 대한 초기 보관 정책을 구성하는 방법을 배워야 합니다.'
ms.openlocfilehash: ab737305561aa20c873bbce6e0f075d17fedd0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820858"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대한 보관 정책 구성
 
**요약:** 이 항목을 읽고 비즈니스용 Skype 서버 사용자에 대한 초기 보관 정책을 구성하는 방법을 배워야 합니다.
  
비즈니스용 Skype 서버에서는 정책을 사용하여 비즈니스용 Skype 서버에 있는 사용자의 내부 통신 및 외부 통신에 대해 보관을 사용하고 사용하지 않도록 설정할 수 있습니다. 여기에는 다음이 포함됩니다.
  
- 비즈니스용 Skype 서버를 배포할 때 기본적으로 만들어지기 위한 글로벌 정책
    
- 특정 사이트에 대해 보관을 구현하는 방법을 지정하는 선택적 사이트 수준 정책
    
- 특정 사용자에 대해 보관을 구현하는 방법을 지정하는 선택적 사용자 수준 정책
    
보관을 배포할 때 처음에는 보관 정책을 설정했지만 배포 후에 정책을 변경, 추가 및 삭제할 수 있습니다. 비즈니스용 Skype 서버 제어판에서는 보관  및 모니터링 그룹의  보관 정책 페이지를 사용하여 전역, 사이트 및 사용자 수준에서 정책을 관리할 수 있습니다.
  
> [!NOTE]
> 보관 구현을 제어하려면 IM 또는 회의 보관 여부, 중요 모드 사용, 삭제 옵션 등의 옵션을 지정해야 합니다. 기본적으로 전역 보관 구성 또는 사이트 또는 풀 보관 구성에서는 옵션이 사용되지 않습니다. 내부 또는 외부 통신에 대해 보관을 사용하도록 설정하기 전에 적절한 모든 옵션을 지정해야 합니다. 자세한 내용은 비즈니스용 Skype 서버에 대한 보관 옵션 [구성을 참조하세요.](configure-archiving-options.md) 
  
> [!NOTE]
> 배포에 대해 Microsoft Exchange 통합을 사용하도록 설정하면 Exchange In-Place 보류 정책은 Exchange에 있으며 사서함을 보류된 사용자에 대해 보관을 사용할지 여부를 In-Place 제어합니다. 
  
전역, 사이트 및 사용자 정책의 계층 구조를 포함하여 보관 정책의 작동 방식에 대한 자세한 내용은 비즈니스용 Skype 서버의 보관 [계획(Plan for archiving)을 참조하세요.](../../plan-your-deployment/archiving/archiving.md) 배포 후 정책을 관리하는 방법에 대한 자세한 내용은 비즈니스용 Skype 서버에서 보관 정책 [관리를 참조하세요.](../../manage/archiving/policies.md)
  
## <a name="global-policy"></a>글로벌 정책

프런트 엔드 서버를 배포하면 비즈니스용 Skype 서버가 보관에 대한 전역 정책을 만듭니다. 기본적으로 보관은 전역 정책에서 사용하지 않도록 설정됩니다. 글로벌 정책은 전역 정책을 다시 설정하는 사이트 또는 사용자 정책을 설정하지 않는 한 또는 일부 또는 모든 사용자에 대해 Microsoft Exchange 통합을 사용하는 경우를 사용하지 않는 한 전체 배포에 대한 내부 및 외부 통신에 보관을 사용할지 여부를 제어합니다. Microsoft Exchange 통합을 사용하는 경우 Exchange에 있으며 사서함이 보류된 사용자에게는 글로벌 정책이 In-Place 않습니다.
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>비즈니스용 Skype 서버 보관 데이터베이스에 대한 보관에 대한 글로벌 정책 구성

1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다. 
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 정책** 을 클릭합니다.
    
4. **보관 정책** 페이지에서 **전역** 을 클릭하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.
    
5. **보관 정책 편집 - 전역** 에서 다음을 수행합니다.
    
   - **이름** 에서 기본 이름으로 "전역"을 사용하지 않으려는 경우 글로벌 정책에 대해 새 이름을 지정합니다. 
    
   - **설명에서** 정책에 대한 정보를 제공합니다(예: *divisionName에* 대한 글로벌 정책).
    
   - 사이트 정책 또는 사용자 정책을 통해 제어되지 않는 모든 사이트 및 사용자에 대한 내부 통신 보관을 제어하려면 **내부 통신 보관** 확인란을 선택하거나 선택을 취소합니다.
    
   - 사이트 정책 또는 사용자 정책을 통해 제어되지 않는 모든 사이트 및 사용자에 대한 외부 통신 보관을 제어하려면 **외부 통신 보관** 확인란을 선택하거나 선택을 취소합니다.
    
6. **커밋** 을 클릭합니다.
    
## <a name="site-policies"></a>사이트 정책

이러한 각 사이트에 대해 보관 정책을 만들어 특정 사이트에 대해 보관을 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다. 사이트 정책은 전역 정책에 적용되지만 사용자 정책은 사이트 정책에 대해 적용됩니다. 보관 정책은 Microsoft Exchange 통합을 사용하지 않는 경우 또는 Microsoft Exchange 통합을 사용하지 않지만 Exchange에 있지 않은 일부 사용자가 사서함을 In-Place 적용합니다.
  
### <a name="create-an-archiving-policy-for-a-site"></a>사이트에 대한 보관 정책 만들기

1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 정책** 을 클릭합니다.
    
    전역, 사이트 및 사용자 정책의 계층 구조를 포함하여 보관 정책의 작동 방식에 대한 자세한 내용은 비즈니스용 Skype 서버의 보관 [계획(Plan for archiving)을 참조하세요.](../../plan-your-deployment/archiving/archiving.md)
    
4. **새로 만들기** 를 클릭하고 **사이트 정책** 을 클릭합니다.
    
5. 사이트 **선택에서** 정책을 적용할 사이트를 클릭합니다.
    
6. **새 보관 정책** 에서 다음을 수행합니다.
    
   - **이름에서** 사이트 정책의 이름을 지정합니다. 
    
   - **설명에서** 사이트 정책에 대한 정보를 제공합니다(예: Redmond의 사이트 정책).
    
   - 지정된 사이트에 대한 내부 통신 보관을 제어하려면 내부 통신 보관 확인란을 선택하거나 **선택을** 취소합니다.
    
   - 지정된 사이트에 대한 외부 통신 보관을 제어하려면 외부 통신 보관 **확인란을** 선택하거나 선택을 취소합니다.
    
7. **커밋** 을 클릭합니다.
    
## <a name="user-policies"></a>사용자 정책

사용자에 대한 보관 정책을 만들고 구성한 다음 특정 사용자 또는 사용자 그룹에 정책을 적용하여 특정 사용자에 대해 보관을 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다. 사용자 정책은 글로벌 정책 또는 사이트 정책을 재정의합니다. 보관 정책은 Microsoft Exchange 통합을 사용하지 않는 경우 또는 Microsoft Exchange 통합을 사용하지 않지만 Exchange에 있지 않은 일부 사용자가 사서함을 In-Place 적용합니다.
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>비즈니스용 Skype 서버에 있는 사용자에 대한 보관 정책 구성

1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다. 
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 정책** 을 클릭합니다.
    
4. **새로 만들기** 를 클릭하고 **사용자 정책** 을 클릭합니다.
    
5. **새 보관 정책** 에서 다음을 수행합니다.
    
   - **이름** 에 사용자 정책의 이름을 지정합니다. 
    
   - **설명** 에서 사용자 정책에 대한 정보를 입력합니다(예: 법률 부서용 사용자 정책).
    
   - 사용자 정책에 대한 내부 통신 보관을 제어하려면 **내부 통신 보관** 확인란을 선택하거나 선택을 취소합니다.
    
   - 사용자 정책에 대한 외부 통신 보관을 제어하려면 **외부 통신 보관** 확인란을 선택하거나 선택을 취소합니다.
    
6. **커밋** 을 클릭합니다.
    
사용자 정책은 해당 정책을 지정한 사용자에게만 적용됩니다.
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>사용자에게 비즈니스용 Skype 서버 보관 정책 적용

1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다. 
    
3. 왼쪽 탐색 모음에서 **사용자** 를 클릭하고 구성하려는 사용자 계정을 검색합니다.
    
4. 검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.
    
5. 보관 **정책에서 비즈니스용 Skype 서버** 사용자 편집에서 적용할 보관 사용자 정책을 선택합니다. 
    
    > [!NOTE]
    > 이 **\<Automatic\>** 설정은 기본 서버 설치 설정을 적용합니다. 이러한 설정은 서버에 의해 자동으로 적용됩니다.
  
6. **커밋** 을 클릭합니다.
    

