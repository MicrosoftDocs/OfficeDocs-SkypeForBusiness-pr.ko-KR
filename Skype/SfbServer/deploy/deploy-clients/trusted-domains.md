---
title: Skype 룸 시스템 트러스트된 도메인
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: 이 항목을 읽고 Skype 룸 시스템 및 비즈니스용 Skype에 대해 신뢰할 수 있는 도메인을 구성하는 방법을 배워야 합니다.
ms.openlocfilehash: c7883ed0cbc2e805ee0ba3cddfb3b2cee1163c35
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834118"
---
# <a name="skype-room-system-trusted-domains"></a>Skype 룸 시스템 트러스트된 도메인
 
이 항목을 읽고 Skype 룸 시스템 및 비즈니스용 Skype에 대해 신뢰할 수 있는 도메인을 구성하는 방법을 배워야 합니다.
  
## <a name="trusted-domains"></a>신뢰할 수 있는 도메인

비즈니스용 Skype 클라이언트는 사용자 계정 로그인의 SIP 도메인이 인증서의 주체 또는 주체 Alt 이름에 제공된 이름과 다른 경우 비즈니스용 Skype 서버에서 인증서를 수락할 수 있는 대화 상자를 표시합니다. 조직에서 비즈니스용 Skype 서버에 대해 구성된 인증서에 주체 또는 주체 Alt 이름에 Skype 룸 시스템 계정의 SIP 도메인 이름이 없는 경우 Skype 룸 시스템 콘솔 컴퓨터의 신뢰할 수 있는 도메인 레지스트리 키 아래에 인증서에 제시된 도메인을 구성해야 합니다. Skype 룸 시스템 제조업체에서 제공하는 Skype 룸 시스템 관리자 가이드에서는 비즈니스용 Skype 클라이언트에서 신뢰할 수 있는 도메인을 추가하는 방법과 위치를 설명합니다. 
  
예를 들어 비즈니스용 Skype 서버에 구성된 인증서에 주체/주체 Alt 이름이 "CONTOSO"라고 가정합니다. LOCAL" 및 Skype 룸 시스템 로그인 주소에 대해 사용자에게 할당된 SIP 도메인 중 하나는 "confrm1@contoso.net."입니다. 인증서가 contoso.net 아니기 때문에 Skype 룸 시스템 시스템에서는 Skype 룸 시스템 제조업체에서 제공하는 Skype 룸 시스템 관리자 가이드에 설명된 따라 "contoso.local"을 레지스트리에서 신뢰할 수 있는 도메인으로 구성해야 합니다. 
  

