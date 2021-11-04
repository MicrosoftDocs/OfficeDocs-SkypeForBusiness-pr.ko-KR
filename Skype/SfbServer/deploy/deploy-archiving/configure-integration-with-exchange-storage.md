---
title: 사용자용 Exchange 저장소와의 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: '요약: 이 항목을 통해 Exchange 저장소와의 통합을 구성하는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: 3ac2db718057b47ebe214c29e339b94dbc5e63a7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759190"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>사용자용 Exchange 저장소와의 비즈니스용 Skype 서버
 
**요약:** 이 항목을 통해 2016년 10월에 저장소와의 통합을 Exchange 방법을 비즈니스용 Skype 서버.
  
배포의 Exchange Microsoft Exchange 통합을 사용하는 경우 사용자에 대한 비즈니스용 Skype 서버 정책을 구성할 필요가 없습니다. 대신 사서함이 Exchange In-Place 보류에 Exchange 사용자의 보관을 지원하도록 In-Place 구성합니다. 저장소와의 Exchange 구성하기 전에 에서 [보관 계획을 비즈니스용 Skype 서버.](../../plan-your-deployment/archiving/archiving.md) 보류 정책에 Exchange In-Place 대한 자세한 내용은 Exchange 참조하십시오. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Microsoft Exchange 통합 구성

1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 구성** 을 클릭합니다.
    
4. 보관 구성 목록에서 적합한 전역, 사이트 또는 풀 구성 이름을 클릭하고 **편집**, **자세한 정보 표시** 를 차례로 클릭한 후 다음을 수행합니다.
    
   - 저장소와의 Exchange 사용하도록 설정하려면 Microsoft Exchange **통합 확인란을** 선택합니다.
    
   - 저장소와의 Exchange 사용하지 않도록 설정하기 위해 Microsoft Exchange **통합 확인란의 선택을** 취소합니다.
    
5. **커밋** 을 클릭합니다.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Microsoft 비즈니스용 Skype 서버 Microsoft Exchange 포리스트에 배포할 때

Microsoft Exchange 통합을 사용하며 Microsoft Exchange Server 동일한 포리스트에 배포되지 비즈니스용 Skype 서버 경우 다음 Exchange Active Directory 특성이 배포된 포리스트와 비즈니스용 Skype 서버 동기화해야 합니다.
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
이 특성은 다중 값 특성입니다. 이 특성을 동기화할 때는 기존 값이 손실되지 않도록 값을 대체하지 않고 병합해야 합니다.
  

