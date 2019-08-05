---
title: 모바일 클라이언트 푸시 알림 구성 만들기 또는 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
description: 모바일 기능에서 핵심적인 두 가지 요소는 푸시 알림 및 PNCH(푸시 알림 클리어링 하우스)입니다. 푸시 알림은 메시지가 PNCH로 전송되는 프로세스입니다. 메시지는 모바일 클라이언트로 배달될 수 있거나 제한 시간이 만료될 때까지 PNCH에 보관됩니다.
ms.openlocfilehash: 5c7d78174ca4cfe180742fa73a801704cb85997c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196376"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>모바일 클라이언트: 푸시 알림 구성 만들기 또는 편집
 
모바일 기능에서 핵심적인 두 가지 요소는 푸시 알림 및 PNCH(푸시 알림 클리어링 하우스)입니다. 푸시 알림은 메시지가 PNCH로 전송되는 프로세스입니다. 메시지는 모바일 클라이언트로 배달될 수 있거나 제한 시간이 만료될 때까지 PNCH에 보관됩니다. 
  
> [!NOTE]
> 기간은 푸시 알림 클리어링 하우스에서 설정되며, 배포 관리자 또는 사용자가 구성할 수는 없습니다. 
  
푸시 알림을 사용하도록 설정하려면 다음을 수행합니다.
  
1. **범위:** 이 정책의 범위를 지정합니다. **전역**(해당 배포의 모든 사용자에게 적용됨) 또는 **사이트**(지정된 사이트의 홈 서버에 할당된 사용자에게만 적용됨)를 선택할 수 있습니다.
    
    > [!IMPORTANT]
    > 하나의 정책 수준에서 적용 되는 정책 설정이 다른 정책 수준에서 적용 되는 설정을 재정의할 수 있습니다. 정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 전역 정책 보다 우선 합니다 (최소 영향). 즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다. 
  
2. 다음 확인란을 클릭하여 사용하도록 설정할 푸시 알림 서비스를 선택합니다.
    
   - **Microsoft 푸시 알림을 사용** 하면 비즈니스용 Skype 앱에서 Windows Phone 용 클라우드 기반 pnch로 푸시 알림을 사용할 수 있습니다.
    
   - Apple **push 알림을 사용** 하면 Apple의 iOS (예: IPhone, iPad)를 실행 하 고 비즈니스용 Skype 앱을 사용 하 여 APPLE pnch에 대 한 푸시 알림을 사용할 수 있습니다.
    
3. 정책 편집을 완료한 후 **커밋**을 클릭하여 변경 내용을 저장합니다. 적용한 변경 내용을 삭제해야 하는 경우 **취소**를 선택합니다. 그러면 변경 내용이 정책에 저장되지 않습니다.
    

