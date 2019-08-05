---
title: 둘 이상의 포리스트를 포함 하도록 AAD Connect 업데이트
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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 이 부록에는 팀과 비즈니스용 Skype에 대 한 클라우드 통합의 일부로 둘 이상의 포리스트를 포함 하도록 AAD Connect를 업데이트 하는 단계에 대 한 자세한 단계가 포함 되어 있습니다.
ms.openlocfilehash: cbb4811d999601524557e7106840a66682565e5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185490"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a>둘 이상의 포리스트를 포함 하도록 AAD Connect 업데이트

Azure AD Connect는 [여러 포리스트에서 동기화를](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies)지원 합니다. 그러나 AAD에 대 한 Azure AD Connect 동기화 인스턴스만 지원 합니다. 따라서 Azure AD가 한 포리스트에 이미 설치 되어 있는 경우 추가 포리스트에서 동기화 되도록 AAD Connect의 기존 인스턴스가 업데이트 되어야 합니다.

 - 모든 id가 두 포리스트 모두에서 한 번만 표시 되는 경우 (즉, 메일 사용 가능 연락처를 만들지 않은 경우) AAD Connect 마법사를 다시 실행 하 여 "동기화 옵션 사용자 지정"을 선택한 다음 **디렉터리 연결 **페이지에서 추가 포리스트 및 자격 증명의 이름을 입력 합니다.<br><br>
 ![디렉터리 연결 페이지](../media/cloud-consolidation-connect-your-directories.png)
 - 그러나 사용자가 둘 이상의 디렉터리에 있고 데이터 (예: 다른 포리스트의 사용자에 게 해당 하는 포리스트에 있는 경우)를 병합할 수 있는 경우에는 Azure AD Connect를 제거 하 고 다시 설치 해야 합니다.  이는 포리스트 간 조인 규칙 조건은 첫 설치 중에만 구성할 수 있기 때문입니다. 다음 페이지에서이 작업을 수행 합니다.<br><br>
 ![사용자가 고유 하 게 식별 하는 페이지](../media/cloud-consolidation-uniquely-identifying-your-users.png)


## <a name="see-also"></a>참고 항목

[팀 및 비즈니스용 Skype에 대 한 클라우드 통합](cloud-consolidation.md)