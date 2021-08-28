---
title: 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: 변환 규칙 및 전화 걸기 문자열 정규화에 대해 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: 94e5fdf3428694f672622c62b76e81886afe1682
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606077"
---
# <a name="translation-rules-in-skype-for-business-server"></a>비즈니스용 Skype 서버

변환 규칙 및 전화 걸기 문자열 정규화에 대해 비즈니스용 Skype 서버 Enterprise Voice.

 Enterprise Voice에서는 RNL(역방향 번호 조회)을 수행하기 위한 목적으로 모든 전화 걸기 문자열이 E.164 형식으로 정규화될 것을 요구합니다. 호출된 번호와 호출 번호 모두에 대해 변환 규칙이 지원됩니다. 트렁크 피어(즉, 연결된 게이트웨이, PBX(Private Branch Exchange) 또는 SIP 트렁크)에는 번호가 로컬 전화 걸기 형식이 필요할 수 있습니다. 번호를 E.164 형식에서 로컬 전화 걸기 형식으로 변환하기 위해 트렁크 피어로 라우팅하기 전에 하나 이상의 변환 규칙을 정의하여 요청 URI를 조작할 수 있습니다. 예를 들어 전화 걸기 문자열의 시작 부분에서 +44를 제거하고 대신 0144를 넣는 변환 규칙을 작성할 수 있습니다.

서버에서 아웃바운드 경로 변환을 수행하면 전화 번호를 로컬 전화 번호 형식으로 변환하기 위해 개별 트렁크 피어의 구성 요구 사항을 줄일 수 있습니다. 특정 중재 서버 클러스터와 연결하도록 게이트웨이 및 게이트웨이 수를 계획할 때 유사한 로컬 전화 걸기 요구 사항을 사용하여 트렁크 피어를 그룹화하는 것이 유용할 수 있습니다. 이렇게 하면 필요한 변환 규칙의 수와 규칙을 작성하는 데 걸리는 시간이 단축될 수 있습니다.

> [!IMPORTANT]
> 하나 이상의 변환 규칙을 트렁크 Enterprise Voice 트렁크 피어에 대한 변환 규칙을 구성하는 대안으로 사용해야 합니다. 트렁크 피어에 변환 규칙을 구성한 경우 두 규칙이 충돌할 수 Enterprise Voice 변환 규칙을 트렁크 구성과 연결하지 않습니다.

## <a name="example-translation-rules"></a>예제 변환 규칙

다음 변환 규칙 예에서는 E.164 형식의 번호를 트렁크 피어의 로컬 형식으로 변환하는 규칙을 서버에서 개발하는 방법을 보여 주며,

변환 규칙을 구현하는 방법에 대한 자세한 내용은 배포 설명서에서 [Defining Translation Rules를](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) 참조하십시오.

|**설명**|**시작 숫자**|**Length**|**제거할 숫자**|**추가할 숫자**|**일치 패턴**|**번역**|**예**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|미국의 기존 시거리 전화 걸기  <br/> ('+'를 제거합니다.)  <br/> |+1  <br/> |정확히 12  <br/> |1  <br/> |0  <br/> |^\+(1\d {10} ) $  <br/> |$1  <br/> |+14255551010 14255551010  <br/> |
|미국 국제 시거리 전화 걸기  <br/> ('+'를 제거하고 011 추가)  <br/> |+  <br/> |11개 이상  <br/> |1  <br/> |011  <br/> |^\+(\d {9} \d+)$  <br/> |011$1  <br/> |+441235551010 011441235551010  <br/> |