---
title: 인증서 요청 (반환 됨)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: 온라인 인증서 요청 상태 페이지에는 온라인 인증서 요청을 성공적으로 만들고 발급 한 결과로 발생 하는 중요 한 정보가 표시 됩니다. 이 페이지에서는 인증서를 고유 하 게 식별 하는 인증서 지문을 제공 합니다. 기본적으로이 인증서를 비즈니스용 Skype 서버 인증서 용도에 할당 확인란을 선택 합니다. 마침을 클릭 하면 인증서 요청의 생성 단계 중에 정의한 목적으로 Lync Server 2013에 인증서가 자동으로 할당 됩니다. 기본적으로 인증서가 할당 되는 용도는 다음과 같습니다.
ms.openlocfilehash: 61e6ea918fea931251470603e2db0b699234267d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197255"
---
# <a name="certificate-request-returned"></a>인증서 요청 (반환 됨)
 
온라인 인증서 **요청 상태** 페이지에는 온라인 인증서 요청을 성공적으로 만들고 발급 한 결과로 발생 하는 중요 한 정보가 표시 됩니다. 이 페이지에서는 인증서를 고유 하 게 식별 하는 인증서 지문을 제공 합니다. 기본적으로이 인증서를 비즈니스용 **Skype 서버 인증서 용도에 할당** 확인란을 선택 합니다. **마침을**클릭 하면 인증서 요청의 생성 단계 중에 정의한 목적으로 Lync Server 2013에 인증서가 자동으로 할당 됩니다. 기본적으로 인증서가 할당 되는 용도는 다음과 같습니다.
  
- MTLS (상호 전송 계층 보안)에 대 한 서버 기본값-클라이언트 및 다른 서버에 대 한 연결
    
- TLS/SSL (Secure Sockets layer) 용 내부 웹 서비스 사이트의 웹 서비스 내부 클라이언트 및 서버 연결
    
- 웹 서비스 외부-TLS/SSL 용 외부 웹 서비스 사이트의 클라이언트 및 서버 연결
    
인증서 **정보 보기** 를 클릭 하 여 인증서를 확인 하 고 인증서의 속성이 의도 한 대로 되어 있는지 확인 하 고, 인증서를 적용 하 고 서버에서 사용할 수 있도록 준비 합니다.
  
**마침을** 클릭 하 여 온라인 인증서 요청 프로세스를 완료 합니다. **이 인증서를 비즈니스용 Skype 서버 인증서 용도에 지정**확인란을 선택한 경우 인증서가 자동으로 할당 됩니다. 이 확인란을 선택 취소 하는 경우 별도의 단계로 인증서를 할당 해야 합니다. 
  
> [!IMPORTANT]
> 발급 하는 CA (인증 기관) 루트 인증서가 컴퓨터의 신뢰할 수 있는 루트 인증 기관 저장소에 없거나 중간 CA 인증서가 올바른 저장소에 없으면 다음 이미지와 같이 요약 상태가 표시 됩니다. 인증서를 할당할 수 있는 옵션이 없습니다. 인증서 할당 프로세스를 완료 하려면 발급 하는 CA 루트 인증서와 중간 CA 인증서를 가져온 다음 기본 인증서 마법사 페이지에서 **할당** 을 클릭 하 여 인증서를 할당 해야 합니다.
  

