---
title: 인증서 요청(반환됨)
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: 온라인 인증서 요청 상태 페이지에는 온라인 인증서 요청이 성공적으로 생성 및 발급된 중요한 정보가 표시됩니다. 이 페이지에서는 인증서를 고유하게 식별하는 인증서 지문을 제공합니다. 기본적으로 인증서 사용법에 이 비즈니스용 Skype 서버 할당 확인란이 선택되어 있습니다. 마친을 클릭하면 인증서 요청 생성 단계에서 정의한 목적으로 인증서가 Lync Server 2013에 자동으로 할당됩니다. 기본적으로 인증서가 할당되는 용도는 다음과 같습니다.
ms.openlocfilehash: ec715e7270247ca35707ea89694b4970c7ece25c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764266"
---
# <a name="certificate-request-returned"></a>인증서 요청(반환됨)
 
온라인 **인증서 요청 상태 페이지에는** 온라인 인증서 요청이 성공적으로 생성 및 발급된 중요한 정보가 표시됩니다. 이 페이지에서는 인증서를 고유하게 식별하는 인증서 지문을 제공합니다. 기본적으로 인증서 사용법에 이 비즈니스용 Skype 서버 **할당 확인란이** 선택되어 있습니다. 마친을 클릭하면 인증서 요청 만들기 단계에서 정의한 목적으로 인증서가 Lync Server 2013에 자동으로 할당됩니다. 기본적으로 인증서가 할당되는 용도는 다음과 같습니다.
  
- MTLS(상호 전송 계층 보안)에 대한 서버 기본값 - 클라이언트 및 기타 서버에 대한 연결
    
- 웹 서비스 내부 - 전송 계층 보안/보안에 대한 내부 웹 서비스 사이트의 클라이언트 및 Secure Sockets Layer(TLS/SSL)
    
- 웹 서비스 외부 - TLS/SSL에 대한 외부 웹 서비스 사이트의 클라이언트 및 서버 연결
    
**인증서 세부 정보 보기** 를 클릭하여 인증서를 보면 인증서의 속성이 의도한 대로인지 확인하고 인증서가 서버에서 적용 및 사용할 수 있는 상태인지를 확인할 수 있습니다.
  
**마친을** 클릭하여 온라인 인증서 요청 프로세스를 완료합니다. 이 인증서를 인증서 비즈니스용 Skype 서버 할당 확인란을 선택한 경우 인증서가 자동으로 할당됩니다. 이 확인란을 선택 취소한 경우 별도의 단계에서 인증서를 할당해야 합니다. 
  
> [!IMPORTANT]
> 발급 CA(인증 기관) 루트 인증서가 컴퓨터의 신뢰할 수 있는 루트 인증 기관 저장소에 없는 경우 또는 중간 CA 인증서가 적절한 저장소에 없는 경우 다음 그림과 같이 요약 상태가 표시됩니다. 인증서를 할당할 수 없습니다. 인증서 할당 프로세스를 완료하려면 발급 CA 루트 인증서 및 모든 중간 CA 인증서를 가져온 다음 기본 인증서 마법사 페이지에서 **할당** 을 클릭하여 인증서를 할당해야 합니다.
  

