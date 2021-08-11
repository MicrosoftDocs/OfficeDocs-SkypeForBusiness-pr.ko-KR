---
title: 사용자에 대한 보관 정책 비즈니스용 Skype 서버
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
description: '요약: 이 항목을 통해 사용자에 대해 초기 보관 정책을 구성하는 비즈니스용 Skype 서버 있습니다.'
ms.openlocfilehash: 9db20eefd26de31eb01ab25d4ef7596319459b68be3f76ce95ba0b355122eee8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312126"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>사용자에 대한 보관 정책 비즈니스용 Skype 서버
 
**요약:** 이 항목을 통해 사용자에 대한 초기 보관 정책을 구성하는 비즈니스용 Skype 서버 있습니다.
  
이 비즈니스용 Skype 서버 정책을 사용하여 사용자에 대해 내부 통신 및 외부 통신에 대해 보관을 사용하도록 설정하고 사용하지 않도록 비즈니스용 Skype 서버. 여기에는 다음이 포함됩니다.
  
- 전역 정책을 배포할 때 기본적으로 비즈니스용 Skype 서버
    
- 특정 사이트에 대해 보관을 구현하는 방법을 지정하는 선택적 사이트 수준 정책
    
- 특정 사용자에 대해 보관을 구현하는 방법을 지정하는 선택적 사용자 수준 정책
    
보관을 배포할 때 처음에는 보관 정책을 설정했지만 배포 후 정책을 변경, 추가 및 삭제할 수 있습니다. 비즈니스용 Skype 서버 제어판에서 보관 및 모니터링  그룹의 보관 정책 페이지를  사용하여 전역, 사이트 및 사용자 수준에서 정책을 관리할 수 있습니다.
  
> [!NOTE]
> 보관 구현을 제어하려면 IM 또는 회의 보관 여부, 중요 모드 사용, 삭제 옵션 등의 옵션을 지정해야 합니다. 기본적으로 전역 보관 구성 또는 모든 사이트 또는 풀 보관 구성에서는 옵션이 사용되지 않습니다. 내부 또는 외부 통신에 대해 보관을 사용하도록 설정하기 전에 적절한 모든 옵션을 지정해야 합니다. 자세한 내용은 [Configure archiving options for 비즈니스용 Skype 서버.](configure-archiving-options.md) 
  
> [!NOTE]
> 배포에 대해 Microsoft Exchange 통합을 사용하도록 설정하면 Exchange In-Place 보류 정책은 Exchange 사서함을 보류로 설정한 사용자에 대해 보관을 사용할지 여부를 In-Place 제어합니다. 
  
전역, 사이트 및 사용자 정책의 계층 구조를 포함하여 보관 정책의 작동 방식에 대한 자세한 내용은 [Plan for archiving in 비즈니스용 Skype 서버.](../../plan-your-deployment/archiving/archiving.md) 배포 후 정책을 관리하는 방법에 대한 자세한 내용은 [Manage archiving policies in 비즈니스용 Skype 서버.](../../manage/archiving/policies.md)
  
## <a name="global-policy"></a>글로벌 정책

프런트 엔드 서버를 배포할 때 비즈니스용 Skype 서버 대한 전역 정책을 만듭니다. 기본적으로 보관은 전역 정책에서 사용하지 않도록 설정됩니다. 글로벌 정책은 전역 정책을 다시 구성하는 사이트 또는 사용자 정책을 설정하거나 일부 또는 모든 사용자에 대해 Microsoft Exchange 통합을 사용하는 경우를 전적으로 배포에 대한 내부 및 외부 통신에 보관을 사용할지 여부를 제어합니다. Microsoft Exchange 통합을 사용하는 경우 전역 정책은 Exchange 사서함을 보류로 설정한 In-Place 않습니다.
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>보관 데이터베이스에 대한 보관에 비즈니스용 Skype 서버 정책 구성

1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 정책** 을 클릭합니다.
    
4. **보관 정책** 페이지에서 **전역** 을 클릭하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.
    
