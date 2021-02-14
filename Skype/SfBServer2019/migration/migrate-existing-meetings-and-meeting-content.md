---
title: 기존 모임 및 모임 콘텐츠 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 사용자 계정을 비즈니스용 Skype 서버 2019 서버로 이동하면 해당 사용자 계정으로 다음 정보가 이동됩니다.
ms.openlocfilehash: 6513f581f55028ec28d4cf05f1f1b3df37c49e65
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752690"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>기존 모임 및 모임 콘텐츠 마이그레이션

사용자 계정을 비즈니스용 Skype 서버 2019 서버로 이동하면 해당 사용자 계정으로 다음 정보가 이동됩니다.
  
- **사용자가 이미 예약한 모임**. 회의 디렉터리 및 회의 데이터 이동이 포함됩니다.
    
- **사용자의 개인식별번호(PIN)** 사용자의 현재 PIN은 만료되거나 사용자가 새 PIN을 요청할 때까지 계속 작동됩니다.
    
다음과 같은 사용자 계정 정보는 새 서버로 이동하지 않습니다.
  
- **모임 콘텐츠**. 모임 중에 공유되는 콘텐츠(예: PowerPoint, 화이트보드, 첨부 파일 또는 폴링 데이터)를 이동하기 위해 **Move-CsUser** cmdlet의 일부로 **-MoveConferenceData** 매개 변수를 사용합니다. 
    

