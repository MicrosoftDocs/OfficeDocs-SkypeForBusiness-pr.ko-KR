---
title: Lync Server 2010의 프론트 엔드 중재 서비스 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 이 대화 상자에서 중재 서버 PSTN 게이트웨이 설정의 속성을 편집 합니다. 다음 설정을 정의 합니다.
ms.openlocfilehash: b57ca675d3681886ea2a2853aa1357b394fda4c4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189912"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Lync Server 2010의 프론트 엔드 중재 서비스 설정 확장기
 
이 대화 상자에서 **중재 서버 PSTN 게이트웨이** 설정의 속성을 편집 합니다. 다음 설정을 정의 합니다.
  
- 이 프런트 엔드 서버 또는 프런트 엔드 풀을 사용 하 여 조정 서버를 collocate 하려면 **Collocated 중재 서버** 를 선택 합니다.
    
- **수신 대기 포트**: 중재 서버가 수신 대기 하는 포트를 정의 합니다. **TLS** 또는 전송 계층 보안, **TCP**또는 전송 제어 프로토콜에 대 한 포트를 정의할 수 있습니다. TCP에 대 한 포트 항목을 사용 하려면 **tcp 포트 사용**확인란을 선택 해야 합니다. 
    
    > [!IMPORTANT]
    > 포트 값 TLS, TCP 또는 둘 다를 사용 하도록 설정 하 고 정의 해야 하는지 여부는 공용 전환 통신 네트워크 (PSTN) 게이트웨이에 대 한 설명서 및 구성 설정을 참조 하세요. TLS는 중재 서버와 PSTN 게이트웨이 간의 트래픽을 암호화 하는 인증서를 사용 하 여 보다 안전한 프로토콜입니다. 일부 PSTN 게이트웨이가 TLS를 지원 하지는 않습니다. 
  
- 현재 연결되어 있는 기존 **트렁크**, 즉 SIP(Session Initiation Protocol) 트렁크, **게이트웨이**(PSTN 게이트웨이 또는 IP-PBX), **사이트**(트렁크 및 게이트웨이용으로 구성된 사이트)의 목록을 정의합니다.
    
- 트렁크, 게이트웨이 및 사이트를 선택하고 **기본값으로 설정**을 클릭하여 선택 항목을 이 중재 서비스의 기본값으로 설정합니다. 선택 항목의 현재 기본값 설정을 제거하려면 현재 기본값을 선택하고 **기본값으로 설정 안 함**을 선택합니다. 그런 다음 새 기본값을 선택하고 **기본값으로 설정**을 클릭합니다.
    
  **확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.
  
  **취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.
  
  **도움말**: 이 도움말 화면을 표시합니다.
  