5. **보관 정책 편집 - 전역** 에서 다음을 수행합니다.
    
   - **이름** 에서 기본 이름으로 "전역"을 사용하지 않으려는 경우 글로벌 정책에 대해 새 이름을 지정합니다. 
    
   - **설명에서** 정책에 대한 정보를 제공합니다(예: *divisionName에* 대한 글로벌 정책).
    
   - 사이트 정책 또는 사용자 정책을 통해 제어되지 않는 모든 사이트 및 사용자에 대한 내부 통신 보관을 제어하려면 **내부 통신 보관** 확인란을 선택하거나 선택을 취소합니다.
    
   - 사이트 정책 또는 사용자 정책을 통해 제어되지 않는 모든 사이트 및 사용자에 대한 외부 통신 보관을 제어하려면 **외부 통신 보관** 확인란을 선택하거나 선택을 취소합니다.
    
6. **커밋** 을 클릭합니다.
    
## <a name="site-policies"></a>사이트 정책

이러한 각 사이트에 대해 보관 정책을 만들어 특정 사이트에 대해 보관을 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다. 사이트 정책은 글로벌 정책에 적용되지만 사용자 정책은 사이트 정책에 대해 의구정합니다. 보관 정책은 Microsoft Exchange 통합을 사용하지 않는 경우 또는 Microsoft Exchange 통합을 사용하지 않지만 일부 사용자가 Exchange 사서함을 보류로 설정한 In-Place 적용됩니다.
  
### <a name="create-an-archiving-policy-for-a-site"></a>사이트에 대한 보관 정책 만들기

1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 정책** 을 클릭합니다.
    
    전역, 사이트 및 사용자 정책의 계층 구조를 포함하여 보관 정책의 작동 방식에 대한 자세한 내용은 [Plan for archiving in 비즈니스용 Skype 서버.](../../plan-your-deployment/archiving/archiving.md)
    
4. **새로 만들기** 를 클릭하고 **사이트 정책** 을 클릭합니다.
    
5. 사이트 **선택에서** 정책을 적용할 사이트를 클릭합니다.
    
6. **새 보관 정책** 에서 다음을 수행합니다.
    
   - **이름에서** 사이트 정책의 이름을 지정합니다. 
    
   - **설명에서** 사이트 정책에 대한 정보를 제공합니다(예: Redmond의 사이트 정책).
    
   - 지정된 사이트에 대한 내부 통신 보관을 제어하려면 내부 통신 보관 확인란을 선택하거나 **선택을** 취소합니다.
    
   - 지정된 사이트에 대한 외부 통신 보관을 제어하려면 외부 통신 보관 확인란을 선택하거나 **선택을** 취소합니다.
    
7. **커밋** 을 클릭합니다.
    
## <a name="user-policies"></a>사용자 정책

사용자에 대한 보관 정책을 만들고 구성한 다음 특정 사용자 또는 사용자 그룹에 정책을 적용하여 특정 사용자에 대해 보관을 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다. 사용자 정책은 글로벌 정책 또는 사이트 정책을 재정의합니다. 보관 정책은 Microsoft Exchange 통합을 사용하지 않는 경우 또는 Microsoft Exchange 통합을 사용하지 않지만 일부 사용자가 Exchange 사서함을 보류로 설정한 In-Place 적용됩니다.
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>보관에 있는 사용자에 대해 보관 정책을 비즈니스용 Skype 서버

1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 
    
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
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 
    
3. 왼쪽 탐색 모음에서 **사용자** 를 클릭하고 구성하려는 사용자 계정을 검색합니다.
    
4. 검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.
    
5. 보관 **비즈니스용 Skype 서버** 사용자 편집에서 적용할 보관 사용자 정책을 선택합니다.
    
    > [!NOTE]
    > 이 **\<Automatic\>** 설정은 기본 서버 설치 설정을 적용합니다. 이러한 설정은 서버에 의해 자동으로 적용됩니다.
  
6. **커밋** 을 클릭합니다.
    

