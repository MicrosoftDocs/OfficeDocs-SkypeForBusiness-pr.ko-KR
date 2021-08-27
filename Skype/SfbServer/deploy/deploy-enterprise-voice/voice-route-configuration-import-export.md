---
title: 음성 경로 구성 파일 내보내기 또는 가져오기 비즈니스용 Skype
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: '요약: 비즈니스용 Skype 서버 제어판을 사용하여 음성 라우팅 구성 파일을 내보내거나 가져오는 비즈니스용 Skype 서버 방법을 제공합니다.'
ms.openlocfilehash: bbad8ca1a9d11074bb99fcd9655b8a8281953344
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626150"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>음성 경로 구성 파일 내보내기 또는 가져오기 비즈니스용 Skype
 
**요약:** 비즈니스용 Skype 서버 제어판을 사용하여 음성 라우팅 구성 파일을 내보내거나 가져오는 비즈니스용 Skype 서버 대해 자세히 알아보습니다.
  
음성 라우팅 구성을 게시하지 않고 저장하려면 다음 단계에 따라 음성 라우팅 구성의 스냅숏을 저장하고 검색합니다. 
  
음성 라우팅 구성 파일(.vcfg)을 가져오지만 그동안 서버의 음성 라우팅 구성이 변경된 경우 비즈니스용 Skype 서버 제어판의 음성 라우팅 그룹에 있는 페이지에 음성 라우팅에 커밋되지 않은 변경 내용이 있는 것으로 표시됩니다.  커밋되지 않은 이러한 변경 내용으로 인해 두 구성 간 차이가 발생하며, 이러한 차이를 조정해야 합니다.
  
그룹 내의 모든 페이지에서 설정을 커밋하지 않은 변경한 경우 변경 내용은 내보낼 음성 구성 파일(.vcfg)에 저장됩니다. 따라서 변경 내용을 게시하기 전에 여러 세션 동안 음성 라우팅 구성을 변경할 수 있습니다. 
  
### <a name="to-export-a-voice-routing-configuration"></a>음성 라우팅 구성을 내보내려면

1. RTCUniversalServerAdmins 그룹의 구성원이나 **CsVoiceAdministrator, CsServerAdministrator** 또는 **CsAdministrator** 관리  역할의 구성원으로 컴퓨터에 로그온합니다.
    
2. 제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭합니다.
    
4. **동작** 메뉴에서 **구성 내보내기** 를 클릭합니다.
    
5. 위치 및 파일 이름을 지정하고 **저장** 을 클릭합니다.
    
### <a name="to-import-a-voice-routing-configuration"></a>음성 라우팅 구성을 가져오려면

1. RTCUniversalServerAdmins 그룹의 구성원이나 **CsVoiceAdministrator, CsServerAdministrator** 또는 **CsAdministrator** 관리  역할의 구성원으로 컴퓨터에 로그온합니다.
    
2. 제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭합니다.
    
4. **동작** 메뉴에서 **구성 가져오기** 를 클릭합니다.
    
5. 가져올 구성 파일을 찾아 **열기** 를 클릭합니다.
    
6. **커밋**, **모두 커밋** 을 차례로 클릭합니다.
    
    > [!NOTE]
    > 음성 구성 파일을 가져올 때마다 **모두 커밋** 명령을 실행하여 구성 변경 내용을 게시해야 합니다. 자세한 내용은 작업 설명서에서 [Publish pending changes to the voice routing configuration in 비즈니스용 Skype](voice-route-config-changes.md) 참조하십시오.
  

