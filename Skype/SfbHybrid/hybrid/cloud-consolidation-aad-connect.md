---
title: 여러 포리스트를 포함하도록 AAD Connect를 업데이트
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
description: 이 부록에는 여러 포리스트를 클라우드 통합의 일부로 포함하기 위해 AAD 커넥트 업데이트하기 위한 자세한 단계가 Teams 비즈니스용 Skype.
ms.openlocfilehash: e803ae1e41fd0e68a56e059bbaf398ee30f807f6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625800"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>여러 포리스트를 포함하도록 AAD Connect를 업데이트

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Azure AD 커넥트 여러 [포리스트에서 동기화를 지원합니다.](/azure/active-directory/connect/active-directory-aadconnect-topologies) 그러나 AAD와 동기화하는 Azure AD 커넥트 인스턴스만 지원됩니다. 따라서 Azure AD가 이미 하나의 포리스트에 설치되어 있는 경우 추가 포리스트에서 동기화하기 위해 AAD 커넥트 인스턴스를 업데이트해야 합니다.

 - 모든 ID가 두 포리스트에서 한 번만 표시되면(즉, 메일 사용이 가능한 연락처를 지정하지 않은 경우) AAD 커넥트 마법사를 다시 실행하고 "동기화 옵션 사용자 지정"을 선택한 다음 커넥트 **Your Directories** 페이지에서 추가 포리스트 및 creds의 이름을 입력합니다.<br><br>
 ![커넥트 페이지](../media/cloud-consolidation-connect-your-directories.png)
 - 그러나 사용자가 두 개 이상의 디렉터리에 있을 수 있으며 데이터를 통합할 경우(예: 연락처 개체가 다른 포리스트의 사용자에 해당하는 포리스트에 있는 경우) Azure AD 커넥트 제거한 후 다시 설치해야 합니다.  이는 포리스트 간 조인 규칙 조건은 첫 번째 설치 중에만 구성할 수 있기 때문에입니다. 이 완료는 다음 페이지에서 수행됩니다.<br><br>
 ![사용자 고유 식별 페이지](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>참고 항목

[비즈니스 및 Teams 클라우드 비즈니스용 Skype](cloud-consolidation.md)