---
title: 비즈니스용 Skype에서 음성 경로 구성 파일 내보내기 또는 가져오기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: '요약: 비즈니스용 skype 서버 제어판을 사용 하 여 비즈니스용 Skype 서버에서 음성 라우팅 구성 파일을 내보내거나 가져오는 방법에 대해 알아봅니다.'
ms.openlocfilehash: b980aa26f4d67cd1697ec17286e6af7d9e657e15
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766881"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>비즈니스용 Skype에서 음성 경로 구성 파일 내보내기 또는 가져오기
 
**요약:** 비즈니스용 skype 서버 제어판을 사용 하 여 비즈니스용 Skype 서버에서 음성 라우팅 구성 파일을 내보내거나 가져오는 방법에 대해 알아봅니다.
  
음성 라우팅 구성을 게시 하지 않고 저장 하려는 경우 다음 단계에 따라 음성 라우팅 구성의 스냅숏을 저장 하 고 검색 합니다. 
  
음성 라우팅 구성 파일 (vcfg)을 가져올 때 그 동안 서버의 음성 라우팅 구성이 변경 된 경우 비즈니스용 Skype Server 제어판의 **음성 라우팅** 그룹에 있는 페이지에는 음성 라우팅에 대 한 커밋되지 않은 변경 내용이 있음을 나타내는 메시지가 표시 됩니다. 커밋되지 않은 변경 내용은 조정을 필요로 하는 두 구성의 차이점입니다.
  
그룹 내의 모든 페이지에서 설정에 대 한 커밋되지 않은 변경 내용이 있는 경우 해당 변경 내용이 내보낸 음성 구성 파일 (vcfg)에 저장 됩니다. 이렇게 하면 변경 내용을 게시 하기 전에 여러 세션 중에 음성 라우팅 구성 변경을 수행할 수 있습니다. 
  
### <a name="to-export-a-voice-routing-configuration"></a>음성 라우팅 구성을 내보내려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 **CsVoiceAdministrator**, **Csserveradministrator**또는 **csadministrator** 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **음성 라우팅을**클릭 합니다.
    
4. **작업** 메뉴에서 **구성 내보내기를**클릭 합니다.
    
5. 위치 및 파일 이름을 지정한 다음 **저장**을 클릭 합니다.
    
### <a name="to-import-a-voice-routing-configuration"></a>음성 라우팅 구성을 가져오려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 **CsVoiceAdministrator**, **Csserveradministrator**또는 **csadministrator** 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **음성 라우팅을**클릭 합니다.
    
4. **작업** 메뉴에서 **구성 가져오기를**클릭 합니다.
    
5. 가져올 구성 파일을 찾은 다음 **열기**를 클릭 합니다.
    
6. **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.
    
    > [!NOTE]
    > 음성 구성 파일을 가져올 때마다 **모두 커밋** 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다. 자세한 내용은 운영 설명서의 비즈니스용 [Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](voice-route-config-changes.md) 를 참조 하세요.
  

