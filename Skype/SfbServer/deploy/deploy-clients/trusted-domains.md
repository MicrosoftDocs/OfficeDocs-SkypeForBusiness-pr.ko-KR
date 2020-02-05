---
title: Skype 채팅방 시스템 신뢰할 수 있는 도메인
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Skype 채팅방 시스템 및 비즈니스용 Skype에 대해 신뢰할 수 있는 도메인을 구성 하는 방법에 대해 알아보려면이 항목을 읽으십시오.
ms.openlocfilehash: 618ea5ce6cd4e12cd1e6a811a065f7a29a5c9ced
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768671"
---
# <a name="skype-room-system-trusted-domains"></a>Skype 채팅방 시스템 신뢰할 수 있는 도메인
 
Skype 채팅방 시스템 및 비즈니스용 Skype에 대해 신뢰할 수 있는 도메인을 구성 하는 방법에 대해 알아보려면이 항목을 읽으십시오.
  
## <a name="trusted-domains"></a>신뢰할 수 있는 도메인

비즈니스용 Skype 클라이언트는 로그인 하는 사용자 계정의 SIP 도메인이 인증서의 주체 또는 주체의 대체 이름에 표시 된 이름과 다른 경우 비즈니스용 Skype 서버에서 인증서를 수락할 수 있는 대화 상자를 표시 합니다. 조직의 비즈니스용 Skype 서버용으로 구성 된 인증서가 주체 또는 주체 대체 이름에 Skype 대화방 시스템 계정의 SIP 도메인 이름을 보유 하 고 있지 않은 경우, 신뢰할 수 있는 도메인 아래의 인증서에 표시 된 해당 도메인을 구성 해야 합니다. Skype 실 시스템 콘솔 컴퓨터의 레지스트리 키입니다. Skype 실 시스템 제조업체에서 제공 하는 skype 실 시스템 관리자 안내서는 비즈니스용 Skype 클라이언트에서 신뢰할 수 있는 도메인을 추가 하는 방법과 위치에 대해 설명 합니다. 
  
예를 들어 비즈니스용 Skype Server에 구성 된 인증서에 "CONTOSO"의 제목/제목 대체 이름이 있다고 가정 합니다. LOCAL "과 Skype 룸 시스템 로그인 주소에 대해 사용자에 게 지정 된 SIP 도메인 중 하나가" confrm1@contoso.net "입니다. Contoso.net이 인증서에 있지 않기 때문에 skype 채팅방 시스템의 경우, skype 룸 시스템 제조업체에서 설명 하는 대로 "contoso. local"을 레지스트리의 신뢰할 수 있는 도메인으로 구성 해야 합니다-skype 실 시스템 관리자 안내서를 제공 합니다. 
  

