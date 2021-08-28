---
title: XMPP 페더레이션 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 이전 버전에서는 XMPP 배포와의 페더럴을 허용하기 위해 별도의 서버 역할로 배포할 수 있는 XMPP(Extensible Messaging and Presence Protocol) 게이트웨이를 제공했습니다. XMPP 기능은 2019년 & 더 이상 사용할 수 비즈니스용 Skype 서버 없습니다. XMPP 기능을 계속 사용하려는 경우 레거시 버전(비즈니스용 Skype 서버 2015/ Lync Server 2013)에서 사용할 수 있습니다. XMPP 기능은 레거시 에지 서버에서 실행되는 XMPP 프록시와 레거시 프런트 엔드 서버에서 실행되는 XMPP 게이트웨이의 두 부분으로 설치됩니다.
ms.openlocfilehash: a0c3eeaa6218c6e3b3726f755adcca6083a9ac3f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580132"
---
# <a name="migrating-xmpp-federation"></a>XMPP 페더레이션 마이그레이션

이전 버전에서는 XMPP 배포와의 페더럴을 허용하기 위해 별도의 서버 역할로 배포할 수 있는 XMPP(Extensible Messaging and Presence Protocol) 게이트웨이를 제공했습니다. XMPP 기능은 2019년 8월에 더 이상 사용할 수 비즈니스용 Skype 서버 않습니다. XMPP 기능을 계속 사용하려는 경우 레거시 버전(비즈니스용 Skype 서버 2015 또는 Lync Server 2013)을 함께 사용할 수 있습니다. XMPP 기능은 레거시 에지 서버에서 실행되는 XMPP 프록시와 레거시 프런트 엔드 서버에서 실행되는 XMPP 게이트웨이의 두 부분으로 설치됩니다. 
  
마이그레이션 관점에서 XMPP 기능을 사용하려는 사용자는 레거시 서버에 유지되고 비즈니스용 Skype 서버 2019 풀로 이동하지 말고 레거시 XMPP 게이트웨이를 계속 사용해야 합니다. 이 설정은 2015 또는 Lync Server 2013에서 XMPP 페더럴 파트너가 비즈니스용 Skype 서버 수 있습니다. XMPP 기능을 계속 사용하려면 레거시 에지 비즈니스용 Skype 서버 2019로 마이그레이션하면 안 됩니다. 그러나 레거시 에지 서버(XMPP 프록시와 함께)와 2019 에지 서버를 함께 사용할 수 비즈니스용 Skype 있습니다.
  

    

