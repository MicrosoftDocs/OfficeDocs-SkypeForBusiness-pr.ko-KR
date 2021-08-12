---
title: 트러스트된 응용 프로그램 서버 구성
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 혼합 환경에서 신뢰할 수 있는 응용 프로그램 서버를 새로 만드는 경우 다음 홉 풀을 2019 풀로 비즈니스용 Skype 서버 합니다. 혼합 환경에서 레거시 풀과 비즈니스용 Skype 서버 2019 풀이 모두 드롭다운 목록에 표시됩니다. 레거시 풀은 선택할 수 없습니다.
ms.openlocfilehash: 6db3aaadfe028e6d1975521ecacb52ad26754b7bcf8766af345d4786bc825f31
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296095"
---
# <a name="configure-trusted-application-servers"></a>트러스트된 응용 프로그램 서버 구성

혼합 환경에서 신뢰할 수 있는 응용 프로그램 서버를 새로 만드는 경우 다음 홉 풀을 2019 풀로 비즈니스용 Skype 서버 합니다. 혼합 환경에서 레거시 풀과 비즈니스용 Skype 서버 2019 풀이 모두 드롭다운 목록에 표시됩니다. 레거시 풀은 선택할 수 없습니다.
  
> [!IMPORTANT]
> 신뢰할 수 있는 응용 프로그램 서버를 마이그레이션하는 경우 사용하는 UCMA 버전도 업데이트해야 합니다. 비즈니스용 Skype 서버 2019에 대해 신뢰할 수 있는 응용 프로그램 풀을 새로 만드는 경우 UCMA를 비즈니스용 Skype 서버 2019 또는 사용 가능한 최신 버전에 포함된 버전으로 업데이트해야 합니다. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>신뢰할 비즈니스용 Skype 서버 서버를 만들 때 다음 홉으로 2019 선택

1. 토폴로지 작성기를 엽니다.
    
2. 왼쪽 창에서 신뢰할 수 있는 응용 프로그램 서버를 마우스 오른쪽 **단추로** 클릭하고 새 신뢰할 수 있는 응용 **프로그램 풀 을 클릭합니다.**
    
3. 신뢰할 수 있는 응용 프로그램 풀의 풀 **FQDN을** 입력하고 단일 서버인지 아니면 다중 서버인지를 선택합니다. 
    
4. **다음** 을 클릭합니다.
    
5. 다음 **홉 선택 페이지의** 목록에서 2019년 비즈니스용 Skype 서버 풀을 선택합니다. 
    
6. **마침** 을 클릭합니다.
    
7. 를 선택하고 비즈니스용 Skype 서버 **메뉴에서** 게시를 **선택합니다.**
    
    신뢰할 수 **있는** 응용 프로그램 풀이 성공적으로 만들어지며 올바른 프런트 엔드 풀과 연결되어 있는지 확인합니다. 
    

