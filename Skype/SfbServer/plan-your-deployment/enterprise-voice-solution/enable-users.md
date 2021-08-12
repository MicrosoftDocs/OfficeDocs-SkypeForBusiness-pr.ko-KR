---
title: 사용자가 E9-1-1을 사용할 수 있도록 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: 사용하도록 설정할 사용자와 로밍 사용자를 지원하는 방법을 포함하여 비즈니스용 Skype 서버 Enterprise Voice E9-1-1 배포의 위치 정책에 필요한 결정
ms.openlocfilehash: b848359cb6a4324ab93804718d9416074f2af942c236d71c7b8e0de6abac4c05
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54328013"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>사용자가 E9-1-1을 사용할 수 있도록 비즈니스용 Skype 서버
 
사용하도록 설정할 사용자와 로밍 사용자를 지원하는 방법을 포함하여 비즈니스용 Skype 서버 Enterprise Voice E9-1-1 배포의 위치 정책에 필요한 결정
  
클라이언트 등록 비즈니스용 Skype 서버 위치 정책을 사용하여 Enterprise Voice 사용자에 대해 E9-1-1 속성을 구성합니다. 이 정책에는 E9-1-1 구현 방법을 정의하는 설정이 포함됩니다. 예를 들어 위치 정책에는 긴급 전화 문자열과 같은 정보가 포함되어 있으며, 위치 정보 서비스에서 자동으로 위치를 제공하지 않는 경우 사용자가 위치를 수동으로 입력해야 하는지 여부가 포함되어 있습니다. 위치 정책의 전체 정의는 [Plan location policies for 비즈니스용 Skype 서버.](location-policies.md)
  
비즈니스용 Skype 서버 서브넷을 기반으로 클라이언트 또는 전역, 사이트당 또는 사용자 기준 정책에 따라 사용자에게 위치 정책을 할당할 수 있습니다. 사용자를 설정하는 방법을 결정하기 위해서는 먼저 다음과 같은 질문을 확인해야 합니다.
  
 **모든 사용자를 설정하시겠습니까? 아니면 해당 기업의 특정 영역으로만 지원을 제한하시겠습니까?**
  
> 전역 위치 정책을 사용하여 기업 내 모든 사용자에게 위치를 지정할 수 있습니다. 그러나 비즈니스용 Skype 서버 네트워크 사이트에 위치 정책을 할당한 다음 사이트에 서브넷을 추가하면 E9-1-1 지원을 엔터프라이즈 내의 선택한 위치로 제한하고 사이트 기준에 따라 E9-1-1 라우팅 동작을 지정할 수 있습니다. 
    
 **사용자 정책을 통해 개별 사용자를 설정할 계획이 있습니까?**
  
> E9-1-1 지원을 사용자 지정하려는 경우 특정 사용자 또는 공통 영역 전화 연락처 개체에 직접 위치 정책을 지정할 수 있습니다.
    
 **클라이언트가 네트워크 외부에서 로밍하거나 정의되지 않은 서브넷에서 연결할 경우에도 해당 클라이언트에 대해 E9-1-1을 설정해야 합니까?**
  
> 사용자에게 전역, 사이트 또는 사용자당 위치 정책이 할당된 경우 클라이언트가 정의된 서브넷 내에 있지 않은 경우 또는 위치 정보 서비스에서 위치를 찾을 수 없는 경우 클라이언트에 위치를 수동으로 입력해야 할 수 있습니다. 자세한 내용은 [Define the user experience for manually acquiring a location in 비즈니스용 Skype 서버.](manually-acquiring-a-location.md)
    

