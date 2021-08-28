---
title: 페더레이션 경로 지정 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: 사이트 페더레이션 경로 할당을 설정하려면 먼저 에지 서버 또는 에지 서버 풀에서 페더레이션을 사용하도록 설정해야 합니다. 에지 서버 또는 풀에서 페더레이션을 사용하도록 설정하지 않은 경우 사이트의 페더레이션 경로 할당 설정을 수정할 수 없습니다.
ms.openlocfilehash: c331fb80e070062ad2aeb373d2b7b19d583f4c34
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58629010"
---
# <a name="federation-route-settings-expander"></a>페더레이션 경로 지정 설정 확장기
 
사이트 페더레이션 경로 할당을 설정하려면 먼저 에지 서버 또는 에지 서버 풀에서 페더레이션을 사용하도록 설정해야 합니다. 에지 서버 또는 풀에서 페더레이션을 사용하도록 설정하지 않은 경우 사이트의 페더레이션 경로 할당 설정을 수정할 수 없습니다.

에지 서버 또는 풀의 페더전 설정이 구성된 경우 다음 옵션을 구성할 수 있습니다. 
  
- 모든 사이트에 대한 **페더전 경로 할당 허용** 이 설정은 모든 사이트에 영향을 미치게 됩니다. 이 사이트에서 구성하는 설정이 모든 사이트에 대해 적합해야 합니다.
    
- **SIP 페더ation 사용** SIP 페더전 경로를 사용하도록 설정하려면 이 옵션을 선택한 다음 페더임 경로로 Director 또는 에지 풀을 선택합니다.
    
- **XMPP 페더럴을 사용하도록 설정** XMPP 페더럴 경로를 사용하도록 설정하려면 이 옵션을 선택한 다음 페더럴 경로로 Director 또는 에지 풀을 선택합니다.
- 
  > [!NOTE]
  > XMPP 게이트웨이 및 xxies는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다. 자세한 [내용은 XMPP 페더링 마이그레이션을](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) 참조하세요.
    

