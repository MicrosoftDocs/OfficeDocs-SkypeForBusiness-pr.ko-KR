---
title: Lync Server 2010 대한 중재 서비스 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 다음 속성을 정의 하 여 중재 서비스의 속성을 편집 합니다.
ms.openlocfilehash: 51fbd889d7e9d673fb75b1062a70ae55a9f8585c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215109"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a>Lync Server 2010 대한 중재 서비스 설정 확장기
 
다음 속성을 정의 하 여 중재 서비스의 속성을 편집 합니다.
  
- **수신 대기 포트**: 중재 서비스가 수신 대기할 **TLS** 포트를 정의 합니다. 기본적으로 포트 값은 TLS (전송 계층 보안)를 통한 TCP 5067입니다.
    
    선택적으로 **TCP** 포트 값을 정의 합니다. 기본적으로이 값은 TCP 5068입니다.
    
    > [!NOTE]
    > Tcp 포트 값 설정은 **tcp 포트 사용**을 선택 하 여 사용 하도록 설정 됩니다. 중재 서비스와 통신 하는 데 필요한 포트 설정에 대 한 요구 사항에 대 한 자세한 내용은 공중 전화망 (PSTN) 게이트웨이나 IP PBX (Internet Protocol Private Branch Exchange)에 대 한 설명서를 참조 해야 합니다. 
  
- **Tcp 포트를 사용 하도록 설정** 하 여 PSTN 게이트웨이 또는 IP-PBX의 tcp 통신에 대 한 포트 값을 정의 합니다.
    
- 현재 연결되어 있는 기존 **트렁크**, 즉 SIP(Session Initiation Protocol) 트렁크, **게이트웨이**(PSTN 게이트웨이 또는 IP-PBX) 및 **사이트**(트렁크 및 게이트웨이용으로 구성된 사이트)의 목록을 정의합니다.
    
- 트렁크, 게이트웨이 및 사이트를 선택하고 **기본값으로 설정**을 클릭하여 선택 항목을 이 중재 서비스의 기본값으로 설정합니다. 선택 항목의 현재 기본값 설정을 제거하려면 현재 기본값을 선택하고 **기본값으로 설정 안 함**을 선택합니다. 그런 다음 새 기본값을 선택하고 **기본값으로 설정**을 클릭합니다.
    
  **확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.
  
  **취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.
  
  **도움말**: 이 도움말 화면을 표시합니다.
  

