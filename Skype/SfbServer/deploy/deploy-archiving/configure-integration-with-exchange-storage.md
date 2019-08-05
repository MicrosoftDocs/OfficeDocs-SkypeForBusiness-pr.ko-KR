---
title: 비즈니스용 Skype 서버에 Exchange 저장소 통합 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: '요약: 비즈니스용 Skype 서버에서 Exchange 저장소와의 통합을 구성 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.'
ms.openlocfilehash: b58aa090e4e6c51beb1f99ba5dc9020e029c8c39
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190503"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 Exchange 저장소 통합 구성
 
**요약:** 비즈니스용 Skype 서버에서 Exchange 저장소와의 통합을 구성 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
  
배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하는 경우 사용자 용 비즈니스용 Skype Server 보관 정책을 구성할 필요가 없습니다. 대신 Exchange에 있는 사용자의 보관을 지원 하도록 Exchange 원본 위치 유지 정책을 구성 하면 해당 사서함이 원본 위치 유지에 배치 됩니다. Exchange 저장소와의 통합을 구성 하기 전에 [비즈니스용 Skype 서버에서 보관 계획](../../plan-your-deployment/archiving/archiving.md)읽기를 참조 하세요. Exchange 원본 위치 유지 정책에 대 한 자세한 내용은 Exchange 제품 설명서를 참조 하세요. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Microsoft Exchange 저장소와 통합 구성

1. CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 
    
3. 왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.
    
4. 보관 구성 목록에서 적절 한 전역, 사이트 또는 풀 구성의 이름을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 하 고 다음을 수행 합니다.
    
   - Exchange 저장소와의 통합을 사용 하도록 설정 하려면 **Microsoft Exchange 통합** 확인란을 선택 합니다.
    
   - Exchange 저장소와의 통합을 사용 하지 않도록 설정 하려면 **Microsoft Exchange 통합** 확인란을 선택 취소 합니다.
    
5. **커밋**을 클릭합니다.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>비즈니스용 Skype 서버와 Microsoft Exchange가 서로 다른 포리스트에 배포 되는 경우

Microsoft Exchange 통합을 사용 하는 경우 Microsoft Exchange Server가 비즈니스용 Skype 서버와 동일한 포리스트에 배포 되지 않은 경우 다음 Exchange Active Directory 특성이 포리스트에 대 한 Skype와 동기화 되었는지 확인 해야 합니다. 비즈니스 서버 배포 됨:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
이것은 다중 값 특성입니다. 이 특성을 동기화 할 때 기존 값이 손실 되지 않도록 값을 바꾸지 않고 병합 해야 합니다.
  

