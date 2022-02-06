---
title: Lync Server 2010 대한 중재 서비스 설정 확장기
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 다음 속성을 정의하여 중재 서비스의 속성을 편집합니다.
---

# <a name="mediation-service-settings-expander-for-lync-server-2010"></a>Lync Server 2010 대한 중재 서비스 설정 확장기
 
다음 속성을 정의하여 중재 서비스의 속성을 편집합니다.
  
- **수신 포트**: 중재 서비스가 수신할 **TLS** 포트를 정의합니다. 기본적으로 포트 값은 TLS(전송 계층 보안)를 통해 TCP 5067입니다.
    
    원하는 경우 **TCP 포트 값을 정의** 합니다. 기본적으로 값은 TCP 5068입니다.
    
    > [!NOTE]
    > TCP 포트 값 설정은 **TCP 포트 사용 을 선택하여 사용하도록 설정됩니다**. 중재 서비스와 통신하는 데 필요한 포트 설정에 대한 요구 사항은 PSTN(Public Switched Telephone Network) 게이트웨이 또는 IP-PBX(Internet Protocol Private Branch Exchange)에 대한 설명서를 참조해야 합니다. 
  
- **TCP 포트** 를 사용하도록 설정하여 PSTN 게이트웨이 또는 IP-PBX에서 TCP 통신에 대한 포트 값을 정의할 수 있습니다.
    
- 현재 연결되어 있는 기존 **트렁크**, 즉 SIP(Session Initiation Protocol) 트렁크, **게이트웨이**(PSTN 게이트웨이 또는 IP-PBX) 및 **사이트**(트렁크 및 게이트웨이용으로 구성된 사이트)의 목록을 정의합니다.
    
- 트렁크, 게이트웨이 및 사이트를 선택하고 **기본값으로 설정** 을 클릭하여 선택 항목을 이 중재 서비스의 기본값으로 설정합니다. 선택 항목의 현재 기본값 설정을 제거하려면 현재 기본값을 선택하고 **기본값으로 설정 안 함** 을 선택합니다. 그런 다음 새 기본값을 선택하고 **기본값으로 설정** 을 클릭합니다.
    
  **확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.
  
  **취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.
  
  **도움말**: 이 도움말 화면을 표시합니다.
  

