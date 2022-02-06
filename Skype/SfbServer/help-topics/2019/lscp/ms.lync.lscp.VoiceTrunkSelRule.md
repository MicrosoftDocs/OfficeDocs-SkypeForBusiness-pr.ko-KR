---
title: 변환 규칙 선택
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
  - ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
f1.keywords:
  - CSH
ms.localizationpriority: medium
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Enterprise Voice에서는 RNL(역방향 번호 조회)을 수행하기 위한 목적으로 모든 전화 걸기 문자열이 E.164 형식으로 정규화될 것을 요구합니다. 트렁크 피어(즉, 연결된 게이트웨이, PBX 또는 SIP 트렁크)에서는 번호가 로컬 전화 걸기 형식이어야 할 수 있습니다. 번호를 E.164 형식에서 로컬 전화 걸기 형식으로 변환하려면 요청 URI를 트렁크 피어로 라우팅하기 전에 요청 URI를 처리하기 위한 변환 규칙을 하나 이상 선택적으로 정의할 수 있습니다. 예를 들어 전화 걸기 문자열의 시작 부분에서 +44를 제거하고 대신 0144를 넣는 변환 규칙을 작성할 수 있습니다.'
---

# <a name="select-translation-rules"></a>변환 규칙 선택
 
 Enterprise Voice에서는 RNL(역방향 번호 조회)을 수행하기 위한 목적으로 모든 전화 걸기 문자열이 E.164 형식으로 정규화될 것을 요구합니다. 트렁크 피어(즉, 연결된 게이트웨이, PBX 또는 SIP 트렁크)에서는 번호가 로컬 전화 걸기 형식이어야 할 수 있습니다. 번호를 E.164 형식에서 로컬 전화 걸기 형식으로 변환하려면 요청 URI를 트렁크 피어로 라우팅하기 전에 요청 URI를 처리하기 위한 변환 규칙을 하나 이상 선택적으로 정의할 수 있습니다. 예를 들어 전화 걸기 문자열의 시작 부분에서 +44를 제거하고 대신 0144를 넣는 변환 규칙을 작성할 수 있습니다.
  
> [!IMPORTANT]
> 트렁크 피어에서 변환 규칙을 구성하는 대신, 하나 이상의 변환 규칙을 Enterprise Voice 트렁크 구성에 연결하는 기능을 사용할 수 있습니다. 트렁크 피어에 대한 변환 규칙을 구성한 경우 변환 규칙을 Enterprise Voice 트렁크 구성과 연결하지 마십시오. 두 규칙이 충돌할 수 있기 때문입니다. 
  
기존 변환 규칙을 사용하려면 목록에서 규칙을 클릭한 다음 **확인** 을 클릭합니다.
  
 
  

