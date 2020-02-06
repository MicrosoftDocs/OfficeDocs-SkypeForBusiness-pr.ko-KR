---
title: XMPP 페더레이션 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이전 버전에서는 XMPP 배포와의 페더레이션을 허용 하는 별도의 서버 역할로 배포 될 수 있는 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 게이트웨이를 제공 했습니다. XMPP 기능은 비즈니스용 Skype 서버 2019에서 더 이상 사용 되지 & 없습니다. XMPP 기능을 계속 사용 하려면 레거시 버전 (비즈니스용 Skype Server 2015/Lync Server 2013)을 사용 하 여 availed 하는 환경에서이를 확인할 수 있습니다. XMPP 기능은 레거시 Edge 서버에서 실행 되는 XMPP 프록시로, 레거시 프런트 엔드 서버에서 실행 되는 XMPP 게이트웨이 등 두 부분으로 설치 됩니다.
ms.openlocfilehash: d8640d90427d5d7ae9c19a092dc10f0d299ae2be
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813436"
---
# <a name="migrating-xmpp-federation"></a>XMPP 페더레이션 마이그레이션

이전 버전에서는 XMPP 배포와의 페더레이션을 허용 하는 별도의 서버 역할로 배포 될 수 있는 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 게이트웨이를 제공 했습니다. XMPP 기능은 더 이상 사용할 수 없으며 비즈니스용 Skype 서버 2019에서 사용 되지 않습니다. XMPP 기능을 계속 사용 하려면 레거시 버전 (비즈니스용 Skype Server 2015 또는 Lync Server 2013)을 사용 하는 공존 환경에서 수행할 수 있습니다. XMPP 기능은 레거시 Edge 서버에서 실행 되는 XMPP 프록시로, 레거시 프런트 엔드 서버에서 실행 되는 XMPP 게이트웨이 등 두 부분으로 설치 됩니다. 
  
마이그레이션 측면에서 XMPP 기능을 사용 하려는 사용자는 레거시 서버에 남아 있어야 하 고 비즈니스용 Skype Server 2019 풀로 이동할 수 없으며 레거시 XMPP 게이트웨이를 계속 사용 해야 합니다. 이는 XMPP 페더레이션 파트너가 비즈니스용 Skype 서버 2015 또는 Lync Server 2013에서 구성 된 경우에만 가능 합니다. XMPP 기능을 계속 사용 하려면 레거시 Edge 서버를 비즈니스용 Skype 서버 2019로 마이그레이션하지 않아야 합니다. 그러나 XMPP 프록시를 사용 하는 레거시 Edge 서버와 비즈니스용 Skype 2019 Edge 서버를 함께 사용할 수 있습니다.
  

    

