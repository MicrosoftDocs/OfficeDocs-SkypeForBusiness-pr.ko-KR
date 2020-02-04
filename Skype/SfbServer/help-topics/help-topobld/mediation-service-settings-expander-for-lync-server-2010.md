---
title: Lync Server 2010에 대한 중재 서비스 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 다음 속성을 정의하여 중재 서비스의 속성을 편집합니다.
ms.openlocfilehash: 29c5172157d993c73ca35a5217c67ee6d6df87ef
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696973"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a>Lync Server 2010에 대한 중재 서비스 설정 확장기
 
다음 속성을 정의하여 중재 서비스의 속성을 편집합니다.
  
- **수신 대기 포트**: 중재 서비스에서 수신 대기할 **TLS** 포트를 정의합니다. 기본적으로 포트 값은 TLS(전송 계층 보안)를 사용하는 경우 TCP 5067입니다.
    
    원하는 경우 **TCP** 포트 값을 정의합니다. 기본값은 TCP 5068입니다.
    
    > [!NOTE]
    > TCP 포트 값 설정을 사용하도록 설정하려면 **TCP 포트 사용**을 선택합니다. 공중 전화망(PSTN) 게이트웨이 또는 IP-PBX(Internet Protocol Private Branch Exchange) 설명서에서 중재 서비스와 통신하는 데 필요한 포트 설정에 대한 요구 사항을 파악해야 합니다. 
  
- **TCP 포트 사용**을 선택하여 PSTN 게이트웨이 또는 IP-PBX의 TCP 통신을 위한 포트 값을 정의합니다.
    
- 현재 연결되어 있는 기존 **트렁크**, 즉 SIP(Session Initiation Protocol) 트렁크, **게이트웨이**(PSTN 게이트웨이 또는 IP-PBX), **사이트**(트렁크 및 게이트웨이용으로 구성된 사이트)의 목록을 정의합니다.
    
- 트렁크, 게이트웨이 및 사이트를 선택하고 **기본값으로 설정**을 클릭하여 선택 항목을 이 중재 서비스의 기본값으로 설정합니다. 선택 항목의 현재 기본값 설정을 제거하려면 현재 기본값을 선택하고 **기본값으로 설정 안 함**을 선택합니다. 그런 다음 새 기본값을 선택하고 **기본값으로 설정**을 클릭합니다.
    
  **확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.
  
  **취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.
  
  **도움말**: 이 도움말 화면을 표시합니다.
  

