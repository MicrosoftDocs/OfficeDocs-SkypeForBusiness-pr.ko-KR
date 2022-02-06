---
title: Lync Server 2010에 대한 프런트 엔드 중재 서비스 설정 확장기
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 이 대화 상자에서 중재 서버 PSTN 게이트웨이 설정의 속성을 편집합니다. 다음과 같은 설정을 정의합니다.
---

# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Lync Server 2010에 대한 프런트 엔드 중재 서비스 설정 확장기
 
이 대화 상자에서 **중재 서버 PSTN 게이트웨이** 설정의 속성을 편집합니다. 다음과 같은 설정을 정의합니다.
  
- 중재 **서버를** 이 프런트 엔드 서버 또는 프런트 엔드 풀과 함께 사용하려면 함께 사용 가능한 중재 서버를 선택합니다.
    
- **수신 포트**: 중재 서버에서 수신할 포트를 정의합니다. **TLS**(전송 계층 보안) 또는 **TCP**(Transport Control Protocol)용 포트를 정의할 수 있습니다. TCP에 대한 포트 항목을 사용할 수 있도록 하려면 **TCP 포트 사용** 확인란을 선택해야 합니다. 
    
    > [!IMPORTANT]
    > 공중 전화망(PSTN) 게이트웨이의 설명서 및 구성 설정을 참조하여 포트 값 TLS 또는 TCP나 둘 다를 사용하도록 설정하고 정의해야 하는지 여부를 확인하십시오. TLS는 인증서를 사용하여 중재 서버와 PSTN 게이트웨이 간의 트래픽을 암호화하는 보다 안전한 프로토콜입니다. 일부 PSTN 게이트웨이에서는 TLS가 지원되지 않습니다. 
  
- 현재 연결되어 있는 기존 **트렁크**, 즉 SIP(Session Initiation Protocol) 트렁크, **게이트웨이**(PSTN 게이트웨이 또는 IP-PBX) 및 **사이트**(트렁크 및 게이트웨이용으로 구성된 사이트)의 목록을 정의합니다.
    
- 트렁크, 게이트웨이 및 사이트를 선택하고 **기본값으로 설정** 을 클릭하여 선택 항목을 이 중재 서비스의 기본값으로 설정합니다. 선택 항목의 현재 기본값 설정을 제거하려면 현재 기본값을 선택하고 **기본값으로 설정 안 함** 을 선택합니다. 그런 다음 새 기본값을 선택하고 **기본값으로 설정** 을 클릭합니다.
    
  **확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.
  
  **취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.
  
  **도움말**: 이 도움말 화면을 표시합니다.
  

