---
title: 외부 응용 프로그램 일반 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: 이미 정의된 신뢰할 수 있는 응용 프로그램 서버의 속성을 편집하려면 다음 지침을 따릅니다.
ms.openlocfilehash: a19a2271caebe2dc0acc6c2c0609e76abfdb338c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626880"
---
# <a name="external-application-general-settings-expander"></a>외부 응용 프로그램 일반 설정 확장기
 
이미 정의된 신뢰할 수 있는 응용 프로그램 서버의 속성을 편집하려면 다음 지침을 따릅니다.
  
수정할 수 있는 두 가지 섹션은 다음과 같습니다.
  
> 일반 설정
> 
> 다음 홉 설정
    
## <a name="general-settings"></a>일반 설정

신뢰할 수 있는 응용 프로그램 서버 풀의 현재 FQDN(정규화된 도메인 이름)을 수정할 수 있습니다. 풀 FQDN의 이름을 편집합니다. 클라이언트 또는 서버에서 새 풀 이름에 연결할 수 있으려면 새 항목에 대한 DNS(Domain Name System) 호스트(A) 레코드가 있어야 합니다.
  
이 풀에 대한 구성 데이터 복제가 필요한 경우 **이 풀에 대한 구성 데이터 복제 사용** 을 선택합니다. 구성 데이터를 복제하지 않으려면 확인 표시를 지웁니다.
  
## <a name="next-hop-settings"></a>다음 홉 설정

드롭다운 목록에서 정의된 프런트 엔드 풀 또는 Enterprise Edition 프런트 엔드 서버를 선택하여 Standard Edition 서버 풀의 다음 홉 서버를 지정할 수 있습니다. 디렉터 또는 디렉터 풀은 신뢰할 수 있는 응용 프로그램 서버 다음 홉에 대한 올바른 선택이 아니며 목록에 표시되지 않습니다.
  

**확인을** 클릭하여 변경 내용을 수락하고 저장합니다. 변경 내용을 취소하고 속성 페이지를 끝내려면 **취소** 를 클릭합니다.
  

