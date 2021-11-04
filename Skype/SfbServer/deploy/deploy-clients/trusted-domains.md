---
title: Skype 방 시스템 신뢰할 수 있는 도메인
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: 이 항목을 통해 Room System 및 Skype 트러스트된 도메인을 구성하는 비즈니스용 Skype.
ms.openlocfilehash: 68449fcb0c1bf4fb608f7d1172b45776fe109958
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60738975"
---
# <a name="skype-room-system-trusted-domains"></a>Skype 방 시스템 신뢰할 수 있는 도메인
 
이 항목을 통해 Room System 및 Skype 트러스트된 도메인을 구성하는 비즈니스용 Skype.
  
## <a name="trusted-domains"></a>신뢰할 수 있는 도메인

비즈니스용 Skype 클라이언트는 로그인하는 사용자 계정의 SIP 도메인이 인증서의 주체 또는 주체 Alt 이름에 제공된 이름과 다른 경우 비즈니스용 Skype 서버 클라이언트에서 인증서를 수락할 수 있는 대화 상자를 표시합니다. 조직에서 비즈니스용 Skype 서버 구성한 인증서에 주체 또는 주체 Alt 이름에 Skype Room System 계정의 SIP 도메인 이름이 없는 경우 Skype Room System 콘솔 컴퓨터의 신뢰할 수 있는 도메인 레지스트리 키 아래에 인증서에 제시된 도메인을 구성해야 합니다. Skype 룸 시스템 제조업체가 Skype Room System 관리자 가이드에서는 클라이언트에서 신뢰할 수 있는 도메인을 추가하는 방법과 비즈니스용 Skype 설명합니다. 
  
예를 들어 인증서에 구성된 인증서에 비즈니스용 Skype 서버/주체 Alt 이름이 "CONTOSO"라고 가정합니다. LOCAL" 및 Skype Room System 로그인 주소에 대해 사용자에게 할당된 SIP 도메인 중 하나는 "confrm1@contoso.net."입니다. contoso.net 인증서가 아니기 때문에 Skype 룸 시스템 시스템에서는 "contoso.local"을 레지스트리에서 신뢰할 수 있는 도메인으로 구성해야 합니다. Skype Room System 제조업체가 제공하는 Skype Room System 관리자 가이드에 설명된 것입니다. 
  

