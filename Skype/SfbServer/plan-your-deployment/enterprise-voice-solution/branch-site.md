---
title: 분기 사이트 SIP 트렁크 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: SIP 트렁크에 대한 자세한 내용은 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: bb8fcc1755e73bba6689f07d2f97cc01cc77549d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582602"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>분기 사이트 SIP 트렁크 비즈니스용 Skype 서버
 
SIP 트렁크에 대한 자세한 내용은 비즈니스용 Skype 서버 Enterprise Voice.
  
경우에 따라 선택한 분기 사이트에서 분산된 SIP 트렁크를 구현해야 할 수 있습니다. 분기 사이트에 SIP 트렁크가 필요한지 여부를 결정하고 분기 사이트에 SIP 트렁크를 배포하기 위한 지원되는 토폴로지 옵션에 대한 자세한 내용은 [비즈니스용 Skype 서버.](sip-trunking.md)
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>예 분기 사이트 SIP 트렁크 요구 사항 분석

분기 사이트 SIP 트렁크를 배포하기로 결정한 경우 사이트별 비용 분석을 수행해야 합니다. 예를 들어 워싱턴주 레드몬드에 중앙 사이트가 있는 기업과 뉴욕에 분기 사이트가 있는 기업은 분석을 수행하여 뉴욕 사이트에서 로컬 서비스 공급자로 SIP 트렁크를 구현할지 여부를 결정해야 합니다.
  
뉴욕에서 분산된 SIP 트렁크가 비용 효율적인지 여부를 확인하려면 SIP 트렁크가 사용되는 DID(내선 직접 호출) 번호를 식별하고 뉴욕에서 레드몬드(425)가 아닌 지역으로 전화를 건 횟수를 분석합니다. 중앙 사이트에서 분기 사이트에 대한 DID 종료를 사용할 수 있습니다. 예를 들어 Redmond 중앙 사이트는 뉴욕 분기 사이트의 DID 번호를 호스팅할 수 있습니다. 분산된 SIP 트렁크를 구현하는 데 드는 비용이 이러한 호출 비용보다 적을 경우 뉴욕 분기 사이트에서 SIP 트렁크를 구현하는 것이 좋습니다. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>기타 분기 사이트 SIP 트렁크 요구 사항

게이트웨이 대신 SIP 트렁크를 배포할 때 선택할 수 있는 옵션은 각 옵션의 PSTN(Public Switched Telephone Network) 시거리 요금 간의 차이에 따라 선택됩니다. 분기 사이트 SIP 트렁크를 배포하는 경우 탄력성 및 대역폭 요구 사항도 결정해야 합니다. 분기 사이트와 중앙 사이트 간의 링크가 탄력적으로 연결되고 대역폭이 충분하면 SIP 트렁크 또는 게이트웨이를 배포할 수 있습니다. 분기 사이트에서 Survivable Branch Appliance를 배포할 필요는 없습니다. 분기 사이트와 중앙 사이트 간의 링크가 탄력적이지 않은 경우 SIP 어플라이언스를 배포하거나 분기 사이트에 게이트웨이 또는 SIP 트렁크를 사용하여 SIP 트렁크를 사용하여 SIP 서버를 배포합니다. 
  

