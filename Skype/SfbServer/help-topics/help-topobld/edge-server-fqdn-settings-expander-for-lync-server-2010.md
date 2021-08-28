---
title: Lync Server 2010용 에지 서버 FQDN 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 외부 설정에서 속성을 정의하려면 다음을 구성합니다.
ms.openlocfilehash: 3aff6f1a185f7f0d4cb3a596bf8dabea0feb9f89
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628770"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Lync Server 2010용 에지 서버 FQDN 설정 확장기
 
외부 설정에서 속성을 **정의하려면** 다음을 구성합니다.
  
웹 회의 및 오디오/비디오에 대해 고유한 풀 FQDN 및 IP 주소를 정의하려면 웹 회의 및 A/V에 대해 별도의 **FQDN** 및 IP 주소 사용 확인란을 선택합니다.
  
> [!NOTE]
> 별도의 FQDN 및 IP 주소에 대한 확인란을 선택하지 않는 경우 에지 서버에서 제공하는 세 가지 서비스에 대해 각각 고유한 포트를 제공해야 합니다. 구성할 유일한 정식 도메인 이름은 액세스 에지 서비스에 연결된 FQDN입니다. 
  
A/V 에지 서비스에서 NAT(Network Address Translation) IP 주소 및 구성을 사용하도록 설정하려면 **A/V** 에지 서비스가 NAT 사용 가능 확인란을 선택합니다.
  
사용하도록 설정된 에지 서비스의 경우 포트 아래에 **풀 FQDN** 및 **포트를 입력합니다.**
  
- 액세스 **에지 서비스** 풀 FQDN 및 서비스를 고유하게 식별하는 포트를 정의합니다.
    
- 웹  회의 에지 서비스 풀 FQDN(웹 회의 및 A/V에 대해 별도의 FQDN 및 IP 주소 사용이 선택되어 있지 않은 경우) 및 서비스를 고유하게 식별하는 포트를 정의합니다.
    
- **A/V** 에지 서비스 풀 FQDN(웹 회의 및 A/V에 대해 별도의 FQDN 및 IP 주소 사용이 선택되어 있지 않은 경우) 및 서비스를 고유하게 식별하는 포트를 정의합니다.
    
  **확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.
  
  **취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.
  
  **도움말**: 이 도움말 화면을 표시합니다.
  

