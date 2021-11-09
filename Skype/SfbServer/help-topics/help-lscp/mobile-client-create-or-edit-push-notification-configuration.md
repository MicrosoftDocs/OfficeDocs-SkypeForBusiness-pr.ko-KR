---
title: 모바일 클라이언트 푸시 알림 구성 만들기 또는 편집
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
description: 푸시 알림 및 PNCH(푸시 알림 클리어링 하우스)는 모바일 기능의 두 가지 주요 부분입니다. 푸시 알림은 메시지가 PNCH로 전송되는 프로세스입니다. 메시지는 모바일 클라이언트로 배달될 수 있거나 제한 시간이 만료될 때까지 PNCH에 보관됩니다.
ms.openlocfilehash: bbab418e580b224ee269adbdf3f1aad3c36de469
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847781"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>모바일 클라이언트: 푸시 알림 구성 만들기 또는 편집
 
푸시 알림 및 PNCH(푸시 알림 클리어링 하우스)는 모바일 기능의 두 가지 주요 부분입니다. 푸시 알림은 메시지가 PNCH로 전송되는 프로세스입니다. 메시지는 모바일 클라이언트로 배달될 수 있거나 제한 시간이 만료될 때까지 PNCH에 보관됩니다. 
  
> [!NOTE]
> 기간은 푸시 알림 클리어링 하우스에서 설정되며, 배포 관리자 또는 사용자가 구성할 수는 없습니다. 
  
푸시 알림을 사용하도록 설정하려면 다음을 수행합니다.
  
1. **범위:** 이 정책의 범위를 유의합니다. 이 배포의 모든 사용자에게 적용되는 **Global** 또는 지정된 사이트의 홈 서버에 할당된 사용자만 사이트일 수 있습니다.
    
    > [!IMPORTANT]
    > 한 정책 수준에서 적용되는 정책 설정은 다른 정책 수준에서 적용되는 설정을 재정의할 수 있습니다. 정책 우선 순위는 사용자 정책(가장 영향이 가장 큰)이 사이트 정책을 다시 설정한 다음 사이트 정책이 글로벌 정책(최소 영향)을 우선합니다. 즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다. 
  
2. 다음 확인란을 클릭하여 사용하도록 설정할 푸시 알림 서비스를 선택합니다.
    
   - **Microsoft 푸시 알림** 사용은 앱에서 클라우드 기반 PNCH에 대한 푸시 Windows Phone 사용하도록 비즈니스용 Skype 있습니다.
    
   - **Apple 푸시** 알림 사용은 Apple의 iOS를 실행하는 장치(예: iPhone, iPad) 및 앱 앱 사용에 대해 Apple PNCH에 대한 푸시 비즈니스용 Skype 사용하도록 설정
    
3. 정책 편집을 완료한 후 **커밋** 을 클릭하여 변경 내용을 저장합니다. 적용한 변경 내용을 삭제해야 하는 경우 **취소** 를 선택합니다. 그러면 변경 내용이 정책에 저장되지 않습니다.
    

