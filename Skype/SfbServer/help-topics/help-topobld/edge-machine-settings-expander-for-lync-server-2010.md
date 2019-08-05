---
title: Lync Server 2010의 Edge 기계 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: Edge 서버 컴퓨터의 속성을 단일 Edge 서버 또는 Edge 풀의 구성원 컴퓨터로 편집 하려면 서버 이름 및 IP 주소 구성 설정을 구성 합니다.
ms.openlocfilehash: c9201cfde9f19391e1cee351de6d4efac00be9dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197298"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Lync Server 2010의 Edge 기계 설정 확장기
 
Edge 서버 컴퓨터의 속성을 단일 Edge 서버 또는 Edge 풀의 구성원 컴퓨터로 편집 하려면 **서버 이름 및 IP 주소 구성** 설정을 구성 합니다.
  
- **내부 이름 또는 FQDN**: DNS (domain name system)에서 참조 되는 컴퓨터의 이름을 입력 합니다. 
    
- **내부 IPv4 주소**:이 컴퓨터에 대 한 내부 NIC (네트워크 인터페이스 카드)의 IPv4 주소를 입력 합니다.
    
- 이 컴퓨터와 연결 된 **외부 IPv4 주소** 에 **대 한 액세스 경계 서비스** 를 구성 합니다.
    
    > [!IMPORTANT]
    > Edge 서버 구성에 단일 IP 주소를 사용 하도록 선택한 경우에는 액세스에 지 서비스에 대 한 외부 IPv4 주소만 편집할 수 있습니다. 다른 Edge 서비스는 액세스 경계 서비스와 동일한 IPv4 주소를 공유 합니다. 
  
- 편집할 수 있는 경우이 컴퓨터와 연결 된 **외부 IPv4 주소** 를 **웹 회의 서비스** 에서 구성 합니다.
    
- 편집할 수 있는 경우이 컴퓨터와 연결 된 **A/V 경계 서비스** **외부 IPv4 주소** 를 구성 합니다.
    
- 편집할 수 있는 경우이 컴퓨터와 연결 된 **NAT 사용 공용 IPv4 주소** 를 구성 합니다.
    
    > [!IMPORTANT]
    > Nat를 사용 하는 **공용 IPv4 주소** 에 대 한 구성 속성은 a/V Edge 서비스에 nat (network address translation)를 제공 하도록 선택한 경우에만 편집할 수 있습니다.
  
  **확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.
  
  **취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.
  
  **도움말**: 이 도움말 화면을 표시합니다.
  

