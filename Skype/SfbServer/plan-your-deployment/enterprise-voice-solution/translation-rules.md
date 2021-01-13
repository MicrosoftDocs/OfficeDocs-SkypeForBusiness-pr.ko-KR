---
title: 비즈니스용 Skype 서버의 변환 규칙
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: 비즈니스용 Skype 서버 2016의 변환 규칙 및 전화 걸기 문자열 정규화에 대해 Enterprise Voice.
ms.openlocfilehash: 0c00776dae502bfd28bbe27e90012fabb6e25c93
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802688"
---
# <a name="translation-rules-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 변환 규칙

비즈니스용 Skype 서버 2016의 변환 규칙 및 전화 걸기 문자열 정규화에 대해 Enterprise Voice.

 Enterprise Voice에서는 RNL(역방향 번호 조회)을 수행하기 위한 목적으로 모든 전화 걸기 문자열이 E.164 형식으로 정규화될 것을 요구합니다. 호출된 번호와 호출 번호 모두에 대해 변환 규칙이 지원됩니다. 트렁크 피어(즉, 연결된 게이트웨이, PBX(Private Branch Exchange) 또는 SIP 트렁크)에는 번호가 로컬 전화 걸기 형식이 필요할 수 있습니다. 번호를 E.164 형식에서 로컬 전화 걸기 형식으로 변환하기 위해 트렁크 피어로 라우팅하기 전에 요청 URI를 조작하는 변환 규칙을 하나 이상 정의할 수 있습니다. 예를 들어 전화 걸기 문자열의 시작 부분에서 +44를 제거하고 대신 0144를 넣는 변환 규칙을 작성할 수 있습니다.

서버에서 아웃바운드 경로 변환을 수행하면 전화 번호를 로컬 전화 번호 형식으로 변환하기 위해 각 개별 트렁크 피어의 구성 요구 사항을 줄일 수 있습니다. 특정 중재 서버 클러스터와 연결하도록 게이트웨이 및 게이트웨이 수를 계획할 때 유사한 로컬 전화 걸기 요구 사항으로 트렁크 피어를 그룹화하는 것이 유용할 수 있습니다. 이렇게 하면 필요한 변환 규칙의 수와 규칙을 작성하는 데 걸리는 시간이 단축될 수 있습니다.

> [!IMPORTANT]
> 하나 이상의 변환 규칙을 트렁크 Enterprise Voice 트렁크 피어에 대한 변환 규칙을 구성하는 대안으로 사용해야 합니다. 트렁크 피어에 변환 규칙을 구성한 경우 두 규칙이 충돌할 수 Enterprise Voice 변환 규칙을 트렁크 구성과 연결하지 않습니다.

## <a name="example-translation-rules"></a>예제 변환 규칙

다음 변환 규칙 예제에서는 번호를 E.164 형식에서 트렁크 피어에 대한 로컬 형식으로 변환하는 규칙을 서버에서 개발하는 방법을 보여 제공합니다.

변환 규칙을 구현하는 방법에 대한 자세한 내용은 배포 설명서에서 변환 규칙 [정의를](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) 참조하십시오.

|**설명**|**시작 숫자**|**Length**|**제거할 숫자**|**추가할 숫자**|**일치 패턴**|**Translation**|**예**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|미국의 기존 시거리 전화 걸기  <br/> ('+'를 제거합니다.)  <br/> |+1  <br/> |정확히 12  <br/> |1   <br/> |0  <br/> |^\+(1\d) {10} $  <br/> |$1  <br/> |+14255551010이 14255551010이 됩니다.  <br/> |
|미국 국제 장거리 전화 걸기  <br/> ('+'를 제거하고 011 추가)  <br/> |+  <br/> |11개 이상  <br/> |1   <br/> |011  <br/> |^\+(\d {9} \d+)$  <br/> |011$1  <br/> |+441235551010이 011441235551010이 됩니다.  <br/> |


