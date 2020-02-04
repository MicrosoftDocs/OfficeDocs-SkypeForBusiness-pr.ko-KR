---
title: Lync Server 2010용 Edge 서버 FQDN 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 외부 설정에서 속성을 정의 하려면 다음을 구성 합니다.
ms.openlocfilehash: 2936c910f2cfc1d7e9106e2dca7477f5e1d2860e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684761"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Lync Server 2010용 Edge 서버 FQDN 설정 확장기
 
**외부 설정**에서 속성을 정의 하려면 다음을 구성 합니다.
  
웹 회의 및 오디오/비디오에 대 한 고유한 풀 FQDN과 IP 주소를 정의 하려면 **웹 회의에 별도의 fqdn 및 ip 주소 사용** 확인란을 선택 합니다.
  
> [!NOTE]
> 별도의 FQDN과 IP 주소에 대 한 확인란을 선택 하지 않도록 선택 하는 경우에는 Edge 서버에서 제공 하는 세 가지 서비스 각각에 대해 별도의 포트를 제공 해야 합니다. 구성 하는 유일한 정규화 된 도메인 이름은 액세스 경계 서비스와 연결 된 FQDN입니다. 
  
A/v Edge 서비스에서 NAT (network address translation) IP 주소와 구성을 사용 하려면 **a/v edge 서비스를** 선택 합니다.
  
사용 하도록 설정한 Edge 서비스의 경우 **포트** 에 **풀 FQDN** 과 포트를 입력 합니다.
  
- 액세스에 **지 서비스** 풀 FQDN과 서비스를 고유 하 게 식별 하는 포트를 정의 합니다.
    
- **웹 회의에 지 서비스** 풀 FQDN (웹 회의에 별도의 FQDN과 IP 주소를 설정 하 고/V가 선택 되지 않음) 및 서비스를 고유 하 게 식별 하는 포트를 정의 합니다.
    
- **A/v Edge 서비스** 풀 FQDN을 정의 합니다 (웹 회의에 별도의 FQDN과 IP 주소를 설정 하 고/V를 선택 하지 않은 경우) 하 고 서비스를 고유 하 게 식별 하는 포트입니다.
    
  **확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.
  
  **취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.
  
  **도움말**: 이 도움말 화면을 표시합니다.
  

